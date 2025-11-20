# Proyecto-Final-Analisis-del-Comportamiento-de-Aplicaciones-bajo-Diferentes-Escenarios-de-Despliegue

## 1. Descripción General del Proyecto
Este proyecto analiza el rendimiento y comportamiento de una aplicación web compuesta por un backend en Django REST Framework, un frontend desarrollado en React y una base de datos MySQL. El objetivo principal es estudiar cómo varían métricas como el tiempo medio de respuesta y el throughput cuando la aplicación se despliega en diferentes escenarios de infraestructura:

- Docker Compose (1 nodo)
- Kubernetes con 1 nodo
- Kubernetes con múltiples nodos
- Variación del número de réplicas del backend (1, 2 y 3)

Para generar carga se utilizó Apache JMeter, y para el análisis de resultados se empleó Python mediante un Notebook de Jupyter.

## 2. Objetivos del Proyecto
- Evaluar el comportamiento de la aplicación en distintos entornos de despliegue.

- Comparar el rendimiento bajo Docker Compose, Kubernetes mononodo y Kubernetes multinodo.

- Analizar el impacto del escalamiento horizontal del backend al aumentar el número de réplicas.

- Medir tiempos de respuesta, throughput y estabilidad bajo carga.

- Visualizar y explicar los resultados mediante herramientas de análisis de datos.

## 3. Arquitectura de la Aplicación

La aplicación está compuesta por tres servicios principales:

- Backend: Django REST Framework expuesto mediante API REST.
- Frontend: React + Vite empaquetado y servido mediante Nginx.
- Base de Datos: MySQL con almacenamiento persistente.

Esta arquitectura se evaluó en los siguientes escenarios:

### 3.1 Docker Compose
Entorno monolítico donde todos los servicios se ejecutan en un mismo nodo.

### 3.2 Kubernetes en un nodo
Los servicios se despliegan como Deployments y Services, pero en un único nodo del clúster.

### 3.3 Kubernetes multinodo
El clúster MicroK8s se encuentra conformado por los nodos gp7, gp25 y gp16. En este escenario se evaluó la distribución de pods, el balanceo de carga y la influencia de múltiples réplicas bajo mayor concurrencia.

## 4. Pruebas de Rendimiento con JMeter

Se realizaron pruebas de carga para tres niveles de usuarios simultáneos: 100 usuarios, 300 usuarios y 500 usuarios.

Se ejecutaron bajo diferentes cantidades de réplicas del backend: 1 réplica, 2 réplicas y 3 réplicas.

Las métricas analizadas fueron:
- Tiempo medio de respuesta
- Throughput
- Desviación estándar
- Porcentaje de errores
- Estabilidad bajo carga

Los resultados fueron exportados y analizados en un Notebook de Jupyter usando Pandas y Matplotlib.