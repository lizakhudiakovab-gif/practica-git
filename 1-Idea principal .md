PROYECTO INTERMODULAR – 2.º ASIR
Plataforma de administración, monitorización y automatización de servidores
1. Idea general del proyecto
La propuesta consiste en desarrollar una plataforma propia para centralizar la administración de los sistemas informáticos de una empresa y automatizar las tareas más repetitivas de mantenimiento.
La idea es crear una infraestructura con varios servidores Linux y Windows, conectados mediante una red configurada por nosotros, y desarrollar un sistema que permita consultar su estado, ejecutar tareas administrativas y detectar posibles problemas desde un único lugar.
El proyecto combinaría administración de sistemas, redes, seguridad, programación, bases de datos, virtualización y desarrollo de una interfaz web.
El objetivo no sería solamente montar varios servidores, sino conseguir que trabajen conjuntamente y que una parte de su administración pueda realizarse automáticamente.
2. Problema que queremos solucionar
En muchas empresas, los administradores de sistemas tienen que realizar manualmente tareas como:
Comprobar si los servidores están funcionando.
Revisar el consumo de memoria RAM, procesador y almacenamiento.
Comprobar que los servicios importantes están activos.
Crear usuarios y gestionar permisos.
Realizar copias de seguridad.
Revisar errores y registrar incidencias.
Ejecutar tareas de mantenimiento periódicas.
Estas tareas consumen tiempo y pueden provocar errores humanos si no se realizan correctamente.
Nuestra propuesta consiste en desarrollar una solución que permita centralizar estas operaciones y automatizar aquellas que sean seguras y repetitivas.

3. ¿Cómo funcionaría?
El proyecto tendría una infraestructura virtualizada y una aplicación central desde la que consultar el estado de los equipos y lanzar las tareas disponibles.
La estructura aproximada sería la siguiente:
               ADMINISTRADOR
                      |
                      v
              PANEL WEB DE GESTIÓN
                      |
                      v
             SISTEMA DE AUTOMATIZACIÓN
                      |
          +-------------------+---------------+
           |                        |                  |
          v                        v                 v
      UBUNTU       WINDOWS     SERVIDOR DE
      SERVER       SERVER         COPIAS DE
                                                    SEGURIDAD
          |                          |                    |
          +--------------------+----------------+
                      |
                      v
              MONITORIZACIÓN,
              REGISTROS Y ALERTAS
La infraestructura se montaría inicialmente en máquinas virtuales, por lo que podríamos desarrollar y probar el proyecto sin necesidad de disponer de varios ordenadores físicos.
4. Funcionalidades principales
4.1. Monitorización de servidores
Comprobar si cada servidor está disponible.
Consultar el uso de CPU, memoria RAM y disco.
Comprobar la conectividad entre máquinas.
Revisar el estado de determinados servicios.
Mostrar los resultados en el panel web.
4.2. Automatización de tareas administrativas
Ejecutar scripts de mantenimiento.
Comprobar automáticamente el estado de los servicios.
Reiniciar servicios seleccionados cuando se cumplan determinadas condiciones.
Programar tareas periódicas.
Generar informes de funcionamiento.
Registrar los resultados de cada ejecución.
4.3. Gestión de usuarios y permisos
Automatizar la creación de usuarios de prueba.
Gestionar grupos y permisos.
Aplicar configuraciones predefinidas.
Registrar los cambios realizados.
Esta parte se desarrollaría con las medidas de seguridad necesarias y en un entorno de laboratorio.
4.4. Sistema de copias de seguridad
Programar copias de seguridad de archivos y configuraciones.
Almacenar las copias en un servidor diferente.
Comprobar que los archivos se han generado correctamente.
Registrar los resultados.
Realizar pruebas de restauración para verificar que las copias funcionan.
4.5. Panel web de administración
Se desarrollaría una interfaz web sencilla que mostrase información como:
Lista de servidores y su estado.
Uso de CPU, RAM y almacenamiento.
Últimas incidencias detectadas.
Historial de tareas ejecutadas.
Estado de las copias de seguridad.
Acciones administrativas disponibles.
Desde el panel también se podrían lanzar determinadas tareas de forma manual, siempre que el usuario tenga los permisos necesarios.
5. Tecnologías que podríamos utilizar
La selección definitiva dependería de la dificultad que queramos asumir y del tiempo disponible.
Tecnología
Utilidad dentro del proyecto
VirtualBox
Crear y conectar las máquinas virtuales
Ubuntu Server
Alojar servicios y ejecutar tareas automatizadas
Windows Server
Configurar servicios y administración de Windows
Python
Desarrollar la lógica de automatización
Bash
Automatizar tareas en Linux
PowerShell
Administrar y automatizar Windows
Ansible
Automatizar la configuración de varios equipos, si resulta viable
Flask
Desarrollar el panel web
HTML y CSS
Diseñar la interfaz
SQLite o MySQL
Almacenar servidores, tareas e incidencias
SSH
Administrar equipos Linux de forma remota
Cron y Programador de tareas
Ejecutar operaciones periódicas

No sería necesario utilizar todas las tecnologías desde el principio. Primero montaríamos una versión funcional y después añadiríamos las herramientas que aportasen valor al resultado final.
6. Relación con los módulos de ASIR
El proyecto permitiría aplicar conocimientos de diferentes módulos del ciclo:
Implantación de Sistemas Operativos: instalación, configuración y administración de Linux y Windows.
Planificación y Administración de Redes: direccionamiento IP, DNS, DHCP, conectividad y configuración de red.
Fundamentos de Hardware: recursos de los equipos y asignación de CPU, memoria y almacenamiento a las máquinas virtuales.
Gestión de Bases de Datos: almacenamiento y consulta de información sobre servidores, tareas e incidencias.
Lenguajes de Marcas y Sistemas de Gestión de Información: creación de la interfaz web y presentación de datos.
Administración de Sistemas Operativos: gestión de usuarios, permisos, servicios, procesos y automatización de tareas.
Servicios de Red e Internet: configuración y administración de los servicios necesarios para el funcionamiento de la infraestructura.
Implantación de Aplicaciones Web: desarrollo y despliegue de la aplicación de administración.
Administración de Sistemas Gestores de Bases de Datos: instalación, configuración y mantenimiento de la base de datos.
Seguridad y Alta Disponibilidad: control de accesos, copias de seguridad, recuperación y medidas para reducir interrupciones.
La relación concreta con cada módulo dependerá del alcance final y de los contenidos que exija el profesorado.

7. Seguridad del sistema
La seguridad sería una parte importante del proyecto, ya que la aplicación podría ejecutar operaciones administrativas sobre otros equipos.
Se contemplarían medidas como:
Autenticación para acceder al panel.
Permisos diferenciados según el usuario.
Uso de conexiones seguras para administrar servidores.
Restricción de las acciones que se pueden ejecutar.
Registro de las operaciones realizadas.
Protección de las credenciales.
Copias de seguridad y pruebas de recuperación.
Separación de la red de laboratorio cuando sea necesario.
La aplicación no permitiría ejecutar comandos arbitrarios sin control. Las operaciones disponibles estarían definidas previamente y se aplicarían con los permisos mínimos necesarios.
8. Fases de desarrollo
Para repartir el trabajo y evitar que el proyecto se haga demasiado grande, lo dividiríamos en varias fases.
Fase 1. Diseño y planificación
Definir el problema, los objetivos, las tecnologías, la arquitectura y las funciones principales.
Fase 2. Infraestructura
Crear las máquinas virtuales, configurar la red e instalar los sistemas operativos y servicios necesarios.
Fase 3. Automatización
Desarrollar scripts para comprobar el estado de los servidores, ejecutar tareas periódicas y registrar resultados.
Fase 4. Base de datos y aplicación web
Crear la base de datos y desarrollar el panel para consultar información y lanzar tareas autorizadas.
Fase 5. Copias de seguridad y seguridad
Configurar las copias, controlar los permisos y aplicar las medidas de protección.

Fase 6. Pruebas
Simular fallos, detener servicios, provocar situaciones de falta de espacio en un entorno controlado y comprobar que el sistema detecta los problemas y registra correctamente las acciones.
Fase 7. Documentación y presentación
Preparar la documentación técnica, los diagramas de red, las capturas, los resultados de las pruebas y una demostración práctica.
9. Reparto del trabajo en el grupo
Si hacemos el proyecto entre varias personas, podemos dividirlo por áreas:
Infraestructura: máquinas virtuales, sistemas operativos y servicios.
Redes y seguridad: direccionamiento, conectividad, accesos y protección.
Automatización: scripts de Python, Bash o PowerShell.
Aplicación web y base de datos: interfaz, almacenamiento y consulta de información.
Integración y pruebas: conexión entre los componentes, pruebas de funcionamiento y documentación.
El reparto definitivo dependería del número de integrantes y de las normas del proyecto. Todos tendríamos que conocer la arquitectura general para poder explicar el funcionamiento completo.
10. Resultado final esperado
Al finalizar, tendríamos una infraestructura funcional que incluiría varios servidores virtualizados, una aplicación web de administración, un sistema de monitorización, tareas automatizadas, registros de actividad y copias de seguridad.
Durante la presentación podríamos demostrar, por ejemplo, cómo el sistema detecta que un servicio está detenido, registra la incidencia y ejecuta una acción de recuperación previamente configurada. También podríamos mostrar cómo se realiza una copia de seguridad y cómo se comprueba su restauración.
De esta forma, el proyecto tendría una parte práctica que se puede enseñar funcionando, además de la documentación técnica.
11. Posibles ampliaciones
Si terminamos las funcionalidades principales con tiempo suficiente, podríamos incorporar:
Alertas por correo electrónico.
Gráficas históricas de rendimiento.
Administración de más servidores.
Despliegue automatizado de configuraciones.
Detección de equipos que dejan de responder.
Informes periódicos de mantenimiento.
Un sistema de roles para distintos administradores.
Estas funciones serían opcionales y se añadirían únicamente cuando la versión básica estuviera terminada.
12. Conclusión
Esta propuesta busca desarrollar un proyecto práctico que reúna diferentes conocimientos de ASIR en una única solución. No se trataría solamente de configurar servidores, sino de integrarlos en una infraestructura que permita administrarlos de forma centralizada y automatizar parte de su mantenimiento.
La principal ventaja es que el proyecto puede comenzar con una infraestructura sencilla e ir creciendo según el tiempo disponible y las capacidades del grupo.
Propuesta de título definitivo:
Diseño e implementación de una plataforma centralizada de administración, monitorización y automatización de infraestructuras informáticas.

