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

Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.

\newpage

## Strategic-Level Domain-Driven Design.

Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.

\newpage

### EventStorming.

Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.

\newpage

#### Candidate Context Discovery.

Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.

\newpage

#### Domain Message Flows Modeling.

Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.

\newpage

#### Bounded Context Canvases.

Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.

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

![System Landscape Diagram - C4](src/img/cap4/structurizr-landscape_rutakids_ecosistema.png)

\newpage

#### Software Architecture Context Level Diagrams.

![System Context Level Diagram - C4](src/img/cap4/structurizr-SystemContext.png)

\newpage

#### Software Architecture Container Level Diagrams.

![System Container Level Diagram - C4](src/img/cap4/structurizr-Containers.png)

\newpage

#### Software Architecture Deployment Diagrams.

![System Deployment Diagram - C4](src/img/cap4/structurizr-Deployment.png)

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

#### Bounded Context Software Architecture Component Level Diagrams.

![Component Level Diagram](src/img/cap4/structurizr-ParentServiceComponents.png)

\newpage

#### Bounded Context Software Architecture Code Level Diagrams.

::: warn
Para una mejor visualización del diagrama, haga click en la [URL](https://www.mermaidchart.com/raw/e0bf6740-f667-4c65-a393-af7fe2bf0815?theme=light&version=v0.1&format=svg) 
:::

![Code Level Diagram Mermaid](src/img/cap4/parent-service-code-diagram.png)

\newpage

##### Bounded Context Domain Layer Class Diagrams.

![Parent Service Class Diagram](src/img/cap4/parent-service-uml.png)

\newpage

##### Bounded Context Database Design Diagram.

::: warn
Para una mejor visualización del diagrama, haga click en la [URL](https://www.mermaidchart.com/raw/3b7cd053-81bd-4b1f-a9f8-633600aaa10b?theme=light&version=v0.1&format=svg) 
:::

![Database Design Diagram Mermaid](src/img/cap4/parent-service-database.png)
