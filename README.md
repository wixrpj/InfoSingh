# Briefing del Proyecto: Sistema de Streaming con Plex, TrueNAS y Página Web Promocional

## 📚 Índice
- Descripción General
- Paso a Paso: Implementación del Sistema de Streaming
  - Infraestructura del Proyecto
- Configuración de la VM con Docker
- Objetivos del Proyecto
  - Objetivos Principales
  - Objetivos Secundarios
- Diagrama de Red
- Estructura del Proyecto
- Materiales Requeridos
- Roles del Equipo
- Tecnologías Implementadas
- Especificaciones del Sistema
- Diagrama de GANT
- Guías de uso
  - DNS
  - DHCP
  - APACHE
  - PFSENCE
- Diagrama de Red
- Documentación y Recursos Adicionales

## 📜 Descripción General
El objetivo de este proyecto es crear un sistema de streaming multimedia eficiente y seguro, utilizando Plex en un entorno virtualizado para gestionar contenido como videos, imágenes y más. Para garantizar la seguridad y disponibilidad de los datos, se implementará un sistema de backups automatizados con TrueNAS, que realizará copias incrementales a medida que se añadan nuevos contenidos. Además, se desarrollará una **página web promocional** para destacar las características del sistema de streaming y redireccionar a los usuarios a las redes sociales del proyecto.

## 📌 Paso a Paso: Implementación del Sistema de Streaming

### 🖥️ Infraestructura del Proyecto
✅ **Máquinas Virtuales con Ubuntu Server:**
- **VM 1:** Docker con contenedores (Plex, MySQL + PHP, Web)
  - Hostea aplicaciones en contenedores Docker, incluyendo Plex para streaming multimedia y un servidor web para aplicaciones.
- **VM 2:** Pi-hole (Servidor DNS y bloqueador de publicidad)
  - Funciona como servidor DNS y bloquea anuncios no deseados en toda la red, mejorando la seguridad y el rendimiento.
- **VM 3:** pfSense (Firewall y servidor DHCP)
  - Aloja aplicaciones web con Apache, PHP para el backend y MySQL para la gestión de bases de datos.



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
- **Apache:** Para hostear la página web del proyecto, con dominio personalizado.
## 🪪 Roles del equipo
| Nombre del miembro |       Roles de equipo       |     Trabajo de cada miembro   |
|:-------------------|:----------------------------|:------------------------------|
|Raul                |Administrador de sistemas    | Experimentar con las maquinas e instalar maquinas nuevas y diseñar la página.  |
|Parwinder           |Diseñador web y diagramas    | Diseñar el diagrama del proyecto y llevar al dia el trello y diseñar la página.|


## 🧑🏽‍💻 Tecnologías Implementadas
El sistema **SPT** se basa en una variedad de tecnologías modernas para garantizar un rendimiento óptimo y una gestión eficiente de incidencias. A continuación se detallan las principales tecnologías utilizadas:

| Categoría        | Tecnología  | Descripción                                                                                       | Icono                                                                                   |
|------------------|-------------|---------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------|
| Infraestructura | Proxmox    | Plataforma de virtualización que permite gestionar máquinas virtuales y contenedores.               | <img src="https://img.icons8.com/color/48/000000/proxmox.png" width="50" height="50" alt="Proxmox">|
|                  ||            ||
| Desarrollo      | HTML       | Estructura básica de las páginas web.                                                               | <img src="https://img.icons8.com/color/48/000000/html-5.png" width="50" height="50" alt="HTML">|
|                 | CSS        | Estilos y diseño visual para una experiencia de usuario atractiva.                                  | <img src="https://img.icons8.com/color/48/000000/css3.png" width="50" height="50" alt="CSS">|
|                 | JavaScript | Interactividad y dinamismo en la interfaz del usuario.                                              | <img src="https://img.icons8.com/color/48/000000/javascript.png" width="50" height="50" alt="JavaScript">|
|                  ||            ||
| Base de Datos   | MySQL      | Sistema de gestión de bases de datos relacional utilizado para almacenar datos.                     | <img src="https://img.icons8.com/color/48/000000/mysql-logo.png" width="50" height="50" alt="MySQL">|
|                  ||            ||
| Redes           | DHCP       | Protocolo utilizado para asignar dinámicamente direcciones IP a dispositivos en la red.             | <img src= "https://github.com/wixrpj/InfoSingh/blob/main/dhcp.png" width="50" height="50" alt="DHCP">|
|                 | DNS        | Sistema de nombres de dominio que traduce nombres legibles por humanos a direcciones IP.            | <img src= "https://libros.catedu.es/uploads/images/gallery/2023-02/pihole-logo.png" width="50" height="75" alt="DNS">|
| Control de Versiones  | GitHub     | Plataforma para alojar repositorios Git y colaborar en proyectos.                             | <img src="https://github.githubassets.com/images/modules/logos_page/GitHub-Mark.png" width="50" height="50" alt="GitHub">|


## 👨🏽‍💻 Especificaciones del Sistema
A continuación, se detallan las especificaciones de los componentes del sistema:
Máquina Host: Es el equipo principal que tiene un Sistema Operativo Windows 11 y tiene una configuración de red DHCP con la IP 100.77.20.65.
DNS (Pi-Hole): Es un servidor DNS que utiliza Ubuntu Server 22.04.01 y está configurado con la IP 10.1.2.10 y un gateway 10.1.2.1. Lo hemos elegido porque Pi-Hole es comúnmente utilizado para bloquear anuncios y rastreos a nivel de red.
| COMPONENTE    | SO                  | ALMACENAMIENTO | CPU          | RAM  | IP                | GATEWAY      |
|---------------|---------------------|----------------|--------------|------|-------------------|--------------|
| MAQUINA HOST  | Windows 11          | 465 GB         | 4            | 8 GB | 100.77.20.65      | 100.77.20.1  |
| DNS(Pi-Hole)  | Ubuntu SV 22.04.01  | 25 GB          | 2            | 2 GB | 10.20.30.101      | 10.20.30.100 |
| PFSENSE       | FREEBSD 64bit       | 16 GB          | 1            | 1 GB | 10.20.30.100      | 10.20.30.100 |
| Apache        | Ubuntu SV 22.04.01  | 25 GB          | 2            | 3 GB | 10.20.30.105      | 10.20.30.100 |
| Docker SV     | Ubuntu SV 22.04.01  | 25 GB          | 2            | 2 GB | 10.20.30.110      | 10.20.30.100 |

## 📅 Diagrama de GANT
Este es nuestro diagrama de Gantt, un cronograma del proyecto. En él se detallan las tareas y su duración. Cada barra horizontal representa una actividad, y su longitud indica el tiempo estimado para su ejecución. Dentro de cada rango he especificado el rango de fecha en el que se va a trabajar aproximadamente.
![](https://github.com/wixrpj/InfoSingh/blob/main/Captura%20de%20pantalla%202025-02-05%20125028.png)

# 📚Guías de uso
## 🛜DNS 
#### 🤔¿Qué es DNS?
El **Sistema de Nombres de Dominio (DNS, Domain Name System)** es un sistema que traduce los nombres de dominio de Internet (como www.google.com) en direcciones IP (como 192.168.1.2). Esto permite que los usuarios accedan a sitios web y otros servicios sin necesidad de recordar direcciones IP numéricas. Además, el DNS permite mejorar la privacidad y seguridad de tu red al bloquear solicitudes de dominios maliciosos o no deseados. Pi-hole actúa como un agujero negro para anuncios y rastreadores, filtrando las solicitudes DNS antes de que lleguen a servidores externos.

#### 👨‍🔧¿Por qué es necesario DNS en este proyecto?
- Permite que los usuarios accedan al servidor **Plex** y a la **página web promocional** mediante nombres de dominio personalizados en lugar de direcciones IP.
- Facilita la integración de **Pi-hole** como bloqueador de publicidad y filtrado DNS, mejorando la experiencia de navegación en la red.
- Optimiza la administración de servicios internos, asegurando que cada componente (Plex, base de datos, web) sea accesible fácilmente sin necesidad de configurar direcciones IP estáticas manualmente.

### Instalacion DNS
La instalacion de DNS ha sido a base de comandos en ubuntu server, y a partir de ahi se ha configurado todo con interfaz grafica poniendo la ip del ordenador anfitrion y configurar un renvio de puertos para poder entrar a la interfaz grafica con la red nat.

Para configurar DNS en Pi-hole, lo primero que hice fue acceder a la interfaz web de administración de Pi-hole. Una vez dentro, navegué hasta la sección "Settings" (Configuración) y seleccioné la pestaña "DNS". En esta sección, elegí los servidores DNS que mejor se adaptaban a mis necesidades, como Google DNS, Cloudflare u OpenDNS. También activé la opción de DNS sobre HTTPS (DoH) para cifrar las consultas DNS y mejorar la privacidad de la red.

Después de seleccionar los servidores DNS, guardé los cambios y reinicié el servicio de Pi-hole para aplicar la configuración. Para asegurarme de que todo funcionaba correctamente, realicé algunas consultas DNS desde dispositivos conectados a la red. Una vez confirmado que los DNS estaban operativos, Pi-hole comenzó a filtrar las solicitudes DNS según las listas de bloqueo que había definido. Estas listas las personalicé para adaptar el filtrado a mis necesidades específicas. La combinación de Pi-hole con servidores DNS confiables no solo mejoró la seguridad de la red, sino que también optimizó la navegación al reducir el tiempo de resolución de dominios.

### Pasos a seguir
Primero, me informé a través de la guía oficial de Pi-hole. Luego, descargué e instalé una **OVA** de Ubuntu Server. Siguiendo las instrucciones de la guía, fui ejecutando los comandos necesarios hasta completar la instalación. Una vez finalizada, pude acceder al menú gráfico, desde donde es posible conectarse a la interfaz gráfica para configurar tanto el DNS como el DHCP.

### Incidencias
Tuvimos una incidencia en la que perdimos la contraseña de acceso a la interfaz gráfica de Pi-hole. Afortunadamente, consultando la guía oficial de Pi-hole, encontré comandos útiles para resolver el problema. En particular, el comando sudo pihole -a -p me permitió restablecer la contraseña y continuar trabajando sin interrupciones en la máquina virtual.

#### Manual [Guía oficial](https://discourse.pi-hole.net/t/how-do-i-configure-my-devices-to-use-pi-hole-as-their-dns-server/245)
---
## DHCP
### ¿Qué es DHCP?
El **Protocolo de Configuración Dinámica de Host (DHCP, Dynamic Host Configuration Protocol)** es un protocolo que asigna automáticamente direcciones IP y otros parámetros de configuración de red (como la máscara de subred y la puerta de enlace) a los dispositivos en una red.

#### ¿Por qué es necesario DHCP?
- Asigna automáticamente direcciones IP a las máquinas virtuales y contenedores en la red, evitando conflictos y asegurando conectividad eficiente.
- Permite que **pfSense** administre la distribución de IPs en la red, organizando el tráfico entre los dispositivos y aplicando reglas de firewall según sea necesario.
- Ayuda a la integración de **Pi-hole**, asegurando que todos los dispositivos usen el servidor DNS correcto para el filtrado de publicidad y seguridad.
- Garantiza una gestión dinámica y escalable de la red sin necesidad de configuración manual de IPs en cada dispositivo.

### Instalacion DHCP
La instalación del DHCP ha sido muy sencilla, ya que venía preinstalado junto con **Pi-hole**. Lo único que he tenido que hacer fue configurar un rango de IPs compatibles.

### Incidencias
Las incidencias que hemos experimentado han sido mínimas y se han debido principalmente a una falta de atención. El problema surgió porque, aunque configuramos el rango de IPs, al conectar el dominio se asignó un rango distinto. Esto ocurrió porque no activamos correctamente el rango de IP previamente configurado

#### Manual [Guía oficial](https://discourse.pi-hole.net/t/how-do-i-use-pi-holes-built-in-dhcp-server-and-why-would-i-want-to/3026)
---
## Apache
#### ¿Qué es Apache?
Apache es un servidor web de código abierto que se usa para alojar sitios y aplicaciones en Internet. Básicamente, es el software que se encarga de recibir las peticiones de los usuarios (cuando alguien entra a un sitio web) y responder enviando la información correspondiente (como páginas HTML, imágenes o archivos). Es uno de los servidores web más utilizados en el mundo por su flexibilidad, seguridad y estabilidad.  

#### ¿Por qué es necesario?
Apache es necesario en mi proyecto porque es el servidor web que se encargará de entregar el contenido multimedia, como películas y series, a los usuarios registrados. Sin un servidor como Apache, no tendría una forma eficiente de servir los archivos y páginas web que componen mi plataforma. Además, Apache es compatible con múltiples tecnologías y lenguajes, lo que me permitirá integrar funcionalidades dinámicas, como la autenticación de usuarios, la gestión de perfiles y la reproducción de contenido. Su flexibilidad y capacidad de configuración lo hacen ideal para adaptarse a las necesidades específicas de mi proyecto.

### ¿Qué es UFW y por qué no lo estamos utilizando?
UFW (Uncomplicated Firewall) es una herramienta de cortafuegos diseñada para simplificar la gestión de iptables en sistemas basados en Linux, como Ubuntu. Su objetivo es proporcionar una interfaz fácil de usar para configurar reglas de firewall y proteger el sistema controlando el tráfico de red entrante y saliente.

**Razones por las que no estamos utilizando UFW por el momento:**
- Facilitar la instalación y configuración de otros servicios:
  - En esta fase inicial del proyecto, priorizamos la instalación y puesta en marcha de servicios críticos como Apache, MySQL, Docker, Pi-hole y pfSense. Evitar UFW en esta etapa nos permite agilizar el proceso y evitar complicaciones innecesarias.
- Conflictos de puertos:
  - UFW podría bloquear puertos esenciales utilizados por servicios como Apache, MySQL, Docker o Pi-hole, lo que generaría problemas de conectividad y accesibilidad en la red.
- Complejidad en la gestión de reglas:
  - Al tener múltiples servicios (Plex, Apache, MySQL, Pi-hole, pfSense, etc.), la configuración de reglas en UFW se volvería compleja y propensa a errores, especialmente si no se recuerda qué reglas se han implementado.


**Plan a futuro:**
Aunque por el momento no estamos utilizando UFW para dar mayor facilidad a la instalación y configuración de los servicios, planeamos implementarlo en una fase posterior del proyecto. Una vez que todos los servicios estén funcionando de manera estable, UFW se añadirá como una capa adicional de seguridad para proteger cada máquina virtual individualmente. Esto nos permitirá gestionar el tráfico de red con mayor precisión, optimizando y fortaleciendo la seguridad del sistema en su conjunto.

## Pasos de instalación
### Paso 1: Actualizar los paquetes del sistema
Antes de instalar Apache, es recomendable actualizar el sistema:

```bash
sudo apt update
```

---
### Paso 2: Instalar Apache2
Ejecuta el siguiente comando para instalar Apache:

```bash
sudo apt install apache2 -y
```

---
### Paso 3: Verificar el estado de Apache
Para verificar si Apache está corriendo:

```bash
sudo systemctl status apache2
```

---
### Paso 4: Abrir el puerto en el firewall (opcional)
Si **UFW (Uncomplicated Firewall)** está activado, permite tráfico HTTP y HTTPS:

```bash
sudo ufw allow 'Apache Full'
```

Verifica las reglas del firewall:

```bash
sudo ufw status
```

---
### Paso 5: Probar Apache en el navegador
Abre un navegador y accede a la dirección IP del servidor o al localhost:

```
http://IP_DEL_SERVIDOR
```

Si Apache está funcionando, verás la página de bienvenida "It works!".

---
## Paso 6: Administrar Apache2

### Reiniciar Apache
```bash
sudo systemctl restart apache2
```

### Recargar configuración sin interrumpir el servicio
```bash
sudo systemctl reload apache2
```
#### Manual [Guía oficial](https://www.php.net/manual/es/book.apache.php)

---
## PFSense
#### ¿Qué es pfSense?
pfSense es una distribución personalizada de FreeBSD adaptado para su uso como firewall y enrutador. Aparte es un programa de código abierto que funciona como un firewall de alto nivel, diseñado para proteger redes y dispositivos de amenazas externas. Se puede instalar en una máquina virtual, descargándolo directamente desde su página oficial, o adquirir como un dispositivo físico (appliance) que ya viene con el sistema preconfigurado y listo para usar. Su principal función es actuar como un cortafuegos, ubicándose entre internet y nuestros dispositivos para detectar y bloquear actividades sospechosas. Esto lo convierte en una herramienta esencial para mantener la seguridad, ya sea en entornos empresariales o incluso para uso personal.

#### ¿Por qué es necesario pfSense?
pfSense es una herramienta muy util para la seguridad y gestión de redes, especialmente en entornos donde proteger datos y optimizar el tráfico son prioritarios. Con un firewall robusto, protege contra intrusiones, malware y otras amenazas cibernéticas, además de permitir la creación de redes privadas virtuales (VPN) para conectar oficinas remotas o usuarios móviles de forma segura. También optimiza el rendimiento de la red con funciones como balanceo de carga y gestión de ancho de banda, útiles en entornos con muchos usuarios o servicios en línea. Su facilidad de uso y capacidad para simplificar la administración de redes lo convierten en una solución eficiente, aunque su interfaz grafica deja mucho que desear.

### ¿En qué sistema se basa?
pfSense se basa en el sistema operativo FreeBSD, un sistema de alto rendimiento en entornos de red. FreeBSD proporciona la base sobre la cual pfSense construye sus funciones avanzadas de firewall, enrutamiento, VPN y gestión de tráfico, lo que lo convierte en una solución confiable y eficiente para la seguridad y administración de redes.

### ¿Cuáles son las principales características de pfSense?
- **Firewall avanzado:** Protege la red bloqueando intrusiones, malware y otras amenazas externas.
- **Enrutamiento:** Permite gestionar el tráfico entre diferentes redes de manera eficiente.
- **VPN (Red Privada Virtual):** Facilita conexiones seguras para usuarios remotos o entre oficinas.
- **Balanceo de carga:** Distribuye el tráfico entre múltiples conexiones para optimizar el rendimiento.
- **Gestión de ancho de banda:** Controla y prioriza el uso de la red para evitar congestiones.
- **Filtrado de contenido:** Bloquea acceso a sitios web o servicios no deseados.
- **Detección de intrusiones:** Monitorea la red en busca de actividades sospechosas.
- **Interfaz web intuitiva:** Facilita la configuración y el monitoreo sin necesidad de conocimientos técnicos avanzados.
- **Personalización:** Admite la instalación de paquetes adicionales para añadir funcionalidades específicas.

### ¿Es pfSense una opción viable para empresas y redes domésticas?
pfSense es una excelente opción tanto para empresas como para redes domésticas por su versatilidad y relación calidad-precio. Para las empresas, ofrece funciones avanzadas como un firewall robusto, VPN para conexiones seguras, balanceo de carga para optimizar el tráfico y gestión del ancho de banda. Además, es personalizable, permitiendo añadir funciones específicas como filtrado de contenido, lo que lo hace ideal para adaptarse a las necesidades de cada organización.

En el ámbito doméstico, pfSense también es muy útil, especialmente si hay varios dispositivos conectados o quieres mejorar la seguridad de tu red. Aunque puede parecer un poco complicado al principio, su interfaz web es intuitiva y fácil de manejar una vez que te familiarizas con ella. Y al ser de código abierto, no requiere licencias costosas, lo que lo convierte en una opción accesible para usuarios particulares.

En definitiva, pfSense es una solución completa que funciona bien tanto en entornos empresariales como en redes caseras, ofreciendo seguridad, rendimiento y flexibilidad sin necesidad de invertir grandes cantidades de dinero.

## Descarga e instalacion PfSense:
La descarga y uso de pfSense CE es completamente gratuita, basta con entrar en la web oficial (https://www.pfsense.org/) e irnos directamente a la pestaña de «Download».
```
https://www.pfsense.org/download/
```
![](https://github.com/wixrpj/InfoSingh/blob/main/Captura%20de%20pantalla%202025-03-05%20121359.png)

----

También tenemos que seleccionar el tipo de imagen, si queremos una imagen ISO para copiar en un DVD o pendrive, o directamente una imagen USB, nosotros hemos seleccionado la imagen ISO DVD. A continuación, deberemos elegir el servidor desde donde realizar la descarga, es recomendable que siempre sea el más cercano físicamente de tu ubicación actual.

Una vez que hayamos descargado la imagen, deberemos descomprimirla ya que viene en formato iso.gz, y deberemos extraer la imagen ISO directamente.

![](https://github.com/wixrpj/InfoSingh/blob/main/Captura%20de%20pantalla%202025-03-05%20121757.png)

----

Una vez que lo hayamos descargado, podremos guardarlo en un disco duro o en una carpeta segura para que no lo eliminen. Vamos a instalar pfSense en una máquina virtual con Oracle VM VirtualBox. La máquina server tiene que crear dos tarjetas de red, REVISAR!!!!!! una en modo bridge y otra en modo host-only para poder acceder vía web desde nuestro ordenador, sin depender de la red local.

Configuración de la máquina virtual:
![](https://github.com/wixrpj/InfoSingh/blob/main/Captura%20de%20pantalla%202025-03-05%20123034.png)

----

Instalación de pfSense en VM
Cuando arrancamos la máquina virtual, podremos ver un menú con varias opciones de arranque, no debemos tocar nada y esperar a que pasen los segundos. Posteriormente cargará, y ya podremos ver las diferentes opciones que nos brinda la imagen ISO para la instalación de pfSense.

![](https://github.com/wixrpj/InfoSingh/blob/main/Captura%20de%20pantalla%202025-03-05%20121834.png)

----

Una vez que arranque la instalación de este sistema operativo, que aceptar el copyright que nos muestra. En el siguiente menú podremos instalar, recuperar el sistema operativo en caso de fallo catastrófico, y también recuperar el archivo de configuración config.xml de una instalación anterior. Nosotros pincharemos en «Install» para instalar el sistema operativo desde cero. En el siguiente menú tendremos que configurar el teclado, eligiendo nuestro idioma y distribución de teclado.
Después nos preguntará cómo queremos instalar el sistema operativo, si con UFS para BIOS o UEFI, de forma manual para expertos, abrir la consola para hacer todo manualmente, o utilizar ZFS como sistema de archivos. En nuestro caso, hemos elegido la primera de todas, Auto (UFS) BIOS y procedemos con la instalación. La instalación tardará un minuto aproximadamente, aunque dependerá del hardware que tengas, cuando finalice nos preguntará si queremos lanzar una consola para hacer configuraciones específicas, pinchamos en «No» y posteriormente nos preguntará si queremos reiniciar el sistema operativo, y aceptamos.
Si después de reiniciar te pide que vuelvas a instalar la iso lo que hacemos es apagar la máquina y quitar la iso para que se solucione el error y volvemos a arrancar-la.

![](https://github.com/wixrpj/InfoSingh/blob/main/Captura%20de%20pantalla%202025-03-05%20121847.png)

----

En cuanto se inicie nuevamente pfSense, podemos ver que se le ha asignado correctamente una IP a la WAN de Internet y otra a la LAN.

![](https://github.com/wixrpj/InfoSingh/blob/main/Captura%20de%20pantalla%202025-03-05%20121900.png)

En el menú de administración por consola podremos realizar las siguientes acciones:
- Cerrar sesión a SSH
- Asignar interfaces físicas a la WAN o LAN, permite configurar también VLANs para la conexión a Internet e incluso de cara a la LAN.
- Configurar la dirección IP de las diferentes interfaces configuradas anteriormente.
- Resetear la contraseña de administrador para entrar vía web.
- Restaurar pfSense a valores de fábrica.
- Reiniciar el sistema operativo.
- Apagar el sistema operativo.
- Hacer ping a un host.
- Lanzar una consola para tareas de administración avanzadas por comandos.
- Lanzar pfTop para ver todas las conexiones actuales.
- Ver los logs del sistema operativo de filtrado.
- Reiniciar el servidor web.
- Lanzar consola con utilidades pfSense para configuraciones rápidas.
- Actualizar desde consola.
- Habilitar SSH en el sistema operativo.
- Restaurar una configuración reciente.
- Reiniciar PHP-FPM por si tenemos problemas de acceso vía web al sistema operativo.

----

Por supuesto, debemos realizar la configuración desde cero, asignando la interfaz correspondiente a la WAN y a la LAN:

![](https://github.com/wixrpj/InfoSingh/blob/main/Captura%20de%20pantalla%202025-03-05%20121916.png)

----
Despues de haber seguido los pasos de instalacon con una maquina cliente accedemos a la interfaz grafica de PfSense para empezar a configurarlo
```
http://IP.DE.TU.SERVER (10.20.30.1)
```
## Port forward
#### ¿Qué es el port forward?
El port forwarding (o reenvío de puertos) es una técnica que permite redirigir el tráfico de internet que llega a un puerto específico de un router o firewall hacia un dispositivo o servicio dentro de una red local. Esto es útil cuando necesitas que un servicio, como un servidor web, un juego en línea o una cámara IP, sea accesible desde fuera de tu red.

Por ejemplo, si tienes un servidor web en tu casa y quieres que alguien pueda acceder a él desde internet, configuras el port forwarding para que el tráfico que llega al puerto 80 (el puerto usado para HTTP) de tu router se redirija hacia la dirección IP local de tu servidor. Sin esta configuración, el router no sabría a qué dispositivo enviar el tráfico, y el servicio no sería accesible desde fuera.

## Objetivos del Port Forward
El objetivo principal del port forwarding es permitir el acceso remoto a servicios alojados dentro de una red local desde cualquier ubicación externa. Esta técnica facilita la publicación de páginas web, la conexión remota por SSH para la administración de servidores y el acceso a otros servicios internos sin comprometer la seguridad general de la red.

En el caso de SSH, el port forwarding se utiliza para establecer túneles seguros que permiten evadir bloqueos de puertos o restricciones de firewall. Gracias a este mecanismo, es posible garantizar la confidencialidad e integridad de los datos transmitidos, ofreciendo una solución eficiente para la administración remota y la comunicación segura entre redes diferentes.

### Pasos a seguir para el Port Forward

- **Acceder a la configuración de pfSense:** Ingresar a la interfaz web de administración de pfSense a través de su dirección IP (en mi caso es el 10.20.30.1).
   
- **Identificar la sección de Port Forwarding:** Navegar a Firewall > NAT y seleccionar la pestaña Port Forward.
   
- **Comprobar la existencia de las reglas de salida:** Asegurarse de que las reglas de salida permitan la conexión desde la red interna hacia el exterior, revisando en Firewall > Rules > LAN que existan reglas que permitan el tráfico saliente.
   
- **Crear las reglas de entrada - Puerto 80:** Ir a Firewall > NAT > Port Forward, hacer clic en Add y configurar la regla con los siguientes parámetros:
   - **Interface:** WAN
   - **Protocol:** TCP
   - **Destination Port Range:** 80 (HTTP)
   - **Redirect Target IP:** 10.20.30.100
   - **Redirect Target Port:** 80
   - **Description:** Mi regla NAT en WAN - acceso por HTTP
     
- **Guardar la configuración:** Aplicar los cambios y asegurarse de que la regla aparezca en la lista.
   
- **Crear la regla de firewall:** Automáticamente, pfSense ofrece la opción de crear la regla de firewall asociada. Seleccioné esta opción para permitir el tráfico entrante.

- **Probar la conexión:** Verificar desde el exterior si el servicio es accesible a través de la dirección IP pública de pfSense y el puerto configurado.
  
Crear las reglas de entrada - Puerto 80, consiste en crear una regla de entrada a traves de la interfaz de la red WAN en el firewall que permita redirigir el trafico web por el puerto 80 hacia el servidor apache que contiene la Web en la Lan
![](https://github.com/wixrpj/InfoSingh/blob/main/Captura%20de%20pantalla%202025-03-06%20115239.png)

En esos instantes, ya podremos acceder vía web a la configuración del pfSense, a través de https://10.20.30.1 con nombre de usuario «admin» y contraseña «pfsense».

---

### Reglas Wan recomendables
| Opcion        | Descripcion         |
|---------------|---------------------|
| Action        |Pass                 |
| Interface     | WAN                 |
| Protocol      | UDP                 |
| Source        | Any                 |
| Destination   | Any                 |
| Destination port range|5194         |
| Logs          | Seleccionamos la opción de guardar|
| Description   | OPENVPN:RULE        |

### Reglas Port Forward recomendables
| Opcion        | Descripcion         |
|---------------|---------------------|
| Interfaz      | WAN                 |
| Address family| IPv4                |
| Protocol      | TCP                 |
| Destination   | WAN address         |
| Destination port|SSH (puerto 22 por defecto) |
| Redirect target port|SSH (puerto 22 por defecto)|
| Description   | regla NAT en WAN para SSH        |

### Reglas Adicionales PfSense
En este apartado voy a ofreceros 2 reglas adcionales para que podais mejorar vuestro server PfSense

#### Puerto HTTP
| Opcion        | Descripcion         |
|---------------|---------------------|
| Interfaz      | WAN                 |
| Address family| IPv4                |
| Protocol      | TCP/UDP             |
| Destination   | WAN address         |
| Destination port|HTTP (puerto 80 por defecto) |
| Redirect target ip|Address or Alias (Ip de la maquina que quieras añadir esta opcion)|
| Description   |Mi Regla NAT - acceso HTTP|


#### Puerto SSH
Esta regla SSH te permite conectarte desde tu maquina host a tu maquina virtual para que te sea mas accesible la transmision de textos y las configuraciones.
| Opcion        | Descripcion         |
|---------------|---------------------|
| Interfaz      | WAN                 |
| Address family| IPv4                |
| Protocol      | TCP                 |
| Destination   | WAN address         |
| Destination port|SSH (puerto 22 por defecto)|
| Redirect target port|Address or Alias (Ip de la maquina que quieras añadir esta opcion)|
| Description   |Mi Regla NAT - acceso SSH|

## Diagrama de Red
Aqui se ve puede apreciar mas visualmente la infrastructura de red que se ha contruido con esta instalacion de firewall.
![](https://github.com/wixrpj/InfoSingh/blob/main/Captura%20de%20pantalla%202025-03-06%20122451.png)

## Incidencias Comunes
- Si no consigues conectarte a la interfaz gráfica de pfSense, asegúrate de estar en la misma red y que puedes interactuar con el comando ping con la máquina servidor.
- A la hora de instalar pfSense vía VirtualBox/Máquina virtual, asegúrate de poner en el sistema "FREEBSD 64", ya que con otra versión podrías tener muchas limitaciones o fallos.
- En el direccionamiento de IP cuando estás configurando la WAN puede hacerse complicado, pero intenta leer todas las explicaciones que te da la máquina y si no conoces alguna función, búscala para no cometer fallos en el servidor.
- Muy importante: quita el adaptador puente en la máquina cliente; solo tiene que tener un adaptador y es el de la "RED interna".
- Hay que instalar el "openssh.server" en la máquina cliente para que pueda funcionar el "SSH" correctamente.

---

## TrueNAS
#### ¿Qué es TrueNAS?
TrueNAS es un sistema operativo especializado en proporcionar servicios de almacenamiento en red (NAS) de manera segura y escalable. Originalmente conocido como FreeNAS, está diseñado para convertir hardware estándar en servidores de almacenamiento profesionales con funciones avanzadas.

Es una plataforma de código abierto basada en FreeBSD que permite crear servidores NAS para almacenamiento masivo, backups automatizados y acceso remoto a archivos. Su versión gratuita (TrueNAS CORE) ofrece herramientas empresariales como cifrado nativo, replicación de datos y soporte para protocolos múltiples.

#### ¿Por qué es necesario?
- **Centralización de datos**: Permite almacenar y acceder a información desde cualquier dispositivo conectado a la red (PCs, móviles, tablets).
- **Seguridad reforzada**: Usa el sistema de archivos ZFS con protección contra corrupción de datos y opciones de cifrado AES-XTS.
- **Reducción de costos**: Elimina la necesidad de software pago para gestión NAS y aprovecha hardware existente.
- **Escalabilidad**: Admite desde configuraciones domésticas hasta empresariales con RAID-Z (hasta triple paridad) y expansión mediante discos adicionales.

#### Base del sistema
TrueNAS CORE se fundamenta en:
- **FreeBSD**: Sistema operativo base que garantiza estabilidad y compatibilidad con hardware x64.
- **OpenZFS**: Sistema de archivos que ofrece integridad de datos mediante checksums, snapshots y reparación automática de errores.

#### Principales características
**Almacenamiento y seguridad:**
- Configuración de pools híbridos (HDD + SSD) para optimizar velocidad y costo.
- Cifrado nativo a nivel de dataset con contraseñas o claves.
- RAID-X  con tolerancia a fallos de hasta 3 discos.

**Conectividad y servicios:**
- Protocolos multi-plataforma: SMB (Windows), AFP (macOS), NFS (Unix), FTP, Rsync.
- Servicios integrados: OpenVPN (cliente/servidor), DNS dinámico, LDAP, Active Directory.
- Soporte para máquinas virtuales y contenedores via bhyve.

**Automatización y gestión:**
- Copias de seguridad programables con replicación local/remota.
- Monitoreo SMART de discos y alertas por email.
- Interfaz web con actualizaciones en un clic y plugins preconfigurados (Ej: Transmission para Torrents).

**Adaptabilidad empresarial:**
- Claves API para integración con herramientas de monitorización como TrueCommand.
- Compatibilidad con estándares empresariales: Kerberos, SNMP, iSCSI.
  
### Instalacion Truenas


---

## PHP Y MYSQL

#### ¿Qué és?

**PHP**
PHP (Hypertext Preprocessor) es un lenguaje de programación del lado del servidor ampliamente utilizado en el desarrollo web. Se ejecuta en el servidor y genera HTML dinámico que se envía al navegador del usuario. Es ideal para crear aplicaciones web interactivas, manejar formularios, gestionar sesiones y conectarse a bases de datos.

**MySQL**
MySQL es un sistema de gestión de bases de datos relacionales (RDBMS) de código abierto. Utiliza el lenguaje SQL (Structured Query Language) para almacenar, organizar y recuperar datos de manera eficiente. Es una de las bases de datos más populares en aplicaciones web.

**PHP y MySQL juntos**
La combinación de PHP y MySQL es una de las más comunes en el desarrollo web. PHP se encarga de la lógica del servidor y la interacción con el usuario, mientras que MySQL gestiona el almacenamiento y la recuperación de datos. Juntos, permiten crear aplicaciones web dinámicas y escalables, como sistemas de gestión de contenido (CMS), tiendas en línea, y plataformas de autenticación.


#### ¿Por qué es necesario?
En mi proyecto de creación de una página web, PHP y MySQL son esenciales porque me permiten construir una plataforma dinámica y funcional. PHP, como lenguaje del lado del servidor, me ayuda a generar contenido que se adapta a las interacciones del usuario, como mostrar información personalizada o procesar datos de formularios. MySQL, por su parte, me permite almacenar y gestionar datos de manera organizada, como los registros de usuarios, productos o cualquier otro contenido relevante. Juntos, estas tecnologías me ofrecen las herramientas necesarias para crear una página web interactiva y escalable.

Además, PHP y MySQL son ideales para mi proyecto debido a su facilidad de uso y flexibilidad. PHP es un lenguaje accesible, perfecto para alguien como yo que está aprendiendo y desarrollando habilidades en el desarrollo web. MySQL, al ser una base de datos confiable y eficiente, me asegura que la información de mi página esté bien estructurada y sea fácil de recuperar. Su combinación no solo reduce costos, al ser tecnologías de código abierto, sino que también me permite enfocarme en crear una experiencia de usuario atractiva y funcional para mi página web.


#### Características
**Características principales de PHP:**

- Fácil de aprender y usar, especialmente para principiantes.
- Compatible con la mayoría de servidores web (Apache, Nginx, etc.).
- Soporte para una amplia variedad de bases de datos, incluyendo MySQL, PostgreSQL, SQLite, y más.
- Gran cantidad de frameworks y librerías disponibles (Laravel, Symfony, CodeIgniter, etc.).
- Comunidad activa y extensa documentación.


**Características principales de MySQL:**

- Alto rendimiento y escalabilidad.
- Soporte para transacciones ACID (Atomicidad, Consistencia, Aislamiento, Durabilidad).
- Fácil integración con lenguajes de programación como PHP, Python, Java, y más.
- Herramientas de administración gráfica como phpMyAdmin y MySQL Workbench.
- Comunidad activa y amplia documentación.

### Instalación



---

## 💼 Documentación y Recursos Adicionales

- **Plex Media Server:** [Guía oficial](https://www.plex.tv/)
- **Docker:** [Documentación oficial](https://docs.docker.com/)
- **TrueNAS:** [Manual oficial](https://www.truenas.com/docs/)
- **Pi-Hole:** [Documentacion Pi-hole](https://pi-hole.net/)
- **DigitalOcean:** [Guía intalación de Apache](https://www.digitalocean.com/community/tutorials/how-to-install-the-apache-web-server-on-ubuntu-20-04-es)
- **pfSense:** [Explicación sobre pfsense](https://keepcoding.io/blog/que-es-pfsense/#%C2%BFQue_es_pfSense)
- **pfSense:** [Explicación sobre pfsense](https://www.youtube.com/watch?v=UIDzzufhNlw)
- **pfSense:** [Explicación sobre pfsense](https://www.openitnet.com/index.php/software/inst-software-libre/pfsense1#:~:text=Las%20principales%20caracter%C3%ADsticas%20incluyen%20detecci%C3%B3n,y%20OpenVPN%2C%20filtrado%20de%20contenido)
- **Port forward:** [Explicacion y configuracion](https://nordvpn.com/es/blog/que-es-port-forwarding/)
- **Port forward:** [Explicacion y configuracion](https://surfshark.com/es/blog/vpn-port-forwarding)
- **Port forward:** [Explicacion y configuracion](https://testpurposes.net/2016/02/23/ssh-port-forwarding/)
- **Sophos:** [Páguina oficial](https://www.sophos.com/es-es)
- **Truenas:** [Explicación y configuración](https://www.redeszone.net/tutoriales/servidores/truenas-core-guia-instalacion-configuracion-nas/)
- **Truenas:** [Información](https://www.neoteo.com/truenas-la-mejor-herramienta-para-almacenar-y-gestionar-datos-en-tu-red/)
- **Truenas:** [Información](https://www.itelca.com.co/truenas-vs-freenas-y-por-que-deberia-actualizar/)
- **Truenas:** [Configuración completa](https://www.redeszone.net/tutoriales/servidores/truenas-core-guia-instalacion-configuracion-nas/)
- **LAMP:** [Configuración completa](https://www.digitalocean.com/community/tutorials/how-to-install-lamp-stack-on-ubuntu#step-6-%E2%80%94-testing-database-connection-from-php-(optional))
- **LAMP:** [Configuración completa](https://www.hostinger.com/es/tutoriales/como-instalar-lamp-en-ubuntu)
- **:** []()
