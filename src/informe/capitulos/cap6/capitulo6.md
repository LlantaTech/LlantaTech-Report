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

# Capítulo VI: Product Implementation, Validation & Deployment

## Software Configuration Management.

En esta sección se establecen las bases para controlar y coordinar todos los elementos que componen nuestro sistema de transporte escolar, desde el entorno de desarrollo hasta el despliegue en producción. Recoge la configuración del entorno de desarrollo, donde se definen las versiones mínimas de IDE, SDK, librerías y contenedores que garantizan entornos homogéneos y fácilmente reproducibles; el control de versiones, con un modelo de ramas, políticas de merge y flujos de pull request que facilitan la colaboración y minimizan conflictos; la guía de estilo y convenciones de código, apoyada en linters y formateadores automáticos para asegurar la legibilidad y mantenibilidad del software; y, finalmente, la configuración de despliegue, a través de pipelines de CI/CD y scripts parametrizados que automatizan la provisión y actualización de los entornos de staging y producción de forma segura y confiable.

Con este enfoque integral de la Gestión de Configuración de Software (SCM), cada cambio queda registrado, validado y desplegado siguiendo un flujo de trabajo claro y trazable, lo que redunda en mayor estabilidad, transparencia y velocidad en la entrega de nuevas funcionalidades.

![Imagen extraída de Canva](src/img/cap6/capitulo5.png)

\newpage

### Software Development Environment Configuration.

En esta sección se detallan los productos de software que el equipo utilizará a lo largo de todo el ciclo de vida del sistema de transporte escolar. Para cada herramienta se especifica su nombre, su propósito dentro del proyecto y la forma de acceso, ya sea mediante la ruta de referencia de un servicio SaaS o el enlace de descarga para instalación local. Además, se cubren todas las fases de trabajo: gestión de proyectos, gestión de requisitos, diseño UX/UI del producto, desarrollo de software, pruebas, despliegue y documentación, garantizando que cada herramienta cumpla con las restricciones y estándares definidos por la institución.

::: norm
**Gestión de Proyectos y Requisitos**
:::

**UxPresia**  

Nos ayudará a capturar y priorizar requerimientos mediante mapas de historias de usuario, tableros de retrospectivas y definición de flujos de trabajo colaborativos.

![Imagen extraída de Canva](src/img/cap6/uxpressia-logo.png)

\newpage

::: norm
Comunicación y Almacenamiento
:::

**Discord**  

Nos ayudará a coordinar comunicación asíncrona y en tiempo real con canales temáticos, integrando notificaciones de repositorios y pipelines.

![Imagen extraída de Canva](src/img/cap6/discord-logo.png)

**Google Drive**  

Nos ayudará a centralizar y compartir recursos estáticos (imágenes, documentos de diseño, exportaciones) con control de versiones automático.

![Imagen extraída de Canva](src/img/cap6/drive-logo.png)

\newpage

::: norm
Diseño UX/UI y Modelado
:::

**Figma**  

Nos ayudará a prototipar y validar interfaces interactivas, facilitando la colaboración en diseño de pantallas móviles y web.

![Imagen extraída de Canva](src/img/cap6/figma-logo.png)

**Mermaid**  

Nos ayudará a generar diagramas (flujo, secuencia, entidad-relación) directamente desde texto, manteniendo la documentación arquitectónica actualizada.

![Imagen extraída de Canva](src/img/cap6/mermaid-logo.png)

\newpage

**Structurizr**  

Nos ayudará a crear modelos C4 de arquitectura de software, exportables para compartir vistas de contexto, contenedores y componentes.

![Imagen extraída de Canva](src/img/cap6/Structurizr-logo.png)

::: norm
Entornos de Desarrollo e IDEs
:::

**WebStorm**  

Nos ayudará a desarrollar el front-end con herramientas avanzadas de refactor, debug y pruebas de JavaScript/TypeScript.

![Imagen extraída de Canva](src/img/cap6/webstorm-logo.png)

\newpage

**IntelliJ IDEA**  

Nos ayudará a programar el backend en Java/Spring Boot con integración nativa de Maven/Gradle y soporte de debugging.

![Imagen extraída de Canva](src/img/cap6/intellij-logo.png)

**Visual Studio Code**  

Nos ayudará a editar scripts, archivos de configuración y pequeños microservicios con su vasta biblioteca de extensiones.

![Imagen extraída de Canva](src/img/cap6/vsc-logo.png)

\newpage

**Vim**  

Nos ayudará a realizar ediciones rápidas en servidor, escribir scripts o revisar logs directamente desde la terminal.

![Imagen extraída de Canva](src/img/cap6/vim-logo.png)

::: norm
Frameworks y Plataformas de Desarrollo
:::

**Spring Boot**  

Nos ayudará a estructurar y exponer servicios RESTful en Java, con arranque rápido, configuración mínima y soporte de seguridad.

![Imagen extraída de Canva](src/img/cap6/spring-logo.png)

\newpage

**Angular**  

Nos ayudará a construir la aplicación web de gestión con componentes modulables, inyección de dependencias y rutinas de pruebas.

![Imagen extraída de Canva](src/img/cap6/angular-logo.png)

**React**  

Nos ayudará a desarrollar la landing page y dashboards ligeros, aprovechando su ecosistema de hooks y librerías de visualización.

![Imagen extraída de Canva](src/img/cap6/react-logo.png)

\newpage

**Flutter**  

Nos ayudará a crear la aplicación móvil multiplataforma con un solo código, garantizando rendimiento nativo y consistencia UI.

![Imagen extraída de Canva](src/img/cap6/flutter-logo.png)

\newpage

### Source Code Management.

En esta subsección de Source Code Management, el equipo establecerá los medios y el esquema de organización que aplicará para el seguimiento de todas las modificaciones al código fuente. Para ello se utilizará GitHub como plataforma y sistema de control de versiones. Se incluirá la URL de cada repositorio correspondiente a los diferentes productos del proyecto (Landing Page, Web Services y Frontend Web Applications). En el caso de los Web Services, el repositorio contendrá tanto el proyecto principal como los archivos de pruebas unitarias y de integración/aceptación.

Asimismo, se implementará el modelo GitFlow (ver “A successful Git branching model” de Vincent Driessen en Referencias) como workflow de control de versiones. Además de la rama principal (main), se creará una rama de desarrollo (develop). Cada nueva funcionalidad o corrección atravesará un branch propio siguiendo la convención feature/< descripción_corta >. De igual forma, se definirán convenciones para las ramas de liberación (release/< versión >) y de corrección urgente (hotfix/< versión >). Para el versionado de lanzamientos se aplicará Semantic Versioning 2.0.0 —p. ej. v1.2.0— y para los mensajes de commit se seguirá el estándar Conventional Commits (ver “Conventional Commits” en Referencias), asegurando claridad y trazabilidad en cada cambio.

\vspace{0.4cm}

![Artefacto creado con Mermaid](src/img/cap6/gitflow.png)

\newpage

### Source Code Style Guide & Conventions.

Para el desarrollo de nuestro sistema de transporte escolar, cada solución (Landing Page, Web Application, Mobile Application y Web Services) cuenta con su propio stack tecnológico, conjunto de herramientas, convenciones de idioma y estrategia de pruebas. A continuación se detalla cada una:

::: box  
**Landing Page**  
:::

- **Tecnologías**  

  - *React* con *HTML5*, *CSS3* y *JavaScript (ES6+)*.  

  - Librerías de estilo: *Tailwind CSS* y componentes de *shadcn/ui*.  

- **Herramientas**  

  - IDE: *Visual Studio Code* / *WebStorm*.  

  - Control de versiones: *Git* y *GitHub* (repositorio `landing-page`).  

  - Diseño visual y prototipos: *Figma*.  

  - Despliegue: *Vercel* con previews automáticas por Pull Request.  

- **Convenciones de idioma**  

  - Código y comentarios en **inglés**.  

  - Implementación de *i18n* para soporte de español.  

- **Pruebas y documentación**  

  - Pruebas de integración y E2E en *Playwright* con escenarios escritos en *Gherkin*.  

  - Documentación de componentes en *Storybook*.  

![Recurso extraido de Canva](src/img/cap6/landing-banner.png)

\newpage

::: box  
**Web Application (Admin Console)**  
:::

- **Tecnologías**  

  - *Angular* (TypeScript, RxJS, Angular CLI).  

  - Componentes modulares y formularios reactivos.  

- **Herramientas**  

  - IDE: *WebStorm* / *Visual Studio Code*.  
  
  - Control de versiones: *Git* y *GitHub* (repositorio `admin-web-app`).  

  - Diseño: *Figma* para wireframes y flujos de usuario.  

  - QA y pruebas: *Cypress* para tests E2E.  

  - Contenedorización local: *Docker Compose* (servicio web + base de datos de desarrollo).  

  - Hosting: *Netlify* para previews y producción.  

- **Convenciones de idioma**  

  - Código y mensajes en **inglés**.  

- **Pruebas y documentación**  

  - Historias de usuario descritas en *Gherkin* dentro del repositorio.  

  - Documentación de API REST consumidas a través de *Swagger UI*.  

![Recurso extraido de Canva](src/img/cap6/web-app-banner.png)

\newpage

::: box  
**Mobile Application (Tutor App)**  
:::

- **Tecnologías**  

  - *Flutter* (Dart) para iOS y Android con arquitectura *BLoC*.  

  - Plugins para geolocalización en tiempo real, notificaciones push y cámara.  

- **Herramientas**  

  - IDE: *Android Studio* / *Visual Studio Code*.  

  - Control de versiones: *Git* y *GitHub* (repositorio `mobile-app`).  

  - Diseño de pantallas: *Figma* + prototipos interactivos.  

  - Emulación y pruebas: *Android Emulator*, *iOS Simulator*.  

- **Convenciones de idioma**  

  - Código y recursos en **inglés**.  

  - Soporte multilenguaje con paquetes *flutter_localizations*.  

- **Pruebas y documentación**  

  - Tests unitarios y widget tests en *Flutter Test*, escenarios de usuario en *Gherkin*.  

  - Documentación de flujos en *Mermaid* incrustada en el README.  

![Recurso extraido de Canva](src/img/cap6/mobile-app-banner.png)

\newpage

::: box  
**Web Services (Backend)**  
:::

- **Tecnologías**  

  - **Auth Service:** *Java*, *Spring Boot*, *Spring Security* y *JWT*.  

  - **Temporary Email Service:** *Python*, *Flask* y librería *TempMail API*.  

  - Persistencia: *MySQL* / *PostgreSQL* con *Flyway* para migraciones.  

  - Mensajería interna con *RabbitMQ*.  

- **Herramientas**  

  - IDE: *IntelliJ IDEA* / *Visual Studio Code*.  

  - Control de versiones: *Git* y *GitHub* (repositorio `web-services`).  

  - Contenedores: *Docker* + *Docker Compose* para entornos locales.  

  - Documentación de API: *Swagger* (OpenAPI 3).  

  - Pruebas: *JUnit 5*, *Mockito* (Java) y *pytest* (Python).  

  - Orquestación CI/CD: *Jenkins* con pipelines definidas en Jenkinsfile.  

  - Monitoreo: *Prometheus* + *Grafana* (métricas de servicios).  

- **Convenciones de idioma**  

  - Código, variables y documentación en **inglés**.  

- **Pruebas y documentación**  

  - Pruebas unitarias, de integración y aceptación descritas en *Gherkin* y enlazadas a las historias de usuario.  

  - Diagrama C4 de la arquitectura en *Structurizr* y diagramas de secuencia en *Mermaid*.  

![Recurso extraido de Canva](src/img/cap6/web-service-banner.png)

\newpage

::: box  
**Convenciones de Commits**  
:::

Adoptamos **Conventional Commits v1.0.0**:
```text
<type>[scope opt]: <short description>
```
- **type:** feat, fix, docs, style, refactor, test, chore  

- **scope:** componente o módulo afectado  

- **description:** resumen breve y claro  

::: box  
**Versionado Semántico**  
:::

Seguimos **Semantic Versioning 2.0.0 (X.Y.Z)**:  

- **X (Major):** cambios incompatibles  

- **Y (Minor):** nuevas funcionalidades compatibles  

- **Z (Patch):** correcciones menores  

Las ramas y tags se nombran así:  

- Feature branches: `feature/<short-description>`  

- Release branches: `release/vX.Y.0`  

- Hotfix branches: `hotfix/vX.Y.Z`

\newpage

### Software Deployment Configuration.

Esta sección describe la configuración de despliegue utilizada para cada componente de la solución digital: Landing Page, Web Services y Aplicacion Web Frontend. A partir del código fuente en los repositorios, se detallan los pasos necesarios para su correcta publicación en entornos de desarrollo y producción.

::: warn
Para acceder al flujo de trabajo, haga click a la [URL](https://github.com/orgs/LlantaTech/repositories)
:::

**Desplegar** ***Landing Page***

* Clone el repositorio: *CodeMinds-LandingPage*

![Organización CodeMinds, imagen extraída de Github](src/img/cap6/landing-deploy-1.png){ width=80% }

* Abra el proyecto en su IDE de confianza y realice lo siguiente:

    - Instale las dependencias del proyecto web

    - Ejecute el proyecto con npm

![Organización CodeMinds, imagen extraída de Github](src/img/cap6/landing-deploy-2.png){ width=80% }

\newpage

**Desplegar** ***Web Application***

* Clone el repositorio: *RutaKids-WebApp*

![Organización CodeMinds, imagen extraída de Github](src/img/cap6/webapp-deploy-1.png){ width=80% }

* Abra el proyecto en su IDE de confianza y realice lo siguiente:

    - Instale las dependencias del proyecto web

    - Ejecute el proyecto con ng

![Organización CodeMinds, imagen extraída de Github](src/img/cap6/webapp-deploy-2.jpg){ width=80% }

\newpage

**Desplegar** ***Web Services***

* Clone el repositorio: *RutaKids-Micro-Servicios*

![Organización CodeMinds, imagen extraída de Github](src/img/cap6/webservices-deploy-1.png){ width=80% }

* Abra el proyecto en su IDE de confianza y realice lo siguiente:

    - Instale las dependencias del proyecto Spring

    - Para pruebas, ejecute cada servicio por separado

![Organización CodeMinds, imagen extraída de Github](src/img/cap6/webservices-deploy-2.jpg){ width=80% }

\newpage

## Landing Page, Services & Applications Implementation.

El desarrollo de páginas de aterrizaje (landing pages), servicios y aplicaciones implica una planificación estratégica centrada en los objetivos del negocio y las necesidades del usuario final. En este proceso, se diseñan y construyen interfaces visuales atractivas que no solo captan la atención del usuario, sino que también lo guían de forma efectiva hacia una acción deseada, como la adquisición de un producto, la suscripción a un servicio o la solicitud de información.

La implementación de servicios web y funcionalidades de backend permite conectar la interfaz con la lógica del sistema, garantizando una experiencia fluida y coherente en la interacción con la plataforma. Se integran APIs, sistemas de autenticación, bases de datos y mecanismos de seguridad que permiten el funcionamiento eficiente y seguro de las aplicaciones.

Además, se considera la escalabilidad y mantenibilidad del código, aplicando buenas prácticas de desarrollo como la modularidad, el uso de frameworks modernos y la documentación adecuada. Este enfoque integral asegura que tanto la landing page como los servicios asociados respondan con eficacia a los requerimientos técnicos y de negocio, aportando valor real al usuario y mejorando la presencia digital de la organización.

![Recurso extraído de Canva](src/img/cap6/landing-page-services-applications.png)

\newpage

### Sprint 1

El Sprint 1 marca el inicio formal del proceso de desarrollo del proyecto, estableciendo las bases tanto a nivel técnico como organizativo. Durante esta etapa, el equipo se enfocó en la consolidación de los primeros capítulos del informe teórico (Capítulo 1 y 2), así como en la elaboración del documento de especificación de requisitos. Estos elementos resultan fundamentales para alinear al equipo en torno a una visión común del sistema a desarrollar. Asimismo, se definieron los objetivos iniciales de implementación, priorizando el desarrollo de la landing page, el análisis y elección de las tecnologías base (frameworks, herramientas y lenguajes de programación), y el inicio de la estructura del backend. Esta primera iteración permitió establecer una dinámica de trabajo colaborativa, con roles definidos y tareas distribuidas de forma equitativa, asegurando que cada integrante aporte activamente al cumplimiento del Sprint Goal.

#### Sprint Planning 1.

\begin{longtable}{|p{5cm}|p{9cm}|}
\hline
\textbf{Sprint Planning Background} & \\ \hline
\endfirsthead
\hline
\textbf{Sprint} & \textbf{Sprint 1} \\ \hline
\endfoot
\hline
\textbf{Date} & 10/05/2025 \\ \hline
\textbf{Time} & 21:00 \\ \hline
\textbf{Location} & Discord Virtual Meeting \\ \hline
\textbf{Prepared By} & Ortega Huaraca, Abel Angel \\ \hline
\textbf{Attendees (to planning meeting)} & Ortega Huaraca, Abel Angel / Avila Asto, Alex Ramon / Vilchez Rios, Mateo Alejandro / Ramos Rios, Belen del Rocio \\ \hline
\textbf{Sprint 1 Review Summary} & Implementación de los segmentos de investigación (Cap 1 y 2), Requirements Specification y primer Sprint de implementación \\ \hline
\textbf{Sprint 1 Retrospective Summary} & El trabajo se realizó a tiempo, y cada integrante terminó lo que se le encomendó. Asimismo, se trabajó en equipo cuando la situación del proyecto lo requería. \\ \hline
\textbf{Sprint Goal \& User Stories} & Implementar la landing page, avanzar una parte del backend de la aplicación y definir las tecnologías a emplear \\ \hline
\textbf{Sprint 1 Velocity} & 1 Sprint cada 2 semanas \\ \hline
\textbf{Sum of Story Points} & 93 \\ \hline
\end{longtable}

\newpage

#### Aspect Leaders and Collaborators.

\begin{longtable}{|p{5cm}|p{9cm}|}
\hline
\textbf{Aspect} & \textbf{Leader and Collaborators} \\ \hline
\endfirsthead

\hline
\textit{Project Coordination and Sprint Management} & \textbf{Leader:} Ortega Huaraca, Abel Angel \\
& \textbf{Collaborator(s):} Vilchez Rios, Mateo Alejandro / Avila Asto, Alex Ramon / Ramos Rios, Belen del Rocio \\ \hline

\textit{Frontend Development (Landing Page)} & \textbf{Leader:} Ortega Huaraca, Abel Angel \\
& \textbf{Collaborator(s):} Vilchez Rios, Mateo Alejandro / Avila Asto, Alex Ramon / Ramos Rios, Belen del Rocio \\ \hline

\textit{Backend Development (Initial Setup)} & \textbf{Leader:} Ortega Huaraca, Abel Angel \\
& \textbf{Collaborator(s):} Vilchez Rios, Mateo Alejandro / Avila Asto, Alex Ramon / Ramos Rios, Belen del Rocio \\ \hline

\textit{Technology Stack Definition} & \textbf{Leader:} Ortega Huaraca, Abel Angel \\
& \textbf{Collaborator(s):} Vilchez Rios, Mateo Alejandro / Avila Asto, Alex Ramon / Ramos Rios, Belen del Rocio \\ \hline

\textit{Requirements Specification and Documentation} & \textbf{Leader:} Ortega Huaraca, Abel Angel \\
& \textbf{Collaborator(s):} Vilchez Rios, Mateo Alejandro / Avila Asto, Alex Ramon / Ramos Rios, Belen del Rocio \\ \hline

\textit{Quality Review and Integration} & \textbf{Leader:} Ortega Huaraca, Abel Angel \\
& \textbf{Collaborator(s):} Vilchez Rios, Mateo Alejandro / Avila Asto, Alex Ramon / Ramos Rios, Belen del Rocio \\ \hline

\end{longtable}

\newpage

#### Sprint Backlog 1

En este primer sprint, se estableció como prioridad el desarrollo de funcionalidades clave relacionadas con la landing page, el backend, la aplicacion web y la aplicación móvil de *RutaKids*. Estas tareas se organizaron en función de User Stories (Historias de Usuario) que representan los requisitos fundamentales para entregar una experiencia de usuario sólida y funcional.

En la siguiente tabla se detalla los elementos de trabajo (Work Items) asignados a cada Historia de Usuario, así como el esfuerzo estimado en horas, los responsables y el estado de progreso de cada tarea. El enfoque de este sprint ha sido garantizar que tanto la landing page como el backend y las funcionalidades de la aplicación móvil estén bien estructurados y listos para futuras integraciones.

\begin{longtable}{|c|p{2.5cm}|p{1cm}|p{4cm}|p{2cm}|p{2cm}|p{1cm}|}
\hline
\textbf{ID} & \textbf{User Story} & \textbf{Work Item (WI)} & \textbf{Description} & \textbf{Estimation (Hours)} & \textbf{Assigned To} & \textbf{Status} \\ \hline
\multirow{3}{*}{US38} & \multirow{3}{*}{\parbox[t]{2.5cm}{Descubrimiento intuitivo \vspace{0.5cm}}} & WI01 & Diseño de la estructura HTML y navegación principal para facilitar el descubrimiento intuitivo en la landing page & 6h & Belén Ramos & Done \\ \cline{3-7} 
 &  & WI02 & Implementación de los elementos de navegación y estructura responsive & 4h & Belén Ramos & Done \\ \cline{3-7} 
 &  & WI03 & Pruebas de usabilidad para navegación y descubrimiento & 2h & Mateo Vílchez & Done \\ \hline
\multirow{2}{*}{US39} & \multirow{2}{*}{\parbox[t]{2.5cm}{Contenido informativo \vspace{0.5cm}}} & WI04 & Redacción de todo el contenido informativo para la landing page & 3h & Belén Ramos & Done \\ \cline{3-7} 
 &  & WI05 & Implementación del contenido en la landing page & 2h & Belén Ramos & Done \\ \hline
\multirow{2}{*}{US40} & \multirow{2}{*}{\parbox[t]{2.5cm}{Compatibilidad móvil \vspace{0.5cm}}} & WI06 & Desarrollo del diseño responsive para dispositivos móviles & 4h & Belén Ramos & Done \\ \cline{3-7} 
 &  & WI07 & Pruebas de responsividad en diferentes resoluciones & 3h & Belén Ramos & Done \\ \hline
\multirow{2}{*}{US41} & \multirow{2}{*}{\parbox[t]{2.5cm}{Formulario de contacto \vspace{0.5cm}}} & WI08 & Diseño e implementación del formulario de contacto & 5h & Belén Ramos & Done \\ \cline{3-7} 
 &  & WI09 & Validación de formulario de contacto & 2h & Mateo Vílchez & Done \\ \hline
\multirow{2}{*}{US42} & \multirow{2}{*}{\parbox[t]{2.5cm}{Contenido multimedia \vspace{0.5cm}}} & WI10 & Integración de imágenes, íconos y secciones visuales multimedia & 3h & Belén Ramos & Done \\ \cline{3-7} 
 &  & WI11 & Optimización de recursos multimedia para tiempos de carga más rápidos & 2h & Mateo Vílchez & Done \\ \hline
US43 & \parbox[t]{2.5cm}{Call-to-action claro \vspace{0.5cm}} & WI12 & Diseño y optimización de los botones de call-to-action (CTA) en la landing page & 3h & Mateo Vílchez & Done \\ \hline
\multirow{3}{*}{US32} & \multirow{3}{*}{\parbox[t]{2.5cm}{RESTful API Registro de usuario \vspace{0.5cm}}} & WI13 & Implementación de la API para el registro de usuario & 6h & Alex Avila & Done \\ \cline{3-7} 
 &  & WI14 & Añadir index para role seed en persistencia & 3h & Alex Avila & Done \\ \cline{3-7} 
 &  & WI15 & Middleware para manejo de excepciones & 4h & Alex Avila & Done \\ \hline
\multirow{2}{*}{US33} & \multirow{2}{*}{\parbox[t]{2.5cm}{RESTful API Inicio de sesión de usuario \vspace{0.5cm}}} & WI16 & Implementación de la API para inicio de sesión & 5h & Alex Avila & Done \\ \cline{3-7} 
 &  & WI17 & Implementación de pipeline de seguridad & 5h & Alex Avila & Done \\ \hline
\multirow{2}{*}{US34} & \multirow{2}{*}{\parbox[t]{2.5cm}{Autenticación basada en token JWT \vspace{0.5cm}}} & WI18 & Implementación de autenticación JWT en backend & 6h & Alex Avila & Done \\ \cline{3-7} 
 &  & WI19 & Configuración inicial de OpenAPI & 5h & Alex Avila & Done \\ \hline
US35 & \parbox[t]{2.5cm}{Recuperación de contraseña \vspace{0.5cm}} & WI20 & Implementación de perfiles en Spring Boot & 4h & Alex Avila & Done \\ \hline
\multirow{3}{*}{US36} & \multirow{3}{*}{\parbox[t]{2.5cm}{RESTful API Creación de sesiones \vspace{0.5cm}}} & WI21 & Implementación de la API para la creación de sesiones & 4h & Alex Avila & Done \\ \cline{3-7} 
 &  & WI22 & Creación de Dockerfile para build y compose & 5h & Alex Avila & Done \\ \cline{3-7} 
 &  & WI23 & Creación de Dockerfile para entorno de desarrollo & 4h & Alex Avila & Done \\ \hline
US37 & \parbox[t]{2.5cm}{Paginación y filtrado de resultados \vspace{0.5cm}} & WI24 & Implementación de la paginación y filtrado & 5h & Alex Avila & In-Process \\ \hline
\multirow{2}{*}{US01} & \multirow{2}{*}{\parbox[t]{2.5cm}{Registro de usuario \vspace{0.5cm}}} & WI025 & Diseño del mockup de la pantalla de registro de usuario & 4h & Abel Ortega & Done \\ \cline{3-7} 
 &  & WI26 & Implementación de la funcionalidad de registro en la app & 6h & Abel Ortega & In Process \\ \hline
\multirow{2}{*}{US02} & \multirow{2}{*}{\parbox[t]{2.5cm}{Confirmación de creación de cuenta \vspace{0.5cm}}} & WI27 & Diseño del correo de confirmación (mockup) & 3h & Abel Ortega & Done \\ \cline{3-7} 
 &  & WI28 & Implementación del inicio de sesión con Google y Facebook & 3h & Abel Ortega & In Process \\ \hline
\multirow{2}{*}{US03} & \multirow{2}{*}{\parbox[t]{2.5cm}{Historial de viajes \vspace{0.5cm}}} & WI29 & Diseño del mockup de la interfaz de historial de viajes & 3h & Abel Ortega & Done \\ \cline{3-7} 
 &  & WI30 & Implementación de la visualización del historial de viajes & 6h & Abel Ortega & To Do \\ \hline
US04 & \parbox[t]{2.5cm}{Eliminación de cuenta \vspace{0.5cm}} & WI31 & Diseño del mockup de la pantalla de eliminación de cuenta & 2h & Abel Ortega & Done \\ \hline
\multirow{2}{*}{US08} & \multirow{2}{*}{\parbox[t]{2.5cm}{Personalización del dominio de correo \vspace{0.5cm}}} & WI32 & Diseño del mockup para personalización del correo & 3h & Abel Ortega & Done \\ \cline{3-7} 
 &  & WI33 & Implementar la funcionalidad de personalización de correos & 5h & Abel Ortega & To-Do \\ \hline
US10 & \parbox[t]{2.5cm}{Redireccionar con el correo del conductor \vspace{0.5cm}} & WI34 & Diseño del mockup de la función redireccionar al correo & 3h & Abel Ortega & Done \\ \hline
\end{longtable}

\newpage

**Gestión de los Sprint (Tablero Kanban):**

Para mejorar la gestión y seguimiento de las tareas de este sprint, se implementó un tablero Kanban.
Este tablero permite visualizar claramente los elementos clave a desarrollar, asignar responsables
para cada tarea, y utilizar etiquetas (labels) que categorizan los Issues de forma precisa. Además, los
Milestones fueron utilizados estratégicamente para planificar las fechas de entrega y gestionar los
entregables, facilitando un control eficiente del progreso del proyecto.

![Imagen extraída de Canva](src/img/cap6/gestion-sprints-kanban.png)

\newpage

#### Development Evidence for Sprint Review.

Evidencia de colaboración en Equipo:

![Imagen extraída de Github](src/img/cap6/insights-kanban-list-1.png){ height=35% }

![Imagen extraída de Github](src/img/cap6/evidence-sprint-tp1.png){ height=35% }

\newpage

#### Testing Suite Evidence for Sprint Review.

***Landing Page US - Gherkin***

```gherkin
US38 - Descubrimiento intuitivo

Feature: Descubrimiento intuitivo
  As a user
  I want to easily discover the main sections of the landing page
  So that I can navigate it intuitively

  Scenario: Successful navigation on landing page
    Given the user is on the landing page
    When they interact with the main navigation bar
    Then they should see links to the main sections of the website
    And the navigation should work smoothly
    
    Examples:
      | User action     | Expected result         |
      | Click "Home"    | Navigates to homepage   |
      | Click "Features"| Navigates to features   |
      | Click "About"   | Navigates to about page |

  Scenario: Responsive design adapts to screen size
    Given the user is accessing the landing page from a mobile device
    When they view the page
    Then the layout should adjust to fit the screen size appropriately
    And all sections should be accessible

    Examples:
      | Device      | Expected behavior                              |
      | Smartphone  | Layout adjusts, elements stack vertically      |
      | Tablet      | Layout adjusts, elements fit wider screen      |
```

```gherkin

US39 - Contenido informativo

Feature: Contenido informativo
  As a visitor
  I want to find clear and informative content on the landing page
  So that I can learn more about the application's features

  Scenario: Display clear content on application features
    Given the user is on the landing page
    When they scroll down to the information section
    Then they should see a clear explanation of the application's main features
    And the text should be easy to read and understand
    
    Examples:
      | Section        | Content                                             |
      | Features       | Explanation of core app functionalities             |
      | Benefits       | Description of the advantages for users             |
      | Testimonials   | Positive feedback from current users                |

  Scenario: Ensure content is displayed correctly across devices
    Given the user is on the landing page on a mobile device
    When they scroll through the information section
    Then the content should remain responsive and clear
    And images should load correctly
    
    Examples:
      | Device        | Expected result                            |
      | Mobile        | Text adjusts, images scale down            |
      | Desktop       | Text and images adjust to full-screen size |

```

```gherkin

US40 - Compatibilidad móvil

Feature: Compatibilidad móvil
  As a visitor
  I want to browse the landing page on my mobile device
  So that I can easily access it from any device

  Scenario: Responsive design for mobile devices
    Given the user accesses the landing page on a smartphone
    When they scroll through the content
    Then the page should display correctly without layout issues
    And images should be scaled appropriately

    Examples:
      | Device      | Expected behavior                                   |
      | iPhone 12   | Responsive, no text overlaps, easy to navigate      |
      | Galaxy S21  | All buttons are accessible, images fit screen size  |

  Scenario: Test page responsiveness for tablets and desktops
    Given the user accesses the page on a tablet or desktop
    When they resize the browser window
    Then the layout and content should adjust fluidly without breaking

    Examples:
      | Device      | Expected behavior                                   |
      | iPad        | Two-column layout, images scale appropriately       |
      | Desktop     | Three-column layout, full image resolution          |

```

```gherkin

US41 - Formulario de contacto

Feature: Formulario de contacto
  As a visitor
  I want to fill out the contact form on the landing page
  So that I can get in touch with the application team

  Scenario: Successful form submission
    Given the user is on the contact form page
    When they fill in all required fields and submit the form
    Then the system should display a confirmation message that the form has been successfully submitted
    And the submitted details should be sent to the application team

    Examples:
      | Name        | Email              | Message                 | Status        |
      | John Doe    | john@example.com   | Inquiry about services  | Submitted     |
      | Jane Smith  | jane@example.com   | Question about pricing  | Submitted     |

  Scenario: Missing required fields
    Given the user is filling out the contact form
    When they leave required fields empty
    Then the system should display an error message asking them to complete the missing fields
    
    Examples:
      | Name        | Email              | Message                 | Error message           |
      | John Doe    |                    | Inquiry about services  | "Email is required"     |
      |             | jane@example.com   |                         | "Name is required"      |

```

```gherkin

US42 - Contenido multimedia

Feature: Contenido multimedia
  As a visitor
  I want to find multimedia content on the landing page
  So that I can learn about the app features in a dynamic way

  Scenario: Display multimedia content successfully
    Given the user is on the landing page
    When they scroll through the multimedia section
    Then they should see images, videos, and icons that explain the app's functionality
    And the multimedia content should load quickly and properly

    Examples:
      | Media Type | Expected Behavior                              |
      | Images     | Display correctly, optimized for loading speed |
      | Videos     | Play smoothly, no buffering                    |
      | Icons      | Scale appropriately without distortion         |

  Scenario: Ensure multimedia content is responsive across devices
    Given the user accesses the landing page from different devices
    When they view the multimedia section
    Then the multimedia content should adjust to fit the screen size and resolution without losing quality

    Examples:
      | Device       | Expected Behavior                                   |
      | Mobile       | Images and videos scale down, responsive layout     |
      | Tablet       | Images and videos adapt to a medium screen layout   |
      | Desktop      | Full resolution, multimedia fills the space         |

```

```gherkin

US43 - Call-to-action claro

Feature: Call-to-action claro
  As a visitor
  I want to find clear call-to-action (CTA) buttons on the landing page
  So that I can take immediate action (e.g., request a demo)

  Scenario: Clear CTA buttons guide user actions
    Given the user is on the landing page
    When they see the "Request Demo" or "Sign Up" buttons
    Then the buttons should be visually prominent and lead to the correct sections of the website

    Examples:
      | CTA Text      | Expected Behavior                            |
      | Request Demo  | Redirects user to contact form               |
      | Sign Up       | Redirects user to registration page          |

  Scenario: CTA buttons work across devices
    Given the user accesses the landing page from different devices
    When they interact with CTA buttons
    Then the buttons should be responsive and work correctly on all screen sizes

    Examples:
      | Device       | Expected Behavior                            |
      | Mobile       | Buttons are visible and clickable             |
      | Tablet       | Buttons scale correctly, remain interactive   |
      | Desktop      | Full-size buttons, clear, and functional      |

```

***Backend US - Gherkin***

```gherkin

US32 - RESTful API Registro de usuario

Feature: Registro de usuario a través de la API RESTful
  As a developer
  I want to implement an API for user registration
  So that users can create an account in the application

  Scenario: Successful user registration
    Given the user has provided a valid email and password
    When the user submits a POST request to "/api/v1/users"
    Then the system should create a new user
    And respond with status 201 and user information

  Scenario: Failed registration due to duplicate email
    Given a user already exists with the provided email
    When the user submits a POST request to "/api/v1/users"
    Then the system should respond with status 400
    And return a message indicating email is already in use

Examples:
  | email             | password    |
  | existing@example.com | password123 |
  | newuser@example.com  | password456 |

```

```gherkin

US33 - RESTful API Inicio de sesión de usuario

Feature: User login through RESTful API
  As a developer
  I want to implement a login API
  So that users can securely log in to their accounts

  Scenario: Successful login
    Given the user exists with valid credentials
    When the user submits a POST request to "/api/v1/login"
    Then the system should authenticate the user
    And respond with status 200 and a JWT token

  Scenario: Failed login due to incorrect password
    Given the user exists with an incorrect password
    When the user submits a POST request to "/api/v1/login"
    Then the system should respond with status 401
    And return a message indicating invalid credentials

Examples:
  | email             | password    |
  | user@example.com  | correctpass |
  | user@example.com  | wrongpass   |

```

```gherkin

US34 - Autenticación basada en token JWT

Feature: JWT-based authentication for the API
  As a developer
  I want to implement JWT authentication
  So that I can secure API endpoints

  Scenario: Successful authentication with JWT
    Given the user is logged in with a valid JWT token
    When the user requests a protected resource "/api/v1/protected"
    Then the system should respond with status 200 and the resource

  Scenario: Failed authentication due to expired token
    Given the user has an expired JWT token
    When the user requests a protected resource "/api/v1/protected"
    Then the system should respond with status 401 and a message "Token expired"

Examples:
  | token_status | response |
  | valid        | 200      |
  | expired      | 401      |

```

```gherkin

US35 - Recuperación de contraseña

Feature: Password recovery via RESTful API
  As a developer
  I want to implement a password recovery API
  So that users can reset their forgotten passwords

  Scenario: Successful password recovery request
    Given the user has provided a valid email
    When the user submits a POST request to "/api/v1/password-recovery"
    Then the system should send a password reset link to the email
    And respond with status 200

  Scenario: Failed password recovery due to invalid email
    Given the user has provided an invalid email
    When the user submits a POST request to "/api/v1/password-recovery"
    Then the system should respond with status 404 and a message "User not found"

Examples:
  | email              |
  | valid@example.com  |
  | invalid@example.com|

```

```gherkin

US36 - RESTful API Creación de sesiones

Feature: Session creation through RESTful API
  As a developer
  I want to implement an API for session management
  So that users can create multiple sessions

  Scenario: Successful session creation
    Given the user has valid credentials
    When the user submits a POST request to "/api/v1/sessions"
    Then the system should create a new session
    And respond with status 201 and session details

  Scenario: Failed session creation due to missing data
    Given the user has not provided all necessary data
    When the user submits a POST request to "/api/v1/sessions"
    Then the system should respond with status 400 and an error message

Examples:
  | email              | session_id |
  | user@example.com    | session123 |
  | incomplete@example.com | N/A     |

```

```gherkin

US37 - Paginación y filtrado de resultados

Feature: Pagination and filtering of API results
  As a developer
  I want to implement pagination and filtering on the API
  So that users can retrieve data efficiently

  Scenario: Retrieve paginated results
    Given there are more than 10 users in the system
    When the user requests page 2 with 10 results per page
    Then the system should return 10 users from page 2
    And respond with status 200

  Scenario: Retrieve filtered results by role
    Given there are users with different roles
    When the user requests a filtered list of users by role "admin"
    Then the system should return only users with the "admin" role

Examples:
  | page | results_per_page | role   |
  | 2    | 10               | admin |
  | 1    | 5                | user  |

```

***Frontend US - Gherking***

```gherkin

US01 - Registro de usuario

Feature: Registro de usuario en la aplicación
  As a user
  I want to register by providing my email and password
  So that I can create an account in the application

  Scenario: Successful user registration
    Given the user has entered a valid email and password
    When the user submits the registration form
    Then the system should create a new user account
    And send a confirmation email to the user

  Scenario: Failed registration due to missing information
    Given the user has not entered an email or password
    When the user submits the registration form
    Then the system should display an error message "Email and password are required"

Examples:
  | email             | password    |
  | newuser1@example.com | pass12345 |
  |                   | pass12345   |

```

```gherkin

US02 - Confirmación de creación de cuenta

Feature: Confirmación de creación de cuenta
  As a user
  I want to receive a confirmation email after registering
  So that I know my account has been created

  Scenario: Successful confirmation email sent
    Given the user has registered successfully
    When the system sends a confirmation email
    Then the user should receive the email in their inbox
    And the email should contain a link to verify the account

  Scenario: Failed to send confirmation email
    Given the system is experiencing technical issues
    When the system tries to send the confirmation email
    Then the system should log an error
    And notify the user that the confirmation email could not be sent

Examples:
  | email             |
  | user@example.com  |
  | another@example.com |

```

```gherkin

US03 - Verificación de cuenta

Feature: Verificación de cuenta mediante correo electrónico
  As a user
  I want to verify my account using the link sent to my email
  So that I can activate my account

  Scenario: Successful account verification
    Given the user has received the confirmation email
    When the user clicks on the verification link
    Then the system should mark the account as verified
    And the user should be redirected to the login page

  Scenario: Failed verification due to invalid link
    Given the user has clicked on an expired or invalid verification link
    When the user tries to verify their account
    Then the system should display an error message "Verification link is invalid or expired"

Examples:
  | verification_status |
  | valid               |
  | invalid             |

```

```gherkin

US04 - Inicio de sesión de cuenta

Feature: Inicio de sesión de usuario
  As a user
  I want to log in using my email and password
  So that I can access my account

  Scenario: Successful login
    Given the user has entered the correct email and password
    When the user submits the login form
    Then the system should log the user in
    And redirect the user to the dashboard

  Scenario: Failed login due to incorrect password
    Given the user has entered an incorrect password
    When the user submits the login form
    Then the system should display an error message "Incorrect password"

Examples:
  | email             | password    |
  | user1@example.com | correctpass |
  | user1@example.com | wrongpass   |

```

```gherkin

US05 - Generación de correo temporal con un click

Feature: Generación de correo temporal
  As a user
  I want to generate a temporary email with one click
  So that I can use it for quick registrations on other websites

  Scenario: Generate temporary email successfully
    Given the user is on the temporary email generation page
    When the user clicks the "Generate Email" button
    Then the system should create a temporary email
    And display the email address to the user

Examples:
  | email               |
  | temp1@example.com   |
  | temp2@example.com   |

```

```gherkin

US06 - Duración específica del correo temporal

Feature: Especificar la duración de correos temporales  

  As a user  
  I want to specify the duration of my temporary email  
  So that the email expires after a set period 

  Scenario: Set a custom expiration time    
  Given the user is creating a temporary email    
  When the user selects a duration of 30 minutes    
  Then the system should set the expiration time to 30 minutes.

  Examples:  
  | duration | 
  | 10 min   |  
  | 30 min   |

```

```gherkin

Feature: Confirmación visual de creación de correo temporal

  As a user
  I want a visual confirmation when my temporary email is created
  So that I know the email is ready to use

  Scenario: Show visual confirmation after email creation
    Given the user has generated a temporary email
    When the email is created
    Then the system should display a confirmation message "Email created successfully"

  Examples:
  | confirmation_status |
  | success             |

```

```gherkin

US08 - Personalización del dominio del correo temporal

Feature: Personalización del dominio del correo temporal

  As a user
  I want to customize the domain of my temporary email
  So that I can choose from different domain options

  Scenario: User selects a custom domain for temporary email
    Given the user is creating a temporary email
    When the user selects a domain from the dropdown
    Then the system should generate the email with the chosen domain

  Examples:
  | domain        |
  | @tempmail.com |
  | @quickmail.io |

```

```gherkin

US09 - Generación múltiple de correos temporales

Feature: Generación múltiple de correos temporales
  As a user
  I want to generate multiple temporary emails in one session
  So that I can use different emails for various registrations

  Scenario: Generate multiple temporary emails
    Given the user is on the email generation page
    When the user requests 3 temporary emails
    Then the system should create and display 3 unique temporary emails

Examples:
  | email_count |
  | 3           |
  | 5           |

```

```gherkin

US10 - Copiar correo temporal al portapapeles

Feature: Copiar correo temporal al portapapeles
  As a user
  I want to copy my generated temporary email to the clipboard
  So that I can paste it easily on other websites

  Scenario: Copy email to clipboard
    Given the user has generated a temporary email
    When the user clicks the "Copy" button
    Then the system should copy the email to the clipboard
    And display a message "Email copied to clipboard"

Examples:
  | email               |
  | temp1@example.com   |
  | temp2@example.com   |

```

```gherkin

US11 - Visualización de correos temporales activos

Feature: Visualización de correos temporales activos
  As a user
  I want to see all my active temporary emails
  So that I can manage them effectively

  Scenario: Display list of active temporary emails
    Given the user has generated multiple temporary emails
    When the user navigates to the active emails page
    Then the system should display a list of active emails

Examples:
  | email_count |
  | 2           |
  | 5           |

```

```gherkin

US12 - Sugerencias automáticas de nombres para correos

Feature: Sugerencias automáticas de nombres para correos temporales
  As a user
  I want the system to suggest email names automatically
  So that I can quickly choose a temporary email name

  Scenario: System provides email name suggestions
    Given the user is generating a temporary email
    When the user clicks on the suggestion box
    Then the system should display a list of suggested email names

Examples:
  | suggestion_count |
  | 3                |
  | 5                |

```

```gherkin

US13 - Proceso de generación rápido y fluido

Feature: Proceso de generación rápido y fluido
  As a user
  I want the temporary email generation process to be fast and smooth
  So that I can generate emails without delays

  Scenario: Generate temporary email in less than 5 seconds
    Given the user is on the temporary email page
    When the user clicks "Generate Email"
    Then the system should create the email within 5 seconds

Examples:
  | generation_time |
  | 3 seconds       |
  | 4.5 seconds     |

```

```gherkin

US14 - Advertencia de expiración de correo temporal

Feature: Advertencia de expiración de correo temporal
  As a user
  I want to be notified when my temporary email is about to expire
  So that I can take necessary actions before it expires

  Scenario: Notify user before email expiration
    Given the user has an active temporary email
    When the email is 5 minutes away from expiration
    Then the system should display a warning message "Email is about to expire"

Examples:
  | warning_time |
  | 5 minutes    |
  | 10 minutes   |

```

```gherkin

US15 - Acceso a bandeja de entrada de correos temporales

Feature: Acceso a bandeja de entrada de correos temporales
  As a user
  I want to access a specific inbox for my temporary emails
  So that I can view and manage the emails received without mixing them with my personal emails

  Scenario: User accesses the inbox for temporary emails
    Given the user has generated one or more temporary emails
    When the user navigates to the "Temporary Inbox" section
    Then the system should display a list of received temporary emails in the inbox

  Scenario: No temporary emails in the inbox
    Given the user has not generated or received any temporary emails
    When the user navigates to the "Temporary Inbox" section
    Then the system should display a message "No emails received"

  Scenario: User opens a specific email from the inbox
    Given the user has received temporary emails
    When the user selects a specific email from the list
    Then the system should display the full content of the selected email

Examples:
  | email_count | email_subject           | sender                | received_date |
  | 5           | "Welcome to TempMail"   | welcome@tempmail.com  | 2024-09-10    |
  | 0           |                         |                       |               |
  | 3           | "Verify your account"   | no-reply@webservice.io| 2024-09-09    |

```

```gherkin

US16 - Visualización de correos recibidos

Feature: Visualización de correos recibidos en la bandeja de entrada
  As a user
  I want to view a list of emails I have received in my temporary inbox
  So that I can manage important messages

  Scenario: Display list of received emails
    Given the user has received emails in the temporary inbox
    When the user opens the inbox
    Then the system should show a list of received emails with subject, sender, and date

  Scenario: View details of a received email
    Given the user is viewing the list of received emails
    When the user selects a specific email
    Then the system should display the full content of the selected email

Examples:
  | email_subject           | sender           | date         |
  | "Welcome"               | welcome@site.com | 2024-09-10   |
  | "Confirm your account"  | no-reply@site.io | 2024-09-11   |

```

\newpage

#### Execution Evidence for Sprint Review.

::: box
**Implemented Landing Page Evidence**
:::

::: warn
Para acceder al repositorio de este proyecto, haga click a la [URL](https://github.com/orgs/LlantaTech/repositories)
:::

**Captura del repositorio:**

![Organización CodeMinds, imagen extraída de Github](src/img/cap6/landing-deploy-1.png){ width=80% }

**Landing Page en funcionamiento:**

![Organización CodeMinds, imagen extraída de Github](src/img/cap6/landing-deploy-2.png){ width=80% }

\newpage

::: box
**Implemented Frontend-Web Application Evidence**
:::

::: warn
Para acceder al repositorio de este proyecto, haga click a la [URL](https://github.com/orgs/LlantaTech/repositories)
:::

**Captura del repositorio:**

![Organización CodeMinds, imagen extraída de Github](src/img/cap6/webapp-deploy-1.png){ width=80% }

**Web Application en funcionamiento:**

![Organización CodeMinds, imagen extraída de Github](src/img/cap6/webapp-deploy-2.jpg){ width=80% }

\newpage

::: box
**Implemented Native-Mobile Application Evidence**
:::

::: warn
Para acceder al repositorio de este proyecto, haga click a la [URL](https://www.figma.com/design/ph6aTjM4mzxkNic0Hk4VLX/RutaKids?node-id=275-3006&t=aZ58NPtaowKWvMte-1)
:::

**Captura del figma:**

![Organización CodeMinds, imagen extraída de Figma](src/img/cap6/mobile-app-figma.png){ width=80% }

**Mobile Application en mockup:**

![Organización CodeMinds, imagen extraída de Figma](src/img/cap6/mobile-app-figma-view.png){ width=50% }

\newpage

::: box
**Implemented RESTful API and/or Serverless Backend Evidence**
:::

::: warn
Para acceder al repositorio de este proyecto, haga click a la [URL](https://github.com/LlantaTech/ruta-kids-microservicios)
:::

**Captura del repositorio:**

![Organización CodeMinds, imagen extraída de Github](src/img/cap6/webservices-deploy-1.png){ width=80% }

**Web Service Application en funcionamiento:**

![Organización CodeMinds, imagen extraída de Github](src/img/cap6/webservices-deploy-2.jpg){ width=80% }

\newpage

### RESTful API documentation

::: warn
Para acceder al repositorio de este proyecto, haga click a la [URL](https://github.com/LlantaTech/ruta-kids-microservicios)
:::

**Captura del repositorio:**

![Organización CodeMinds, imagen extraída de Github](src/img/cap6/webservices-doc.png)

\newpage

#### Services Documentation Evidence for Sprint Review.


En esta seccion, se muestra la documentacion de los servicios del back end de la aplicación móvil, asi como tambien se muestra el uso de Swagger para la documentacion de los servicios.

Utilizamos *SpringBoot*, *Spring Security*, *Spring Mongo*, *Spring Oauthclient*, *JWToken* y *Spring Data*

::: warn
**https://docs.spring.io/spring-boot/index.html**
:::

![Imagen extraída de la documentación de Spring](src/img/cap6/documentation1.png)

\newpage

::: warn
**https://docs.spring.io/spring-boot/reference/web/spring-security.html#page-title**
:::

![Imagen extraída de la documentación de Spring](src/img/cap6/documentation2.png)

::: warn
**https://www.npmjs.com/package/jsonwebtoken**
:::

![Imagen extraída de NPMjs](src/img/cap6/documentation3.png)

\newpage

::: warn
**https://spring.io/projects/spring-data-jpa**
:::

![Imagen extraída de la documentación de Spring](src/img/cap6/documentation4.png)

\newpage

#### Software Deployment Evidence for Sprint Review.

***Landing Page deployment***

![Organización CodeMinds, imagen extraída de Github](src/img/cap6/landing-deploy-2.png){ width=80% }

**Web Application deployment**

![Organización CodeMinds, imagen extraída de Github](src/img/cap6/webapp-deploy-2.jpg){ width=80% }

\newpage

**Web Service Deployment**

![Organización CodeMinds, imagen extraída de Github](src/img/cap6/webservices-deploy-2.jpg){ width=80% }

\newpage

#### Team Collaboration Insights during Sprint.

::: warn
Para acceder los insights de este proyecto, haga click a la [URL](https://github.com/orgs/LlantaTech/repositories)
:::

**Tablero Kanban:**

![Organización CodeMinds, imagen extraída de Github](src/img/cap6/insights-kanban-todo-1.png){ width=80% }

**Kanban List:**

![Organización CodeMinds, imagen extraída de Github](src/img/cap6/insights-kanban-list-1.png){ width=80% }

\newpage

**Network Graph:**

![Organización CodeMinds, imagen extraída de Github](src/img/cap6/insights-network-graph-1.png){ width=80% }

**Traffic Map:**

![Organización CodeMinds, imagen extraída de Github](src/img/cap6/insights-traffic-1.png){ width=80% }

\newpage
