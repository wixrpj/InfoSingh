# Briefing del Proyecto: Sistema de Streaming con Plex, TrueNAS y Página Web Promocional

## 📚 Índice
- Descripcion Gereral
- Objetivos del Proyecto
- Estructura del Proyecto

## Descripción General
1. Este proyecto tiene como objetivo principal la implementación de un sistema de streaming para contenido multimedia (videos, imágenes, etc.) utilizando **Plex** en un entorno virtualizado, acompañado de una estrategia de backup con **TrueNAS** para garantizar la seguridad y disponibilidad de los datos. Además, se desarrollará una **página web promocional** para destacar las características del sistema de streaming y redireccionar a los usuarios a las redes sociales del proyecto.

2. El objetivo de este proyecto es crear un sistema de streaming multimedia eficiente y seguro, utilizando Plex en un entorno virtualizado para gestionar contenido como videos, imágenes y más. Para garantizar la seguridad y disponibilidad de los datos, se implementará un sistema de backups automatizados con TrueNAS, que realizará copias incrementales a medida que se añadan nuevos contenidos. Además, se desarrollará una **página web promocional** para destacar las características del sistema de streaming y redireccionar a los usuarios a las redes sociales del proyecto.

El sistema se estructura en dos máquinas virtuales y una página web:

- **Máquina Virtual 1 (Linux + Docker):** Alojamiento del servidor de streaming con Plex, configurado dentro de un contenedor Docker.
- **Máquina Virtual 2 (TrueNAS):** Almacenamiento seguro de los datos con backups automáticos e incrementales.
- **Página Web Promocional:** Información del proyecto, características de Plex y enlaces a redes sociales.

## Objetivos del Proyecto

### Objetivos Principales

1. **Implementar un servidor de streaming:** Configurar Plex dentro de un contenedor Docker para ofrecer un sistema eficiente y accesible de transmisión de contenidos multimedia.
2. **Seguridad y Backup:** Utilizar TrueNAS para realizar backups incrementales del contenido del servidor Plex, asegurando la integridad y disponibilidad de los datos.
3. **Desarrollar una página web promocional:** Crear un sitio web para promocionar el contenedor de streaming y redirigir a las redes sociales del proyecto.

### Objetivos Secundarios

- Optimizar el rendimiento del servidor Plex dentro de Docker para garantizar una experiencia fluida de streaming.
- Configurar alertas en TrueNAS para notificar posibles problemas en los backups.
- Proveer un diseño atractivo y responsive en la página web para mejorar la experiencia de usuario.

## Estructura del Proyecto

### Máquina Virtual 1: Sistema Operativo Linux + Docker

- **Sistema Operativo:** Distribución de Linux ligera (por ejemplo, Ubuntu Server o Debian).
- **Docker:** Configuración de un contenedor que ejecute Plex para la transmisión de contenido multimedia.
- **Almacenamiento:** Montaje de volúmenes en Docker para gestionar la carga y organización de los contenidos (videos, imágenes, etc.).

### Máquina Virtual 2: TrueNAS

- **TrueNAS:** Configuración como servidor NAS para almacenar backups del sistema Plex.
- **Backups Incrementales:** Implementación de un sistema automatizado para realizar copias de seguridad solo de los archivos modificados o añadidos recientemente.
- **Cifrado:** Protección de los datos respaldados para garantizar su seguridad.

### Página Web Promocional

- **Funcionalidades:**
  - Información del servidor de streaming (ventajas, características, tecnología utilizada).
  - Promoción de los contenidos disponibles y ventajas de usar Plex.
  - Redirección a redes sociales del proyecto.
- **Diseño:** Responsive y enfocado en la usabilidad.
- **Tecnologías:**
  - **Frontend:** HTML, CSS, JavaScript (opcionalmente usar frameworks como Bootstrap).
  - **Hosting:** Uso de servicios gratuitos como GitHub Pages o servidores propios.

## Materiales Requeridos

### Físicos

- **Servidor o Hardware para Máquinas Virtuales:** Equipo capaz de ejecutar dos máquinas virtuales con los recursos necesarios.
- **Conexión a Internet:** Para garantizar un acceso fluido al servidor Plex y sincronización de backups con TrueNAS.

### Lógicos
- **Linux (Distribución Ligera):** Base para la Máquina Virtual 1.
- **Docker:** Para contenerizar Plex y facilitar su implementación.
- **Plex Media Server:** Herramienta principal de transmisión de contenido.
- **TrueNAS:** Sistema operativo para gestionar los backups en la Máquina Virtual 2.
- **HTML, CSS, JavaScript:** Para desarrollar la página web promocional.
## Roles del equipo
| Nombre del miembro |       Roles de equipo       |     Trabajo de cada miembro   |
|:-------------------|:----------------------------|:------------------------------|
|Raul                |Administrador de sistemas    | Experimentar con las maquinas e instalar maquinas nuevas y diseñar la pagina.  |
|Parwinder           |Diseñador web y diagramas    | Diseñar el diagrama del proyecto y llevar al dia el trello y diseñar la pagina.|



## Maquinas Virtuales
|    Iso     | Almacenamiento |   CPU    |  RAM  | 
|------------|----------------|----------|-------|
|Ubuntu Sever|     20gb       |  1 cores |  3gb  |
|Ubuntu Sever|     20gb       |  1 cores |  3gb  |

## Documentación y Recursos Adicionales

- **Plex Media Server:** [Guía oficial](https://www.plex.tv/)
- **Docker:** [Documentación oficial](https://docs.docker.com/)
- **TrueNAS:** [Manual oficial](https://www.truenas.com/docs/)
