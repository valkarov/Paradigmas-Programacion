# Paradigmas-Programacion

# Proyecto Jenkins Pipeline con Groovy

Este repositorio contiene un pipeline básico de Jenkins utilizando Groovy para clonar un repositorio de GitHub, compilar un proyecto y ejecutar pruebas.

## Descripción

Este repositorio proporciona un ejemplo sencillo de un pipeline de Jenkins definido en Groovy. El pipeline realiza las siguientes acciones:
1. Clona el repositorio desde GitHub.
2. Compila el proyecto usando Maven.
3. Ejecuta las pruebas del proyecto.

### Groovy en Jenkins

Groovy es un lenguaje de programación dinámico que se utiliza para definir pipelines en Jenkins. Los scripts de pipeline escritos en Groovy permiten automatizar las tareas de construcción, prueba y despliegue de proyectos de software.

## Uso del Pipeline

Para usar este pipeline en tu instancia de Jenkins, sigue estos pasos:

1. Clona este repositorio en tu máquina local:
    ```bash
    git clone https://github.com/tu-usuario/tu-repositorio.git
    ```
2. Navega al directorio del proyecto:
    ```bash
    cd tu-repositorio
    ```
3. Configura tu pipeline en Jenkins:
    - Crea un nuevo item (job) en Jenkins y selecciona "Pipeline".
    - En la sección de configuración del Pipeline, selecciona "Pipeline script from SCM".
    - Configura tu repositorio de GitHub y asegúrate de que Jenkins use el archivo `Jenkinsfile`.

## Estructura del Proyecto

La estructura de este repositorio es la siguiente:

```plaintext
tu-repositorio/
├── Jenkinsfile         # Archivo de configuración del pipeline de Jenkins
└── README.md           # Este archivo
