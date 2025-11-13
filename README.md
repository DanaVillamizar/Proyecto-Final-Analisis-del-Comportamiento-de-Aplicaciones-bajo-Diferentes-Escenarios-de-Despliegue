# Proyecto-Final-An-lisis-del-Comportamiento-de-Aplicaciones-bajo-Diferentes-Escenarios-de-Despliegue

## 1. Descripción General del Proyecto
Este proyecto analiza el comportamiento de una aplicación backend con API REST y base de datos persistente, desplegada en distintos entornos:

- Docker Compose (1 nodo)
- Kubernetes con 1 nodo
- Kubernetes con 2 nodos
- Variación del número de réplicas: 1, 2 y 3

El objetivo es medir el rendimiento de la aplicación (tiempo medio de respuesta y throughput) bajo diferentes configuraciones, usando **JMeter** para generar carga.  
El análisis final se presenta en un **Notebook de Jupyter**.
