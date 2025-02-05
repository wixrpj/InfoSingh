# Briefing del Proyecto: Sistema de Streaming con Plex, TrueNAS y Página Web Promocional

## 📚 Índice
- Descripción Gereral
- Objetivos del Proyecto
- Diagrama de Red
- Estructura del Proyecto
- Materiales Requeridos
- Roles del equipo
- Tegnologias Implementadas
- Especificaciones del Sistema
- Documentación y Recursos Adicionales

## 📜 Descripción General
El objetivo de este proyecto es crear un sistema de streaming multimedia eficiente y seguro, utilizando Plex en un entorno virtualizado para gestionar contenido como videos, imágenes y más. Para garantizar la seguridad y disponibilidad de los datos, se implementará un sistema de backups automatizados con TrueNAS, que realizará copias incrementales a medida que se añadan nuevos contenidos. Además, se desarrollará una **página web promocional** para destacar las características del sistema de streaming y redireccionar a los usuarios a las redes sociales del proyecto.

## 📌 Paso a Paso: Implementación del Sistema de Streaming

### 🖥️ Infraestructura del Proyecto
✅ **Máquinas Virtuales con Ubuntu Server:**
- **VM 1:** Docker con contenedores (Plex, MySQL + PHP, Web)
- **VM 2:** Pi-hole (Servidor DNS y bloqueador de publicidad)
- **VM 3:** pfSense (Firewall y servidor DHCP)

## 🚀 1. Configuración de la VM con Docker
### 1.1. Instalación de Docker y Docker Compose
- [ ] Instalar Docker en Ubuntu Server
- [ ] Instalar Docker Compose
- [ ] Crear una red de Docker para comunicación entre los contenedores

### 1.2. Implementación de Contenedores
#### 🟠 **Contenedor 1: Plex (Servidor de Streaming)**
- [ ] Descargar la imagen oficial de Plex
- [ ] Configurar volúmenes para almacenamiento de medios
- [ ] Asignar puertos para acceso web y streaming
- [ ] Probar la reproducción de contenido en la red local

#### 🟡 **Contenedor 2: MySQL + PHP (Base de Datos y Backend)**
- [ ] Descargar la imagen de MySQL
- [ ] Configurar usuarios y permisos en la base de datos
- [ ] Descargar la imagen de PHP y phpMyAdmin
- [ ] Configurar conexión entre PHP y MySQL
- [ ] Verificar acceso a la base de datos desde otros contenedores

#### 🔵 **Contenedor 3: Página Web Promocional (HTML, CSS, JavaScript)**
- [ ] Elegir y configurar el servidor web (Nginx o Apache)
- [ ] Crear y desplegar la página web con HTML, CSS y JavaScript
- [ ] Configurar el acceso desde la red local
- [ ] Implementar medidas básicas de seguridad (HTTPS, firewall, etc.)

---

## 🌐 2. Configuración de Infraestructura Adicional
### 2.1. **VM con Pi-hole (Servidor DNS y Bloqueador de Publicidad)**
- [ ] Instalar Pi-hole en Ubuntu Server
- [ ] Configurar como servidor DNS de la red
- [ ] Establecer reglas de bloqueo de anuncios
- [ ] Verificar que los dispositivos de la red usan Pi-hole

### 2.2. **VM con pfSense (Firewall y Servidor DHCP)**
- [ ] Instalar pfSense en Ubuntu Server
- [ ] Configurar interfaces de red
- [ ] Activar y configurar el servidor DHCP
- [ ] Definir reglas de firewall para permitir tráfico a los servicios necesarios
- [ ] Habilitar NAT si es necesario

---

## ✅ 3. Pruebas y Ajustes Finales
✅ **Verificar que cada servicio funciona correctamente:**
- [ ] Probar la reproducción de medios en Plex
- [ ] Acceder a la base de datos desde la web
- [ ] Asegurar que la web promocional carga sin problemas
- [ ] Comprobar que Pi-hole bloquea anuncios y funciona como DNS
- [ ] Probar conectividad a internet y filtrado de tráfico con pfSense

---

## 🔥 4. Opcional (Mejoras y Optimización)
- [ ] Configurar backups automáticos en TrueNAS
- [ ] Implementar HTTPS con Let's Encrypt en la web
- [ ] Crear reglas avanzadas en pfSense para mayor seguridad
- [ ] Optimizar rendimiento de Docker con ajuste de recursos



:computer: Estructura del Proyecto:

Maquinas Virtuales:
- **Máquina Virtual 1 (Linux + Docker):** Alojamiento del servidor de streaming con Plex, configurado dentro de un contenedor Docker.
- **Máquina Virtual 2 (TrueNAS):** Almacenamiento seguro de los datos con backups automáticos e incrementales.
- **Máquina Virtual 3 (Servidor Web):**
  

## :dart: Objetivos del Proyecto

### :one: Objetivos Principales

1. **Implementar un servidor de streaming:** Configurar Plex dentro de un contenedor Docker para ofrecer un sistema eficiente y accesible de transmisión de contenidos multimedia.
2. **Seguridad y Backup:** Utilizar TrueNAS para realizar backups incrementales del contenido del servidor Plex, asegurando la integridad y disponibilidad de los datos.
3. **Desarrollar una página web promocional:** Crear un sitio web para promocionar el contenedor de streaming y redirigir a las redes sociales del proyecto.

### :two: Objetivos Secundarios

- Optimizar el rendimiento del servidor Plex dentro de Docker para garantizar una experiencia fluida de streaming.
- Configurar alertas en TrueNAS para notificar posibles problemas en los backups.
- Proveer un diseño atractivo y responsive en la página web para mejorar la experiencia de usuario.
  
## 🛜 Diagrama de Red
![](https://github.com/wixrpj/InfoSingh/blob/main/Diagrama%20de%20seguridad%20de%20red.png)
## 🏗️ Estructura del Proyecto

### 🐋 Máquina Virtual 1: Sistema Operativo Linux + Docker

- **Sistema Operativo:** Distribución de Linux ligera (por ejemplo, Ubuntu Server o Debian).
- **Docker:** Configuración de un contenedor que ejecute Plex para la transmisión de contenido multimedia.
- **Almacenamiento:** Montaje de volúmenes en Docker para gestionar la carga y organización de los contenidos (videos, imágenes, etc.).

### ☁️ Máquina Virtual 2: TrueNAS

- **TrueNAS:** Configuración como servidor NAS para almacenar backups del sistema Plex.
- **Backups Incrementales:** Implementación de un sistema automatizado para realizar copias de seguridad solo de los archivos modificados o añadidos recientemente.
- **Cifrado:** Protección de los datos respaldados para garantizar su seguridad.

### 🌐 Página Web Promocional

⚙️ **Funcionalidades:**
  - Información del servidor de streaming (ventajas, características, tecnología utilizada).
  - Promoción de los contenidos disponibles y ventajas de usar Plex.
  - Redirección a redes sociales del proyecto.
🖌️ **Diseño:** Responsive y enfocado en la usabilidad.

🖥️ **Tecnologías:**
  - **Frontend:** HTML, CSS, JavaScript (opcionalmente usar frameworks como Bootstrap).
  - **Hosting:** Uso de servicios gratuitos como GitHub Pages o servidores propios.

## 🧱 Materiales Requeridos

### 💪 Físicos

- **Servidor o Hardware para Máquinas Virtuales:** Equipo capaz de ejecutar dos máquinas virtuales con los recursos necesarios.
- **Conexión a Internet:** Para garantizar un acceso fluido al servidor Plex y sincronización de backups con TrueNAS.

### 🧠 Lógicos
- **Linux (Distribución Ligera):** Base para la Máquina Virtual 1.
- **Docker:** Para contenerizar Plex y facilitar su implementación.
- **Plex Media Server:** Herramienta principal de transmisión de contenido.
- **TrueNAS:** Sistema operativo para gestionar los backups en la Máquina Virtual 2.
- **HTML, CSS, JavaScript:** Para desarrollar la página web promocional.
## 🪪 Roles del equipo
| Nombre del miembro |       Roles de equipo       |     Trabajo de cada miembro   |
|:-------------------|:----------------------------|:------------------------------|
|Raul                |Administrador de sistemas    | Experimentar con las maquinas e instalar maquinas nuevas y diseñar la página.  |
|Parwinder           |Diseñador web y diagramas    | Diseñar el diagrama del proyecto y llevar al dia el trello y diseñar la página.|


## 💼 Documentación y Recursos Adicionales

- **Plex Media Server:** [Guía oficial](https://www.plex.tv/)
- **Docker:** [Documentación oficial](https://docs.docker.com/)
- **TrueNAS:** [Manual oficial](https://www.truenas.com/docs/)

## 🧑🏽‍💻 Tegnologias Implementadas
El sistema **SPT** se basa en una variedad de tecnologías modernas para garantizar un rendimiento óptimo y una gestión eficiente de incidencias. A continuación se detallan las principales tecnologías utilizadas:

| Categoría        | Tecnología  | Descripción                                                                                       | Icono                                                                                   |
|------------------|-------------|---------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------|
| Infraestructura | Proxmox    | Plataforma de virtualización que permite gestionar máquinas virtuales y contenedores.            | <img src="https://img.icons8.com/color/48/000000/proxmox.png" width="50" height="50" alt="Proxmox">                       |
|                  ||            ||
|                  ||            ||
| Desarrollo     | HTML       | Estructura básica de las páginas web.                                                            | <img src="https://img.icons8.com/color/48/000000/html-5.png" width="50" height="50" alt="HTML">                           |
|                | CSS        | Estilos y diseño visual para una experiencia de usuario atractiva.                               | <img src="https://img.icons8.com/color/48/000000/css3.png" width="50" height="50" alt="CSS">                             |
|                  | JavaScript | Interactividad y dinamismo en la interfaz del usuario.                                          | <img src="https://img.icons8.com/color/48/000000/javascript.png" width="50" height="50" alt="JavaScript">                 |
|                  ||            ||
| Base de Datos   | MySQL      | Sistema de gestión de bases de datos relacional utilizado para almacenar datos.                   | <img src="https://img.icons8.com/color/48/000000/mysql-logo.png" width="50" height="50" alt="MySQL">                      |
|                  ||            ||
| Redes         | DHCP       | Protocolo utilizado para asignar dinámicamente direcciones IP a dispositivos en la red.          |<img src= "https://github.com/wixrpj/InfoSingh/blob/main/dhcp.png" width="50" height="50" alt="DHCP">|
|                  | DNS        | Sistema de nombres de dominio que traduce nombres legibles por humanos a direcciones IP.        |<img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRf3nc9CLvb2mKqLziw76kewntr4O8SYG5sR-UVJGLSqteRdSh1oGO76paD9Z5UWrWMBEQ&usqp=CAU" width="50" height="50" alt="DNS">|
| Control de Versiones  | GitHub     | Plataforma para alojar repositorios Git y colaborar en proyectos.                                | <img src="https://github.githubassets.com/images/modules/logos_page/GitHub-Mark.png" width="50" height="50" alt="GitHub">|


## 👨🏽‍💻 Especificaciones del Sistema
A continuación, se detallan las especificaciones de los componentes del sistema:
Máquina Host: Es el equipo principal que tiene un Sistema Operativo Windows 11 y tiene una configuración de red DHCP con la IP 100.77.20.65.
DNS (Pi-Hole): Es un servidor DNS que utiliza Ubuntu Server 22.04.01 y está configurado con la IP 10.1.2.10 y un gateway 10.1.2.1. Hemos elegido porque Pi-Hole es comúnmente utilizado para bloquear anuncios y rastreos a nivel de red.
| COMPONENTE    | SO                  | ALMACENAMIENTO | CPU          | RAM  | IP                | GATEWAY      |
|---------------|---------------------|----------------|--------------|------|-------------------|--------------|
| MAQUINA HOST  | Windows 11          | 465 GB         | 4 Cores      | 8 GB | 100.77.20.65      | 100.77.20.1  |
| DNS(Pi-Hole)  | Ubuntu SV 22.04.01  | 25 GB          | 2            | 2 GB | 10.1.2.10         | 10.1.2.1     |

## 📅 Diagrama de GANT
Este es nuestro diagrama de Gantt, un cronograma del proyecto. En él se detallan las tareas y su duración. Cada barra horizontal representa una actividad, y su longitud indica el tiempo estimado para su ejecución. Dentro de cada rango he especificado el rango de fecha en el que se va a trabajar aproximadamente.
![](https://github.com/wixrpj/InfoSingh/blob/main/Captura%20de%20pantalla%202025-02-05%20125028.png)

