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
block-headings: true
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

![Recurso creado en Canva](src/img/cap4/solution-software-design.png)

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

Este diagrama anticipa la integración de dispositivos IoT (como GPS y lectores RFID) para el monitoreo en tiempo real de movilidades escolares. 
\newpage

#### Candidate Context Discovery.

Durante el proceso de modelado inicial mediante EventStorming, se analizaron los eventos, comandos y entidades más relevantes de la aplicación RutaKids. A partir de estos hallazgos, se identificaron agrupaciones naturales de funcionalidades que permiten definir los primeros *Candidate Contexts* para el sistema.

Estos contextos representan divisiones lógicas que agrupan conceptos coherentes entre sí, ayudando a delimitar responsabilidades claras, reducir el acoplamiento y preparar el terreno para una futura arquitectura de microservicios bien alineada al negocio.

A continuación, se detallan los principales *Candidate Contexts* identificados:

\begin{longtable}{|p{5cm}|p{10cm}|}
\hline
\multicolumn{1}{|c|}{\textbf{Candidate Context}} & \multicolumn{1}{c|}{\textbf{Descripción breve}} \\
\hline
\textbf{Authentication} & Manejo de login, logout, recuperación y cambio de contraseñas para los usuarios del sistema. \\
\hline
\textbf{Student Management} & Registro, edición, listado y asignación de estudiantes a rutas escolares. \\
\hline
\textbf{School Transport Management} & Gestión de movilidades escolares: registro de vehículos, conductores y control operativo de las unidades. \\
\hline
\textbf{School Routes Management} & Creación, edición y asignación de rutas escolares a estudiantes y movilidades. \\
\hline
\textbf{IoT Monitoring} & Supervisión de ubicación en tiempo real de movilidades y control de asistencia mediante dispositivos RFID. \\
\hline
\textbf{Administration and Settings} & Configuración de usuarios, gestión de notificaciones, preguntas frecuentes y acceso a políticas institucionales. \\
\hline
\end{longtable}

![Artefacto creado en Structurizr](src/img/cap4/CandidateContextMap.png)

\newpage

#### Domain Message Flows Modeling.

Una vez definidos los contextos candidatos, se procede a modelar los flujos de mensajes que ocurren entre ellos. Esta actividad permite identificar cómo los diferentes módulos del sistema intercambian información, qué eventos o comandos son necesarios y qué dependencias se establecen.

En **RutaKids**, dado el enfoque orientado a eventos y la necesidad de mantener contextos altamente desacoplados, se privilegia el intercambio mediante **eventos asíncronos** siempre que sea posible. A continuación, se detalla el modelo preliminar de flujos de mensajes:

\begin{longtable}{|p{4cm}|p{5cm}|p{4cm}|p{1cm}|}
\hline
\multicolumn{1}{|c|}{\textbf{Emisor}} & \multicolumn{1}{c|}{\textbf{Mensaje}} & \multicolumn{1}{c|}{\textbf{Receptor}} & \multicolumn{1}{c|}{\textbf{Tipo}} \\
\hline
\textbf{Authentication Context} & Usuario autenticado & Student Management Context & Evento \\
\hline
\textbf{Student Management Context} & Estudiante asignado a ruta & School Routes Management Context & Evento \\
\hline
\textbf{School Transport Management Context} & Movilidad registrada & School Routes Management Context & Evento \\
\hline
\textbf{IoT Monitoring Context} & Ubicación de movilidad actualizada & School Routes Management Context & Evento \\
\hline
\textbf{IoT Monitoring Context} & Estudiante sube/baja de movilidad & Notifications Context & Evento \\
\hline
\textbf{School Routes Management Context} & Ruta creada & Notifications Context & Evento \\
\hline
\textbf{Notifications Context} & Alerta de llegada/cambio de ruta & Padres de Familia (vía WebSocket) & Evento \\
\hline
\textbf{Administration and Settings Context} & Configuración de usuario actualizada & Authentication Context & Evento \\
\hline
\end{longtable}

Estos flujos de comunicación establecen la base para el diseño de contratos de integración, las políticas de publicación/suscripción en una infraestructura de mensajería basada en eventos, y la orquestación mínima entre servicios.

\newpage

#### Bounded Context Canvases.

A partir de la identificación de los Candidate Contexts en el sistema **RutaKids**, se detallan a continuación los *Bounded Context Canvases* correspondientes. Cada uno define el propósito, responsabilidades, interacciones y reglas de negocio específicas, facilitando la alineación técnica y funcional del diseño basado en Domain-Driven Design (DDD).

::: box
**Authentication Context**
:::

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

::: box
**Student Management Context**
:::

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


::: box
**School Transport Management Context**
:::

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

::: box
**School Routes Management Context**
:::

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


::: box
**IoT Monitoring Context**
:::

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


::: box
**Notifications Context**
:::

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

El Context Mapping es una técnica fundamental en el análisis de sistemas complejos, especialmente en proyectos de diseño de software y modelado de negocios. Su propósito es identificar, visualizar y comprender los diferentes contextos en los que una solución interactúa, ya sea mediante relaciones de cooperación, dependencia o conflicto. A través de esta práctica, se pueden representar de manera clara las limitaciones, influencias externas y dinámicas internas que afectan al sistema en estudio, permitiendo una mejor toma de decisiones estratégicas. El mapeo de contextos no solo facilita la alineación entre equipos y stakeholders, sino que también contribuye a la delimitación de responsabilidades y la gestión efectiva de las integraciones futuras.

::: warn
Para una mejor visualización del diagrama, haga click en la [URL](https://www.mermaidchart.com/raw/e86c0884-547b-4c03-b207-f64cc4474216?theme=light&version=v0.1&format=svg) 
:::

![Context Mapping - Mermaid](src/img/cap4/context-mapping.png){height=60%}

\newpage

### Software Architecture.

![Imagen extraída de Canva](src/img/cap4/soodesign.png)

En el desarrollo de software, la arquitectura representa un componente esencial para construir soluciones robustas, escalables y alineadas con los objetivos del negocio. Un enfoque particularmente relevante en este contexto es la arquitectura impulsada por el dominio (Domain-Driven Software Architecture), que orienta el diseño del sistema alrededor de los conceptos y procesos clave del dominio de negocio.

\begin{quote} Este enfoque, popularizado por Eric Evans en su libro "Domain-Driven Design", promueve la construcción de sistemas que reflejen fielmente las complejidades y reglas propias del negocio. \end{quote}

La esencia de esta arquitectura radica en su capacidad para capturar las necesidades del dominio en la estructura del software, fomentando una colaboración estrecha entre los expertos de negocio y los equipos de desarrollo. De esta manera, se asegura que las decisiones arquitectónicas estén profundamente alineadas con las necesidades estratégicas de la organización. Al adoptar un enfoque centrado en el dominio, se facilita la mantenibilidad del sistema, se mejora su adaptabilidad frente a cambios en los requisitos de negocio y se favorece una evolución continua sin comprometer la calidad. En un entorno donde la capacidad de respuesta y la escalabilidad son fundamentales, una arquitectura de software sólida y centrada en el dominio se convierte en un pilar clave para el éxito a largo plazo de las soluciones tecnológicas.

\newpage

#### Software Architecture System Landscape Diagram.

![System Landscape Diagram - C4](src/img/cap4/structurizr-landscape_rutakids_ecosistema.png){ height=70% }

![System Landscape Diagram - C4 - Keys](src/img/cap4/structurizr-landscape_rutakids_ecosistema-keys.png)

\newpage

#### Software Architecture Context Level Diagrams.

![System Context Level Diagram - C4](src/img/cap4/structurizr-SystemContext.png)

![System Context Level Diagram - C4](src/img/cap4/structurizr-SystemContext-keys.png)

\newpage

#### Software Architecture Container Level Diagrams.

![System Container Level Diagram - C4](src/img/cap4/structurizr-Containers.png)

![System Container Level Diagram - C4](src/img/cap4/structurizr-Containers-keys.png)

\newpage

#### Software Architecture Deployment Diagrams.

![System Deployment Diagram - C4](src/img/cap4/structurizr-Deployment.png){ height=90% }

![System Deployment Diagram - C4](src/img/cap4/structurizr-Deployment-keys.png)

\newpage

## Tactical-Level Domain-Driven Design

![Imagen extraída de Canva](src/img/cap4/dddimage.png)

Dentro de la arquitectura impulsada por el dominio, el Diseño Táctico (Tactical-Level Domain-Driven Design) proporciona un conjunto de patrones y herramientas prácticas que permiten modelar de manera precisa y estructurada las distintas partes del dominio. Mientras que el nivel estratégico se enfoca en definir los límites y relaciones entre diferentes subdominios, el diseño táctico desciende a un nivel de detalle que facilita la implementación efectiva de las reglas de negocio dentro de los componentes de software.

\begin{quote} Estos patrones, como Entities, Value Objects, Aggregates, Repositories y Domain Services, permiten capturar las complejidades del dominio y mantener la cohesión, la consistencia y la expresividad en el modelo de software. \end{quote}

El enfoque táctico favorece la creación de modelos que son tanto ricos en significado como resilientes frente al cambio. Gracias a estos patrones, los equipos de desarrollo pueden traducir el conocimiento del dominio en estructuras de código claras, mantenibles y alineadas con los principios fundamentales del negocio. Al utilizar el diseño táctico de manera efectiva, se logra reducir la complejidad accidental, mejorar la comunicación entre técnicos y expertos del dominio, y construir soluciones más sostenibles a largo plazo. En entornos dinámicos y competitivos, dominar las herramientas del diseño táctico resulta crucial para construir sistemas adaptables y orientados al verdadero valor de negocio.

\newpage

### Bounded Context: Parent Service

El **Bounded Context: Parent Service** define un dominio autónomo encargado de gestionar todo lo relacionado con los tutores (*Parents*), sus dependientes (*Children*) y la vinculación con usuarios registrados (*Users*). Dentro de este límite conceptual se modelan las reglas de negocio, las invariantes de los agregados y los casos de uso asociados a la exploración, creación y actualización de padres, la consulta de sus hijos y la obtención de información de usuario. Al aislar este contexto, garantizamos que el lenguaje ubicuo (términos como *Parent*, *Child*, *User*) se mantenga coherente y que los cambios internos no propaguen efectos indeseados a otros dominios de la plataforma.

#### Domain Layer

- **Entidades**  

  - `Parent`  

    - Agregado raíz que encapsula la identidad (`UUID id`), la referencia al usuario propietario (`UUID userId`), atributos de identidad (`firstName`, `lastName`) y la colección de hijos (`List<Child>`). Se encarga de validar invariantes como mínimo un apellido o la unicidad de cada hijo dentro de su lista.  

  - `Child`  

    - Entidad hija con su propia identidad y atributos esenciales (`firstName`, `lastName`, `birthDate`). Puede incluir lógica de negocio para calcular la edad o validar el rango de fechas.  

  - `User`  

    - Representa al propietario del *Parent* en el sistema de autenticación. Mantiene `username`, `email`, `password` y lista de `roles`.  

- **Interfaces de Repositorio**  

  - `ParentRepository`  

  - `ChildRepository`  

  - `UserRepository`  

  Estos contratos definen las operaciones de persistencia requeridas por el modelo de dominio (p. ej., `findById`, `findAllByParentId`, `findByUsername`). Al ubicarlos aquí, aseguramos que la capa de dominio dependa únicamente de abstracciones, no de detalles tecnológicos.

#### Interface Layer

- **Controladores REST**  

  - `ParentController` expone endpoints como `GET /parents` y `GET /parents/{id}`.  

  - `ChildController` ofrece `GET /parents/{parentId}/children`.  

  - `UserController` maneja `GET /users/{username}`.  

  Cada controlador recibe la petición HTTP, extrae parámetros, invoca el servicio de aplicación y envuelve la respuesta en un `ResponseEntity` con los DTO correspondientes.

- **DTOs (Data Transfer Objects)**  

  - `ParentDTO`, `ChildDTO`, `UserDTO`  

  Sirven para desacoplar la representación externa de la estructura interna de las entidades, evitando exponer datos sensibles (p. ej., `password`) y facilitando la evolución independiente de la API.

- **Consumidor de Mensajes Kafka**  

  - `ParentKafkaConsumer` escucha eventos de padres en un topic, parsea el payload JSON (`parseParentPayload`) a un `ParentDTO` y delega en el servicio de aplicación para su procesamiento o persistencia.

#### Application Layer

- **Servicios de Aplicación**  

  - `ParentService`  

    - Casos de uso: `findAllParents()`, `findParentById(UUID)`  

    - Orquesta la llamada a `ParentRepository`, aplica reglas de negocio adicionales (p. ej., validaciones de visibilidad) y convierte entidades a `ParentDTO`.  
    
  - `ChildService`  

    - Caso de uso: `findChildrenByParentId(UUID)`  

    - Recupera la lista de hijos mediante `ChildRepository` y produce `ChildDTO`.  

  - `UserService`  

    - Caso de uso: `findUserByUsername(String)`  

    - Consulta `UserRepository` y construye `UserDTO`.

En esta capa se concentra la lógica de orquestación de flujos, sin exponer detalles de cómo se almacenan o transportan los datos.

#### Infrastructure Layer

- **Implementaciones de Repositorio**  

  - Usualmente basadas en Spring Data JPA o MyBatis, proveen las clases concretas que implementan los métodos de `ParentRepository`, `ChildRepository` y `UserRepository`, traduciendo consultas a SQL y materializando entidades.

- **Configuración Técnica**  

  - `AppConfigParent`  

    - Define el bean `DataSource` y otras configuraciones transversales (p. ej., transaction managers, configuración de JPA).  

    - Registra los repositorios y el consumidor de Kafka en el contexto de Spring.

- **Integración con Mensajería**  

  - `ParentKafkaConsumer`  

    - Se configura aquí el listener (p. ej., `@KafkaListener`), el deserializador de mensajes y la inyección de `ParentService`.

Con esta separación clara, cada capa cumple un rol específico desde la pureza del modelo de dominio hasta los detalles tecnológicos de persistencia y mensajería, garantizando mantenibilidad, testabilidad y capacidad de evolución independiente en el **Bounded Context: Parent Service**.

\newpage

#### Bounded Context Software Architecture Component Level Diagrams

![Component Level Diagram](src/img/cap4/structurizr-ParentServiceComponents.png)

\newpage

#### Bounded Context Software Architecture Code Level Diagrams

**Code Level Diagram Mermaid**

::: warn
Para una mejor visualización del diagrama, haga click en la [URL](https://mermaid.live/edit#pako:eNqVVF1vmzAU_SvIVd-cCkgghUqVVie8VJ0iGC9r9uCBk1ghdmSbrl2b_76L-UjaVNr2xj0HzrkcX99XVMiSoRitFd1vnG-zpXAcXf9sSyKFUbKqmNIN7jgL8rigiglzZH60DCGPZMOr8ozIyWOumfqAM1EuxTuvjKknXrDeKOuMOrh3yVqX92ieWYtT8Fw_ZXupuZGKDx5p5zFQL71N2tqcEXlqnT7g52YPTGu65mLdOd33ud3T1ZZCFrrefUzi8hJ6rGjBpWC6j56WUkE1uu3y4dI2vyDOaHT7lmv6BlE1CDlBiEXyEyTPPvMYJBv9Yz6dRWY_X8DZc22YU1IjNbil1u1zklgy_5zM06EHm4LTx2Dd7ttuv0rDV7ygDnuCtKzhsfW5NryCbgspHMOejXQEWyvZsEVFtZ6xVcN1c-aseFXFF_Nx4iczrAHdsvjC96IwGXfl6BcvzSb298-4kJVU8YXrujfv9HQ7VL3YdRLMo0FsQr4kgfvvYgoy7pSSu3k0nw5KSTJ1J__R1tYm2EklyfXcO0rdEdef_UVqEINRwoRgGJZjcjcnbIZJhuFEuxxOqRSTFOep_atTHI7StmdtEEZwxDvKS1gyr81bS2Q2bMeWKIbHkqrtEi3FAd6jtZHZiyhQbFTNMFKyXm9QvKKVhqrewxyxGadww3YDuqfiu5S7_hMoUfyKnlHseeFVOHanfhROAz_yoylGLwCH0ZXvBZNg4rleEPrBAaPfVsC9CqLAdcdeOA2vgY_GGLGyuRAP7Ya0ixLDomx-pesQLm-z2mphGmnv8AcLzMFm)
:::

![Code Level Diagram Mermaid](src/img/cap4/parent-service-code-diagram.png)

\newpage

##### Bounded Context Domain Layer Class Diagrams

**Parent Service Class Diagram**

::: warn
Para una mejor visualización del diagrama, haga click en la [URL](https://mermaid.live/edit#pako:eNq9V1Fv2jAQ_iuRpUpsAwS00BEhJAp0ikqhSmAPEy9eYiBqsCPb6cY6_vvsJJDEGAZMGi_E5-983_k7X5x34BIPARO4AWRs4MMlhes5vrkxhuOpNbWGzhwb4hdPGy-QIsyN98Qmf53OEHOfb7rdzPZpNrMGhu-ploghauWtDqc-XhoLnzI-hmt0OCWiqjMjn_FOf-UHXtdw5Z-glExv5zhPNsZcwfU6VsSFwQByZHz3KV_JJy2pmdiD6znJHcRaSmgN_eDQHIqYPwj11P1LprsGJQFiOaJC98F0otFcWIu0heG_aK4T9Qoy_xhWynZ91LNk2-2_PXyZONZ0YmvPno1CwnxO6KbIJbMXKC187PWCoPTBNGLdk0VUxMPG8kope4GchNwnGAZFtE6I69g8bJKFd0HDdLQjmRzuozpcEfRhM0slKCmS5NOVmG5RDGdof7X6OiEcRN98FxUppEZd0okXU5SQJaRgkwlFkj36uBYXEeqnjfMsKTKSGjUuCisdTmqRnrOiCP3JeGpPRqOhrdGhTzAXXSxQ22pmL7BYIl4Uw0YsJJihpA13FG0UV602ygqqsDqtLietCnYgly6PvXrH5bucyV81VJikkioH66n3-NSTyjqz56F9KOsTXLxCQYJFa5VaPCXzQ1hh5yb4ZIXhm9ymlN4aMQaXkt0bKXRosYMsdXiBm4BAr7R_dcbDI4cvKctH68vM7k2tyTifQS8MBfOFv9Rdl5KZiELZdArsPcghIxF1UYKR1SnuEdCJbepLYhSHdeQ4DTMH9TkwSKUinj6Kp-T-YxoryIxuhsu1z87valVpZ6ZUMsarDT4GFzpNhlXacgzNN4cMuWOxm6lUurkbhmmElHiRm2OQB-5f_kVcPpKE7V7WRdQucq7is-BH0lewJ7JXkKeTLxa3jkWIKBMVHnud9kkTlWWcxlDLL8PmJDINNy3ExE3npFbAOT5KJZzjostP9QNlIMzisuSJT5X4PM0BXyFxpQKmePQgfZ2DOd4KHIw4cTbYBSanESoDSqLlCpgLGDAxikJxzFD6nbODhBB_IyQ_BOY7-AnMer1Vbd3W7hvt1n2z0W6078tgI8ytdrVRb9417-q1erPVaG7L4Fe8QK3abDdrtdtGrfW53m7f3d2WAfLkXjynn1nyrwyWVGaSEkTYkwUUYS6Xbm7_AKSxSAY)
:::

![Parent Service Class Diagram](src/img/cap4/parent-service-uml.png)

\newpage

##### Bounded Context Database Design Diagram

**Database Design Diagram Mermaid**

::: warn
Para una mejor visualización del diagrama, haga click en la [URL](https://mermaid.live/edit#pako:eNqtU8tuwjAQ_BVrzwElgSSKbxGkApVSGqCHCilyaxOigo0cR5QC_17nQQFR1B7qk3dnNbOza-_gTVAGGJjspiSRZDXjSJ_pOIzQrrqX8bTfRSlFo_tT7jmIOr0gQnnGJCcrhqbD_tM0vC5gK5Iub6JrkmUbIWmFHE76cfQ4CK-aKNTiG51IsWTfQM00CqJwOPnNywX13Q_U81RmKi5sXmNLcgHVwp1ef9D9k-6aSMbVPygXpxtMQvSaSrWIKVGnls72ut83GmJ3nAxGYsOza_i0Aoz0itKEMxoXE84uBltXV24xWhANgwErJvXWqX5Z5QRmoBZMtwlYXymR7zOY8YOuI7kS4y1_A6xkzgyQIk8WgOdkmekoXxce6pd5LFkT_iLEeQh4Bx-ALcttui3Ts33Xc2zf9j0Dtjrt-k3bctpO2zItx7WdgwGfJYHZdHzHNFuW67mmaXmeawCjqRLyofoV5ecwIJGFk7pBximTHZFzVVIfvgBz_O2Y)
:::

![Database Design Diagram Mermaid](src/img/cap4/parent-service-database.png){height=70%}

\newpage

### Bounded Context: Routes Service

El **Bounded Context: Routes Service** representa un dominio autónomo enfocado en la gestión de rutas geográficas y sus respectivos historiales de recorrido. Dentro de este límite conceptual se definen las entidades clave como *Route*, *RoutePoint* y *TravelHistory*, que permiten modelar tanto la estructura de una ruta como su historial de ejecución. Este contexto también incluye mecanismos de consulta, persistencia, transformación de datos y consumo de eventos externos (vía Kafka), lo que lo convierte en un componente central para la trazabilidad de trayectos dentro de la plataforma.

#### Domain Layer

* **Entidades**

  * `Route`

    * Agregado raíz que encapsula la identidad (`UUID id`), el nombre de la ruta, su descripción y una lista ordenada de puntos de paso (`List<RoutePoint>`). Se asegura de mantener la coherencia de los puntos, como el orden secuencial.

  * `RoutePoint`

    * Entidad asociada a `Route` que representa un punto geográfico con latitud, longitud y su posición dentro del recorrido. Se utiliza para reconstruir la trayectoria.

  * `TravelHistory`

    * Entidad que representa un historial de recorrido. Contiene el identificador de un padre o usuario (`UUID parentId`), la ruta asociada (`UUID routeId`) y las marcas temporales de inicio y fin (`startedAt`, `endedAt`).

* **Interfaces de Repositorio**

  * `RouteRepository`

    * Define métodos para la consulta de rutas completas (`findAll`, `findById`).

  * `TravelHistoryRepository`

    * Permite acceder a historiales de viaje filtrados por `parentId`.

Estas interfaces se definen dentro de la capa de dominio para garantizar que los casos de uso dependan únicamente de abstracciones.

#### Interface Layer

* **Controladores REST**

  * `RouteController`

    * Expone los endpoints `GET /routes` y `GET /routes/{id}` para recuperar rutas disponibles.

  * `TravelHistoryController`

    * Proporciona el endpoint `GET /travel-histories?parentId={uuid}` para consultar historiales de viaje por usuario.

* **DTOs (Data Transfer Objects)**

  * `RouteDTO`, `RoutePointDTO`, `TravelHistoryDTO`

    * Permiten transportar datos entre capas sin exponer directamente las entidades del dominio. Son esenciales para la representación externa de las rutas y los historiales.

* **Consumidor de Mensajes Kafka**

  * `RoutesKafkaConsumer`

    * Escucha eventos relacionados con rutas desde un topic de Kafka. Parsea los mensajes (`parseRoutePayload`) y delega al servicio de aplicación para su procesamiento (`consumeRouteEvent`).

#### Application Layer

* **Servicios de Aplicación**

  * `RouteService`

    * Casos de uso: `findAllRoutes()`, `findRouteById(UUID)`
    * Orquesta la recuperación de datos desde `RouteRepository`, transforma las entidades en `RouteDTO` y aplica lógica de negocio adicional si es necesario.

  * `TravelHistoryService`

    * Caso de uso: `findTravelHistoriesByParent(UUID)`
    * Recupera los historiales de viaje asociados a un padre mediante `TravelHistoryRepository`, devolviendo una colección de `TravelHistoryDTO`.

Estos servicios representan los casos de uso expuestos al exterior y actúan como intermediarios entre la capa de presentación y la lógica de persistencia.

#### Infrastructure Layer

* **Implementaciones de Repositorio**

  * Aunque no se detallan en el diagrama, se infiere que están implementadas usando tecnologías como Spring Data JPA, traduciendo métodos como `findById` y `findAll` a consultas SQL u ORM.

* **Configuración Técnica**

  * `AppConfigRoutes`

    * Define beans y configuraciones necesarias para habilitar la conexión con la base de datos y registrar repositorios y consumidores. Incluye la creación del `DataSource` y la inyección de dependencias relevantes.

* **Integración con Mensajería (Kafka)**

  * `RoutesKafkaConsumer`

    * Se configura para escuchar eventos de rutas en tiempo real. Se encarga de la deserialización del mensaje y la transformación del payload a un objeto del dominio (`RouteDTO`), que luego es procesado por `RouteService`.

#### Bounded Context Software Architecture Component Level Diagrams

![Component Level Diagram](src/img/cap4/structurizr-RoutesServiceComponents.png)

\newpage

#### Bounded Context Software Architecture Code Level Diagrams

**Code Level Diagram Mermaid**

::: warn
Para una mejor visualización del diagrama, haga click en la [URL](https://mermaid.live/edit#pako:eNqVlO1umzAUhm_FctV_bkX5SuJKk1ICa7W1myD7s2SaPDCJFYKRMVmzqheza9mN7fARCqqmbb_gfPjR6_fYfsKxTDimeKNYsUXLxTpH6PwcRdW3jaoKWaJCKhSzgpV1pazTdeNdrrlKWcy_vmdHruoaQqG3CmWluSdzrWSWcfWlLSxvvdVSsQPPbkWppTq-6vA-PESf7v2wBZTvWLpj0FRW-66F58k6H0mYF0UmYqaFzEciopYRcXUQMe8VRGMFw_Jr9kLumRhjO2khB1NETejJ4Zj8qsN_WK78XAsteElRQyHt56MUuSZotPwPiu7yVLFSqyrWlRq5DtYFd29XYAcYlopN6-AYAxMNecZi8IqX6PDrZyaSdqKhhy4u3oBrdQBzaiJwqw5PQ3nJNSuidkXYroi6athV227Yc1sehB0SxA4Ag0TDGGVOAvpN-KUWmWyExxkrywVPkTgdRZSKLKNnvhWYwYKAV3LH6Zl5NXMDqwsvvotEb6lZPJJYZlLRM8Mwrkc49nKsTsBp4PizHmh788Ax_h2YNGepYwVBYPlGzwpupp7xHyxRn4KTrIU_Cdwe5U6s-c3kL6geBnMnMG3Sj7h38XrQE5F6vgNHhsUQiiGByXY7HNS6ETZqIY0JhmsMPQk8NE912xrrLd_zNabwmzC1W-N1_gx9rNIyOuYxpnDUOcFKVpstpinLSoiqImGaLwSDO7HvswXLP0u5Py2BENMn_IipaU8uZ1PXmZim67imQ_AR06uZc2matnllurZrT21r-kzwj2a9cWm7U9u2nYltOaY1cwnmSX2T79s3snkqCTyV9UY6fXDFuPJklWtMneffC-e6FQ)
:::

![Code Level Diagram Mermaid](src/img/cap4/routes-service-code-diagram.png)

\newpage

##### Bounded Context Domain Layer Class Diagrams

**Routes Service Class Diagram**

::: warn
Para una mejor visualización del diagrama, haga click en la [URL](https://mermaid.live/edit#pako:eNqtVlFv2jAQ_iuWpUrdRtGaBQYRQmKFblFpqRK6h4kXLznSqMGObKca6_rfZyehxEnatWi8kJy_83333fniBxywELCDg4QIMY1JxMlmRY-O0Oxq6S7dmb-iSP3yZeSxTAJ6KEz6NxrNqIzldjze2z7c3LhTFIcViy95TCNEyQaa1hBEwONUxoxWFuexkKM83jWLqRyjVP-JAvG4og1aOewAblOW_UwAJURhsxBaVhiN6ksulRABR4yHwFs5LTm5h-SbyoLx7QG0cktKOFDpNuxcJ2yY5ywgyZRIWMYbQEISLiGcyGcRQMP9ek5dlXy6XDTLrYwmfWV4a7mfrdcBm7-1Xi_V5YDw_0Vob3a98N3lwms7Xx6kTMTNttnbDYrrmIaTJDl-56D9makDvmzd8LhMRgEX-WkjiQF-SajDOH3ZXpcNfGy0846qEWJsSuTPvO_uWYs8PvD7OKhNodLYRiJ3EqY8usw1ZG6vybTD_lufN5GqesYgdiq9QqM9751MZ4urpbeYz2deU6kzRiVnSaLmlMFrbzeoRSANuTwQKaMCinE1MtWrObaqZ_rXhH9JzbcTr0nakLItl4ayNWkvJucXEy2wf3M58xrqiguyviOKksg2daL5kg4CtMY1KPD5DrN7XfVyWG5ACBKB4nrPjIGjshAF_ppsE0bCnUdavLb3adEa5-7XG2-ydBdXVfqTNFW013FU5NHQWK1knOgJYVAPiSSCZTyAAqN7RI054ue2-oCb52F9_V7cGlb4dIUROzlRT-_VU-Wj7aCAbdQggRCxNVIxzY9ngT85GZd7FPs5iMMaVIUDlcL4KU5lUo3-dLvmzHBQJgr0c9Mt92k92nvfMtJuQRN7-lI6KOUszIKWKFV84ytk-pURKufgKcg_Uqm5vC6TWiu3xEqBC7VJ7vSiS5mL7tkyQr3bnqAV1XUDFG1XeLX5PFex1_i2Ua774Q5W5g2JQ3Ubzo_ECstbUFcY7KjHkPC7FV7RR4UjmWT-lgbYkTyDDlbXsegWO2uSCPWWpeqkQHmV3kFSQn8wVn3FzgP-hR3L_twdDvq9z5bV7_WtXgdvsXM67HUty7ZOrb7dtwf2p8FjB__O_T927f7Atu3e4ONwOBgMrQ6GUCtxWd7j9V8HR1znUdLTdxB-xjIqsTN8_AsPXc6i)
:::

![Routes Service Class Diagram](src/img/cap4/routes-service-uml.png)

\newpage

##### Bounded Context Database Design Diagram

**Database Design Diagram Mermaid**

::: warn
Para una mejor visualización del diagrama, haga click en la [URL](https://mermaid.live/edit#pako:eNqNUttuwjAM_ZXIzwVBSUvpGxsdq8ZNpUzaVAllxEA1SFBIpTHovy8FpnGTRt7sc2KfY3sLE8kRfEDVStlMsWUiiHlRfxQHZHsIijcahS2ScjJ4-csN4yjstYlgS7xKclxPVLrSqRQHLE_ESenxoB_24v8a7HNKZhrHBnk6QVr90UMnIAumU51xvAakmF0gpl_QDiIiFUd1oSmOmq9BZ_wcDuN-9HaXrBVTKLTRdZfcZhzEYTcga82URj5m-gaIgp9A5wMju12pJLdn0_PJnK1vcC7c-CQBhVM0eifIyccmgUSABUtUS5Zys_y93wT0HM0moeBzpj4LWm54LNNyuBET8LXK0ALjcDYHf8oWaxNlK840Ho_nl7Ji4l3K0xD8LXyBb9N6ueG5Tt22Xce1HQs24FcbTtm2qV21XepSj9a83ILv_f9KmboepdRxG5UardGqZwHyVEvVPdzt_nwtmKnCyFFfMUf1KDOhTe1a_gNZ3tTZ)
:::

![Database Design Diagram Mermaid](src/img/cap4/routes-service-database.png){height=70%}


\newpage

### Bounded Context: IoT Service

El **Bounded Context: IoT Service** encapsula las responsabilidades relacionadas con la gestión de dispositivos IoT, sus sensores asociados y los datos generados por estos sensores. Este contexto autónomo define las reglas de negocio, entidades y contratos necesarios para supervisar dispositivos, consultar sensores y almacenar información captada en tiempo real. Gracias a la delimitación clara de sus componentes, se garantiza una evolución independiente, un lenguaje ubicuo centrado en términos como *Device*, *Sensor* y *SensorData*, y una interfaz bien definida para consumidores externos como controladores REST y listeners de eventos.

#### Domain Layer

* **Entidades**

  * `Device`

    * Agregado raíz que representa un dispositivo físico en el sistema. Incluye su identificador (`UUID id`), nombre (`name`), tipo (`type`), posible jerarquía mediante `parentId` y una colección de sensores (`List<Sensor>`). Encapsula relaciones y reglas relacionadas con la agrupación de sensores por dispositivo.

  * `Sensor`

    * Entidad que modela un sensor específico dentro de un dispositivo. Mantiene su `UUID id`, el tipo de medición que realiza (`type`) y la unidad asociada (`unit`).

  * `SensorData`

    * Entidad que representa una lectura puntual generada por un sensor, compuesta por su `id`, una referencia al sensor (`sensorId`), un `timestamp` y el `valor` captado. Puede extenderse para incluir validaciones de rango o detección de valores anómalos.

* **Interfaces de Repositorio**

  * `DeviceRepository`

  * `SensorRepository`

  * `SensorDataRepository`

  Estos contratos definen operaciones de consulta como `findAll`, `findById`, `findAllByDeviceId` o `findAllBySensorId`, permitiendo que la lógica del dominio interactúe con fuentes de datos sin conocer detalles de implementación.

#### Interface Layer

* **Controladores REST**

  * `DeviceController` expone operaciones como `GET /devices` y `GET /devices/{id}`, que permiten recuperar información sobre dispositivos registrados.

  * `SensorController` permite consultar sensores por dispositivo (`GET /devices/{deviceId}/sensors`).

  * `SensorDataController` ofrece endpoints para consultar las lecturas de un sensor específico (`GET /sensors/{sensorId}/data`).

* **DTOs (Data Transfer Objects)**

  * `DeviceDTO`, `SensorDTO`, `SensorDataDTO`

  Estos objetos desacoplan la estructura interna de las entidades del dominio respecto a la vista externa que consumen las APIs, facilitando el versionado y la protección de datos sensibles.

* **Consumidor de Mensajes Kafka**

  * `IoTKafkaConsumer` escucha eventos provenientes del ecosistema IoT a través de un topic de Kafka. Se encarga de parsear mensajes (JSON) a `SensorDataDTO`, y delega en el servicio de aplicación para su almacenamiento.

#### Application Layer

* **Servicios de Aplicación**

  * `DeviceService`

    * Casos de uso: `findAllDevices()`, `findDeviceById(UUID id)`

    * Coordina el acceso al repositorio de dispositivos, transforma los resultados a `DeviceDTO` y aplica cualquier lógica adicional como validaciones de visibilidad o filtrado.

  * `SensorService`

    * Caso de uso: `findSensorsByDeviceId(UUID deviceId)`

    * Encargado de obtener sensores vinculados a un dispositivo y convertirlos en `SensorDTO`.

  * `SensorDataService`

    * Casos de uso: `findSensorDataBySensorId(UUID sensorId)`, `saveSensorData(SensorDataDTO dto)`

    * Administra la recuperación y almacenamiento de datos sensoriales. En el caso de `saveSensorData`, permite la recepción de datos desde el listener Kafka para ser persistidos en el sistema.

Esta capa es responsable de la orquestación de los flujos de datos, sin exponer detalles de persistencia ni de transporte.

#### Infrastructure Layer

* **Implementaciones de Repositorio**

  * Las implementaciones concretas (ej. basadas en MongoDB) de `DeviceRepository`, `SensorRepository` y `SensorDataRepository` se definen en esta capa, traduciendo los métodos abstractos del dominio a consultas técnicas ejecutables.

* **Configuración Técnica**

  * `AppConfigIoT`

    * Define y registra beans como `MongoTemplate` y `KafkaConsumerFactory`, necesarios para el acceso a la base de datos y al sistema de mensajería respectivamente.

    * También se encarga de registrar e inyectar los repositorios y consumidores necesarios para la ejecución del sistema.

* **Integración con Mensajería**

  * `IoTKafkaConsumer`

    * Configurado mediante anotaciones como `@KafkaListener`, escucha eventos desde el sistema de mensajería Kafka, transforma el payload recibido y lo pasa al servicio de aplicación para su procesamiento.

\newpage

#### Bounded Context Software Architecture Component Level Diagrams

![Component Level Diagram](src/img/cap4/structurizr-IoTServiceComponents.png)

\newpage

#### Bounded Context Software Architecture Code Level Diagrams

**Code Level Diagram Mermaid**

::: warn
Para una mejor visualización del diagrama, haga click en la [URL](https://mermaid.live/edit#pako:eNqNVWtvmzAU_SuRq36jFQGSEKpOSnlM0dZ2Clk_LEyVB06DSuwITNes6n_fNTbEeUxrFAV8z_XxuT439htKWUaQh55KvFn15kFCE3p-3ru-vu5NKSflEqek9xVvSSliCa3qXzK1Qx8bNKE9-AT-IiAveUp8RnnJioKUPyUS-4uY0IqVx0jQQgHm-Aj27-_i77fhbDFl8y94-Swyqnrd4IRmmt7JZlPkKeY5oycVa_ie5vihVR2TUjxaYQKQyg6AYIcIzTt0X1DA1jg_rUVCezLCh8dZ-O1eSZmRDatyzsptu2h4F8sEufDphGAyn-hZQt5RZng3n86nYbwIKc95TiovSahc1oA3OXP3JjiOapvSZYkrXtYpr8t_dYieotcKnkbTzwswBMxc5k9g7dECM1LgFKwilaRtgF1LXnzS_QT5fu8CYsIZ0C0HsRwoKJZY2096rOHW20cwNQ4BMWRIamUQMLahzhOxyl6w80GRq1YAWOx5hjNSAbVibKa1pgBVy3oq3hEfgGp7TpiSMkpJKsqqmuph5w_q0YJaRYdRrSQNardTcy6seF4wZVta4KoKyLKXd9Yt86LwzkI7sqLAALXsmXhnVn88jGw1vPidZ3zlWZtXI2UFK70z0zSvNDKseaXo3GgQjjs6x59EA_OjdJl0RzJFUWSHZscU3bi--WGmXDjQSgrCUTTsiIYje3Iz-g-RooKD1IjhC4-uX7sNvOqSoOWMuPlpuk_blV2OctnonDX23TTaHlK70M1UJjcVQRAZCA5dyMjgtngT_-ME8RVZkwR58Jrh8jlBCX2HPFxzFm9pijxoRWKgktVPK-QtcVHBqN5kmJMgx3BKrLvoBtMfjK3bKTBE3ht6RZ7lDC7H7nBgDR13bA1GroG2yOuPB5eW5Vh9CAPg2O67gf40BOalM3Qdxxk4Tt-xbNt0DEQycf7dyquuufEMuPFEKUohnD0Erqaaclix__4Xmh9PVQ)
:::

![Code Level Diagram Mermaid](src/img/cap4/iot-service-code-diagram.png)

\newpage

##### Bounded Context Domain Layer Class Diagrams

**Iot Service Class Diagram**

::: warn
Para una mejor visualización del diagrama, haga click en la [URL](https://mermaid.live/edit#pako:eNq1V21vmzAQ_ivI0qRsS6MkpXlBUaSsSTfUl1RAN2nKFy-4GSrYCJtoWdf_PgNm2IY2HdryIYHzvTx3z53tPIIt8RGwwDaElC4DuEtgtMFv3hirG8_27JW7wQb_5MvGEu2DLTIeC1n2mc1WmAXsMJ9Xsvd3d_bSCHxJ4rIkwDsDwwjVpewQI906hgnCzJZ9XAWUzVyEKUnmBs1_abH8tMEyykKnPUoNj5CmOGAvhFtCBluEzCVFMmqyZAtD7hN5QYQMxr8og1EsaSxJ-i1Exh6GKZJwceaW3rqBNS5V8XHBv2GtuR6tw7Uuf4uQ_6P8zup27dre2mkcHgfFhAaMJAcVayVXIN8H2F-EYeetZeT9XzjRNT4cbL8jsuOa65gFBMNQ1W6sWzs4Hw6F5zKqL95KlGJKj_DVNrYr-Ooo7KmxM_9zlRd35Xy2z5s4cVFS39eEsAlCYUU1UrJu03SLBY2dP9ovlOevEBUm9HWkVCif5aVF8Mzs9cRolaJwj6rFjjrQPiPcwZ6UY1uyeb6-8Zz11dXKaSD0nGCWkDBE2ilQyZU8doiprDqIxgRTVGzhM41kzbSRZM2D3iGNtf971BrzNd6b8qja4FgftMWTs6i3wAtQREdo43q5uLhcZDS7d9crR0ZoE-8S3j9k-Gga6ejypcw9whrAbaFfRF3t-f2iIw4Xvr1TuENKo-Um_BpChcEtPIQE-qVJXLxyEyWLWpNe2B_vnIVnr2_kFBZxzNHfBzueS624XJwmMNvCFfgRwTvioSgO-bmUdem1LJAUH-TiXMBttpNm-ppIP7WucpSu8cX2PmVCcdnbgMEGGOTkhD-940_idmUZvJwMBpgaHKQQNuvmVyPLSNCWJH6uXjqXToDZr15P244tI6VIcq9rq1ulrq2dMJKFvMdVViWmcuXkZC7dnDL4LE3kbGXF6s7ToCjHk5TFBqcYlCCk0atwPJeppny8LI0Gz1WlNm3PmcQooXzscrMjRkXe-XCJKMpAVClLBOYNl49GYVOzqDXJKy20RjlqVctNtwBdwMURDHz-vyof7g1g3xG_RAOLP_owediADX7iejBlxD3gLbBYkqIuSEi6-w6sexhS_pbGPp9s8afsjzSG-CshUWnCX4H1CH4AazDqjcaTs745NU8n5nh0NuqCAxePB73-dGqOh33zbDKdmOZTF_zMPfR7k_5w2B9MB6Ph4PTUHI67APlZHa7Fv8Lspwt2SZaLgIiwj3jPpZgByxw-_QYdRYMe)
:::

![Iot Service Class Diagram](src/img/cap4/iot-service-uml.png)

\newpage

##### Bounded Context Database Design Diagram

**Database Design Diagram Mermaid**

::: warn
Para una mejor visualización del diagrama, haga click en la [URL](https://mermaid.live/edit#pako:eNqNUttugkAQ_ZXNPKNBQJB9s0obY9VGtA8Nidm4UyWVXbIsplb9966iqdomdp5mzlzO3LYwlxyBAqpuyhaKZYkgRrrRa68TkW1lHWQ67XVJyslL_weLJ-Pe8IkIluEvUG9yvMnOmUKhZymv8H0iKiWOhvFofI_siHFcp3M0Jchj_w7lCSxFqv_km3Xbk_a_SAsUhVS3pCY9mvQGEdFphoVmWX7hG00fniOyZqsSb8hPm93tajW5PY9OyZIVV8u48letUqJwLhU3gWBBhipjKTenO46QgF6iOQNQo3KmPhJIxN7EsVLLeCPmQLUq0QIly8US6DtbFcYqc840nk5_DsmZeJPy0gS6hU-gruvV_aDlhYHb8Lym27BgAzR06nYYNm2n6bte4Df9vQVfx3y73rIdx26EXtBw3MDzQwuQp1qqQfV1x-ezYKEOg5z6Q8FRdWQptCkd7L8BYvq_Sg)
:::

![Database Design Diagram Mermaid](src/img/cap4/iot-service-database.png){height=70%}

\newpage

### Bounded Context: IoT Interceptor Service

El **Bounded Context: IoT Interceptor Service** encapsula la lógica necesaria para interceptar y procesar datos provenientes de dispositivos IoT. Este servicio se encarga de recibir eventos sensoriales en tiempo real a través de mensajería Kafka, transformarlos en estructuras comprensibles por el sistema (`SensorDataDTO`) y transmitirlos mediante WebSocket a consumidores interesados, como dashboards u otras interfaces. La separación de responsabilidades asegura que el servicio pueda evolucionar con independencia, facilitando la escalabilidad de nuevas fuentes de datos y consumidores.

#### Domain Layer

* **Entidades y Value Objects**

  * `SensorDataDTO`

    * Objeto de transferencia que encapsula los datos sensoriales recibidos. Incluye atributos clave como `id`, `deviceId`, `sensorId`, `timestamp` y `value`. Aunque es un DTO, actúa aquí como representación estructural del dato del dominio.
    * Podría evolucionar en una entidad del dominio si se integran reglas como validaciones de umbrales o formatos de tiempo.

#### Interface Layer

* **Controlador WebSocket**

  * `WebSocketController`

    * Exposición de endpoints mediante WebSocket para enviar datos en tiempo real hacia los clientes.
    * Métodos clave:

       ```java
       broadcastSensorData(destination, payload)
       ```

      ```java
       broadcastAlert(destination, message)
      ```
    * Maneja la serialización y canalización de datos hacia destinos específicos (topics/subscripciones) y encapsula el protocolo WebSocket.

* **DTOs (Data Transfer Objects)**

  * `SensorDataDTO`

    * Utilizado como contrato de datos entre capas y para exponer únicamente la información relevante.

* **Consumidor de Mensajes Kafka**

  * `IoTConsumer`

    * Anotado con `@KafkaListener`, recibe mensajes del broker Kafka.
    * Métodos clave:

      ```java
      consumeIoTEvent(String message)
      ```

      Deserializa el mensaje y delega al procesamiento.

      ```java
      processSensorData(SensorDataDTO data)
      ```

      Encapsula reglas básicas como validación de estructura y decisión de retransmisión.

#### Application Layer

* **Orquestación de Flujos**

  * Esta lógica se encuentra parcialmente dentro del `IoTConsumer`, que podría dividirse para una mayor pureza arquitectónica en un servicio separado como `SensorDataService` (a definir en futuras iteraciones).
  * Actualmente, la capa de aplicación orquesta:

    * El consumo del mensaje IoT.
    * La transformación del payload en `SensorDataDTO`.
    * La delegación hacia `WebSocketController` para su retransmisión.

* **Casos de Uso (implícitos en la orquestación)**

  * *Receive and parse IoT data from Kafka.*
  * *Emit processed sensor data via WebSocket.*
  * *Send alert notifications when necessary.*

#### Infrastructure Layer

* **Configuración Técnica**

  * `AppConfigInterceptor`

    * Proveedor de beans de infraestructura:


      ```java
      kafkaConsumerFactory()
      ```

      Define la configuración para la recepción de eventos Kafka, incluyendo deserializadores, grupos de consumidores y seguridad.

      ```java
      webSocketConfig()
      ```

      Implementa `WebSocketConfigurer`, establece los handlers y mapeos necesarios para la conexión WebSocket.

* **Integración con Mensajería (Kafka)**

  * `IoTConsumer` está conectado directamente mediante anotaciones a la infraestructura de mensajería, definiendo en esta capa los detalles de conexión al topic, la deserialización del payload y los logs.

* **Integración WebSocket**

  * El `WebSocketController` se configura dentro del contexto Spring como endpoint activo, listo para enviar información a los suscriptores.

\newpage

#### Bounded Context Software Architecture Component Level Diagrams

![Component Level Diagram](src/img/cap4/structurizr-InterceptorComponents.png){ height=90%}

\newpage

#### Bounded Context Software Architecture Code Level Diagrams

**Code Level Diagram Mermaid**

::: warn
Para una mejor visualización del diagrama, haga click en la [URL](https://mermaid.live/edit#pako:eNqVk9uK2zAQhl9FKCy04KQ-H1RSyMGGZbu0kEChdS-0trwRsSUjyd1ss3mqPkJfrLKdOE2glNWF0Qy_Po9-zexhxnMCEXwUuN6A9TJlQC_ZPPSJFN7yNbhlioiM1IqLFPaKduVUkExRzsB6nrJzfouLLf5IpSKMiG8dYsGZbCoi0pS9Oe4B-UGY4hLctfK3Kfx-JjxJLVKCl2UH-EIeVjzbEnXOtqB4V3NGwGr96f7zu0HTk_5RDRiPP7ysBWayomoo4eXih_1RwvIT5eYGTKdTEEtFS11vTsAC11i2yV6QlVjKJSkAbY0qcEZAQcsSjWInsZOlITV5S9DItiI_cY7h-InmaoPsemdkvOQCjUzTfH8FxHVd0gx3Jh-RYeLF0YB0F7PEM1-DzHmF6YmWJIkTmwMtmYcL81U0ygqBT6Ut4yDxB5gfOLN58B_YhcOz7rIZ_f2LtS6To-EYtF_Gc37t-dXjDvb_XeXF215IoAF1S2o3cj0A-_ZICtWGVCSFSG9zLLZtux-0DjeKr55ZBpESDTGg4M3jBqICl1JHTZ1jRZYU66GphmyN2VfOq9MRHUK0hzuIbCucuGbo-ZHjeJETeAZ8hsgKzYkVuo7n-2Hkeo5lHwz4swOYkyAMXTewwsh3gtB3IgOSnOpxvO-ntxtiQw9xe5VjhbqBiVjwhimIfNs9_AHQ10R9)
:::

![Code Level Diagram Mermaid](src/img/cap4/iot-interceptor-code-diagram.png)

\newpage

##### Bounded Context Domain Layer Class Diagrams

**Iot Interceptor Service Class Diagram**

::: warn
Para una mejor visualización del diagrama, haga click en la [URL](https://mermaid.live/edit#pako:eNqVVN9v2jAQ_lcsPzE1RSWkSWpVSFXZJLROe4Cq0pQXYx_BIrEj22FjiP99TkIhgVTV_BDbd_fdffcj3mOmOGCCWUaNmQqaaponErlVS9BMLZ6VNGUOGu0bRbUeH7_T1Ya-CGNBgp5Mzqob1tg75NctSDuYWy1kinIwhqbwhaCtErxlX2jFnG4O0ig9pZYOzsfp4ifibu-gDolsU3yD5VyxDVhH1GqVZZdUTwYdmkutKGfU2HbghioHY4WkVijpoS6Zgu4yh7vO4uTuycW3_Z4-LsRFSk9F4ZJZiXQmLWgGhVUXOTXqUteuO3ltqsa89-wbZQ66G7hgF6IW4nergM5pZfzWFZUadC_RbnFaDG9eX2dT1KlQLeGwFQxmV3JTO-rIXxSjmXMNC5EDsu5jLM2LlsVUlcsM0JZmJVzQa8_t7e2kS5Sg44waNOk375kpgrgwBbVsfYb19qnCt_zVwZoafo7rjXuN7xv5nixPM_m_QA0MxLaJhz3sssip4O6ZqDucYLuGHBJM3JFTvUlwIg_OjpZWzXeSYWJ1CR7WqkzXmKxoZtytLNyfDMc35iQtqPylVP4OcVdM9vgPJv4oHgZ3cRjch_5DHPuxh3eYjKJoGPphMA7GfjiKRnF88PDf2sHdMIrjIIhGfhiF9w_jKPAwcOFK--P4xlWbh1NdpXJkCJKDflaltJiEY__wDzdZpJU)
:::

![Iot Interceptor Service Class Diagram](src/img/cap4/iot-interceptor-uml.png)

##### Bounded Context Database Design Diagram

**Database Design Diagram Mermaid**

::: warn
Para una mejor visualización del diagrama, haga click en la [URL](https://mermaid.live/edit#pako:eNpdkE1vwjAMhv9K5XOFaBuSkBsbPaANmMbHYaqEIuJBNJKgNEVjqP994WPThk_2Y_vVa59g7RSCAPRDLTdemsomMWblZDZ9XQ0H88GqXJaTeXK6Ns6xWIyGiVbJy9MdU3jQa1xpdcdrtLXz_3hULuejcZkEbbAO0uz_9KaLh-cyOchdg1faVhZSMOiN1Cq6vZipIGzRYAUipkr6jwoq28Y52QQ3O9o1iOAbTMG7ZrMF8S53dayavZIBb9f-0r20b86Zn5VYgjjBJ4g84x3S5ZT0aN7nPOcpHEFkjHVoTklBipxmLOO8TeHrItDtMM4JYRkreLdfMNJLAZUOzo-vr758PIWNP59yc4hWoX90jQ0gaEHbbxpId9c)
:::

![Database Design Diagram Mermaid](src/img/cap4/iot-interceptor-database.png){height=70%}
