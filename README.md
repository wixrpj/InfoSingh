# Briefing del Proyecto: Servidor de Backups Automatizados con Docker, TrueNAS y Duplicity

## Descripción General

El proyecto tiene como objetivo implementar un sistema de backups automatizados utilizando **TrueNAS** como servidor de almacenamiento local, **Docker** para facilitar la implementación y automatización, y **Duplicity** como herramienta de backups. Esta combinación ofrece una solución robusta y segura para respaldar grandes volúmenes de datos de manera eficiente.

**TrueNAS** es un sistema operativo de código abierto basado en FreeBSD que permite configurar servidores de almacenamiento de alto rendimiento, ideal para gestionar grandes volúmenes de datos de manera segura y confiable. **Docker** se emplea para contenerizar las aplicaciones, lo que facilita su implementación, escalabilidad y mantenimiento, además de asegurar que el entorno de ejecución sea consistente y portátil. Por último, **Duplicity** es una herramienta de backup que soporta la creación de copias de seguridad cifradas y comprimidas, permitiendo realizar respaldos incrementales de manera eficiente, lo que optimiza el uso del espacio de almacenamiento y reduce el tiempo de ejecución de los backups. Esta combinación de tecnologías proporciona una solución robusta, escalable y segura para respaldar grandes volúmenes de datos de forma eficiente y automatizada

## Objetivos del Proyecto

### Objetivos Principales

1. **Automatización de Backups:** Configurar un sistema que ejecute copias de seguridad de manera autónoma y programada, sincronizando los datos de TrueNAS con un servicio en la nube.
2. **Seguridad de Datos:** Implementar cifrado de datos con Duplicity para garantizar su protección durante el almacenamiento y la transferencia.
3. **Optimización de Recursos:** Reducir el uso de ancho de banda y espacio en la nube mediante backups incrementales.
4. **Recuperación de Datos:** Establecer un proceso sencillo y eficiente para restaurar los datos en caso de pérdida.

### Objetivos Secundarios

- Monitorear los backups y configurar alertas en caso de fallos.
- Simplificar el proceso de restauración utilizando las capacidades de Duplicity.

## Audiencia Objetivo

Este proyecto está diseñado para:

- **Usuarios domésticos o pequeñas empresas:** Que buscan una solución de backups confiable, sencilla y segura.
- **Administradores de sistemas:** Que necesitan integrar soluciones escalables con herramientas como Docker.
- **Profesionales de IT:** Que desean aprender a combinar tecnologías como TrueNAS, Docker y Duplicity para protección de datos en la nube.

## Competencias Involucradas

1. **Administración de sistemas y redes:** Configuración de TrueNAS, gestión de redes y automatización de tareas con Docker y cron jobs.
2. **Seguridad informática:** Cifrado de datos sensibles con Duplicity, siguiendo prácticas de protección en tránsito y reposo.
3. **Automatización y scripting:** Uso de Docker para contenedores, creación de scripts y cron jobs para procesos recurrentes.

## Materiales Requeridos

### Físicos

- **Servidor o NAS (TrueNAS):** Para el almacenamiento de datos.
- **Conexión a Internet:** Para sincronizar datos con servicios en la nube (Google Drive, AWS S3, Backblaze B2, etc.).
- **Dispositivos de almacenamiento adicionales** (opcional): Para copias locales de seguridad.

### Lógicos

- **TrueNAS:** Sistema operativo de almacenamiento.
- **Docker:** Plataforma para contenedores y automatización.
- **Duplicity:** Herramienta para backups cifrados e incrementales.
- **Cron jobs:** Para automatizar la ejecución periódica de los backups.
- **Servicio en la nube:** Almacenamiento remoto seguro.

## Documentación y Recursos Adicionales

- **TrueNAS:** [Guía oficial](https://www.truenas.com/docs/)
- **Docker:** [Documentación oficial](https://docs.docker.com/)
- **Duplicity:** [Manual oficial](https://duplicity.nongnu.org/)
- **Configuración de Duplicity en la nube:** [Guía](https://www.microlinux.fr/blog/duplicity-backup-en-ligne-avec-cryptage/)
- **Curso de Docker en Udemy:** [Enlace al curso](https://www.udemy.com/course/docker-masters/)
- **Automatización con Duplicity:** [Tutoriales en YouTube](https://www.youtube.com/results?search_query=duplicity+backup+docker)
- **Cron jobs en Linux:** [Guía práctica](https://www.digitalocean.com/community/tutorials/understanding-cron-jobs-on-ubuntu-20-04)





# Briefing del Proyecto: Sistema de Streaming con Plex, TrueNAS y Página Web Promocional

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

## Documentación y Recursos Adicionales

- **Plex Media Server:** [Guía oficial](https://www.plex.tv/)
- **Docker:** [Documentación oficial](https://docs.docker.com/)
- **TrueNAS:** [Manual oficial](https://www.truenas.com/docs/)
