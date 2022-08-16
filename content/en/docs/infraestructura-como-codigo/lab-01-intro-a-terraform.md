---
title : "Lab 7.1: Introducción a Terraform"
description: ""
lead: ""
date: 2022-08-14T08:48:45+00:00
lastmod: 2022-08-14T08:48:45+00:00
draft: false
images: []
menu:
  docs:
    parent: "infraestructura-como-codigo"
weight: 807
toc: true
---

## Instalar Terraform

Para instalar Terraform, solo basta con seguir las instrucciones de la página oficial en: [Install Terraform]. Cuando haya terminado, debería poder ejecutar el comando terraform:

```shell
$ terraform version
Terraform v1.2.5
```

En este laboratio, utulizaremos Terraform para desplegar recursos en [AWS]; puede usar la misma cuenta de AWS que creó en el laboratorio [Lab 2.1](../../02-computacion-en-la-nube/lab-01-crear-vm-en-aws). Para que Terraform pueda realizar cambios en su cuenta de AWS, deberá autenticarse en AWS en la línea de comandos. Una de las formas más sencillas de hacerlo es configurar esas credenciales mediante las variables de entorno `AWS_ACCESS_KEY_ID` y `AWS_SECRET_ACCESS_KEY`. Por ejemplo:

```shell
export AWS_ACCESS_KEY_ID=<>
export AWS_SECRET_ACCESS_KEY=<>

# Reemplaza 'export' por 'set' si estás en Windows.
```

## Desplegando un servidor simple

El código de Terraform está escrito en un lenguaje llamado `HCL` en archivos con la extensión `.tf`. Es un lenguaje declarativo, por lo que su objetivo es describir la infraestructura que desea y Terraform descubrirá cómo crearla.

El primer paso para usar Terraform suele ser configurar los proveedores que desea usar. Cree una carpeta llamada `server` y cree un archivo en ella llamado `main.tf` con el siguiente código:

```terraform
provider "aws" {
  region = "us-east-1"
}
```

Esto le dice a Terraform que va a utilizar el proveedor de AWS y que desea implementar su infraestructura en la región `us-east-1`.

Para cada proveedor, hay muchos tipos diferentes de *recursos* que puede crear, como `servidores`, `bases de datos` y `balanceadores de carga`. Agregue el siguiente código a `main.tf`, que utiliza el recurso `aws_instance` para implementar un servidor virtual (instancia EC2):

```terraform
resource "aws_instance" "example" {
  ami           = "ami-02f3416038bdb17fb"
  instance_type = "t2.micro"
  key_name      = "<YOUR KEY PAIR NAME>"

  tags = {
    Name = "terraform-example"
  }
}
```

La sintaxis general para un recurso de Terraform es:

```text
resource "<PROVIDER>_<TYPE>" "<NAME>" {
  [CONFIG …]
}
```

Donde:

- `PRIVDER` es el nombre de un proveedor (p. ej., `aws`),
- `TYPE` es el tipo de recursos que se crearán en ese proveedor (p. ej., `instance`),
- `NAME` es un identificador que puede usar en todo el código de Terraform para hacer referencia a este recurso (p. ej., `example`),
- `CONFIG` consta de uno o más argumentos que son específicos de ese recurso (por ejemplo, `ami = "ami-0c55b159cbfafe1f0"`). Para el recurso `aws_instance`, hay muchos argumentos diferentes, pero por ahora, solo necesita configurar los siguientes:
  - `ami`: la imagen de máquina de Amazon (AMI) que se ejecutará en la instancia EC2. El código anterior establece el parámetro `ami` en el ID de la misma AMI de Ubuntu gratuita que usó en el **Lab 2.1**.
  - `instance_type`: el tipo de instancia EC2 que se ejecutará. Cada tipo de instancia EC2 proporciona una cantidad diferente de CPU, memoria, espacio en disco y capacidad de trabajo en red. El ejemplo anterior utiliza `t2.micro`, que tiene una CPU virtual, 1 GB de memoria y forma parte de la capa gratuita de AWS.
  - `key_name`: el par de claves para asociar con la instancia. Podrá usar este par de claves para SSH a la instancia.
  - `tags`: etiquetas para aplicar a la instancia. El código anterior establece una etiqueta de `Name` para facilitar la identificación de la instancia.

### Comando `terraform init`

En una terminal, vaya a la carpeta donde creó `main.tf` y ejecute el comando `terraform init`:

```shell
$ terraform initInitializing the backend...

Initializing provider plugins...
- Finding latest version of hashicorp/aws...
- Installing hashicorp/aws v4.23.0...
- Installed hashicorp/aws v4.23.0 (signed by HashiCorp)

[...]

Terraform has been successfully initialized!
```

El binario de `terraform` contiene la funcionalidad básica de Terraform, pero no viene con el código de ninguno de los proveedores (por ejemplo, el proveedor de AWS, el proveedor de Azure, el proveedor de GCP, etc.), por lo que cuando comience a usar Terraform por primera vez, debe ejecutar `terraform init` para indicarle a Terraform que escanee el código, averigüe qué proveedores está utilizando y descargue el código para ellos.

### Comando `terraform plan`

Ahora que ha descargado el código del proveedor, ejecute el comando `terraform plan`:

```shell
$ terraform planTerraform will perform the following actions:

  # aws_instance.example will be created
  + resource "aws_instance" "example" {
    + ami              = "ami-<id>"
    + id               = (known after apply)
    + instance_state   = (known after apply)
    + instance_type    = "t2.micro"
    + tags             = {
        + "Name" = "terraform-example"
    }

    [...]
  }

Plan: 1 to add, 0 to change, 0 to destroy.
```

El comando `plan` permite ver lo que hará Terraform antes de hacerlo. Esta es una excelente manera de verificar la cordura de sus cambios antes de liberarlos en el mundo. La salida del comando plan es un poco como la salida del comando `diff`: los recursos con un signo más (`+`) se crearán, los recursos con un signo menos (`-`) se eliminarán y los recursos con una tilde signo (`~`) se modificarán o actualizarán. En el resultado anterior, puede ver que Terraform planea crear una única instancia EC2 y nada más, que es exactamente lo que queremos.

### Comando `terraform apply`

Para crear realmente la instancia, ejecute el comando `terraform apply`:

```shell
$ terraform apply

Terraform will perform the following actions:

  # aws_instance.example will be created
  + resource "aws_instance" "example" {
    + ami              = "ami-<id>"
    + id               = (known after apply)
    + instance_state   = (known after apply)
    + instance_type    = "t2.micro"
    + tags             = {
        + "Name" = "terraform-example"
    }

    [...]
  }

Plan: 1 to add, 0 to change, 0 to destroy.

Do you want to perform these actions?
  Terraform will perform the actions described above.
  Only 'yes' will be accepted to approve.

  Enter a value: [user input]
```

El comando `apply` muestra el mismo resultado del plan y pide que confirmemos si realmente desea continuar con este plan. Entonces, si bien el plan está disponible como un comando separado, es principalmente útil para verificaciones rápidas de cordura y durante las revisiones de código, y la mayoría de las veces ejecutará `apply` directamente y revisará el resultado del plan que le muestra.

Escriba "**yes**" y presione **ENTER** para DESPLEGAR la instancia EC2:

```shell
Do you want to perform these actions?
  Terraform will perform the actions described above.
  Only 'yes' will be accepted to approve.

  Enter a value: yes

aws_instance.example: Creating…
aws_instance.example: Still creating… [10s elapsed]
aws_instance.example: Creation complete after 18s

Apply complete! Resources: 1 added, 0 changed, 0 destroyed.
```

---

¡Felicitaciones, acaba de desplegar un servidor con Terraform! :partying_face:

Para verificar, puede iniciar sesión en la consola de EC2 y ver su instancia.

<!-- Referencias -->
[Install Terraform]: ../../referencias/enlaces#terraform-install
[AWS]: ../../referencias/enlaces#aws
[HCL]: ../../referencias/enlaces#hcl
