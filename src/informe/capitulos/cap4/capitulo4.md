---
title: "Universidad Peruana de Ciencias Aplicadas - Informe de Trabajo Final"
author: 
  - "Startup: LLantaTech"
  - "Producto: RutaKids"
  - "Profesor: Leon Baca, Marco Antonio"
  - "Integrantes:"
  - "Ortega Huaraca, Abel Angel: U20201B380"
  - "Avila Asto, Alex Ramon: U20221A322"
  - "Vilchez Rios, Mateo Alejandro: U202210059"
  - "Ramos Rios, Belén del Rocio: U202216246"

date: "2025-01"
subject: "Markdown"
keywords: [Markdown, Report]
subtitle: "Desarrollo de Soluciones IOT - 15185 - 1ASI0572"
lang: "es"
colorlinks: true
footer-left: "LLantaTech"
titlepage: true
titlepage-text-color: "FFFAFA"
titlepage-color: "DC143C"
titlepage-rule-height: 2
titlepage-rule-color: "FFFAFA"
titlepage-logo: "src/img/logo/logo-upc.pdf"
logo-width: 30mm
bibliography: src/informe/bibliografia/bibliografia.bib
csl: src/informe/bibliografia/apa.csl
book: true
classoption: oneside
code-block-font-size: \scriptsize
nocite: |
  @gothelf2021,
  @hernandez2018,
  @kasparova2022,
  @kalbach2016,
  @smith2020,
  @johnson2019,
  @brown2022,
  @igartua2019desconexion,
  @jiang2024pervasive,
  @kaspersky_privacy,
  @collave2024datos
header-includes:
- |
  ```{=latex} 
  \usepackage{morefloats}
  \usepackage{awesomebox}
  \usepackage{fontawesome5}
  \usepackage{tcolorbox}
  \usepackage{graphicx}
  \usepackage{parskip}
  \usepackage{xcolor}
  \usepackage{float} 
  \usepackage{longtable}
  \usepackage{array}
  \usepackage{lscape}
  \usepackage{multirow}
  \usepackage{geometry}
  \usepackage{booktabs}
 
  \newtcolorbox{info-box}{colback=cyan!5!white,arc=0pt,outer arc=0pt,colframe=cyan!60!black}
  \newtcolorbox{error-box}{colback=red!5!white,arc=0pt,outer arc=0pt,colframe=red!75!black}
  \newtcolorbox{norm-box}{colback=gray!5!white,arc=0pt,outer arc=0pt,colframe=gray!60!black}
  \newtcolorbox{warn-box}{colback=orange!5!white,arc=0pt,outer arc=0pt,colframe=orange!80!black}
  \newtcolorbox{attn-box}{colback=green!5!white,arc=0pt,outer arc=0pt,colframe=green!75!black}
  \newtcolorbox{code-box}{colback=pink!5!white,arc=0pt,outer arc=0pt,colframe=pink!80!black}
  \newtcolorbox{learn-box}{colback=blue!5!white,arc=0pt,outer arc=0pt,colframe=blue!40!black,title=\textbf{Objectives:}}
  \newtcolorbox{scenario-box}{colback=orange!5!white,arc=0pt,outer arc=0pt,colframe=orange!80!black,title=\textbf{Scenario:}}
  \newtcolorbox{outline-box}{colback=cyan!5!white,arc=0pt,outer arc=0pt,colframe=cyan!60!black,title=\textbf{Outline:}}
  \newtcolorbox{prereqs-box}{colback=red!5!white,arc=0pt,outer arc=0pt,colframe=red!60!black,title=\textbf{Prerequisites:}}
  \newtcolorbox{labtime-box}{colback=yellow!5!white,arc=0pt,outer arc=0pt,colframe=yellow!60!black,title=\textbf{Lab:}}
  \newcommand{\pandocbounded}[1]{#1} 
  ```
pandoc-latex-environment:
  tcolorbox: [box]
  info-box: [info]
  error-box: [error]
  norm-box: [norm]
  warn-box: [warn]
  attn-box: [attn]
  code-box: [code]
  learn-box: [learn]
  scenario-box: [scenario]
  outline-box: [outline]
  prereqs-box: [prereqs]
  labtime-box: [labtime]
  noteblock: [note]
  tipblock: [tip]
  warningblock: [warning]
  cautionblock: [caution]
  importantblock: [important]
---

# Capítulo IV: Solution Software Design

El diseño de la solución de software constituye una etapa crítica para garantizar que el sistema responda de manera eficaz a las necesidades estratégicas del dominio de negocio identificado. A partir de la estructura de Bounded Contexts previamente definida, se propone una arquitectura modular basada en microservicios, donde cada servicio es responsable de una parte específica del dominio y se comunica a través de interfaces bien delimitadas.

En **RutaKids**, esta solución se implementa mediante una combinación de tecnologías modernas como **Spring Boot** para el desarrollo de microservicios, **Kafka** para la comunicación asíncrona basada en eventos, **OAuth2 / Keycloak** para la autenticación segura de usuarios, y **Angular 17** como framework principal para el frontend modularizado. Además, se adoptan principios de arquitectura orientada a eventos, utilizando técnicas como EventStorming, Domain Message Flow Modeling y Bounded Context Canvas para asegurar una alineación continua entre el diseño técnico y los objetivos de negocio.

A continuación, se detallan los principales artefactos de diseño generados, los cuales representan la estructura, comunicación y responsabilidades de los diferentes componentes que conforman la plataforma RutaKids.

\newpage

## Strategic-Level Domain-Driven Design.

El diseño estratégico en Domain-Driven Design (DDD) se centra en comprender y modelar el dominio del negocio, estableciendo límites claros —conocidos como *Bounded Contexts*— que reflejan las divisiones naturales de conocimiento y responsabilidad dentro del sistema. A diferencia de un enfoque técnico o puramente arquitectónico, el Strategic-Level DDD busca alinear la estructura del software con la realidad organizacional, permitiendo que cada contexto evolucione de manera independiente y coherente. 

En **RutaKids**, este enfoque resulta fundamental para gestionar eficazmente los diferentes dominios que intervienen en la operación de la plataforma, tales como la administración de estudiantes, la gestión de movilidades escolares, la planificación de rutas escolares y la autenticación de usuarios. Al identificar y delimitar explícitamente estos contextos, se facilita no solo la escalabilidad técnica, sino también la colaboración interdisciplinaria y el mantenimiento a largo plazo del sistema. A continuación, se presentarán técnicas como EventStorming, Candidate Context Discovery y Domain Message Flow Modeling, que permiten descubrir y modelar de forma colaborativa los Bounded Contexts pertinentes para RutaKids.


### EventStorming.

En el proyecto **RutaKids**, EventStorming fue empleado para mapear los procesos esenciales del sistema, facilitando la definición de Bounded Contexts y preparando el terreno para el diseño de una arquitectura de microservicios eficiente, alineada al negocio y enfocada en las necesidades reales de los usuarios.\newline

***General Overview***

![Artefacto creado en PlantUML](src/img/cap4/event_storming/general.png)

Este EventStorming proporciona una visión global de los eventos principales del sistema RutaKids. Se identifican los flujos generales como la autenticación de usuarios, la gestión de estudiantes, las movilidades, las rutas escolares y la supervisión general del transporte. Sirve como mapa de alto nivel para comprender la interacción entre los principales contextos.\newline

***Authentication Context***

![Artefacto creado en PlantUML](src/img/cap4/event_storming/auth.png)

En este diagrama se modela el flujo de autenticación y autorización de usuarios dentro de RutaKids. Se capturan eventos como "Usuario inicia sesión", "Usuario olvida contraseña", "Usuario restablece contraseña" y "Usuario cierra sesión", reflejando los procesos de seguridad necesarios para proteger el acceso a la plataforma.\newline


***Students Context***

![Artefacto creado en PlantUML](src/img/cap4/event_storming/students.png)

Este EventStorming se centra en la administración de estudiantes. Incluye eventos como "Estudiante registrado", "Estudiante editado" y "Estudiante asignado a ruta escolar", mostrando cómo el sistema permite gestionar la información de los alumnos y su asociación posterior a rutas de transporte.\newline

***School Transport Context***

![Artefacto creado en PlantUML](src/img/cap4/event_storming/school_transport.png)

Aquí se modela la gestión de movilidades escolares. Se representan eventos como "Movilidad registrada", "Movilidad editada" y "Movilidad asignada a ruta", que permiten un control preciso de la flota de transporte destinada al traslado de estudiantes, asegurando trazabilidad y organización.

\newpage

***School Routes Context***

![Artefacto creado en PlantUML](src/img/cap4/event_storming/school_routes.png)

Este EventStorming describe la planificación y gestión de rutas escolares. Se modelan acciones como "Ruta creada", "Ruta actualizada" y "Estudiantes asignados a ruta", permitiendo comprender cómo se organiza la cobertura de transporte a nivel operativo dentro del sistema.\newline

***IoT and Monitoring Context***

![Artefacto creado en PlantUML](src/img/cap4/event_storming/iot.png)

Este diagrama anticipa la integración de dispositivos IoT (como GPS y lectores RFID) para el monitoreo en tiempo real de movilidades escolares. Se incluyen eventos futuros como "Ubicación de movilidad actualizada" y "Estudiante sube/baja de movilidad", planteando las bases para ampliar la plataforma hacia funcionalidades de rastreo y control de presencia de estudiantes.\newline

\newpage

#### Candidate Context Discovery.

Durante el proceso de modelado inicial mediante EventStorming, se analizaron los eventos, comandos y entidades más relevantes de la aplicación RutaKids. A partir de estos hallazgos, se identificaron agrupaciones naturales de funcionalidades que permiten definir los primeros *Candidate Contexts* para el sistema.

Estos contextos representan divisiones lógicas que agrupan conceptos coherentes entre sí, ayudando a delimitar responsabilidades claras, reducir el acoplamiento y preparar el terreno para una futura arquitectura de microservicios bien alineada al negocio.

A continuación, se detallan los principales *Candidate Contexts* identificados:

| Candidate Context                | Descripción breve |
|:----------------------------------|:------------------|
| **Authentication**               | Manejo de login, logout, recuperación y cambio de contraseñas para los usuarios del sistema. |
| **Student Management**            | Registro, edición, listado y asignación de estudiantes a rutas escolares. |
| **School Transport Management**   | Gestión de movilidades escolares: registro de vehículos, conductores y control operativo de las unidades. |
| **School Routes Management**      | Creación, edición y asignación de rutas escolares a estudiantes y movilidades. |
| **IoT Monitoring**                | Supervisión de ubicación en tiempo real de movilidades y control de asistencia mediante dispositivos RFID. |
| **Administration and Settings**   | Configuración de usuarios, gestión de notificaciones, preguntas frecuentes y acceso a políticas institucionales. |

![Artefacto creado en Structurizr](src/img/cap4/CandidateContextMap.png)

\newpage

#### Domain Message Flows Modeling.

Una vez definidos los contextos candidatos, se procede a modelar los flujos de mensajes que ocurren entre ellos. Esta actividad permite identificar cómo los diferentes módulos del sistema intercambian información, qué eventos o comandos son necesarios y qué dependencias se establecen.

En **RutaKids**, dado el enfoque orientado a eventos y la necesidad de mantener contextos altamente desacoplados, se privilegia el intercambio mediante **eventos asíncronos** siempre que sea posible. A continuación, se detalla el modelo preliminar de flujos de mensajes:

| Emisor                           | Mensaje                               | Receptor                         | Tipo   |
|:----------------------------------|:--------------------------------------|:----------------------------------|:-------|
| Authentication Context            | Usuario autenticado                  | Student Management Context        | Evento |
| Student Management Context        | Estudiante asignado a ruta            | School Routes Management Context  | Evento |
| School Transport Management Context| Movilidad registrada                 | School Routes Management Context  | Evento |
| IoT Monitoring Context             | Ubicación de movilidad actualizada   | School Routes Management Context  | Evento |
| IoT Monitoring Context             | Estudiante sube/baja de movilidad     | Notifications Context             | Evento |
| School Routes Management Context   | Ruta creada                          | Notifications Context             | Evento |
| Notifications Context              | Alerta de llegada/cambio de ruta      | Padres de Familia (vía WebSocket) | Evento |
| Administration and Settings Context| Configuración de usuario actualizada | Authentication Context            | Evento |

Estos flujos de comunicación establecen la base para el diseño de contratos de integración, las políticas de publicación/suscripción en una infraestructura de mensajería basada en eventos, y la orquestación mínima entre servicios.

\newpage

#### Bounded Context Canvases.

A partir de la identificación de los Candidate Contexts en el sistema **RutaKids**, se detallan a continuación los *Bounded Context Canvases* correspondientes. Cada uno define el propósito, responsabilidades, interacciones y reglas de negocio específicas, facilitando la alineación técnica y funcional del diseño basado en Domain-Driven Design (DDD).

**Authentication Context**

- **Propósito**:  
  Garantizar la autenticación segura de los usuarios (padres, directivos y choferes) mediante procesos de login, recuperación de contraseñas y control de sesiones activas.

- **Responsabilidades**:  
  - Login de usuarios.
  - Recuperación y restablecimiento de contraseñas.
  - Cierre seguro de sesiones.
  - Integración con OAuth2 para autenticación federada.

- **Mensajes Entrantes**:  
  - Comando: Iniciar sesión.
  - Comando: Recuperar contraseña.
  - Comando: Cambiar contraseña.

- **Mensajes Salientes**:  
  - Evento: Usuario autenticado.
  - Evento: Error de autenticación.

- **Entidades Principales**:  
  - Usuario.
  - Sesión.

- **Reglas de Negocio**:  
  - Un usuario no puede acceder sin una autenticación válida.
  - Las contraseñas deben cumplir políticas de seguridad definidas.


**Student Management Context**

- **Propósito**:  
  Gestionar el registro, edición y asignación de estudiantes a rutas escolares.

- **Responsabilidades**:  
  - Registro de nuevos estudiantes.
  - Edición de información de estudiantes existentes.
  - Asignación de estudiantes a rutas escolares.

- **Mensajes Entrantes**:  
  - Comando: Registrar estudiante.
  - Comando: Asignar estudiante a ruta.

- **Mensajes Salientes**:  
  - Evento: Estudiante registrado.
  - Evento: Estudiante asignado a ruta.

- **Entidades Principales**:  
  - Estudiante.

- **Reglas de Negocio**:  
  - Todo estudiante debe estar asociado a al menos una ruta activa si utiliza el transporte escolar.


**School Transport Management Context**

- **Propósito**:  
  Administrar la información de movilidades escolares y choferes.

- **Responsabilidades**:  
  - Registro y edición de vehículos escolares.
  - Registro de conductores asignados a movilidades.
  - Control operativo de movilidades activas.

- **Mensajes Entrantes**:  
  - Comando: Registrar movilidad escolar.

- **Mensajes Salientes**:  
  - Evento: Movilidad registrada.

- **Entidades Principales**:  
  - Movilidad escolar.
  - Chofer.

- **Reglas de Negocio**:  
  - Toda movilidad debe tener un chofer asignado para operar.


**School Routes Management Context**

- **Propósito**:  
  Planificar, crear y gestionar rutas escolares seguras para el transporte de estudiantes.

- **Responsabilidades**:  
  - Creación de nuevas rutas.
  - Asignación de estudiantes y movilidades a rutas.
  - Visualización y supervisión de rutas activas.

- **Mensajes Entrantes**:  
  - Evento: Estudiante asignado a ruta.
  - Evento: Movilidad registrada.

- **Mensajes Salientes**:  
  - Evento: Ruta creada.
  - Evento: Ruta actualizada.

- **Entidades Principales**:  
  - Ruta escolar.

- **Reglas de Negocio**:  
  - Cada ruta debe tener asignada al menos una movilidad y un estudiante.
  - Una movilidad solo puede pertenecer a una ruta activa a la vez.


**IoT Monitoring Context**

- **Propósito**:  
  Supervisar en tiempo real la ubicación de las movilidades escolares y registrar el abordaje/bajada de estudiantes.

- **Responsabilidades**:  
  - Recepción de datos GPS de movilidades.
  - Detección de eventos de subida/bajada mediante lectores RFID.
  - Envío de eventos de ubicación y abordaje al sistema.

- **Mensajes Entrantes**:  
  - Ninguno (recibe datos externos de dispositivos IoT).

- **Mensajes Salientes**:  
  - Evento: Ubicación de movilidad actualizada.
  - Evento: Estudiante subió/bajó de movilidad.

- **Entidades Principales**:  
  - Dispositivo GPS.
  - Lector RFID.

- **Reglas de Negocio**:  
  - Las actualizaciones de ubicación deben ser reportadas al menos cada 30 segundos.
  - El evento de subida o bajada de un estudiante debe generar una notificación inmediata.


**Notifications Context**

- **Propósito**:  
  Gestionar el envío de notificaciones relevantes a padres y administradores sobre el estado del transporte escolar.

- **Responsabilidades**:  
  - Recepción de eventos críticos (llegadas, cambios de ruta, incidencias).
  - Generación de alertas personalizadas vía WebSocket.

- **Mensajes Entrantes**:  
  - Evento: Estudiante subió/bajó de movilidad.
  - Evento: Ruta creada o modificada.

- **Mensajes Salientes**:  
  - Evento: Alerta enviada a usuarios.

- **Entidades Principales**:  
  - Notificación.

- **Reglas de Negocio**:  
  - Las notificaciones deben ser enviadas en tiempo real ante eventos críticos.
  - Los usuarios deben poder configurar qué tipos de alertas desean recibir.


\newpage

### Context Mapping.

Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.

\newpage

### Software Architecture.

Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.

\newpage

#### Software Architecture System Landscape Diagram.

Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.

\newpage

#### Software Architecture Context Level Diagrams.

Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.

\newpage

#### Software Architecture Container Level Diagrams.

Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.

\newpage

#### Software Architecture Deployment Diagrams.

Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.

\newpage

## Tactical-Level Domain-Driven Design

Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.

\newpage

### Bounded Context: <Bounded Context Name>

Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.

\newpage

#### Domain Layer.

Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.

\newpage

#### Interface Layer.

Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.

\newpage

#### Application Layer.

Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.

\newpage

#### Infrastructure Layer.

Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.

\newpage

#### Bounded Context Software Architecture Component Level Diagrams.

Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.

\newpage

#### Bounded Context Software Architecture Code Level Diagrams.

Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.

\newpage

##### Bounded Context Domain Layer Class Diagrams.

Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.

\newpage

##### Bounded Context Database Design Diagram.

Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.
