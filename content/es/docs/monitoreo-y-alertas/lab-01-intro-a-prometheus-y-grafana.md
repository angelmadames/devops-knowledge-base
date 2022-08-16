---
title : "Lab 8.1: Configurando Prometheus y Grafana"
description: ""
lead: ""
date: 2022-08-14T08:48:45+00:00
lastmod: 2022-08-14T08:48:45+00:00
draft: false
images: []
menu:
  docs:
    parent: "monitore-y-alertas"
weight: 905
toc: true
---

El archivo `docker-compose.yml` define dos servicios: **prometheus** y **grafana**. Al desplegar los servicios, docker compose mapea los puertos predeterminados de cada servicio a los puertos equivalentes en el host para inspeccionar más fácilmente la interfaz web de cada servicio. Asegúrese de que los puertos `9090` y `3000` del host no estén en uso.

## Despliegue con `docker-compose`

Para desplegar los servicios, solo basta con ejecutar:

```shell
$ docker-compose up -d
❯ dc up -d
[...]
  ⠿ prometheus Pulled
  ⠿ grafana Pulled
[+] Running 3/3
  ⠿ Network monitoreo-yalertas       Created      0.0s
  ⠿ Container grafana                Started      0.4s
  ⠿ Container prometheus             Started      0.4s
```

Si todo sale bien, podemos ejecutar el comando `docker-compose ps` para ver el status de nuestros servicios:

```shell
$ docker-compose ps
NAME                COMMAND                  SERVICE             STATUS              PORTS
grafana             "/run.sh"                grafana             running             0.0.0.0:3000->3000/tcp
prometheus          "/bin/prometheus --c…"   prometheus          running             0.0.0.0:9090->9090/tcp
```

## Accediendo a Prometheus

Al acceder a la URL [localhost:9090](http://localhost:9090) podemos visualizar el UI de Prometheus con el cual podemos interactuar y obtener data sobre las métricas recolectadas y sus gráficos asociados:

![C1-M08-L801-001](images/C1-M08-L801-001.png)

Por ejemplo, el gráfico de la métrica de `process_cpu_seconds_total` se vería similar a esto:

![C1-M08-L801-002](images/C1-M08-L801-002.png)

## Visualizando métricas con Grafana

Al acceder a la URL [localhost:3000](https://localhost:3000) podemos visualizar el UI de Grafana con el cual podemos tener una visualización más amplias de métricas por defecto exportadas por Prometheus.

![C1-M08-L801-003](images/C1-M08-L801-003.png)

Similar al gráfico que vimos con Prometheus, desde Grafana podemos ver algo bastante similar aunque con más opciones de filtrado y visualizuación:

![C1-M08-L801-004](images/C1-M08-L801-004.png)

---

Aunque estos son ejemplos bastantes simples, ya tienes una idea de cómo podemos empezar a monitorear de una manera robusta.
