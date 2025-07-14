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

### Source Code Style Guide & Conventions

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

### Software Deployment Configuration

Esta sección describe la configuración de despliegue utilizada para cada componente de la solución digital: Landing Page, Web Services y Aplicacion Web Frontend. A partir del código fuente en los repositorios, se detallan los pasos necesarios para su correcta publicación en entornos de desarrollo y producción.

::: warn
Para acceder al flujo de trabajo, haga click a la [URL](https://github.com/orgs/LlantaTech/repositories)
:::

**Desplegar** ***Landing Page***

* Clone el repositorio: *LLantatech-LandingPage*

![Organización LLantatech, imagen extraída de Github](src/img/cap6/landing-deploy-1.png){ width=80% }

* Abra el proyecto en su IDE de confianza y realice lo siguiente:

    - Instale las dependencias del proyecto web

    - Ejecute el proyecto con npm

![Organización LLantatech, imagen extraída de Github](src/img/cap6/landing-deploy-2.png){ width=80% }

\newpage

**Desplegar** ***Web Application***

* Clone el repositorio: *RutaKids-WebApp*

![Organización LLantatech, imagen extraída de Github](src/img/cap6/webapp-deploy-1.png){ width=80% }

* Abra el proyecto en su IDE de confianza y realice lo siguiente:

    - Instale las dependencias del proyecto web

    - Ejecute el proyecto con ng

![Organización LLantatech, imagen extraída de Github](src/img/cap6/webapp-deploy-2.jpg){ width=80% }

\newpage

**Desplegar** ***Web Services***

* Clone el repositorio: *RutaKids-Micro-Servicios*

![Organización LLantatech, imagen extraída de Github](src/img/cap6/webservices-deploy-1.png){ width=80% }

* Abra el proyecto en su IDE de confianza y realice lo siguiente:

    - Instale las dependencias del proyecto Spring

    - Para pruebas, ejecute cada servicio por separado

![Organización LLantatech, imagen extraída de Github](src/img/cap6/webservices-deploy-2.jpg){ width=80% }

\newpage

## Landing Page, Services & Applications Implementation

El desarrollo de páginas de aterrizaje (landing pages), servicios y aplicaciones implica una planificación estratégica centrada en los objetivos del negocio y las necesidades del usuario final. En este proceso, se diseñan y construyen interfaces visuales atractivas que no solo captan la atención del usuario, sino que también lo guían de forma efectiva hacia una acción deseada, como la adquisición de un producto, la suscripción a un servicio o la solicitud de información.

La implementación de servicios web y funcionalidades de backend permite conectar la interfaz con la lógica del sistema, garantizando una experiencia fluida y coherente en la interacción con la plataforma. Se integran APIs, sistemas de autenticación, bases de datos y mecanismos de seguridad que permiten el funcionamiento eficiente y seguro de las aplicaciones.

Además, se considera la escalabilidad y mantenibilidad del código, aplicando buenas prácticas de desarrollo como la modularidad, el uso de frameworks modernos y la documentación adecuada. Este enfoque integral asegura que tanto la landing page como los servicios asociados respondan con eficacia a los requerimientos técnicos y de negocio, aportando valor real al usuario y mejorando la presencia digital de la organización.

![Recurso extraído de Canva](src/img/cap6/landing-page-services-applications.png)

\newpage

### Sprint 1

El Sprint 1 marca el inicio formal del proceso de desarrollo del proyecto, estableciendo las bases tanto a nivel técnico como organizativo. Durante esta etapa, el equipo se enfocó en la consolidación de los primeros capítulos del informe teórico (Capítulo 1 y 2), así como en la elaboración del documento de especificación de requisitos. Estos elementos resultan fundamentales para alinear al equipo en torno a una visión común del sistema a desarrollar. Asimismo, se definieron los objetivos iniciales de implementación, priorizando el desarrollo de la landing page, el análisis y elección de las tecnologías base (frameworks, herramientas y lenguajes de programación), y el inicio de la estructura del backend. Esta primera iteración permitió establecer una dinámica de trabajo colaborativa, con roles definidos y tareas distribuidas de forma equitativa, asegurando que cada integrante aporte activamente al cumplimiento del Sprint Goal.

#### Sprint Planning 1

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

#### Aspect Leaders and Collaborators

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

#### Development Evidence for Sprint Review

Evidencia de colaboración en Equipo:

![Imagen extraída de Github](src/img/cap6/insights-kanban-list-1.png){ height=35% }

![Imagen extraída de Github](src/img/cap6/evidence-sprint-tp1.png){ height=35% }

\newpage

#### Testing Suite Evidence for Sprint Review

::: info
***Landing Page US - Gherkin***
:::

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

\newpage

::: info
***Backend US - Gherkin***
:::

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

\newpage

::: info
***Frontend US - Gherking***
:::

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

#### Execution Evidence for Sprint Review

::: box
**Implemented Landing Page Evidence**
:::

::: warn
Para acceder al repositorio de este proyecto, haga click a la [URL](https://github.com/orgs/LlantaTech/repositories)
:::

**Captura del repositorio:**

![Organización LLantatech, imagen extraída de Github](src/img/cap6/landing-deploy-1.png){ width=80% }

**Landing Page en funcionamiento:**

![Organización LLantatech, imagen extraída de Github](src/img/cap6/landing-deploy-2.png){ width=80% }

\newpage

::: box
**Implemented Frontend-Web Application Evidence**
:::

::: warn
Para acceder al repositorio de este proyecto, haga click a la [URL](https://github.com/orgs/LlantaTech/repositories)
:::

**Captura del repositorio:**

![Organización LLantatech, imagen extraída de Github](src/img/cap6/webapp-deploy-1.png){ width=80% }

**Web Application en funcionamiento:**

![Organización LLantatech, imagen extraída de Github](src/img/cap6/webapp-deploy-2.jpg){ width=80% }

\newpage

::: box
**Implemented Native-Mobile Application Evidence**
:::

::: warn
Para acceder al repositorio de este proyecto, haga click a la [URL](https://www.figma.com/design/ph6aTjM4mzxkNic0Hk4VLX/RutaKids?node-id=275-3006&t=aZ58NPtaowKWvMte-1)
:::

**Captura del figma:**

![Organización LLantatech, imagen extraída de Figma](src/img/cap6/mobile-app-figma.png){ width=80% }

**Mobile Application en mockup:**

![Organización LLantatech, imagen extraída de Figma](src/img/cap6/mobile-app-figma-view.png){ width=50% }

\newpage

::: box
**Implemented RESTful API and/or Serverless Backend Evidence**
:::

::: warn
Para acceder al repositorio de este proyecto, haga click a la [URL](https://github.com/LlantaTech/ruta-kids-microservicios)
:::

**Captura del repositorio:**

![Organización LLantatech, imagen extraída de Github](src/img/cap6/webservices-deploy-1.png){ width=80% }

**Web Service Application en funcionamiento:**

![Organización LLantatech, imagen extraída de Github](src/img/cap6/webservices-deploy-2.jpg){ width=80% }

\newpage

**RESTful API documentation**

::: warn
Para acceder al repositorio de este proyecto, haga click a la [URL](https://github.com/LlantaTech/ruta-kids-microservicios)
:::

**Captura del repositorio:**

![Organización LLantatech, imagen extraída de Github](src/img/cap6/webservices-doc.png)

\newpage

#### Services Documentation Evidence for Sprint Review


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

#### Software Deployment Evidence for Sprint Review

***Landing Page deployment***

![Organización LLantatech, imagen extraída de Github](src/img/cap6/landing-deploy-2.png){ width=80% }

**Web Application deployment**

![Organización LLantatech, imagen extraída de Github](src/img/cap6/webapp-deploy-2.jpg){ width=80% }

\newpage

**Web Service Deployment**

![Organización LLantatech, imagen extraída de Github](src/img/cap6/webservices-deploy-2.jpg){ width=80% }

\newpage

#### Team Collaboration Insights during Sprint

::: warn
Para acceder los insights de este proyecto, haga click a la [URL](https://github.com/orgs/LlantaTech/repositories)
:::

**Tablero Kanban:**

![Organización LLantatech, imagen extraída de Github](src/img/cap6/insights-kanban-todo-1.png){ width=80% }

**Kanban List:**

![Organización LLantatech, imagen extraída de Github](src/img/cap6/insights-kanban-list-1.png){ width=80% }

\newpage

**Network Graph:**

![Organización LLantatech, imagen extraída de Github](src/img/cap6/insights-network-graph-1.png){ width=80% }

**Traffic Map:**

![Organización LLantatech, imagen extraída de Github](src/img/cap6/insights-traffic-1.png){ width=80% }

\newpage

### Sprint 2

El Sprint 2 representa una etapa clave en el desarrollo del proyecto, centrada en la implementación de los componentes funcionales del sistema. Durante esta iteración, el equipo orientó sus esfuerzos hacia el desarrollo de la aplicación web, la aplicación móvil y la arquitectura basada en microservicios. Estas actividades están directamente relacionadas con los capítulos 4 y 5 del informe, los cuales abordan el diseño y la implementación del sistema propuesto.

Se avanzó significativamente en la construcción de interfaces interactivas y responsivas para ambas plataformas (web y mobile), asegurando la coherencia visual y funcional entre ellas. Paralelamente, se diseñaron e implementaron microservicios que permiten una mayor escalabilidad, mantenibilidad y separación de responsabilidades dentro del sistema. Este enfoque permitió establecer una base técnica sólida que facilitará futuras integraciones y pruebas. 

#### Sprint Planning 2

\begin{longtable}{|p{5cm}|p{9cm}|}
\hline
\textbf{Sprint Planning Background} & \\ \hline
\endfirsthead
\hline
\textbf{Sprint} & \textbf{Sprint 2} \\ \hline
\endfoot
\hline
\textbf{Date} & 15/06/2025 \\ \hline
\textbf{Time} & 21:00 \\ \hline
\textbf{Location} & Discord Virtual Meeting \\ \hline
\textbf{Prepared By} & Ortega Huaraca, Abel Angel \\ \hline
\textbf{Attendees (to planning meeting)} & Ortega Huaraca, Abel Angel / Avila Asto, Alex Ramon / Vilchez Rios, Mateo Alejandro / Ramos Rios, Belen del Rocio \\ \hline
\textbf{Sprint 2 Review Summary} & Se desarrollaron los primeros componentes funcionales de la aplicación web y móvil, además de los microservicios base. Todo en línea con los capítulos 4 y 5 del informe. \\ \hline
\textbf{Sprint 2 Retrospective Summary} & Se logró cumplir con los entregables planificados. La colaboración entre los integrantes fue constante y se mantuvo una buena organización del trabajo. \\ \hline
\textbf{Sprint Goal \& User Stories} & Desarrollar la aplicación web y mobile, e implementar microservicios base. Todo ello conforme al diseño propuesto en los capítulos 4 y 5 del informe. \\ \hline
\textbf{Sprint 2 Velocity} & 1 Sprint cada 2 semanas \\ \hline
\textbf{Sum of Story Points} & 120 \\ \hline
\end{longtable}


\newpage

#### Aspect Leaders and Collaborators

\begin{longtable}{|p{5cm}|p{9cm}|}
\hline
\textbf{Aspect} & \textbf{Leader and Collaborators} \\ \hline
\endfirsthead

\hline
\textit{Project Coordination and Sprint Management} & \textbf{Leader:} Ortega Huaraca, Abel Angel \\
& \textbf{Collaborator(s):} Vilchez Rios, Mateo Alejandro / Avila Asto, Alex Ramon / Ramos Rios, Belen del Rocio \\ \hline

\textit{Frontend Development (Landing Page)} & \textbf{Leader:} Ortega Huaraca, Abel Angel \\
& \textbf{Collaborator(s):} Vilchez Rios, Mateo Alejandro / Avila Asto, Alex Ramon / Ramos Rios, Belen del Rocio \\ \hline

\textit{Web Application Development} & \textbf{Leader:} Ortega Huaraca, Abel Angel \\
& \textbf{Collaborator(s):} Vilchez Rios, Mateo Alejandro / Avila Asto, Alex Ramon \\ \hline

\textit{Mobile Application Development} & \textbf{Leader:} Avila Asto, Alex Ramon \\
& \textbf{Collaborator(s):} Ortega Huaraca, Abel Angel / Ramos Rios, Belen del Rocio \\ \hline

\textit{Microservices Architecture} & \textbf{Leader:} Vilchez Rios, Mateo Alejandro \\
& \textbf{Collaborator(s):} Ortega Huaraca, Abel Angel / Avila Asto, Alex Ramon \\ \hline

\textit{Technology Stack Definition} & \textbf{Leader:} Ortega Huaraca, Abel Angel \\
& \textbf{Collaborator(s):} Vilchez Rios, Mateo Alejandro / Avila Asto, Alex Ramon / Ramos Rios, Belen del Rocio \\ \hline

\textit{Requirements Specification and Documentation} & \textbf{Leader:} Ortega Huaraca, Abel Angel \\
& \textbf{Collaborator(s):} Vilchez Rios, Mateo Alejandro / Avila Asto, Alex Ramon / Ramos Rios, Belen del Rocio \\ \hline

\textit{Quality Review and Integration} & \textbf{Leader:} Ortega Huaraca, Abel Angel \\
& \textbf{Collaborator(s):} Vilchez Rios, Mateo Alejandro / Avila Asto, Alex Ramon / Ramos Rios, Belen del Rocio \\ \hline

\end{longtable}

\newpage

#### Sprint Backlog 2

En este segundo sprint, se priorizó el desarrollo de componentes fundamentales del sistema, centrados en la implementación de la arquitectura de microservicios, la aplicación web y la aplicación móvil de *RutaKids*. Estas tareas fueron organizadas con base en Historias de Usuario que representan funcionalidades clave necesarias para comenzar a construir una experiencia de usuario fluida, escalable y coherente en todas las plataformas.

La planificación se enfocó en asegurar que los microservicios proporcionen una base sólida para la integración de módulos futuros, mientras que las aplicaciones web y móvil comenzaran a tomar forma con interfaces iniciales y lógica de navegación funcional. Asimismo, se incluyó la integración con la landing page desarrollada previamente, garantizando consistencia visual y técnica.

En la siguiente tabla se detallan los elementos de trabajo (Work Items) asignados a cada Historia de Usuario, junto con su esfuerzo estimado en horas, responsables y estado de avance correspondiente.


\begin{longtable}{|c|p{2.5cm}|p{1cm}|p{4cm}|p{2cm}|p{2cm}|p{1cm}|}
\hline
\textbf{ID} & \textbf{User Story} & \textbf{Work Item (WI)} & \textbf{Description} & \textbf{Estimation (Hours)} & \textbf{Assigned To} & \textbf{Status} \\ \hline
\multicolumn{7}{|l|}{\textbf{Microservicios (Implementación de Arquitectura)}} \\ \hline
\multirow{3}{*}{US01} & \multirow{3}{*}{\parbox[t]{2.5cm}{API para Gestión de Cuentas de Administrador Educativo }} & WI01 & Diseño e implementación de endpoints para registro (Admin EP01-US01) y confirmación de cuenta (Admin EP01-US02) & 8h & Alex Avila & Done \\ \cline{3-7}
 &  & WI02 & Implementación de endpoints para inicio de sesión (Admin EP01-US04) y recuperación de contraseña (Admin EP01-US05) & 7h & Alex Avila & Done \\ \cline{3-7}
 &  & WI03 & Configuración de DTOs, validaciones y manejo de excepciones para APIs de cuentas de administrador & 5h & Alex Avila & In-Process \\ \hline
\multirow{3}{*}{US02} & \multirow{3}{*}{\parbox[t]{2.5cm}{API para Gestión de Cuentas de Padres/Tutores }} & WI04 & Diseño e implementación de endpoints para registro e inicio de sesión de tutores (Tutor EP01-US01) & 7h & Alex Avila & Done \\ \cline{3-7}
 &  & WI05 & Implementación de endpoints para recuperación de contraseña (Tutor EP01-US02) y edición de perfil (Tutor EP01-US03) & 6h & Alex Avila & In-Process \\ \cline{3-7}
 &  & WI06 & Configuración de DTOs y validaciones para APIs de cuentas de tutor & 4h & Alex Avila & To Do \\ \hline
US03 & \parbox[t]{2.5cm}{Autenticación y Autorización (JWT) \newline (Común)} & WI07 & Implementación de la generación y validación de tokens JWT para todas las APIs seguras & 8h & Alex Avila & Done \\ \hline
\multirow{2}{*}{US04} & \multirow{2}{*}{\parbox[t]{2.5cm}{API para Gestión Inicial de Flotas (Vehículos) }} & WI08 & Diseño e implementación de endpoints CRUD básicos para vehículos (Admin EP02-US01) & 7h & Alex Avila & In-Process \\ \cline{3-7}
 &  & WI09 & Definición de modelos de datos y DTOs para vehículos & 4h & Alex Avila & Done \\ \hline
\multirow{2}{*}{US05} & \multirow{2}{*}{\parbox[t]{2.5cm}{API para Captura y Consulta de Geolocalización (IoT Básico) }} & WI10 & Implementación de endpoint para recepción de datos de posición de vehículos (Admin EP04-US01) & 6h & Alex Avila & In-Process \\ \cline{3-7}
 &  & WI11 & Implementación de endpoint para consulta de ubicación en tiempo real por la app móvil (Tutor EP02-US01) & 5h & Alex Avila & To Do \\ \hline
\multirow{2}{*}{US06} & \multirow{2}{*}{\parbox[t]{2.5cm}{Infraestructura de Microservicios (Docker)}} & WI12 & Creación de Dockerfiles para build y compose de los microservicios de cuentas y flotas & 6h & Alex Avila & Done \\ \cline{3-7}
 &  & WI13 & Configuración inicial de gateway API para enrutamiento a microservicios & 5h & Alex Avila & In-Process \\ \hline
\multicolumn{7}{|l|}{\textbf{Aplicación Web (Administrador Educativo)}} \\ \hline
\multirow{3}{*}{US07} & \multirow{3}{*}{\parbox[t]{2.5cm}{Interfaz Web: Registro e Inicio de Sesión Administrador }} & WI14 & Diseño UI/UX de las pantallas de registro, inicio de sesión y recuperación de contraseña (Web Admin) & 6h & Belén Ramos & Done \\ \cline{3-7}
 &  & WI15 & Desarrollo del frontend para formularios y lógica de navegación (Web Admin) & 8h & Belén Ramos & In-Process \\ \cline{3-7}
 &  & WI16 & Integración con microservicios de autenticación (US01, US03) & 5h & Mateo Vílchez & In-Process \\ \hline
\multirow{3}{*}{US08} & \multirow{3}{*}{\parbox[t]{2.5cm}{Interfaz Web: Dashboard Inicial y Gestión de Perfil }} & WI17 & Diseño UI/UX del dashboard principal (Admin EP07-US01) y pantalla de gestión de perfil (Admin EP01-US06) & 7h & Belén Ramos & Done \\ \cline{3-7}
 &  & WI18 & Implementación frontend del dashboard con KPIs iniciales y navegación funcional & 8h & Belén Ramos & To Do \\ \cline{3-7}
 &  & WI19 & Implementación frontend para la gestión del perfil administrativo & 5h & Mateo Vílchez & To Do \\ \hline
\multirow{2}{*}{US09} & \multirow{2}{*}{\parbox[t]{2.5cm}{Interfaz Web: Gestión Inicial de Vehículos }} & WI20 & Diseño UI/UX para listado, creación y edición de vehículos (Admin EP02-US01) & 6h & Belén Ramos & In-Process \\ \cline{3-7}
 &  & WI21 & Implementación frontend CRUD para vehículos e integración con API (US04) & 8h & Mateo Vílchez & To Do \\ \hline
\multicolumn{7}{|l|}{\textbf{Aplicación Móvil (Tutor Legal)}} \\ \hline
\multirow{3}{*}{US10} & \multirow{3}{*}{\parbox[t]{2.5cm}{App Móvil: Registro e Inicio de Sesión de Tutor }} & WI22 & Diseño UI/UX de pantallas de registro, inicio de sesión y recuperación de contraseña (Móvil) & 6h & Abel Ortega & Done \\ \cline{3-7}
 &  & WI23 & Implementación del frontend (Flutter) para formularios y lógica de navegación (Móvil) & 8h & Abel Ortega & In-Process \\ \cline{3-7}
 &  & WI24 & Integración con microservicios de autenticación (US02, US03) & 5h & Abel Ortega & In-Process \\ \hline
\multirow{3}{*}{US11} & \multirow{3}{*}{\parbox[t]{2.5cm}{App Móvil: Visualización de Ubicación del Vehículo}} & WI25 & Diseño UI/UX de la pantalla de mapa para seguimiento en tiempo real (Tutor EP02-US01) & 5h & Abel Ortega & Done \\ \cline{3-7}
 &  & WI26 & Implementación de la visualización del mapa y marcador de vehículo & 7h & Abel Ortega & To Do \\ \cline{3-7}
 &  & WI27 & Integración con microservicio de geolocalización (US05) & 4h & Abel Ortega & To Do \\ \hline
\multirow{2}{*}{US12} & \multirow{2}{*}{\parbox[t]{2.5cm}{App Móvil: Configuración Inicial de Notificaciones }} & WI28 & Diseño UI/UX para la gestión de dispositivos de notificación (Tutor EP01-US04) y preferencias básicas de alertas & 4h & Abel Ortega & In-Process \\ \cline{3-7}
 &  & WI29 & Implementación de la lógica inicial para recibir notificaciones push (e.g., abordaje Tutor EP03-US01) & 6h & Abel Ortega & To Do \\ \hline
\multicolumn{7}{|l|}{\textbf{Integración Landing Page (Continuación Sprint Anterior)}} \\ \hline
\multirow{3}{*}{US38} & \multirow{3}{*}{\parbox[t]{2.5cm}{Descubrimiento intuitivo \vspace{0.5cm}}} & WI30 & Diseño de la estructura HTML y navegación principal para facilitar el descubrimiento intuitivo en la landing page & 6h & Belén Ramos & Done \\ \cline{3-7}
 &  & WI31 & Implementación de los elementos de navegación y estructura responsive & 4h & Belén Ramos & Done \\ \cline{3-7}
 &  & WI32 & Pruebas de usabilidad para navegación y descubrimiento & 2h & Mateo Vílchez & Done \\ \hline
\multirow{2}{*}{US39} & \multirow{2}{*}{\parbox[t]{2.5cm}{Contenido informativo \vspace{0.5cm}}} & WI33 & Redacción de todo el contenido informativo para la landing page & 3h & Belén Ramos & Done \\ \cline{3-7}
 &  & WI34 & Implementación del contenido en la landing page & 2h & Belén Ramos & Done \\ \hline
\multirow{2}{*}{US40} & \multirow{2}{*}{\parbox[t]{2.5cm}{Compatibilidad móvil \vspace{0.5cm}}} & WI35 & Desarrollo del diseño responsive para dispositivos móviles & 4h & Belén Ramos & Done \\ \cline{3-7}
 &  & WI36 & Pruebas de responsividad en diferentes resoluciones & 3h & Belén Ramos & Done \\ \hline
\multirow{2}{*}{US41} & \multirow{2}{*}{\parbox[t]{2.5cm}{Formulario de contacto \vspace{0.5cm}}} & WI37 & Diseño e implementación del formulario de contacto & 5h & Belén Ramos & Done \\ \cline{3-7}
 &  & WI38 & Validación de formulario de contacto & 2h & Mateo Vílchez & Done \\ \hline
\multirow{2}{*}{US42} & \multirow{2}{*}{\parbox[t]{2.5cm}{Contenido multimedia \vspace{0.5cm}}} & WI39 & Integración de imágenes, íconos y secciones visuales multimedia & 3h & Belén Ramos & Done \\ \cline{3-7}
 &  & WI40 & Optimización de recursos multimedia para tiempos de carga más rápidos & 2h & Mateo Vílchez & Done \\ \hline
US43 & \parbox[t]{2.5cm}{Call-to-action claro \vspace{0.5cm}} & WI41 & Diseño y optimización de los botones de call-to-action (CTA) en la landing page & 3h & Mateo Vílchez & Done \\ \hline
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

#### Development Evidence for Sprint Review

Evidencia de colaboración en Equipo:

![Imagen extraída de Github](src/img/cap6/insights-kanban-list-1.png){ height=35% }

![Imagen extraída de Github](src/img/cap6/evidence-sprint-tp1.png){ height=35% }

\newpage

#### Testing Suite Evidence for Sprint Review

::: info
***Landing Page US - Gherkin***
:::

```gherkin
Feature: US38 - Intuitive Discovery of RutaKids Landing Page
  As a visitor interested in RutaKids,
  I want to easily discover the main sections of the landing page
  So that I can navigate intuitively and find the information I need about the system.

  Scenario: Successful navigation on the landing page
    Given the visitor is on the RutaKids landing page
    When they interact with the main navigation bar
    Then they should see clear links to the main sections (e.g., "Home", "Admin Features", "Parent App", "Contact")
    And navigation should work smoothly when clicking these links.

    Examples:
      | Visitor Action         | Expected Result                                       |
      | Click "Home"           | Navigates to the main section of the page.            |
      | Click "Admin Features" | Navigates to the section detailing the admin portal. |
      | Click "Parent App"     | Navigates to the section detailing the mobile app.   |
      | Click "Contact"        | Navigates to the contact form.                       |

  Scenario: Responsive design adapts to screen size
    Given the visitor accesses the landing page from a mobile device
    When they view the page
    Then the layout should adjust to fit the screen size appropriately
    And all sections should be accessible and readable.

    Examples:
      | Device     | Expected Behavior                                         |
      | Smartphone | Layout adjusts, elements stack vertically.               |
      | Tablet     | Layout adjusts, elements fit a wider screen.            |
```

```gherkin
Feature: US39 - Informative and Updated Content on Landing Page
  As a visitor,
  I want to find clear and informative content on the RutaKids landing page
  So that I can learn more about the system's features and benefits, including the admin portal and the mobile app.

  Scenario: Display clear content about application features
    Given the visitor is on the RutaKids landing page
    When they scroll to the information sections
    Then they should see a clear explanation of the main features of the admin portal (fleet management, user management, etc.)
    And they should see a clear explanation of the functionalities of the mobile app for parents (real-time tracking, notifications, etc.)
    And the text should be easy to read and understand.

    Examples:
      | Section             | Expected Content                                                                    |
      | Admin Portal        | Explanation of key functionalities: account management, fleets, zones, drivers, students, reports. |
      | Parent Mobile App   | Description of advantages: real-time tracking, notifications, history, communication. |
      | How It Works        | Summary of the IoT integration, monitoring, and communication process.             |

  Scenario: Ensure content is displayed correctly across devices
    Given the visitor is on the landing page on a mobile device
    When they scroll through the information sections
    Then the content should remain responsive and clear
    And images related to the portal and mobile app should load correctly.

    Examples:
      | Device   | Expected Result                                           |
      | Mobile   | Text adjusts, images scale appropriately.                |
      | Desktop  | Text and images adjust to full-screen size.              |

```

```gherkin
Feature: US40 - Mobile Compatibility of the Landing Page
  As a visitor,
  I want to browse the RutaKids landing page on my mobile device
  So that I can easily access information from any device.

  Scenario: Responsive design for mobile devices
    Given the visitor accesses the landing page on a smartphone
    When they scroll through the content
    Then the page should display correctly without layout issues (overlapping text, cut-off elements)
    And images and videos should scale appropriately.

    Examples:
      | Device      | Expected Behavior                                                              |
      | iPhone 13   | Responsive, no text overlap, easy to navigate, CTAs visible.                  |
      | Samsung S22 | All buttons are accessible, images fit the screen size.                       |

  Scenario: Test page responsiveness on tablets and desktops
    Given the visitor accesses the page on a tablet or desktop
    When they resize the browser window
    Then the layout and content should adjust fluidly without breaking
    And interactive elements must remain functional.

    Examples:
      | Device   | Expected Behavior                                                               |
      | iPad     | Two-column layout (or appropriate), images scaled correctly.                   |
      | Desktop  | Multi-column layout (or appropriate), full image resolution.                   |
```

```gherkin
Feature: US41 - Functional Contact Form on the Landing Page
  As a visitor interested in RutaKids,
  I want to fill out the contact form on the landing page
  So that I can get in touch with the RutaKids team for inquiries or to request a demo.

  Scenario: Successful contact form submission
    Given the visitor is on the contact section of the landing page
    When they fill in all required fields (Name, Email, Message, Inquiry Type [e.g., "Educational Administrator", "Parent/Guardian"]) and submit the form
    Then the system should display a confirmation message that the form has been successfully submitted
    And the submitted details should be received by the RutaKids team.

    Examples:
      | Name       | Email                  | Message                          | Inquiry Type            | Status    |
      | Ana Perez  | ana.perez@school.edu   | Information about implementation. | Educational Administrator | Submitted |
      | Luis Gomez | luis.gomez@email.com   | Question about the mobile app.   | Parent/Guardian         | Submitted |

  Scenario: Missing required fields in the contact form
    Given the visitor is filling out the contact form
    When they leave required fields empty and try to submit
    Then the system should display an error message indicating the missing fields.

    Examples:
      | Name       | Email                  | Message                          | Missing Field | Expected Error Message     |
      | Ana Perez  |                        | Information about implementation. | Email         | "Email is required"        |
      |            | luis.gomez@email.com   |                                  | Message       | "Message is required"      |
```

```gherkin
Feature: US42 - Relevant Multimedia Content on the Landing Page
  As a visitor,
  I want to find attractive multimedia content on the RutaKids landing page
  So that I can learn about the features of the admin portal and mobile app in a dynamic and visual way.

  Scenario: Display multimedia content successfully
    Given the visitor is on the landing page
    When they scroll through sections with multimedia content
    Then they should see images, short videos, or icons that explain RutaKids' functionality (admin portal and mobile app)
    And the multimedia content should load quickly and display correctly.

    Examples:
      | Media Type    | Expected Content                                          | Expected Behavior                               |
      | Images        | Screenshots of the admin portal, mobile app mockups.      | Display correctly, optimized for loading.        |
      | Short Videos  | Brief system usage demonstrations.                        | Play smoothly, without excessive buffering.      |
      | Icons         | Representative iconography for features.                  | Scale appropriately without distortion.          |

  Scenario: Ensure multimedia content is responsive across devices
    Given the visitor accesses the landing page from different devices
    When they view sections with multimedia content
    Then the multimedia content should adjust to fit the screen size and resolution without losing quality or functionality.

    Examples:
      | Device   | Expected Behavior                                                         |
      | Mobile   | Images and videos scale, layout is responsive.                           |
      | Tablet   | Images and videos adapt to a medium screen layout.                       |
      | Desktop  | Full resolution, multimedia fills the space appropriately.               |
```

```gherkin
Feature: US43 - Clear and Effective Call-to-Actions (CTAs) on the Landing Page
  As a visitor,
  I want to find clear and prominent call-to-action (CTA) buttons on the landing page
  So that I can take immediate actions, like registering my institution or learning more about the parent mobile app.

  Scenario: Clear CTA buttons guide visitor actions towards new components
    Given the visitor is on the RutaKids landing page
    When they see the "Register Institution", "Learn About Parent App", or "Request Demo" buttons
    Then the buttons should be visually prominent and easily identifiable
    And upon clicking, they should redirect to the correct sections or pages related to the admin portal or mobile app.

    Examples:
      | CTA Text                 | Expected Behavior                                                                         |
      | "Register Institution"   | Redirects the visitor to the start of the admin web application registration flow.       |
      | "Learn About Parent App" | Redirects the visitor to a section/page with detailed information about the mobile app and download/access links. |
      | "Request Demo"           | Redirects the visitor to the contact form, ideally with the demo purpose pre-selected.   |

  Scenario: CTA buttons work correctly across devices
    Given the visitor accesses the landing page from different devices (mobile, tablet, desktop)
    When they interact with CTA buttons
    Then the buttons should be responsive, easily clickable, and work correctly on all screen sizes.

    Examples:
      | Device   | Expected Behavior                                                                |
      | Mobile   | Buttons are visible, appropriately sized for touch, and functional.             |
      | Tablet   | Buttons scale correctly, remain interactive and functional.                      |
      | Desktop  | Full-sized buttons, clear, interactive, and functional.                          |
```

\newpage

::: info
***Backend US - Gherkin***
:::


```gherkin
Feature: US01 - API for Educational Administrator Account Management
  As a client application for the RutaKids system,
  I want to interact with secure API endpoints for managing educational administrator accounts,
  So that administrators can register, log in, and manage their credentials.

  Scenario: Successful administrator registration
    Given the client application has valid administrator registration data (name, email, password, institution details)
    When a POST request is made to "/api/v1/admins/register" with the administrator data
    Then the system should create a new administrator account
    And respond with HTTP status 201 (Created)
    And the response should include administrator details (excluding sensitive data like password)
    # And a confirmation process (e.g., email verification) should be initiated (Admin EP01-US02) - Implicit or separate US

  Scenario: Administrator registration with an already existing email
    Given an administrator account already exists with "admin@school.com"
    When a POST request is made to "/api/v1/admins/register" with "admin@school.com" and other valid data
    Then the system should not create a new administrator account
    And respond with HTTP status 409 (Conflict)
    And the response body should contain an error message indicating the email is already in use.

  Scenario: Successful administrator login
    Given an administrator account exists for "admin@school.com" with password "securePassword123"
    When a POST request is made to "/api/v1/admins/login" with "admin@school.com" and "securePassword123"
    Then the system should authenticate the administrator
    And respond with HTTP status 200 (OK)
    And the response body should contain a JWT access token.

  Scenario: Administrator login with incorrect credentials
    Given an administrator account exists for "admin@school.com"
    When a POST request is made to "/api/v1/admins/login" with "admin@school.com" and "wrongPassword"
    Then the system should not authenticate the administrator
    And respond with HTTP status 401 (Unauthorized)
    And the response body should contain an error message indicating invalid credentials.

  Scenario: Successful administrator password recovery request
    Given an administrator account exists for "admin@school.com"
    When a POST request is made to "/api/v1/admins/password-recovery/request" with "email": "admin@school.com"
    Then the system should initiate the password recovery process (e.g., send a reset link)
    And respond with HTTP status 200 (OK)
    And the response body should contain a success message.

  Scenario: Administrator password recovery request for a non-existent email
    When a POST request is made to "/api/v1/admins/password-recovery/request" with "email": "nonexistent@school.com"
    Then the system should not find the administrator account
    And respond with HTTP status 404 (Not Found)
    And the response body should contain an error message.
```

```gherkin
Feature: US02 - API for Parent/Tutor Account Management
  As a client application for the RutaKids system,
  I want to interact with secure API endpoints for managing parent/tutor accounts,
  So that parents/tutors can register, log in, and manage their profiles.

  Scenario: Successful parent/tutor registration
    Given the client application has valid parent/tutor registration data (name, email, password, children association info)
    When a POST request is made to "/api/v1/parents/register" with the parent/tutor data
    Then the system should create a new parent/tutor account
    And respond with HTTP status 201 (Created)
    And the response should include parent/tutor details (excluding sensitive data).

  Scenario: Parent/tutor registration with an already existing email
    Given a parent/tutor account already exists with "parent@family.com"
    When a POST request is made to "/api/v1/parents/register" with "parent@family.com" and other valid data
    Then the system should not create a new parent/tutor account
    And respond with HTTP status 409 (Conflict).

  Scenario: Successful parent/tutor login
    Given a parent/tutor account exists for "parent@family.com" with password "myChildsSafe123"
    When a POST request is made to "/api/v1/parents/login" with "parent@family.com" and "myChildsSafe123"
    Then the system should authenticate the parent/tutor
    And respond with HTTP status 200 (OK)
    And the response body should contain a JWT access token.

  Scenario: Parent/tutor login with incorrect credentials
    Given a parent/tutor account exists for "parent@family.com"
    When a POST request is made to "/api/v1/parents/login" with "parent@family.com" and "wrongPassword"
    Then the system should not authenticate the parent/tutor
    And respond with HTTP status 401 (Unauthorized).

  Scenario: Successful parent/tutor profile update
    Given a parent/tutor is logged in with a valid JWT token for "parent@family.com"
    And the client application has updated profile data (e.g., phone number, notification preferences)
    When a PUT request is made to "/api/v1/parents/profile" with the updated data and the JWT token in the Authorization header
    Then the system should update the parent/tutor's profile
    And respond with HTTP status 200 (OK)
    And the response should include the updated parent/tutor details.

  Scenario: Attempt to update parent/tutor profile without authentication
    When a PUT request is made to "/api/v1/parents/profile" with profile data but without a valid JWT token
    Then the system should reject the request
    And respond with HTTP status 401 (Unauthorized).
```

```gherkin
Feature: US03 - JWT-based Authentication and Authorization for APIs
  As a client application,
  I want API endpoints to be secured using JWT (JSON Web Tokens),
  So that only authenticated and authorized users can access protected resources.

  Scenario: Successful access to a protected resource with a valid JWT
    Given a user (administrator or parent) is logged in and has a valid JWT token
    When a GET request is made to a protected endpoint (e.g., "/api/v1/admins/dashboard-data" or "/api/v1/parents/my-children/status") with the JWT in the Authorization header
    Then the system should validate the JWT
    And grant access to the resource
    And respond with HTTP status 200 (OK)
    And the response body should contain the requested data.

  Scenario: Denied access to a protected resource with an invalid or expired JWT
    Given a user attempts to access a protected endpoint with an invalid or expired JWT token
    When a GET request is made to a protected endpoint (e.g., "/api/v1/admins/dashboard-data") with the invalid/expired JWT
    Then the system should validate the JWT and find it invalid/expired
    And deny access to the resource
    And respond with HTTP status 401 (Unauthorized)
    And the response body should contain an error message indicating token invalidity or expiration.

  Scenario: Denied access to a protected resource without a JWT
    When a GET request is made to a protected endpoint (e.g., "/api/v1/parents/my-children/status") without a JWT in the Authorization header
    Then the system should deny access
    And respond with HTTP status 401 (Unauthorized)
    And the response body should contain an error message indicating authentication is required.
```

```gherkin
Feature: US04 - API for Initial Fleet Management (Vehicles)
  As an authenticated Educational Administrator client application,
  I want to interact with API endpoints for managing vehicle information,
  So that I can register, view, update, and list vehicles in the system.

  Scenario: Successfully register a new vehicle
    Given the client application is authenticated as an Educational Administrator
    And has valid vehicle data (plate number "XYZ-123", model "School Bus 2023", capacity 30)
    When a POST request is made to "/api/v1/vehicles" with the vehicle data
    Then the system should create a new vehicle record
    And respond with HTTP status 201 (Created)
    And the response body should include the details of the created vehicle.

  Scenario: Attempt to register a vehicle with a duplicate plate number
    Given the client application is authenticated as an Educational Administrator
    And a vehicle with plate number "ABC-789" already exists
    When a POST request is made to "/api/v1/vehicles" with plate number "ABC-789" and other data
    Then the system should not create the vehicle
    And respond with HTTP status 409 (Conflict)
    And the response body should contain an error message about the duplicate plate number.

  Scenario: Successfully retrieve a list of all vehicles
    Given the client application is authenticated as an Educational Administrator
    And multiple vehicles are registered in the system
    When a GET request is made to "/api/v1/vehicles"
    Then the system should respond with HTTP status 200 (OK)
    And the response body should contain a list of all registered vehicles.

  Scenario: Successfully retrieve details for a specific vehicle
    Given the client application is authenticated as an Educational Administrator
    And a vehicle with ID "vehicle-id-001" exists
    When a GET request is made to "/api/v1/vehicles/vehicle-id-001"
    Then the system should respond with HTTP status 200 (OK)
    And the response body should contain the details of vehicle "vehicle-id-001".

  Scenario: Successfully update an existing vehicle's information
    Given the client application is authenticated as an Educational Administrator
    And a vehicle with ID "vehicle-id-002" exists
    And the client has new data for the vehicle (e.g., capacity 35, status "Active")
    When a PUT request is made to "/api/v1/vehicles/vehicle-id-002" with the new data
    Then the system should update the vehicle's information
    And respond with HTTP status 200 (OK)
    And the response body should include the updated vehicle details.
```

```gherkin
Feature: US05 - API for Geolocation Data Capture and Query (Basic IoT)
  As a client application (IoT device or backend service),
  I want to submit vehicle geolocation data,
  And as an authenticated client application (Admin Web or Parent Mobile),
  I want to query the real-time location of vehicles.

  Scenario: Successfully submit vehicle geolocation data
    Given an IoT device for vehicle "V-101" has new geolocation data (latitude 10.123, longitude -70.456, speed 50km/h, timestamp)
    When a POST request is made to "/api/v1/iot/location-updates" with the geolocation data for "V-101"
    Then the system should process and store the geolocation update
    And respond with HTTP status 202 (Accepted) or 200 (OK) if processed synchronously.

  Scenario: Attempt to submit invalid geolocation data
    Given an IoT device attempts to submit geolocation data with missing required fields (e.g., missing vehicleId or coordinates)
    When a POST request is made to "/api/v1/iot/location-updates" with the invalid data
    Then the system should reject the data
    And respond with HTTP status 400 (Bad Request)
    And the response body should contain an error message detailing the validation errors.

  Scenario: Successfully query real-time location of a specific vehicle (for Parent App)
    Given a Parent is logged in and is authorized to view the location of the bus assigned to their child (e.g., vehicle "V-101")
    And vehicle "V-101" has recent geolocation updates
    When a GET request is made to "/api/v1/vehicles/V-101/location" (or similar endpoint) with a valid JWT
    Then the system should respond with HTTP status 200 (OK)
    And the response body should contain the latest known location (latitude, longitude, speed, timestamp) of vehicle "V-101".

  Scenario: Query location for a vehicle with no recent data or non-existent vehicle (for Parent App)
    Given a Parent is logged in and requests the location for vehicle "V-999" which has no data or doesn't exist
    When a GET request is made to "/api/v1/vehicles/V-999/location" with a valid JWT
    Then the system should respond with HTTP status 404 (Not Found)
    And the response body should contain an appropriate message (e.g., "Location data not available" or "Vehicle not found").
```

```gherkin
Feature: US06 - API Gateway Routing and Microservice Accessibility
  As a client application,
  I want to interact with a unified API gateway
  So that my requests are correctly routed to the appropriate backend microservices without needing to know their individual addresses.

  Scenario: API Gateway successfully routes request to Accounts Microservice
    Given the Accounts Microservice is running and registered with the API Gateway
    When a POST request is made to the API Gateway at "/api/v1/admins/login" with valid administrator credentials
    Then the API Gateway should route the request to the Accounts Microservice
    And the Accounts Microservice should process the login
    And the API Gateway should return the Accounts Microservice's response (e.g., HTTP 200 OK with JWT).

  Scenario: API Gateway successfully routes request to Fleet Microservice
    Given the Fleet Microservice is running and registered with the API Gateway
    And the client is authenticated as an Educational Administrator
    When a GET request is made to the API Gateway at "/api/v1/vehicles"
    Then the API Gateway should route the request to the Fleet Microservice
    And the Fleet Microservice should process the request
    And the API Gateway should return the Fleet Microservice's response (e.g., HTTP 200 OK with a list of vehicles).

  Scenario: API Gateway handles request to a non-existent microservice path
    When a GET request is made to the API Gateway at "/api/v1/non-existent-service/data"
    Then the API Gateway should determine that no microservice handles this path
    And respond with HTTP status 404 (Not Found) or an appropriate gateway error.
```

```gherkin
Feature: US37 - Pagination and Filtering of API Results
  As a client application,
  I want to request paginated and filtered lists of resources from the API,
  So that I can retrieve data efficiently and display it in manageable chunks.

  Scenario: Retrieve a paginated list of resources (e.g., vehicles)
    Given there are 50 vehicle records in the system
    When a GET request is made to "/api/v1/vehicles?page=2&size=10"
    Then the system should respond with HTTP status 200 (OK)
    And the response body should contain 10 vehicle records, corresponding to the second page
    And the response should include pagination metadata (total items, total pages, current page, page size).

  Scenario: Retrieve a filtered list of resources (e.g., vehicles by status)
    Given there are vehicles with status "Active" and "Inactive"
    When a GET request is made to "/api/v1/vehicles?status=Active"
    Then the system should respond with HTTP status 200 (OK)
    And the response body should contain only vehicles with the status "Active".

  Scenario: Retrieve a paginated and filtered list of resources
    Given there are 30 vehicles with status "Active"
    When a GET request is made to "/api/v1/vehicles?status=Active&page=1&size=5"
    Then the system should respond with HTTP status 200 (OK)
    And the response body should contain the first 5 vehicles with status "Active"
    And the response should include relevant pagination metadata for the filtered set.

    Examples: Resource Endpoints
      | ResourcePath     | FilterParameter | Page | Size |
      | /api/v1/vehicles | status=OutOfService | 1    | 20   |
      | /api/v1/users    | role=driver         | 3    | 10   |
```

\newpage

::: info
***Frontend US (Web Admin Application) - Gherkin***
:::

```gherkin
Feature: US07 - Web Admin: Administrator Registration and Login Interface
  As an Educational Administrator,
  I want to use a web interface to register a new institutional account and log in,
  So that I can securely access the RutaKids administration platform.

  Scenario: Successful new administrator registration via web form
    Given I am on the RutaKids administrator registration page
    When I fill in the registration form with valid details (institution name "Colegio Ejemplo", my name "Jane Doe", email "jane.doe@colegio.ejemplo.com", password "SecurePass123", confirm password "SecurePass123")
    And I submit the registration form
    Then I should see a success message indicating my registration is processing or requires confirmation
    And I should be redirected to a confirmation pending page or the login page.
    # And an API call to the backend (US01 - Admin Registration) should be made

  Scenario: Attempt administrator registration with mismatched passwords
    Given I am on the RutaKids administrator registration page
    When I fill in the registration form with email "john.doe@school.org", password "Pass1", and confirm password "Pass2"
    And I submit the registration form
    Then I should see an error message on the page stating "Passwords do not match."
    And the form should not be submitted.

  Scenario: Attempt administrator registration with an already registered email
    Given an administrator account with "jane.doe@colegio.ejemplo.com" already exists
    When I attempt to register using "jane.doe@colegio.ejemplo.com" again on the web form
    And I submit the registration form
    Then I should see an error message on the page stating "This email is already registered."
    # And an API call to the backend (US01 - Admin Registration) results in a conflict

  Scenario: Successful administrator login via web form
    Given I am on the RutaKids administrator login page
    And an administrator account exists for "admin@rutakids.com" with password "AdminPass!"
    When I enter "admin@rutakids.com" in the email field
    And I enter "AdminPass!" in the password field
    And I click the "Login" button
    Then I should be redirected to the administrator dashboard
    And I should see elements indicating a successful login (e.g., my username, dashboard content).
    # And an API call to the backend (US01 - Admin Login) should be successful

  Scenario: Administrator login with incorrect credentials via web form
    Given I am on the RutaKids administrator login page
    When I enter "admin@rutakids.com" in the email field
    And I enter "WrongPassword" in the password field
    And I click the "Login" button
    Then I should remain on the login page or see it re-rendered
    And I should see an error message on the page stating "Invalid email or password."

  Scenario: Accessing password recovery interface
    Given I am on the RutaKids administrator login page
    When I click the "Forgot Password?" link
    Then I should be navigated to the password recovery page
    Where I can enter my email to initiate the recovery process.
```

```gherkin
Feature: US08 - Web Admin: Initial Dashboard and Profile Management Interface
  As an Educational Administrator,
  I want to access an initial dashboard with key information and manage my profile settings,
  So that I can have an overview of the system and keep my account details up to date.

  Scenario: View initial administrator dashboard after login
    Given I am an Educational Administrator and I have successfully logged into the web platform
    When I land on the administrator dashboard page
    Then I should see a welcome message or my institution's name
    And I should see placeholders or initial Key Performance Indicators (KPIs) (e.g., "Total Vehicles: N/A", "Active Routes: N/A") (Ref: Admin EP07-US01)
    And I should see navigation options to other sections of the admin portal (e.g., "Fleet Management", "User Management").

  Scenario: Navigate to and view profile management page
    Given I am logged in as an Educational Administrator
    When I navigate to the "My Profile" or "Account Settings" section from the dashboard or main navigation
    Then I should see a page displaying my current profile information (e.g., Name, Email, Institution) (Ref: Admin EP01-US06)
    And I should see options to edit my profile information.

  Scenario: Successfully update profile information
    Given I am on my profile management page
    And my current name is "Jane Doe"
    When I change my name to "Jane A. Doe" in the profile form
    And I save the changes
    Then I should see a success message "Profile updated successfully."
    And my displayed name on the profile page and potentially in the header should reflect "Jane A. Doe".
    # And an API call to update the profile on the backend should be made

  Scenario: Attempt to update profile with invalid data (e.g., invalid email format)
    Given I am on my profile management page
    When I try to change my email to an invalid format like "jane.doe"
    And I save the changes
    Then I should see an error message on the page stating "Invalid email format."
    And my email should not be updated.
```

```gherkin
Feature: US09 - Web Admin: Initial Vehicle Management Interface
  As an Educational Administrator,
  I want to use a web interface to view, add, and edit vehicle information,
  So that I can manage the school's transport fleet effectively.

  Scenario: View list of registered vehicles
    Given I am logged in as an Educational Administrator
    And I navigate to the "Fleet Management" or "Vehicles" section
    When the page loads
    Then I should see a table or list displaying registered vehicles with key details (e.g., Plate Number, Model, Capacity, Status).
    And if no vehicles are registered, I should see a message like "No vehicles registered yet. Add a new vehicle."
    # And an API call to the backend (US04 - List Vehicles) should be made

  Scenario: Successfully add a new vehicle via web form
    Given I am on the vehicle management page
    When I click the "Add New Vehicle" button
    And I fill in the new vehicle form with valid data (Plate: "NEW-001", Model: "Minibus", Capacity: 20, Status: "Active")
    And I submit the form
    Then I should see a success message "Vehicle NEW-001 added successfully."
    And the new vehicle "NEW-001" should appear in the list of vehicles.
    # And an API call to the backend (US04 - Register Vehicle) should be made

  Scenario: Attempt to add a new vehicle with missing required fields
    Given I am on the new vehicle form
    When I fill in the Plate as "BAD-002" but leave the Capacity field empty
    And I submit the form
    Then I should see an error message on the page next to the Capacity field, like "Capacity is required."
    And the vehicle should not be added.

  Scenario: Successfully edit an existing vehicle's information
    Given I am on the vehicle management page and vehicle "EDIT-003" with Capacity 15 exists
    When I select vehicle "EDIT-003" to edit
    And I change its Capacity to 18 in the edit form
    And I save the changes
    Then I should see a success message "Vehicle EDIT-003 updated successfully."
    And the vehicle "EDIT-003" in the list should now show Capacity 18.
    # And an API call to the backend (US04 - Update Vehicle) should be made

  Scenario: Navigate to vehicle details page (if applicable)
    Given I am on the vehicle management page and vehicle "DETAIL-004" exists
    When I click on vehicle "DETAIL-004" or a "View Details" button associated with it
    Then I should be navigated to a page showing more comprehensive details for vehicle "DETAIL-004".
```

\newpage

::: info
***Mobile App US (Parent/Tutor Application) - Gherkin***
:::

```gherkin
Feature: US10 - Mobile App: Parent/Tutor Registration and Login
  As a Parent/Tutor,
  I want to register for an account and log in using the mobile app,
  So that I can access RutaKids features to monitor my child's transport.

  Scenario: Successful new parent/tutor registration via mobile app form
    Given I am on the RutaKids mobile app registration screen
    When I fill in the registration form with my valid details (Name "John Parent", Email "john.parent@example.com", Password "MyChildsSafeR!de", Confirm Password "MyChildsSafeR!de", and information to link to my child/children)
    And I tap the "Register" button
    Then I should see a success message on the screen (e.g., "Registration successful! Please check your email for verification.") or be taken to a verification pending screen
    And my account creation process should be initiated.
    # And an API call to the backend (US02 - Parent/Tutor Registration) should be made

  Scenario: Attempt parent/tutor registration with mismatched passwords in mobile app
    Given I am on the RutaKids mobile app registration screen
    When I fill in the registration form with email "jane.parent@example.com", password "PassA", and confirm password "PassB"
    And I tap the "Register" button
    Then I should see an error message on the screen stating "Passwords do not match."
    And the form should not be submitted.

  Scenario: Attempt parent/tutor registration with an already registered email in mobile app
    Given a parent/tutor account with "john.parent@example.com" already exists
    When I attempt to register using "john.parent@example.com" again in the mobile app
    And I tap the "Register" button
    Then I should see an error message on the screen stating "This email is already registered."
    # And an API call to the backend (US02 - Parent/Tutor Registration) results in a conflict

  Scenario: Successful parent/tutor login via mobile app
    Given I am on the RutaKids mobile app login screen
    And a parent/tutor account exists for "lucy.guardian@example.com" with password "SecureApp123"
    When I enter "lucy.guardian@example.com" in the email field
    And I enter "SecureApp123" in the password field
    And I tap the "Login" button
    Then I should be navigated to the main screen or dashboard of the mobile app
    And I should see elements indicating a successful login (e.g., my child's name, map view).
    # And an API call to the backend (US02 - Parent/Tutor Login) should be successful

  Scenario: Parent/tutor login with incorrect credentials via mobile app
    Given I am on the RutaKids mobile app login screen
    When I enter "lucy.guardian@example.com" in the email field
    And I enter "WrongPassword" in the password field
    And I tap the "Login" button
    Then I should remain on the login screen or see it re-rendered
    And I should see an error message on the screen stating "Invalid email or password."

  Scenario: Accessing password recovery from mobile app login screen
    Given I am on the RutaKids mobile app login screen
    When I tap the "Forgot Password?" link or button
    Then I should be navigated to a password recovery screen within the app
    Where I can enter my email to initiate the recovery process.
```

```gherkin
Feature: US11 - Mobile App: Real-time Vehicle Location Tracking
  As a Parent/Tutor,
  I want to view the real-time location of my child's assigned transport vehicle on a map within the mobile app,
  So that I can be informed about the progress of their journey.

  Scenario: View real-time location of the assigned vehicle on the map
    Given I am logged into the RutaKids mobile app
    And my child is assigned to a bus (e.g., "BUS-A1") which is currently on its route
    And the bus "BUS-A1" is transmitting location updates
    When I navigate to the "Track Ride" or "Map View" screen
    Then I should see a map displayed on the screen
    And I should see an icon representing my child's bus "BUS-A1" at its current location on the map
    And the icon's position should update periodically to reflect real-time movement.
    # And an API call to the backend (US05 - Query Vehicle Location) should be made to fetch location data

  Scenario: Map displays correctly on different mobile devices and orientations
    Given I am logged into the RutaKids mobile app and viewing the map screen
    When I use the app on different mobile devices (e.g., Android, iOS, varying screen sizes)
    Or I rotate my device screen (portrait/landscape)
    Then the map should render correctly, filling the available space appropriately
    And all map controls (zoom, pan) should remain functional.

  Scenario: Handling situation when vehicle location data is unavailable
    Given I am logged into the RutaKids mobile app
    And my child's assigned bus "BUS-B2" is not currently transmitting location data (e.g., out of service, GPS issue)
    When I navigate to the "Track Ride" or "Map View" screen for "BUS-B2"
    Then I should see a message on the screen like "Vehicle location is currently unavailable" or "Bus is not active"
    And the map might show a default view or the last known location with a clear indicator of its staleness.

  Scenario: Display basic route information along with vehicle location (Future Enhancement Hint)
    Given I am viewing the real-time location of my child's bus "BUS-C3"
    When the map screen loads
    Then I might see a faint overlay or markers indicating the planned route for "BUS-C3" (Ref: Tutor EP02-US02)
    And I might see an estimated time of arrival (ETA) to the next stop or destination (Ref: Tutor EP02-US03).
    # This scenario hints at related functionalities that might be built upon this core tracking.
```

```gherkin
Feature: US12 - Mobile App: Initial Notification Configuration and Reception
  As a Parent/Tutor,
  I want to manage basic notification preferences in the mobile app and receive initial critical alerts,
  So that I can stay informed about important events related to my child's transport.

  Scenario: Access notification settings screen
    Given I am logged into the RutaKids mobile app
    When I navigate to the "Settings" or "Notifications" section within the app
    Then I should see a screen where I can manage my notification preferences (Ref: Tutor EP01-US04, Tutor EP06-US01).

  Scenario: Enable/Disable a basic notification type (e.g., "Child Aboard Vehicle")
    Given I am on the notification settings screen
    And there is an option to toggle notifications for "Child Aboard Vehicle"
    When I toggle the "Child Aboard Vehicle" notification switch to "ON" (or "OFF")
    Then the setting should be saved
    And I should receive (or stop receiving) this type of notification accordingly.
    # And an API call might be made to the backend to store this preference

  Scenario: Receive a "Child Aboard Vehicle" push notification
    Given I have "Child Aboard Vehicle" notifications enabled in the mobile app
    And my child has just boarded their assigned school bus
    And the system detects this event (e.g., via RFID scan, Ref: Admin EP03-US02)
    When the event occurs
    Then I should receive a push notification on my mobile device stating something like "Notification: [Child's Name] has boarded bus [Bus ID]." (Ref: Tutor EP03-US01)

  Scenario: Receive a "Vehicle Arrived at Destination" push notification
    Given I have relevant arrival notifications enabled
    And my child's bus has just completed its route and arrived at the school (or home stop)
    When the bus arrival event is registered by the system
    Then I should receive a push notification on my mobile device stating something like "Notification: Bus [Bus ID] has arrived at [Destination]." (Ref: Tutor EP03-US02)

  Scenario: View notification history (basic placeholder)
    Given I have received several notifications
    When I navigate to a "Notification History" or "Alerts" section in the app (if available in this sprint)
    Then I should see a list of recent notifications I have received.
    # This is a basic placeholder; full history might be a later feature (Ref: Tutor EP05)
```

\newpage

#### Execution Evidence for Sprint Review

::: box
**Implemented Landing Page Evidence**
:::

::: warn
Para acceder al repositorio de este proyecto, haga click a la [URL](https://github.com/orgs/LlantaTech/repositories)
:::

**Captura del repositorio:**

![Organización LLantatech, imagen extraída de Github](src/img/cap6/landing-deploy-1.png){ width=80% }

**Landing Page en funcionamiento:**

![Organización LLantatech, imagen extraída de Github](src/img/cap6/landing-deploy-2.png){ width=80% }

\newpage

::: box
**Implemented Frontend-Web Application Evidence**
:::

::: warn
Para acceder al repositorio de este proyecto, haga click a la [URL](https://github.com/orgs/LlantaTech/repositories)
:::

**Captura del repositorio:**

![Organización LLantatech, imagen extraída de Github](src/img/cap6/webapp-deploy-1.png){ width=80% }

**Web Application en funcionamiento:**

![Organización LLantatech, imagen extraída de Github](src/img/cap6/webapp-deploy-2.jpg){ width=80% }

\newpage

::: box
**Implemented Native-Mobile Application Evidence**
:::

::: warn
Para acceder al repositorio de este proyecto, haga click a la [URL](https://www.figma.com/design/ph6aTjM4mzxkNic0Hk4VLX/RutaKids?node-id=275-3006&t=aZ58NPtaowKWvMte-1)
:::

**Captura del figma:**

![Organización LLantatech, imagen extraída de Figma](src/img/cap6/rutakids-mobileapp-github-implementation.png){ width=80% }

**Mobile Application en funcionamiento:**

![Organización LLantatech, imagen extraída de Figma](src/img/cap6/mobile-app-figma-view.png){ width=50% }

\newpage

::: box
**Implemented RESTful API and/or Serverless Backend Evidence**
:::

::: warn
Para acceder al repositorio de este proyecto, haga click a la [URL](https://github.com/LlantaTech/ruta-kids-microservicios)
:::

**Captura del repositorio:**

![Organización LLantatech, imagen extraída de Github](src/img/cap6/webservices-deploy-1.png){ width=80% }

**Web Service Application en funcionamiento:**

![Organización LLantatech, imagen extraída de Github](src/img/cap6/webservices-deploy-2.jpg){ width=80% }

\newpage

**RESTful API documentation**

::: warn
Para acceder al repositorio de este proyecto, haga click a la [URL](https://github.com/LlantaTech/ruta-kids-microservicios)
:::

**Captura del repositorio:**

![Organización LLantatech, imagen extraída de Github](src/img/cap6/webservices-doc.png)

\newpage

#### Services Documentation Evidence for Sprint Review


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

#### Software Deployment Evidence for Sprint Review

***Landing Page Deployment***

![Organización LLantatech, imagen extraída de Github](src/img/cap6/landing-deploy-2.png){ width=80% }

**Web Application Deployment**

![Organización LLantatech, imagen extraída de Github](src/img/cap6/webapp-deploy-2.jpg){ width=80% }

\newpage

**Mobile Application Deployment**

![Organización LLantatech, imagen extraída del Github](src/img/cap6/mobile-app-figma-view.png){ width=50% }

**Web Service Deployment**

![Organización LLantatech, imagen extraída de Github](src/img/cap6/webservices-deploy-2.jpg){ width=80% }

\newpage

#### Team Collaboration Insights during Sprint

::: warn
Para acceder los insights de este proyecto, haga click a la [URL](https://github.com/orgs/LlantaTech/repositories)
:::

**Tablero Kanban:**

![Organización LLantatech, imagen extraída de Github](src/img/cap6/insights-kanban-todo-1.png){ width=80% }

**Kanban List:**

![Organización LLantatech, imagen extraída de Github](src/img/cap6/insights-kanban-list-1.png){ width=80% }

\newpage

**Network Graph:**

![Organización LLantatech, imagen extraída de Github](src/img/cap6/insights-network-graph-tb2.png){ width=80% }

**Traffic Map:**

![Organización LLantatech, imagen extraída de Github](src/img/cap6/insights-traffic-map-tb2.png){ width=80% }

\newpage


### Sprint 3

Durante el Sprint 3, el equipo se enfocó en completar una de las metas más críticas del proyecto: la implementación del dispositivo IoT en las movilidades escolares, orientado a mejorar la seguridad y trazabilidad del servicio de transporte. Este sprint marcó un hito técnico, ya que permitió enlazar por primera vez los componentes físicos (hardware IoT) con los módulos software previamente desarrollados (aplicaciones web, móvil y microservicios backend).

Se llevaron a cabo tareas de integración, configuración de red, pruebas funcionales y validaciones de comunicación en tiempo real, todo bajo un enfoque colaborativo y orientado a despliegue. El equipo aseguró que el dispositivo IoT pudiera transmitir datos de geolocalización de manera continua, estable y segura hacia el ecosistema RutaKids, permitiendo su visualización inmediata tanto en el panel web como en la app de padres.

Asimismo, se realizaron pruebas de campo, ajustes en los endpoints de recepción y despliegue completo del sistema en un entorno de staging funcional, lo que valida la viabilidad técnica de la solución en condiciones reales de uso. Este sprint culmina la fase de implementación del sistema RutaKids, consolidando su arquitectura integral y sentando las bases para la entrega final del producto.

\newpage

#### Sprint Planning 3

\begin{longtable}{|p{5cm}|p{9cm}|}
\hline
\textbf{Sprint Planning Background} & \\ \hline
\endfirsthead
\hline
\textbf{Sprint} & \textbf{Sprint 3} \\ \hline
\endfoot
\hline
\textbf{Date} & 30/06/2025 \\ \hline
\textbf{Time} & 21:00 \\ \hline
\textbf{Location} & Discord Virtual Meeting \\ \hline
\textbf{Prepared By} & Ortega Huaraca, Abel Angel \\ \hline
\textbf{Attendees (to planning meeting)} & Ortega Huaraca, Abel Angel / Avila Asto, Alex Ramon / Vilchez Rios, Mateo Alejandro / Ramos Rios, Belen del Rocio \\ \hline
\textbf{Sprint 3 Review Summary} & Durante este sprint se logró la implementación e integración del dispositivo IoT en las movilidades escolares, permitiendo capturar y transmitir datos en tiempo real. Además, se desarrollaron los endpoints necesarios para su interacción con los microservicios existentes, logrando su conexión efectiva con la aplicación web y móvil. Se completó el despliegue final del sistema. \\ \hline
\textbf{Sprint 3 Retrospective Summary} & Se alcanzaron todos los objetivos del sprint. La planificación previa y la coordinación entre los miembros permitió una integración exitosa del sistema IoT, y su despliegue se realizó sin incidencias críticas. Las herramientas utilizadas facilitaron el monitoreo y validación del funcionamiento en entornos reales. \\ \hline
\textbf{Sprint Goal \& User Stories} & Implementar, integrar y desplegar el sistema IoT conectado a las movilidades escolares. Completar la integración entre los dispositivos físicos y los sistemas software (web y móvil), validando su funcionamiento en conjunto. Historias de usuario involucradas: US13, US14, US15, US16, US17. \\ \hline
\textbf{Sprint 3 Velocity} & 1 Sprint cada 2 semanas \\ \hline
\textbf{Sum of Story Points} & 130 \\ \hline
\end{longtable}


\newpage

#### Aspect Leaders and Collaborators

\begin{longtable}{|p{5cm}|p{9cm}|}
\hline
\textbf{Aspect} & \textbf{Leader and Collaborators} \\ \hline
\endfirsthead

\hline
\textit{Project Coordination and Sprint Management} & \textbf{Leader:} Ortega Huaraca, Abel Angel \\
& \textbf{Collaborator(s):} Avila Asto, Alex Ramon / Vilchez Rios, Mateo Alejandro / Ramos Rios, Belen del Rocio \\ \hline

\textit{IoT Device Integration and Deployment} & \textbf{Leader:} Avila Asto, Alex Ramon \\
& \textbf{Collaborator(s):} Ortega Huaraca, Abel Angel / Vilchez Rios, Mateo Alejandro \\ \hline

\textit{Web Application Integration (IoT Data)} & \textbf{Leader:} Vilchez Rios, Mateo Alejandro \\
& \textbf{Collaborator(s):} Avila Asto, Alex Ramon / Ortega Huaraca, Abel Angel \\ \hline

\textit{Mobile Application Integration (IoT Data)} & \textbf{Leader:} Ortega Huaraca, Abel Angel \\
& \textbf{Collaborator(s):} Avila Asto, Alex Ramon / Ramos Rios, Belen del Rocio \\ \hline

\textit{Microservices Adaptation for IoT Events} & \textbf{Leader:} Avila Asto, Alex Ramon \\
& \textbf{Collaborator(s):} Vilchez Rios, Mateo Alejandro / Ortega Huaraca, Abel Angel \\ \hline

\textit{Testing (Functional and BDD)} & \textbf{Leader:} Ramos Rios, Belen del Rocio \\
& \textbf{Collaborator(s):} Ortega Huaraca, Abel Angel / Vilchez Rios, Mateo Alejandro \\ \hline

\textit{Documentation and Evidence Compilation} & \textbf{Leader:} Ramos Rios, Belen del Rocio \\
& \textbf{Collaborator(s):} Ortega Huaraca, Abel Angel / Avila Asto, Alex Ramon \\ \hline

\textit{CI/CD and Final System Deployment} & \textbf{Leader:} Avila Asto, Alex Ramon \\
& \textbf{Collaborator(s):} Ortega Huaraca, Abel Angel / Vilchez Rios, Mateo Alejandro \\ \hline

\end{longtable}


\newpage

#### Sprint Backlog 3

En este tercer sprint, se priorizó la implementación del sistema de IoT integrado en las movilidades escolares, permitiendo el envío y recepción de datos de geolocalización en tiempo real. Esta funcionalidad se complementó con el desarrollo e integración de los módulos web y móviles ya construidos, fortaleciendo la arquitectura del sistema completo de RutaKids.

Además, se adaptaron los microservicios para aceptar eventos provenientes de los dispositivos IoT, se integraron con las vistas móviles y web, y se desplegaron los componentes en un entorno funcional y testeado. La planificación incluyó la verificación del flujo completo: desde la captura del dato físico en el vehículo hasta su visualización por parte de los usuarios finales (padres y administradores).

En la siguiente tabla se detallan los elementos de trabajo (Work Items) asignados a cada Historia de Usuario, junto con su esfuerzo estimado en horas, responsables y estado de avance correspondiente.


\begin{longtable}{|c|p{2.5cm}|p{1cm}|p{4cm}|p{2cm}|p{2cm}|p{1cm}|}
\hline
\textbf{ID} & \textbf{User Story} & \textbf{Work Item (WI)} & \textbf{Description} & \textbf{Estimation (Hours)} & \textbf{Assigned To} & \textbf{Status} \\ \hline
\multicolumn{7}{|l|}{\textbf{Microservicios (Implementación de Arquitectura)}} \\ \hline
\multirow{3}{*}{US01} & \multirow{3}{*}{\parbox[t]{2.5cm}{API para Gestión de Cuentas de Administrador Educativo }} & WI01 & Diseño e implementación de endpoints para registro (Admin EP01-US01) y confirmación de cuenta (Admin EP01-US02) & 8h & Alex Avila & Done \\ \cline{3-7}
 &  & WI02 & Implementación de endpoints para inicio de sesión (Admin EP01-US04) y recuperación de contraseña (Admin EP01-US05) & 7h & Alex Avila & Done \\ \cline{3-7}
 &  & WI03 & Configuración de DTOs, validaciones y manejo de excepciones para APIs de cuentas de administrador & 5h & Alex Avila & In-Process \\ \hline
\multirow{3}{*}{US02} & \multirow{3}{*}{\parbox[t]{2.5cm}{API para Gestión de Cuentas de Padres/Tutores }} & WI04 & Diseño e implementación de endpoints para registro e inicio de sesión de tutores (Tutor EP01-US01) & 7h & Alex Avila & Done \\ \cline{3-7}
 &  & WI05 & Implementación de endpoints para recuperación de contraseña (Tutor EP01-US02) y edición de perfil (Tutor EP01-US03) & 6h & Alex Avila & In-Process \\ \cline{3-7}
 &  & WI06 & Configuración de DTOs y validaciones para APIs de cuentas de tutor & 4h & Alex Avila & To Do \\ \hline
US03 & \parbox[t]{2.5cm}{Autenticación y Autorización (JWT) \newline (Común)} & WI07 & Implementación de la generación y validación de tokens JWT para todas las APIs seguras & 8h & Alex Avila & Done \\ \hline
\multirow{2}{*}{US04} & \multirow{2}{*}{\parbox[t]{2.5cm}{API para Gestión Inicial de Flotas (Vehículos) }} & WI08 & Diseño e implementación de endpoints CRUD básicos para vehículos (Admin EP02-US01) & 7h & Alex Avila & In-Process \\ \cline{3-7}
 &  & WI09 & Definición de modelos de datos y DTOs para vehículos & 4h & Alex Avila & Done \\ \hline
\multirow{2}{*}{US05} & \multirow{2}{*}{\parbox[t]{2.5cm}{API para Captura y Consulta de Geolocalización (IoT Básico) }} & WI10 & Implementación de endpoint para recepción de datos de posición de vehículos (Admin EP04-US01) & 6h & Alex Avila & In-Process \\ \cline{3-7}
 &  & WI11 & Implementación de endpoint para consulta de ubicación en tiempo real por la app móvil (Tutor EP02-US01) & 5h & Alex Avila & To Do \\ \hline
\multirow{2}{*}{US06} & \multirow{2}{*}{\parbox[t]{2.5cm}{Infraestructura de Microservicios (Docker)}} & WI12 & Creación de Dockerfiles para build y compose de los microservicios de cuentas y flotas & 6h & Alex Avila & Done \\ \cline{3-7}
 &  & WI13 & Configuración inicial de gateway API para enrutamiento a microservicios & 5h & Alex Avila & In-Process \\ \hline
\multicolumn{7}{|l|}{\textbf{Aplicación Web (Administrador Educativo)}} \\ \hline
\multirow{3}{*}{US07} & \multirow{3}{*}{\parbox[t]{2.5cm}{Interfaz Web: Registro e Inicio de Sesión Administrador }} & WI14 & Diseño UI/UX de las pantallas de registro, inicio de sesión y recuperación de contraseña (Web Admin) & 6h & Belén Ramos & Done \\ \cline{3-7}
 &  & WI15 & Desarrollo del frontend para formularios y lógica de navegación (Web Admin) & 8h & Belén Ramos & In-Process \\ \cline{3-7}
 &  & WI16 & Integración con microservicios de autenticación (US01, US03) & 5h & Mateo Vílchez & In-Process \\ \hline
\multirow{3}{*}{US08} & \multirow{3}{*}{\parbox[t]{2.5cm}{Interfaz Web: Dashboard Inicial y Gestión de Perfil }} & WI17 & Diseño UI/UX del dashboard principal (Admin EP07-US01) y pantalla de gestión de perfil (Admin EP01-US06) & 7h & Belén Ramos & Done \\ \cline{3-7}
 &  & WI18 & Implementación frontend del dashboard con KPIs iniciales y navegación funcional & 8h & Belén Ramos & To Do \\ \cline{3-7}
 &  & WI19 & Implementación frontend para la gestión del perfil administrativo & 5h & Mateo Vílchez & To Do \\ \hline
\multirow{2}{*}{US09} & \multirow{2}{*}{\parbox[t]{2.5cm}{Interfaz Web: Gestión Inicial de Vehículos }} & WI20 & Diseño UI/UX para listado, creación y edición de vehículos (Admin EP02-US01) & 6h & Belén Ramos & In-Process \\ \cline{3-7}
 &  & WI21 & Implementación frontend CRUD para vehículos e integración con API (US04) & 8h & Mateo Vílchez & To Do \\ \hline
\multicolumn{7}{|l|}{\textbf{Aplicación Móvil (Tutor Legal)}} \\ \hline
\multirow{3}{*}{US10} & \multirow{3}{*}{\parbox[t]{2.5cm}{App Móvil: Registro e Inicio de Sesión de Tutor }} & WI22 & Diseño UI/UX de pantallas de registro, inicio de sesión y recuperación de contraseña (Móvil) & 6h & Abel Ortega & Done \\ \cline{3-7}
 &  & WI23 & Implementación del frontend (Flutter) para formularios y lógica de navegación (Móvil) & 8h & Abel Ortega & In-Process \\ \cline{3-7}
 &  & WI24 & Integración con microservicios de autenticación (US02, US03) & 5h & Abel Ortega & In-Process \\ \hline
\multirow{3}{*}{US11} & \multirow{3}{*}{\parbox[t]{2.5cm}{App Móvil: Visualización de Ubicación del Vehículo}} & WI25 & Diseño UI/UX de la pantalla de mapa para seguimiento en tiempo real (Tutor EP02-US01) & 5h & Abel Ortega & Done \\ \cline{3-7}
 &  & WI26 & Implementación de la visualización del mapa y marcador de vehículo & 7h & Abel Ortega & To Do \\ \cline{3-7}
 &  & WI27 & Integración con microservicio de geolocalización (US05) & 4h & Abel Ortega & To Do \\ \hline
\multirow{2}{*}{US12} & \multirow{2}{*}{\parbox[t]{2.5cm}{App Móvil: Configuración Inicial de Notificaciones }} & WI28 & Diseño UI/UX para la gestión de dispositivos de notificación (Tutor EP01-US04) y preferencias básicas de alertas & 4h & Abel Ortega & In-Process \\ \cline{3-7}
 &  & WI29 & Implementación de la lógica inicial para recibir notificaciones push (e.g., abordaje Tutor EP03-US01) & 6h & Abel Ortega & To Do \\ \hline
\multicolumn{7}{|l|}{\textbf{Integración Landing Page (Continuación Sprint Anterior)}} \\ \hline
\multirow{3}{*}{US38} & \multirow{3}{*}{\parbox[t]{2.5cm}{Descubrimiento intuitivo \vspace{0.5cm}}} & WI30 & Diseño de la estructura HTML y navegación principal para facilitar el descubrimiento intuitivo en la landing page & 6h & Belén Ramos & Done \\ \cline{3-7}
 &  & WI31 & Implementación de los elementos de navegación y estructura responsive & 4h & Belén Ramos & Done \\ \cline{3-7}
 &  & WI32 & Pruebas de usabilidad para navegación y descubrimiento & 2h & Mateo Vílchez & Done \\ \hline
\multirow{2}{*}{US39} & \multirow{2}{*}{\parbox[t]{2.5cm}{Contenido informativo \vspace{0.5cm}}} & WI33 & Redacción de todo el contenido informativo para la landing page & 3h & Belén Ramos & Done \\ \cline{3-7}
 &  & WI34 & Implementación del contenido en la landing page & 2h & Belén Ramos & Done \\ \hline
\multirow{2}{*}{US40} & \multirow{2}{*}{\parbox[t]{2.5cm}{Compatibilidad móvil \vspace{0.5cm}}} & WI35 & Desarrollo del diseño responsive para dispositivos móviles & 4h & Belén Ramos & Done \\ \cline{3-7}
 &  & WI36 & Pruebas de responsividad en diferentes resoluciones & 3h & Belén Ramos & Done \\ \hline
\multirow{2}{*}{US41} & \multirow{2}{*}{\parbox[t]{2.5cm}{Formulario de contacto \vspace{0.5cm}}} & WI37 & Diseño e implementación del formulario de contacto & 5h & Belén Ramos & Done \\ \cline{3-7}
 &  & WI38 & Validación de formulario de contacto & 2h & Mateo Vílchez & Done \\ \hline
\multirow{2}{*}{US42} & \multirow{2}{*}{\parbox[t]{2.5cm}{Contenido multimedia \vspace{0.5cm}}} & WI39 & Integración de imágenes, íconos y secciones visuales multimedia & 3h & Belén Ramos & Done \\ \cline{3-7}
 &  & WI40 & Optimización de recursos multimedia para tiempos de carga más rápidos & 2h & Mateo Vílchez & Done \\ \hline
US43 & \parbox[t]{2.5cm}{Call-to-action claro \vspace{0.5cm}} & WI41 & Diseño y optimización de los botones de call-to-action (CTA) en la landing page & 3h & Mateo Vílchez & Done \\ \hline
\end{longtable}

\newpage

**Gestión de los Sprint (Tablero Kanban):**

Para optimizar la gestión y el seguimiento de las tareas durante el Sprint 3, se utilizó un tablero Kanban digital como herramienta principal de organización. Esta metodología permitió visualizar con claridad las actividades pendientes, en proceso y finalizadas, facilitando la identificación de cuellos de botella y promoviendo la colaboración en tiempo real entre los integrantes del equipo.

Cada tarea fue gestionada como un Issue, con asignaciones específicas y categorizaciones mediante etiquetas (labels) que identificaban el tipo de trabajo (frontend, backend, IoT, documentación, etc.). Asimismo, se utilizaron Milestones para establecer objetivos intermedios, controlar fechas clave de entrega y vincular avances técnicos con los entregables académicos del proyecto.

Esta estrategia de gestión visual contribuyó significativamente al cumplimiento efectivo de los objetivos del sprint, manteniendo la trazabilidad del desarrollo y fomentando una cultura ágil dentro del equipo.

![Imagen extraída de Canva](src/img/cap6/gestion-sprints-kanban.png)

\newpage

#### Development Evidence for Sprint Review

Durante el Sprint 3, se logró consolidar el desarrollo técnico del sistema mediante una ejecución efectiva de tareas clave, destacando la integración exitosa del dispositivo IoT con las plataformas web y móvil. El equipo trabajó colaborativamente en múltiples frentes de desarrollo, permitiendo que los distintos módulos del sistema interactúen de forma estable y en tiempo real.

La evidencia presentada a continuación muestra la dinámica de trabajo durante el sprint: desde la planificación en el tablero Kanban hasta la coordinación en la resolución de issues y la entrega continua de componentes. Los commits registrados, issues cerrados y pull requests revisados reflejan el compromiso del equipo con una estrategia ágil y con una comunicación técnica activa.

Evidencia de colaboración en Equipo:

![Imagen extraída de Github](src/img/cap6/insights-kanban-list-1.png){ height=35% }

![Imagen extraída de Github](src/img/cap6/evidence-sprint-tp1.png){ height=35% }


Además, se realizaron integraciones directas entre los microservicios backend y el hardware IoT, validando con éxito la transmisión de datos desde las movilidades hacia el sistema de visualización en la app móvil. Estas tareas fueron documentadas y versionadas en los repositorios correspondientes, evidenciando trazabilidad y calidad en el desarrollo.


![Imagen extraída de reunion grupal sprint 3](src/img/cap6/evidence-sprint-TF1.png)

![Imagen extraída de reunion grupal sprint 3](src/img/cap6/evidence-sprint-TF2.png)


\newpage

#### Testing Suite Evidence for Sprint Review

Durante el Sprint 3, se desarrolló y documentó un conjunto de escenarios de prueba escritos en lenguaje Gherkin, con el fin de validar el cumplimiento de las historias de usuario implementadas. Estos escenarios cubren funcionalidades clave de la landing page, el portal web administrativo, la aplicación móvil para padres/tutores, y los microservicios backend (incluyendo la integración IoT). Esta estrategia de pruebas permitió asegurar el correcto funcionamiento de los módulos desarrollados, manteniendo la trazabilidad con los objetivos definidos en la planificación del sprint.

::: info
***Landing Page US - Gherkin***
:::

```gherkin
Feature: US38 - Intuitive Discovery of RutaKids Landing Page
  As a visitor interested in RutaKids,
  I want to easily discover the main sections of the landing page
  So that I can navigate intuitively and find the information I need about the system.

  Scenario: Successful navigation on the landing page
    Given the visitor is on the RutaKids landing page
    When they interact with the main navigation bar
    Then they should see clear links to the main sections (e.g., "Home", "Admin Features", "Parent App", "Contact")
    And navigation should work smoothly when clicking these links.

    Examples:
      | Visitor Action         | Expected Result                                       |
      | Click "Home"           | Navigates to the main section of the page.            |
      | Click "Admin Features" | Navigates to the section detailing the admin portal. |
      | Click "Parent App"     | Navigates to the section detailing the mobile app.   |
      | Click "Contact"        | Navigates to the contact form.                       |

  Scenario: Responsive design adapts to screen size
    Given the visitor accesses the landing page from a mobile device
    When they view the page
    Then the layout should adjust to fit the screen size appropriately
    And all sections should be accessible and readable.

    Examples:
      | Device     | Expected Behavior                                         |
      | Smartphone | Layout adjusts, elements stack vertically.               |
      | Tablet     | Layout adjusts, elements fit a wider screen.            |
```

```gherkin
Feature: US39 - Informative and Updated Content on Landing Page
  As a visitor,
  I want to find clear and informative content on the RutaKids landing page
  So that I can learn more about the system's features and benefits, including the admin portal and the mobile app.

  Scenario: Display clear content about application features
    Given the visitor is on the RutaKids landing page
    When they scroll to the information sections
    Then they should see a clear explanation of the main features of the admin portal (fleet management, user management, etc.)
    And they should see a clear explanation of the functionalities of the mobile app for parents (real-time tracking, notifications, etc.)
    And the text should be easy to read and understand.

    Examples:
      | Section             | Expected Content                                                                    |
      | Admin Portal        | Explanation of key functionalities: account management, fleets, zones, drivers, students, reports. |
      | Parent Mobile App   | Description of advantages: real-time tracking, notifications, history, communication. |
      | How It Works        | Summary of the IoT integration, monitoring, and communication process.             |

  Scenario: Ensure content is displayed correctly across devices
    Given the visitor is on the landing page on a mobile device
    When they scroll through the information sections
    Then the content should remain responsive and clear
    And images related to the portal and mobile app should load correctly.

    Examples:
      | Device   | Expected Result                                           |
      | Mobile   | Text adjusts, images scale appropriately.                |
      | Desktop  | Text and images adjust to full-screen size.              |

```

```gherkin
Feature: US40 - Mobile Compatibility of the Landing Page
  As a visitor,
  I want to browse the RutaKids landing page on my mobile device
  So that I can easily access information from any device.

  Scenario: Responsive design for mobile devices
    Given the visitor accesses the landing page on a smartphone
    When they scroll through the content
    Then the page should display correctly without layout issues (overlapping text, cut-off elements)
    And images and videos should scale appropriately.

    Examples:
      | Device      | Expected Behavior                                                              |
      | iPhone 13   | Responsive, no text overlap, easy to navigate, CTAs visible.                  |
      | Samsung S22 | All buttons are accessible, images fit the screen size.                       |

  Scenario: Test page responsiveness on tablets and desktops
    Given the visitor accesses the page on a tablet or desktop
    When they resize the browser window
    Then the layout and content should adjust fluidly without breaking
    And interactive elements must remain functional.

    Examples:
      | Device   | Expected Behavior                                                               |
      | iPad     | Two-column layout (or appropriate), images scaled correctly.                   |
      | Desktop  | Multi-column layout (or appropriate), full image resolution.                   |
```

```gherkin
Feature: US41 - Functional Contact Form on the Landing Page
  As a visitor interested in RutaKids,
  I want to fill out the contact form on the landing page
  So that I can get in touch with the RutaKids team for inquiries or to request a demo.

  Scenario: Successful contact form submission
    Given the visitor is on the contact section of the landing page
    When they fill in all required fields (Name, Email, Message, Inquiry Type [e.g., "Educational Administrator", "Parent/Guardian"]) and submit the form
    Then the system should display a confirmation message that the form has been successfully submitted
    And the submitted details should be received by the RutaKids team.

    Examples:
      | Name       | Email                  | Message                          | Inquiry Type            | Status    |
      | Ana Perez  | ana.perez@school.edu   | Information about implementation. | Educational Administrator | Submitted |
      | Luis Gomez | luis.gomez@email.com   | Question about the mobile app.   | Parent/Guardian         | Submitted |

  Scenario: Missing required fields in the contact form
    Given the visitor is filling out the contact form
    When they leave required fields empty and try to submit
    Then the system should display an error message indicating the missing fields.

    Examples:
      | Name       | Email                  | Message                          | Missing Field | Expected Error Message     |
      | Ana Perez  |                        | Information about implementation. | Email         | "Email is required"        |
      |            | luis.gomez@email.com   |                                  | Message       | "Message is required"      |
```

```gherkin
Feature: US42 - Relevant Multimedia Content on the Landing Page
  As a visitor,
  I want to find attractive multimedia content on the RutaKids landing page
  So that I can learn about the features of the admin portal and mobile app in a dynamic and visual way.

  Scenario: Display multimedia content successfully
    Given the visitor is on the landing page
    When they scroll through sections with multimedia content
    Then they should see images, short videos, or icons that explain RutaKids' functionality (admin portal and mobile app)
    And the multimedia content should load quickly and display correctly.

    Examples:
      | Media Type    | Expected Content                                          | Expected Behavior                               |
      | Images        | Screenshots of the admin portal, mobile app mockups.      | Display correctly, optimized for loading.        |
      | Short Videos  | Brief system usage demonstrations.                        | Play smoothly, without excessive buffering.      |
      | Icons         | Representative iconography for features.                  | Scale appropriately without distortion.          |

  Scenario: Ensure multimedia content is responsive across devices
    Given the visitor accesses the landing page from different devices
    When they view sections with multimedia content
    Then the multimedia content should adjust to fit the screen size and resolution without losing quality or functionality.

    Examples:
      | Device   | Expected Behavior                                                         |
      | Mobile   | Images and videos scale, layout is responsive.                           |
      | Tablet   | Images and videos adapt to a medium screen layout.                       |
      | Desktop  | Full resolution, multimedia fills the space appropriately.               |
```

```gherkin
Feature: US43 - Clear and Effective Call-to-Actions (CTAs) on the Landing Page
  As a visitor,
  I want to find clear and prominent call-to-action (CTA) buttons on the landing page
  So that I can take immediate actions, like registering my institution or learning more about the parent mobile app.

  Scenario: Clear CTA buttons guide visitor actions towards new components
    Given the visitor is on the RutaKids landing page
    When they see the "Register Institution", "Learn About Parent App", or "Request Demo" buttons
    Then the buttons should be visually prominent and easily identifiable
    And upon clicking, they should redirect to the correct sections or pages related to the admin portal or mobile app.

    Examples:
      | CTA Text                 | Expected Behavior                                                                         |
      | "Register Institution"   | Redirects the visitor to the start of the admin web application registration flow.       |
      | "Learn About Parent App" | Redirects the visitor to a section/page with detailed information about the mobile app and download/access links. |
      | "Request Demo"           | Redirects the visitor to the contact form, ideally with the demo purpose pre-selected.   |

  Scenario: CTA buttons work correctly across devices
    Given the visitor accesses the landing page from different devices (mobile, tablet, desktop)
    When they interact with CTA buttons
    Then the buttons should be responsive, easily clickable, and work correctly on all screen sizes.

    Examples:
      | Device   | Expected Behavior                                                                |
      | Mobile   | Buttons are visible, appropriately sized for touch, and functional.             |
      | Tablet   | Buttons scale correctly, remain interactive and functional.                      |
      | Desktop  | Full-sized buttons, clear, interactive, and functional.                          |
```

\newpage

::: info
***Backend US - Gherkin***
:::


```gherkin
Feature: US01 - API for Educational Administrator Account Management
  As a client application for the RutaKids system,
  I want to interact with secure API endpoints for managing educational administrator accounts,
  So that administrators can register, log in, and manage their credentials.

  Scenario: Successful administrator registration
    Given the client application has valid administrator registration data (name, email, password, institution details)
    When a POST request is made to "/api/v1/admins/register" with the administrator data
    Then the system should create a new administrator account
    And respond with HTTP status 201 (Created)
    And the response should include administrator details (excluding sensitive data like password)
    # And a confirmation process (e.g., email verification) should be initiated (Admin EP01-US02) - Implicit or separate US

  Scenario: Administrator registration with an already existing email
    Given an administrator account already exists with "admin@school.com"
    When a POST request is made to "/api/v1/admins/register" with "admin@school.com" and other valid data
    Then the system should not create a new administrator account
    And respond with HTTP status 409 (Conflict)
    And the response body should contain an error message indicating the email is already in use.

  Scenario: Successful administrator login
    Given an administrator account exists for "admin@school.com" with password "securePassword123"
    When a POST request is made to "/api/v1/admins/login" with "admin@school.com" and "securePassword123"
    Then the system should authenticate the administrator
    And respond with HTTP status 200 (OK)
    And the response body should contain a JWT access token.

  Scenario: Administrator login with incorrect credentials
    Given an administrator account exists for "admin@school.com"
    When a POST request is made to "/api/v1/admins/login" with "admin@school.com" and "wrongPassword"
    Then the system should not authenticate the administrator
    And respond with HTTP status 401 (Unauthorized)
    And the response body should contain an error message indicating invalid credentials.

  Scenario: Successful administrator password recovery request
    Given an administrator account exists for "admin@school.com"
    When a POST request is made to "/api/v1/admins/password-recovery/request" with "email": "admin@school.com"
    Then the system should initiate the password recovery process (e.g., send a reset link)
    And respond with HTTP status 200 (OK)
    And the response body should contain a success message.

  Scenario: Administrator password recovery request for a non-existent email
    When a POST request is made to "/api/v1/admins/password-recovery/request" with "email": "nonexistent@school.com"
    Then the system should not find the administrator account
    And respond with HTTP status 404 (Not Found)
    And the response body should contain an error message.
```

```gherkin
Feature: US02 - API for Parent/Tutor Account Management
  As a client application for the RutaKids system,
  I want to interact with secure API endpoints for managing parent/tutor accounts,
  So that parents/tutors can register, log in, and manage their profiles.

  Scenario: Successful parent/tutor registration
    Given the client application has valid parent/tutor registration data (name, email, password, children association info)
    When a POST request is made to "/api/v1/parents/register" with the parent/tutor data
    Then the system should create a new parent/tutor account
    And respond with HTTP status 201 (Created)
    And the response should include parent/tutor details (excluding sensitive data).

  Scenario: Parent/tutor registration with an already existing email
    Given a parent/tutor account already exists with "parent@family.com"
    When a POST request is made to "/api/v1/parents/register" with "parent@family.com" and other valid data
    Then the system should not create a new parent/tutor account
    And respond with HTTP status 409 (Conflict).

  Scenario: Successful parent/tutor login
    Given a parent/tutor account exists for "parent@family.com" with password "myChildsSafe123"
    When a POST request is made to "/api/v1/parents/login" with "parent@family.com" and "myChildsSafe123"
    Then the system should authenticate the parent/tutor
    And respond with HTTP status 200 (OK)
    And the response body should contain a JWT access token.

  Scenario: Parent/tutor login with incorrect credentials
    Given a parent/tutor account exists for "parent@family.com"
    When a POST request is made to "/api/v1/parents/login" with "parent@family.com" and "wrongPassword"
    Then the system should not authenticate the parent/tutor
    And respond with HTTP status 401 (Unauthorized).

  Scenario: Successful parent/tutor profile update
    Given a parent/tutor is logged in with a valid JWT token for "parent@family.com"
    And the client application has updated profile data (e.g., phone number, notification preferences)
    When a PUT request is made to "/api/v1/parents/profile" with the updated data and the JWT token in the Authorization header
    Then the system should update the parent/tutor's profile
    And respond with HTTP status 200 (OK)
    And the response should include the updated parent/tutor details.

  Scenario: Attempt to update parent/tutor profile without authentication
    When a PUT request is made to "/api/v1/parents/profile" with profile data but without a valid JWT token
    Then the system should reject the request
    And respond with HTTP status 401 (Unauthorized).
```

```gherkin
Feature: US03 - JWT-based Authentication and Authorization for APIs
  As a client application,
  I want API endpoints to be secured using JWT (JSON Web Tokens),
  So that only authenticated and authorized users can access protected resources.

  Scenario: Successful access to a protected resource with a valid JWT
    Given a user (administrator or parent) is logged in and has a valid JWT token
    When a GET request is made to a protected endpoint (e.g., "/api/v1/admins/dashboard-data" or "/api/v1/parents/my-children/status") with the JWT in the Authorization header
    Then the system should validate the JWT
    And grant access to the resource
    And respond with HTTP status 200 (OK)
    And the response body should contain the requested data.

  Scenario: Denied access to a protected resource with an invalid or expired JWT
    Given a user attempts to access a protected endpoint with an invalid or expired JWT token
    When a GET request is made to a protected endpoint (e.g., "/api/v1/admins/dashboard-data") with the invalid/expired JWT
    Then the system should validate the JWT and find it invalid/expired
    And deny access to the resource
    And respond with HTTP status 401 (Unauthorized)
    And the response body should contain an error message indicating token invalidity or expiration.

  Scenario: Denied access to a protected resource without a JWT
    When a GET request is made to a protected endpoint (e.g., "/api/v1/parents/my-children/status") without a JWT in the Authorization header
    Then the system should deny access
    And respond with HTTP status 401 (Unauthorized)
    And the response body should contain an error message indicating authentication is required.
```

```gherkin
Feature: US04 - API for Initial Fleet Management (Vehicles)
  As an authenticated Educational Administrator client application,
  I want to interact with API endpoints for managing vehicle information,
  So that I can register, view, update, and list vehicles in the system.

  Scenario: Successfully register a new vehicle
    Given the client application is authenticated as an Educational Administrator
    And has valid vehicle data (plate number "XYZ-123", model "School Bus 2023", capacity 30)
    When a POST request is made to "/api/v1/vehicles" with the vehicle data
    Then the system should create a new vehicle record
    And respond with HTTP status 201 (Created)
    And the response body should include the details of the created vehicle.

  Scenario: Attempt to register a vehicle with a duplicate plate number
    Given the client application is authenticated as an Educational Administrator
    And a vehicle with plate number "ABC-789" already exists
    When a POST request is made to "/api/v1/vehicles" with plate number "ABC-789" and other data
    Then the system should not create the vehicle
    And respond with HTTP status 409 (Conflict)
    And the response body should contain an error message about the duplicate plate number.

  Scenario: Successfully retrieve a list of all vehicles
    Given the client application is authenticated as an Educational Administrator
    And multiple vehicles are registered in the system
    When a GET request is made to "/api/v1/vehicles"
    Then the system should respond with HTTP status 200 (OK)
    And the response body should contain a list of all registered vehicles.

  Scenario: Successfully retrieve details for a specific vehicle
    Given the client application is authenticated as an Educational Administrator
    And a vehicle with ID "vehicle-id-001" exists
    When a GET request is made to "/api/v1/vehicles/vehicle-id-001"
    Then the system should respond with HTTP status 200 (OK)
    And the response body should contain the details of vehicle "vehicle-id-001".

  Scenario: Successfully update an existing vehicle's information
    Given the client application is authenticated as an Educational Administrator
    And a vehicle with ID "vehicle-id-002" exists
    And the client has new data for the vehicle (e.g., capacity 35, status "Active")
    When a PUT request is made to "/api/v1/vehicles/vehicle-id-002" with the new data
    Then the system should update the vehicle's information
    And respond with HTTP status 200 (OK)
    And the response body should include the updated vehicle details.
```

```gherkin
Feature: US05 - API for Geolocation Data Capture and Query (Basic IoT)
  As a client application (IoT device or backend service),
  I want to submit vehicle geolocation data,
  And as an authenticated client application (Admin Web or Parent Mobile),
  I want to query the real-time location of vehicles.

  Scenario: Successfully submit vehicle geolocation data
    Given an IoT device for vehicle "V-101" has new geolocation data (latitude 10.123, longitude -70.456, speed 50km/h, timestamp)
    When a POST request is made to "/api/v1/iot/location-updates" with the geolocation data for "V-101"
    Then the system should process and store the geolocation update
    And respond with HTTP status 202 (Accepted) or 200 (OK) if processed synchronously.

  Scenario: Attempt to submit invalid geolocation data
    Given an IoT device attempts to submit geolocation data with missing required fields (e.g., missing vehicleId or coordinates)
    When a POST request is made to "/api/v1/iot/location-updates" with the invalid data
    Then the system should reject the data
    And respond with HTTP status 400 (Bad Request)
    And the response body should contain an error message detailing the validation errors.

  Scenario: Successfully query real-time location of a specific vehicle (for Parent App)
    Given a Parent is logged in and is authorized to view the location of the bus assigned to their child (e.g., vehicle "V-101")
    And vehicle "V-101" has recent geolocation updates
    When a GET request is made to "/api/v1/vehicles/V-101/location" (or similar endpoint) with a valid JWT
    Then the system should respond with HTTP status 200 (OK)
    And the response body should contain the latest known location (latitude, longitude, speed, timestamp) of vehicle "V-101".

  Scenario: Query location for a vehicle with no recent data or non-existent vehicle (for Parent App)
    Given a Parent is logged in and requests the location for vehicle "V-999" which has no data or doesn't exist
    When a GET request is made to "/api/v1/vehicles/V-999/location" with a valid JWT
    Then the system should respond with HTTP status 404 (Not Found)
    And the response body should contain an appropriate message (e.g., "Location data not available" or "Vehicle not found").
```

```gherkin
Feature: US06 - API Gateway Routing and Microservice Accessibility
  As a client application,
  I want to interact with a unified API gateway
  So that my requests are correctly routed to the appropriate backend microservices without needing to know their individual addresses.

  Scenario: API Gateway successfully routes request to Accounts Microservice
    Given the Accounts Microservice is running and registered with the API Gateway
    When a POST request is made to the API Gateway at "/api/v1/admins/login" with valid administrator credentials
    Then the API Gateway should route the request to the Accounts Microservice
    And the Accounts Microservice should process the login
    And the API Gateway should return the Accounts Microservice's response (e.g., HTTP 200 OK with JWT).

  Scenario: API Gateway successfully routes request to Fleet Microservice
    Given the Fleet Microservice is running and registered with the API Gateway
    And the client is authenticated as an Educational Administrator
    When a GET request is made to the API Gateway at "/api/v1/vehicles"
    Then the API Gateway should route the request to the Fleet Microservice
    And the Fleet Microservice should process the request
    And the API Gateway should return the Fleet Microservice's response (e.g., HTTP 200 OK with a list of vehicles).

  Scenario: API Gateway handles request to a non-existent microservice path
    When a GET request is made to the API Gateway at "/api/v1/non-existent-service/data"
    Then the API Gateway should determine that no microservice handles this path
    And respond with HTTP status 404 (Not Found) or an appropriate gateway error.
```

```gherkin
Feature: US37 - Pagination and Filtering of API Results
  As a client application,
  I want to request paginated and filtered lists of resources from the API,
  So that I can retrieve data efficiently and display it in manageable chunks.

  Scenario: Retrieve a paginated list of resources (e.g., vehicles)
    Given there are 50 vehicle records in the system
    When a GET request is made to "/api/v1/vehicles?page=2&size=10"
    Then the system should respond with HTTP status 200 (OK)
    And the response body should contain 10 vehicle records, corresponding to the second page
    And the response should include pagination metadata (total items, total pages, current page, page size).

  Scenario: Retrieve a filtered list of resources (e.g., vehicles by status)
    Given there are vehicles with status "Active" and "Inactive"
    When a GET request is made to "/api/v1/vehicles?status=Active"
    Then the system should respond with HTTP status 200 (OK)
    And the response body should contain only vehicles with the status "Active".

  Scenario: Retrieve a paginated and filtered list of resources
    Given there are 30 vehicles with status "Active"
    When a GET request is made to "/api/v1/vehicles?status=Active&page=1&size=5"
    Then the system should respond with HTTP status 200 (OK)
    And the response body should contain the first 5 vehicles with status "Active"
    And the response should include relevant pagination metadata for the filtered set.

    Examples: Resource Endpoints
      | ResourcePath     | FilterParameter | Page | Size |
      | /api/v1/vehicles | status=OutOfService | 1    | 20   |
      | /api/v1/users    | role=driver         | 3    | 10   |
```

\newpage

::: info
***Frontend US (Web Admin Application) - Gherkin***
:::

```gherkin
Feature: US07 - Web Admin: Administrator Registration and Login Interface
  As an Educational Administrator,
  I want to use a web interface to register a new institutional account and log in,
  So that I can securely access the RutaKids administration platform.

  Scenario: Successful new administrator registration via web form
    Given I am on the RutaKids administrator registration page
    When I fill in the registration form with valid details (institution name "Colegio Ejemplo", my name "Jane Doe", email "jane.doe@colegio.ejemplo.com", password "SecurePass123", confirm password "SecurePass123")
    And I submit the registration form
    Then I should see a success message indicating my registration is processing or requires confirmation
    And I should be redirected to a confirmation pending page or the login page.
    # And an API call to the backend (US01 - Admin Registration) should be made

  Scenario: Attempt administrator registration with mismatched passwords
    Given I am on the RutaKids administrator registration page
    When I fill in the registration form with email "john.doe@school.org", password "Pass1", and confirm password "Pass2"
    And I submit the registration form
    Then I should see an error message on the page stating "Passwords do not match."
    And the form should not be submitted.

  Scenario: Attempt administrator registration with an already registered email
    Given an administrator account with "jane.doe@colegio.ejemplo.com" already exists
    When I attempt to register using "jane.doe@colegio.ejemplo.com" again on the web form
    And I submit the registration form
    Then I should see an error message on the page stating "This email is already registered."
    # And an API call to the backend (US01 - Admin Registration) results in a conflict

  Scenario: Successful administrator login via web form
    Given I am on the RutaKids administrator login page
    And an administrator account exists for "admin@rutakids.com" with password "AdminPass!"
    When I enter "admin@rutakids.com" in the email field
    And I enter "AdminPass!" in the password field
    And I click the "Login" button
    Then I should be redirected to the administrator dashboard
    And I should see elements indicating a successful login (e.g., my username, dashboard content).
    # And an API call to the backend (US01 - Admin Login) should be successful

  Scenario: Administrator login with incorrect credentials via web form
    Given I am on the RutaKids administrator login page
    When I enter "admin@rutakids.com" in the email field
    And I enter "WrongPassword" in the password field
    And I click the "Login" button
    Then I should remain on the login page or see it re-rendered
    And I should see an error message on the page stating "Invalid email or password."

  Scenario: Accessing password recovery interface
    Given I am on the RutaKids administrator login page
    When I click the "Forgot Password?" link
    Then I should be navigated to the password recovery page
    Where I can enter my email to initiate the recovery process.
```

```gherkin
Feature: US08 - Web Admin: Initial Dashboard and Profile Management Interface
  As an Educational Administrator,
  I want to access an initial dashboard with key information and manage my profile settings,
  So that I can have an overview of the system and keep my account details up to date.

  Scenario: View initial administrator dashboard after login
    Given I am an Educational Administrator and I have successfully logged into the web platform
    When I land on the administrator dashboard page
    Then I should see a welcome message or my institution's name
    And I should see placeholders or initial Key Performance Indicators (KPIs) (e.g., "Total Vehicles: N/A", "Active Routes: N/A") (Ref: Admin EP07-US01)
    And I should see navigation options to other sections of the admin portal (e.g., "Fleet Management", "User Management").

  Scenario: Navigate to and view profile management page
    Given I am logged in as an Educational Administrator
    When I navigate to the "My Profile" or "Account Settings" section from the dashboard or main navigation
    Then I should see a page displaying my current profile information (e.g., Name, Email, Institution) (Ref: Admin EP01-US06)
    And I should see options to edit my profile information.

  Scenario: Successfully update profile information
    Given I am on my profile management page
    And my current name is "Jane Doe"
    When I change my name to "Jane A. Doe" in the profile form
    And I save the changes
    Then I should see a success message "Profile updated successfully."
    And my displayed name on the profile page and potentially in the header should reflect "Jane A. Doe".
    # And an API call to update the profile on the backend should be made

  Scenario: Attempt to update profile with invalid data (e.g., invalid email format)
    Given I am on my profile management page
    When I try to change my email to an invalid format like "jane.doe"
    And I save the changes
    Then I should see an error message on the page stating "Invalid email format."
    And my email should not be updated.
```

```gherkin
Feature: US09 - Web Admin: Initial Vehicle Management Interface
  As an Educational Administrator,
  I want to use a web interface to view, add, and edit vehicle information,
  So that I can manage the school's transport fleet effectively.

  Scenario: View list of registered vehicles
    Given I am logged in as an Educational Administrator
    And I navigate to the "Fleet Management" or "Vehicles" section
    When the page loads
    Then I should see a table or list displaying registered vehicles with key details (e.g., Plate Number, Model, Capacity, Status).
    And if no vehicles are registered, I should see a message like "No vehicles registered yet. Add a new vehicle."
    # And an API call to the backend (US04 - List Vehicles) should be made

  Scenario: Successfully add a new vehicle via web form
    Given I am on the vehicle management page
    When I click the "Add New Vehicle" button
    And I fill in the new vehicle form with valid data (Plate: "NEW-001", Model: "Minibus", Capacity: 20, Status: "Active")
    And I submit the form
    Then I should see a success message "Vehicle NEW-001 added successfully."
    And the new vehicle "NEW-001" should appear in the list of vehicles.
    # And an API call to the backend (US04 - Register Vehicle) should be made

  Scenario: Attempt to add a new vehicle with missing required fields
    Given I am on the new vehicle form
    When I fill in the Plate as "BAD-002" but leave the Capacity field empty
    And I submit the form
    Then I should see an error message on the page next to the Capacity field, like "Capacity is required."
    And the vehicle should not be added.

  Scenario: Successfully edit an existing vehicle's information
    Given I am on the vehicle management page and vehicle "EDIT-003" with Capacity 15 exists
    When I select vehicle "EDIT-003" to edit
    And I change its Capacity to 18 in the edit form
    And I save the changes
    Then I should see a success message "Vehicle EDIT-003 updated successfully."
    And the vehicle "EDIT-003" in the list should now show Capacity 18.
    # And an API call to the backend (US04 - Update Vehicle) should be made

  Scenario: Navigate to vehicle details page (if applicable)
    Given I am on the vehicle management page and vehicle "DETAIL-004" exists
    When I click on vehicle "DETAIL-004" or a "View Details" button associated with it
    Then I should be navigated to a page showing more comprehensive details for vehicle "DETAIL-004".
```

\newpage

::: info
***Mobile App US (Parent/Tutor Application) - Gherkin***
:::

```gherkin
Feature: US10 - Mobile App: Parent/Tutor Registration and Login
  As a Parent/Tutor,
  I want to register for an account and log in using the mobile app,
  So that I can access RutaKids features to monitor my child's transport.

  Scenario: Successful new parent/tutor registration via mobile app form
    Given I am on the RutaKids mobile app registration screen
    When I fill in the registration form with my valid details (Name "John Parent", Email "john.parent@example.com", Password "MyChildsSafeR!de", Confirm Password "MyChildsSafeR!de", and information to link to my child/children)
    And I tap the "Register" button
    Then I should see a success message on the screen (e.g., "Registration successful! Please check your email for verification.") or be taken to a verification pending screen
    And my account creation process should be initiated.
    # And an API call to the backend (US02 - Parent/Tutor Registration) should be made

  Scenario: Attempt parent/tutor registration with mismatched passwords in mobile app
    Given I am on the RutaKids mobile app registration screen
    When I fill in the registration form with email "jane.parent@example.com", password "PassA", and confirm password "PassB"
    And I tap the "Register" button
    Then I should see an error message on the screen stating "Passwords do not match."
    And the form should not be submitted.

  Scenario: Attempt parent/tutor registration with an already registered email in mobile app
    Given a parent/tutor account with "john.parent@example.com" already exists
    When I attempt to register using "john.parent@example.com" again in the mobile app
    And I tap the "Register" button
    Then I should see an error message on the screen stating "This email is already registered."
    # And an API call to the backend (US02 - Parent/Tutor Registration) results in a conflict

  Scenario: Successful parent/tutor login via mobile app
    Given I am on the RutaKids mobile app login screen
    And a parent/tutor account exists for "lucy.guardian@example.com" with password "SecureApp123"
    When I enter "lucy.guardian@example.com" in the email field
    And I enter "SecureApp123" in the password field
    And I tap the "Login" button
    Then I should be navigated to the main screen or dashboard of the mobile app
    And I should see elements indicating a successful login (e.g., my child's name, map view).
    # And an API call to the backend (US02 - Parent/Tutor Login) should be successful

  Scenario: Parent/tutor login with incorrect credentials via mobile app
    Given I am on the RutaKids mobile app login screen
    When I enter "lucy.guardian@example.com" in the email field
    And I enter "WrongPassword" in the password field
    And I tap the "Login" button
    Then I should remain on the login screen or see it re-rendered
    And I should see an error message on the screen stating "Invalid email or password."

  Scenario: Accessing password recovery from mobile app login screen
    Given I am on the RutaKids mobile app login screen
    When I tap the "Forgot Password?" link or button
    Then I should be navigated to a password recovery screen within the app
    Where I can enter my email to initiate the recovery process.
```

```gherkin
Feature: US11 - Mobile App: Real-time Vehicle Location Tracking
  As a Parent/Tutor,
  I want to view the real-time location of my child's assigned transport vehicle on a map within the mobile app,
  So that I can be informed about the progress of their journey.

  Scenario: View real-time location of the assigned vehicle on the map
    Given I am logged into the RutaKids mobile app
    And my child is assigned to a bus (e.g., "BUS-A1") which is currently on its route
    And the bus "BUS-A1" is transmitting location updates
    When I navigate to the "Track Ride" or "Map View" screen
    Then I should see a map displayed on the screen
    And I should see an icon representing my child's bus "BUS-A1" at its current location on the map
    And the icon's position should update periodically to reflect real-time movement.
    # And an API call to the backend (US05 - Query Vehicle Location) should be made to fetch location data

  Scenario: Map displays correctly on different mobile devices and orientations
    Given I am logged into the RutaKids mobile app and viewing the map screen
    When I use the app on different mobile devices (e.g., Android, iOS, varying screen sizes)
    Or I rotate my device screen (portrait/landscape)
    Then the map should render correctly, filling the available space appropriately
    And all map controls (zoom, pan) should remain functional.

  Scenario: Handling situation when vehicle location data is unavailable
    Given I am logged into the RutaKids mobile app
    And my child's assigned bus "BUS-B2" is not currently transmitting location data (e.g., out of service, GPS issue)
    When I navigate to the "Track Ride" or "Map View" screen for "BUS-B2"
    Then I should see a message on the screen like "Vehicle location is currently unavailable" or "Bus is not active"
    And the map might show a default view or the last known location with a clear indicator of its staleness.

  Scenario: Display basic route information along with vehicle location (Future Enhancement Hint)
    Given I am viewing the real-time location of my child's bus "BUS-C3"
    When the map screen loads
    Then I might see a faint overlay or markers indicating the planned route for "BUS-C3" (Ref: Tutor EP02-US02)
    And I might see an estimated time of arrival (ETA) to the next stop or destination (Ref: Tutor EP02-US03).
    # This scenario hints at related functionalities that might be built upon this core tracking.
```

```gherkin
Feature: US12 - Mobile App: Initial Notification Configuration and Reception
  As a Parent/Tutor,
  I want to manage basic notification preferences in the mobile app and receive initial critical alerts,
  So that I can stay informed about important events related to my child's transport.

  Scenario: Access notification settings screen
    Given I am logged into the RutaKids mobile app
    When I navigate to the "Settings" or "Notifications" section within the app
    Then I should see a screen where I can manage my notification preferences (Ref: Tutor EP01-US04, Tutor EP06-US01).

  Scenario: Enable/Disable a basic notification type (e.g., "Child Aboard Vehicle")
    Given I am on the notification settings screen
    And there is an option to toggle notifications for "Child Aboard Vehicle"
    When I toggle the "Child Aboard Vehicle" notification switch to "ON" (or "OFF")
    Then the setting should be saved
    And I should receive (or stop receiving) this type of notification accordingly.
    # And an API call might be made to the backend to store this preference

  Scenario: Receive a "Child Aboard Vehicle" push notification
    Given I have "Child Aboard Vehicle" notifications enabled in the mobile app
    And my child has just boarded their assigned school bus
    And the system detects this event (e.g., via RFID scan, Ref: Admin EP03-US02)
    When the event occurs
    Then I should receive a push notification on my mobile device stating something like "Notification: [Child's Name] has boarded bus [Bus ID]." (Ref: Tutor EP03-US01)

  Scenario: Receive a "Vehicle Arrived at Destination" push notification
    Given I have relevant arrival notifications enabled
    And my child's bus has just completed its route and arrived at the school (or home stop)
    When the bus arrival event is registered by the system
    Then I should receive a push notification on my mobile device stating something like "Notification: Bus [Bus ID] has arrived at [Destination]." (Ref: Tutor EP03-US02)

  Scenario: View notification history (basic placeholder)
    Given I have received several notifications
    When I navigate to a "Notification History" or "Alerts" section in the app (if available in this sprint)
    Then I should see a list of recent notifications I have received.
    # This is a basic placeholder; full history might be a later feature (Ref: Tutor EP05)
```

\newpage

#### Execution Evidence for Sprint Review

Durante el Sprint 3, se llevaron a cabo los despliegues e integraciones clave de los distintos componentes desarrollados del sistema \textbf{RutaKids}. Esta sección recopila evidencias visuales del estado actual de implementación de cada uno de estos módulos: landing page, aplicación web administrativa, aplicación móvil y backend basado en microservicios. También se incluyen los enlaces a los repositorios respectivos y visualizaciones funcionales, lo que permite verificar que las entregas planificadas para este sprint han sido efectivamente concretadas.


::: box
**Implemented Landing Page Evidence**
:::

::: warn
Para acceder al repositorio de este proyecto, haga click a la [URL](https://github.com/orgs/LlantaTech/repositories)
:::

**Captura del repositorio:**

![Organización LLantatech, imagen extraída de Github](src/img/cap6/landing-deploy-1.png){ width=80% }

\newpage

**Landing Page en funcionamiento:**

::: warn
Para acceder a la landing page, haga click a la [URL](https://llantatech.org.pe/)
:::

![Organización LLantatech, imagen extraída de Github](src/img/cap6/landing-deploy-2.png){ width=80% }

\newpage

::: box
**Implemented Frontend-Web Application Evidence**
:::

::: warn
Para acceder al repositorio de este proyecto, haga click a la [URL](https://github.com/orgs/LlantaTech/repositories)
:::

**Captura del repositorio:**

![Organización LLantatech, imagen extraída de Github](src/img/cap6/webapp-deploy-1.png){ heigth=35% }

**Web Application en funcionamiento:**


::: warn
Para acceder a la pagina web, haga click a la [URL](https://rutakids.llantatech.org.pe/)
:::


![Organización LLantatech, imagen extraída de Github](src/img/cap6/webapp-deploy-2.jpg){ heigth=35% }

\newpage


::: box
**Implemented Native-Mobile Application Evidence**
:::

::: warn
Para acceder al repositorio de este proyecto, haga click a la [URL](https://www.figma.com/design/ph6aTjM4mzxkNic0Hk4VLX/RutaKids?node-id=275-3006&t=aZ58NPtaowKWvMte-1)
:::

**Captura del figma:**

![Organización LLantatech, imagen extraída de Figma](src/img/cap6/rutakids-mobileapp-github-implementation.png){ width=80% }

**Mobile Application en funcionamiento:**

![Organización LLantatech, imagen extraída de Figma](src/img/cap6/mobile-app-figma-view.png){ width=50% }

\newpage

::: box
**Implemented RESTful API and/or Serverless Backend Evidence**
:::

::: warn
Para acceder al repositorio de este proyecto, haga click a la [URL](https://github.com/LlantaTech/ruta-kids-microservicios)
:::

::: warn
Para acceder a la documentación swagger de este proyecto, haga click a la [URL](https://api.rutakids.llantatech.org.pe/swagger-ui/index.html?urls.primaryName=Transportation+Service)
:::

**Captura del repositorio:**

![Organización LLantatech, imagen extraída de Github](src/img/cap6/webservices-deploy-1.png){ height=35% }

**Web Service Application en funcionamiento:**

![Organización LLantatech, imagen extraída de Github](src/img/cap6/webservices-deploy-2.jpg){ height=35% }


\newpage

**RESTful API documentation**

::: warn
Para acceder al repositorio de este proyecto, haga click a la [URL](https://github.com/LlantaTech/ruta-kids-microservicios)
:::

**Captura del repositorio:**

![Organización LLantatech, imagen extraída de Github](src/img/cap6/webservices-doc.png)

\newpage


#### Services Documentation Evidence for Sprint Review


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


**IoT Services Documentation Evidence for Sprint Review**

Como parte del Sprint 3, se logró la implementación funcional del dispositivo IoT destinado a mejorar la seguridad en el transporte escolar. Este dispositivo fue instalado en las unidades vehiculares y se integró completamente con los microservicios backend del sistema RutaKids.

- **Componentes de Hardware Utilizados**

  El prototipo fue construido con los siguientes elementos:

  - ESP32: Microcontrolador principal, encargado de gestionar sensores y comunicaciones.

  - Raspberry Pi: Nodo auxiliar usado para tareas de gateway local, procesamiento intermedio o comunicación con servicios cloud.

  - 3 sensores DHT22: Captura de temperatura interna en diferentes puntos del vehículo.

  - Módulo GPS NEO-6M: Geolocalización en tiempo real del vehículo escolar.

  - Lector RFID PN532: Identificación de ingreso/salida de estudiantes mediante tarjetas RFID.

  - Módulo I2C: Expansión de bus para facilitar la comunicación entre dispositivos.

  - Pantalla LCD 16x2 (I2C): Visualización local de mensajes, estado del sistema y confirmaciones al conductor.

- **Tecnologías de Software y Protocolos de Comunicación**
  
  El dispositivo IoT utiliza tecnologías modernas y livianas para garantizar una comunicación eficiente y estable:

  - MQTT para comunicación asincrónica entre el dispositivo y los microservicios backend.

  - **Cliente MQTT:** PubSubClient (Arduino).

  - **Broker MQTT:** Mosquitto, desplegado en nube.

  - **WiFiClient:** Gestión de la conexión a internet mediante redes inalámbricas.

  - **NMEA Parser:** Decodificación de datos GPS desde el módulo NEO-6M.

  - **RFID library PN532:** Gestión de escaneo e identificación de tarjetas.

  ::: warn
  https://pubsubclient.knolleary.net/ – Cliente MQTT para microcontroladores
  https://mosquitto.org/documentation/ – Broker MQTT ligero y escalable
  https://www.arduino.cc/en/Reference/WiFiClient – Cliente WiFi embebido para ESP32
  :::


\newpage

#### Software Deployment Evidence for Sprint Review


::: warn
Para acceder a la landing page, haga click a la [URL](https://llantatech.org.pe/)
:::

***Landing Page Deployment*** : https://llantatech.org.pe/ 

![Organización LLantatech, imagen extraída de Github](src/img/cap6/landing-deploy-2.png){ width=80% }


**Web Application Deployment** : https://rutakids.llantatech.org.pe/

![Organización LLantatech, imagen extraída de Github](src/img/cap6/webapp-deploy-2.jpg){ width=80% }

::: warn
Para acceder a la pagina web, haga click a la [URL](https://rutakids.llantatech.org.pe/)
:::


\newpage

**Mobile Application Deployment**

![Organización LLantatech, imagen extraída del Github](src/img/cap6/mobile-app-figma-view.png){ width=50% }


**Web Service Deployment**: https://tinyurl.com/swaggerDocumentation 

![Organización LLantatech, imagen extraída de Github](src/img/cap6/webservices-deploy-2.jpg){ width=80% }

::: warn
Para acceder a la documentación swagger de este proyecto, haga click a la [URL](https://api.rutakids.llantatech.org.pe/swagger-ui/index.html?urls.primaryName=Transportation+Service)
:::

\newpage

#### Team Collaboration Insights during Sprint

Durante el Sprint 3, el equipo de trabajo colaboró activamente mediante herramientas de gestión como GitHub Projects y GitHub Insights. A continuación se presenta la evidencia de las interacciones, tráfico y flujos de trabajo utilizados para garantizar una entrega continua y coordinada.

::: warn
Para acceder los insights de este proyecto, haga click a la [URL](https://github.com/orgs/LlantaTech/repositories)
:::

**Tablero Kanban:**

![Organización LLantatech, imagen extraída de Github](src/img/cap6/insights-kanban-todo-1.png){ width=80% }

**Kanban List:**

![Organización LLantatech, imagen extraída de Github](src/img/cap6/insights-kanban-list-1.png){ width=80% }

\newpage

**Network Graph:**

![Organización LLantatech, imagen extraída de Github](src/img/cap6/insights-network-graph-tb2.png){ width=80% }

**Traffic Map:**

![Organización LLantatech, imagen extraída de Github](src/img/cap6/insights-traffic-map-tb2.png){ width=80% }

\newpage


## Validation Interviews


Las entrevistas de validación constituyen una herramienta cualitativa fundamental en la evaluación temprana de productos digitales, ya que permiten recopilar información directa y contextualizada sobre la experiencia de uso desde la perspectiva de los usuarios finales. En el presente proyecto, se llevaron a cabo entrevistas semiestructuradas con individuos representativos de los segmentos objetivo de la solución *RutaKids*, con el propósito de validar su adecuación funcional, nivel de usabilidad y grado de satisfacción percibida.

Estas entrevistas se diseñaron cuidadosamente para cubrir los principales puntos de contacto del sistema, incluyendo:

* La **landing page** promocional, orientada a captar nuevos usuarios y comunicar el valor diferencial de la propuesta.
* El **dashboard escolar** (aplicación web), dirigido a instituciones educativas y personal administrativo encargado de la gestión de rutas, alumnos y control logístico.
* La **aplicación móvil**, orientada principalmente a padres de familia y/o apoderados, quienes monitorean en tiempo real la ubicación y estado del transporte escolar.

Durante las sesiones, se solicitaron a los participantes que ejecutaran tareas específicas previamente definidas por el equipo (por ejemplo: registrarse, asignar un alumno, monitorear una ruta o revisar notificaciones). Al mismo tiempo, se documentaron tanto sus reacciones espontáneas como sus comentarios verbales, siguiendo la técnica del *think-aloud protocol*, que facilita la identificación de puntos de fricción, malentendidos o barreras cognitivas.

::: warn
Para acceder al video de las entrevistas, haga click en la [URL](https://upcedupe-my.sharepoint.com/:v:/g/personal/u202210059_upc_edu_pe/EV28HExaIsFIh22vN6-VY-sBzdw5JApHhMXCx5KyLMdBPQ?nav=eyJyZWZlcnJhbEluZm8iOnsicmVmZXJyYWxBcHAiOiJTdHJlYW1XZWJBcHAiLCJyZWZlcnJhbFZpZXciOiJTaGFyZURpYWxvZy1MaW5rIiwicmVmZXJyYWxBcHBQbGF0Zm9ybSI6IldlYiIsInJlZmVycmFsTW9kZSI6InZpZXcifX0%3D&e=X20C3t)
:::

![Recurso extraído de Canva](src/img/cap2/entrevistas-introduccion.png)

\newpage

### Diseño de Entrevistas 

Las entrevistas de validación fueron diseñadas considerando las necesidades, contextos de uso y tareas más relevantes para cada segmento objetivo del proyecto. A cada entrevistado se le presentó un conjunto de escenarios y se le asignaron tareas concretas vinculadas con los *user flows* principales de su perfil de usuario.

::: box
**Segmento Objetivo 1:** Directivos escolares o personal administrativo
:::

**Interfaces validadas:**

* **Dashboard web** (gestión de rutas, reportes, alertas, asistencia)

* **Landing page** (como introducción al producto)

**Objetivo:** Validar si la plataforma facilita la gestión del transporte escolar, si la interfaz es clara, y si la información mostrada es suficiente y útil para sus tareas diarias.

**User Flows Evaluados y Preguntas de Validación:**

1) **Landing Page**  

  - **Objetivo:** Validar si la página comunica correctamente la propuesta de valor del sistema.  

  - **Preguntas:**  

    - ¿La información presentada en la landing page te ayudó a entender la solución?  

    - ¿Qué parte te pareció más útil o convincente?  
          
    - ¿Qué información adicional crees que podría motivarte a adquirir esta solución?



2) **User Flow 1: Ingreso al sistema**

    - **Objetivo:** Validar que el login sea claro, sencillo y transmita seguridad.  

    - **Preguntas:**  

      - ¿El proceso de inicio de sesión fue claro y fácil de completar?  

      - ¿La interfaz te generó confianza para ingresar tus credenciales?  

      - ¿Cambiarías o mejorarías algo en esta pantalla?

      

3) **User Flow 2: Visualización del panel de rutas activas** 

  - **Objetivo:** Evaluar si la información operativa de rutas es accesible y entendible. 

  - **Preguntas:**  

    - ¿Cómo percibes la organización del panel principal? ¿Te parece clara?

    - ¿Puedes identificar fácilmente el estado de las rutas y de cada bus?  

    - ¿La información presentada es la que necesitas para tomar decisiones?  

    - ¿Te gustaría ver algún otro tipo de dato aquí?

4) **User Flow 3: Emisión de notificaciones a padres**  

  - **Objetivo:** Validar la facilidad de enviar alertas y la percepción de control sobre la comunicación.  

  - **Preguntas:**  

    - ¿Cómo fue tu experiencia al intentar enviar una notificación a los padres?  

    - ¿Sentiste que el sistema te ofrecía suficiente control sobre el mensaje y el destinatario?  

    - ¿Agregarías algún tipo de notificación o canal adicional (SMS, correo, etc.)?  

    - ¿Consideras útil tener mensajes predefinidos o plantillas?

5) **User Flow 4: Consulta de reportes de asistencia y trayectos**  

  - **Objetivo:** Comprobar la utilidad, estructura y legibilidad de los reportes generados.  

  - **Preguntas:**  

    - ¿Los reportes presentados fueron fáciles de interpretar?  

    - ¿Te parecen útiles para reuniones o auditorías internas?  

    - ¿Preferirías recibir estos reportes automáticamente al correo?  

    - ¿Sientes que hay datos innecesarios o que falta información clave?

6) **User Flow 5: Configuración de alertas de llegada/salida**  

  - **Objetivo:** Verificar si el proceso es intuitivo y útil desde una perspectiva operativa.  

  - **Preguntas:**  

    - ¿Te pareció sencillo configurar alertas para los trayectos escolares?  

    - ¿Crees que estas alertas cubrirían tus necesidades diarias de supervisión?  

    - ¿Qué nivel de personalización esperas tener en estas configuraciones?  

    - ¿Preferirías una opción para programarlas automáticamente por curso o sección?

      
\newpage

::: box
**Segmento Objetivo 2:** Padres de familia con hijos en edad escolar
:::


**Interfaces validadas:**

* **Aplicación móvil para padres** (visualización del bus, notificaciones, historial, perfil)

* **Landing page** (introducción general del servicio)

**Objetivo:** Validar que los padres puedan usar la aplicación sin dificultad, que perciban seguridad y tranquilidad, y que reciban la información relevante de manera oportuna.

**User Flows Evaluados y Preguntas de Validación:**


1) **Landing Page**  

  - **Objetivo:** Evaluar si la landing page genera confianza y comunica el valor de la app.  

  - **Preguntas:**  

    - ¿La página te ayudó a entender qué hace la app?  

    - ¿Confías en la solución después de ver la información?  

    - ¿Qué mejorarías o agregarías para que más padres se interesen?


2) **User Flow 1: Registro e inicio de sesión como padre**  

  - **Objetivo:** Evaluar la claridad del proceso de registro e ingreso, especialmente en usuarios no técnicos.  

  - **Preguntas:**  

    - ¿Cómo te pareció el proceso de registro e inicio de sesión?  

    - ¿Algún paso te generó confusión o fue innecesario?  

    - ¿Te sentiste seguro al ingresar tu información personal?  

    - ¿Qué parte mejorarías para que sea más rápida o clara?

3) **User Flow 2: Visualización del bus escolar en tiempo real**  

  - **Objetivo:** Confirmar que el tracking funcione de forma comprensible y confiable.  

  - **Preguntas:**  

    - ¿Pudiste ubicar el bus de forma clara en el mapa?  

    - ¿La visualización te dio tranquilidad respecto al trayecto de tu hijo?  

    - ¿Te gustaría ver algún otro dato en esta pantalla (nombre del chofer, tiempo estimado de llegada, etc.)?  

    - ¿Te parece útil esta función en tu rutina diaria?

4)  **User Flow 3: Recepción de alertas de llegada y salida**  

  - **Objetivo:** Evaluar si las notificaciones automáticas son visibles, comprensibles y oportunas.  

  - **Preguntas:**  

    - ¿Las alertas de llegada o salida fueron fáciles de entender?  

    - ¿En qué momento te gustaría recibir estas notificaciones?  

    - ¿Qué medio prefieres: notificaciones en la app, correo, WhatsApp?  

    - ¿Te gustaría personalizar el contenido o la frecuencia de las alertas?

5) **User Flow 4: Consulta del historial de trayectos**  

  - **Objetivo:** Verificar la utilidad del historial para el control parental.  

  - **Preguntas:**  

    - ¿Encontraste fácilmente el historial de rutas?  

    - ¿Te parece útil ver los trayectos pasados de tu hijo?  

    - ¿Qué información extra agregarías a este historial (fecha, hora, chofer, etc.)?  

    - ¿Lo usarías como referencia ante algún problema o retraso?

6) **User Flow 5: Acceso y edición del perfil del estudiante**  

  - **Objetivo:** Evaluar si los padres pueden gestionar correctamente la información del alumno.  

  - **Preguntas:**  

    - ¿Fue fácil encontrar y editar la información de tu hijo?  

    - ¿Qué datos crees que deberían estar incluidos en ese perfil?  

    - ¿Preferirías tener un control más limitado o más detallado sobre el perfil?  

    - ¿Consideras útil que puedas vincular este perfil a varios acudientes (mamá, papá, tutor)?  


\newpage

### Registro de Entrevistas 

::: box
**Segmento Objetivo 1:** Directivos escolares o personal administrativo
:::

**Entrevista #1**

\begin{table}[H]
\begin{center}
\begin{tabular}{|p{5cm}|p{6cm}|}
\hline
\textbf{Nombre y Apellido}    & Max Paul Ramos Chupitazzi \\ \hline
\textbf{Edad}                 & 55 años                   \\ \hline
\textbf{Ubicación geográfica} & Paiján, Ascope, La Libertad, Perú \\ \hline
\textbf{Cargo}                & Docente de secundaria y asesor tecnológico \\ \hline
\textbf{Tiempo de entrevista} & 00:00 - 10:34             \\ \hline
\end{tabular}
\end{center}
\end{table}

**Resumen de la entrevista**

Max Paul Ramos Chupitazzi, docente de matemáticas y asesor tecnológico, señala que el colegio donde trabaja no cuenta con un sistema propio de transporte escolar. Actualmente, la responsabilidad recae enteramente en los padres, quienes contratan transportes de forma independiente y sin supervisión de la institución. Esto genera una serie de problemas: falta de puntualidad, ausencia de control de asistencia, y condiciones inseguras en los vehículos, muchos de los cuales carecen de seguro y operan con sobrecupo.
El colegio ha detectado una necesidad urgente de implementar un sistema institucional de transporte, especialmente para estudiantes que provienen de distritos cercanos como Rázuri y Macaví. Se ha planteado la adquisición de unidades propias, lo cual permitiría garantizar la seguridad de los alumnos, asegurar la puntualidad y mejorar la percepción del colegio ante la comunidad.
Actualmente, el colegio utiliza un sistema de photochip para controlar el ingreso de los estudiantes, lo que permite identificar ausencias tempranas. Sin embargo, no existe ningún control al abordar o descender del transporte escolar, lo que ha causado incidentes preocupantes, como el caso de una estudiante que terminó en otra ciudad sin ser detectada.
El entrevistado propone un sistema tecnológico que permita el registro digital de embarque y desembarque mediante códigos de barras, notificaciones automáticas a los padres, y una app o panel de control para el monitoreo en tiempo real. Destaca que esto brindaría beneficios como: Mayor seguridad y tranquilidad para las familias,  fidelización de los padres hacia la institución y una reputación positiva del colegio como espacio moderno y confiable.
El principal obstáculo para la implementación es el costo adicional para las familias, aunque considera que si el incremento no es excesivo, los padres estarían dispuestos a asumirlo a cambio de mayor seguridad.

![Imagen extraída del video de entrevistas](src/img/cap2/EntrevistaPaul.png)

\newpage

**Entrevista #2**

\begin{table}[H]
\begin{center}
\begin{tabular}{|p{5cm}|p{6cm}|}
\hline
\textbf{Nombre y Apellido}    & Juliana Chávez \\ \hline
\textbf{Edad}                 & 32 años                   \\ \hline
\textbf{Ubicación geográfica} & Paiján, Ascope, La Libertad, Perú \\ \hline
\textbf{Cargo}                & Directora de institución educativa privada \\ \hline
\textbf{Tiempo de entrevista} & 10:34 - 19:40             \\ \hline
\end{tabular}
\end{center}
\end{table}

**Resumen de la entrevista**

Juliana Chávez, directora de una institución educativa privada en Paiján, explica que actualmente no cuentan con un sistema de transporte escolar institucional. La organización del traslado de los alumnos recae completamente en los padres, quienes contratan por su cuenta movilidades desde distintas zonas como Puerto Malabrigo, Casagrande, Chiclín y Chumpón.
La institución se encarga de definir los horarios escolares, pero no participa en la selección de choferes, rutas o tarifas. Las movilidades contratadas llegan hasta la puerta del colegio, donde auxiliares y porteros reciben a los estudiantes, y a la salida los acompañan hasta que aborden.
Uno de los problemas identificados es la falta de respuesta rápida en caso de emergencias médicas. Si un estudiante se enferma durante el horario escolar, la movilidad no puede recogerlo, por lo que deben llamar a los padres, lo que puede generar complicaciones si no hay quien lo recoja de inmediato.
Aunque no han recibido reclamos formales por parte de los padres sobre el transporte, existen comentarios informales sobre la posibilidad de que el colegio implemente su propia movilidad, lo que, según la directora, aumentaría la seguridad y tranquilidad de las familias.
Juliana considera que sería muy útil implementar una aplicación o plataforma digital para monitorear en tiempo real el transporte escolar. Esta permitiría:

   - Ver si los alumnos subieron o no a la movilidad.
   - Notificar a los padres en caso de desvíos o incidentes.
   - Usar un sistema tipo GPS que registre las rutas y desplazamientos.

En cuanto a la viabilidad de este tipo de solución, cree que los padres estarían dispuestos a pagar por ella, siempre que el costo no sea mayor que el actual. Destaca que sería una inversión valiosa tanto para el bienestar emocional de los padres como para la imagen y compromiso del colegio.

![Imagen extraída del video de entrevistas](src/img/cap2/EntrevistaJuliana.png)

\newpage

**Entrevista #3**

\begin{table}[H]
\begin{center}
\begin{tabular}{|p{5cm}|p{6cm}|}
\hline
\textbf{Nombre y Apellido}    & Graciela Rios Alza \\ \hline
\textbf{Edad}                 & 52 años                   \\ \hline
\textbf{Ubicación geográfica} & Paiján, Ascope, La Libertad, Perú \\ \hline
\textbf{Cargo}                & Promotora de institución educativa \\ \hline
\textbf{Tiempo de entrevista} & 19:40 - 29:26             \\ \hline
\end{tabular}
\end{center}
\end{table}

**Resumen de la entrevista**

Graciela Rios Alza se desempeña como promotora en una institución educativa de Paiján, donde observa de cerca las dinámicas del transporte escolar. Actualmente, la movilidad de los estudiantes es gestionada por terceros, especialmente combis que llegan desde distritos cercanos como Puerto Malabrigo. La institución no cuenta con un sistema de transporte propio, ni tecnología para monitorear en tiempo real los viajes.
Aunque el colegio establece los horarios de entrada y salida, no interviene en la organización ni supervisión del transporte escolar: ni en rutas, ni en selección de choferes, ni en el control de asistencia. La única comunicación activa ocurre cuando:
   - El conductor se comunica con el colegio para avisar retrasos por problemas como llantas pinchadas.
   - Los padres avisan si un alumno no asistirá.
Todo el proceso es manual y reactivo, sin herramientas tecnológicas. No existe un sistema para confirmar si los alumnos llegaron o regresaron, y no se registra asistencia al abordar o descender de los vehículos. Esto ha llevado a situaciones preocupantes: algunos estudiantes no fueron recogidos a la salida, obligando al conductor a regresar al colegio por ellos tras ser olvidados.
Graciela señala que los padres se mantienen constantemente preocupados por la seguridad del traslado de sus hijos, y que no se sienten completamente tranquilos con el sistema actual. Aunque no hay una cantidad alta de reclamos formales, sí se han reportado fallas mecánicas y descuidos logísticos.
A pesar de que no se ha usado nunca un sistema digital para la gestión del transporte, Graciela ve con buenos ojos la implementación de una aplicación tecnológica que permita:
   - Notificar automáticamente cuando los niños llegan al colegio o están en camino a casa.
   - Proveer información en tiempo real sobre el trayecto.
   - Permitir a los padres confirmar si enviarán a su hijo o no, facilitando la gestión administrativa del colegio.
También menciona que el uso de este tipo de tecnología sería bien recibido por los padres, especialmente aquellos que dependen del transporte escolar diariamente. Considera que esto mejoraría la seguridad y la tranquilidad emocional tanto de los padres como del personal educativo.
Está convencida de que sería viable implementar esta solución en su colegio y que beneficiaría directamente a varias áreas institucionales, como administración, psicología y auxiliares, al mejorar la organización, la comunicación y la prevención de incidentes.


![Imagen extraída del video de entrevistas](src/img/cap2/EntrevistaRocio.png)

\newpage


::: box
**Segmento Objetivo 2:** Padres de familia con hijos en edad escolar
:::

**Entrevista #1**

\begin{table}[H]
\begin{center}
\begin{tabular}{|p{5cm}|p{6cm}|}
\hline
\textbf{Nombre y Apellido}    & Gabriela Ríos Lazaro \\ \hline
\textbf{Edad}                 & 52 años                   \\ \hline
\textbf{Ubicación geográfica} & Trujillo, La libertad \\ \hline
\textbf{Ocupación}            & Obstetra \\ \hline
\textbf{Relación con la educación} & Madre de un estudiante de secundaria \\ \hline
\textbf{Tiempo de entrevista} & 29:26 - 39:23             \\ \hline
\end{tabular}
\end{center}
\end{table}

**Resumen de la entrevista**

Gabriela Ríos es madre de un estudiante de nivel secundario que utiliza un servicio de movilidad escolar privado de lunes a viernes. Aunque no recibe notificaciones diarias sobre la llegada de su hijo al colegio, confía en el conductor con el que ha establecido un acuerdo de transporte. La comunicación es directa, principalmente mediante llamadas en caso de imprevistos, como fallas menores del vehículo.
En su experiencia, nunca ha tenido un incidente grave relacionado al transporte, aunque reconoce que ha habido ocasiones donde ha tenido que comunicarse por su cuenta para confirmar el paradero de su hijo. La movilidad cuenta con una persona encargada que apoya a los estudiantes durante el trayecto, lo cual le brinda seguridad adicional.
Gabriela califica el servicio actual con un 8 sobre 10. El motivo de esta calificación se relaciona con un ajuste logístico reciente: debido a que el conductor asumió una nueva ruta para otro colegio, su hijo comenzó a ser dejado a unas cuadras de casa en lugar del domicilio exacto. Aun así, al tratarse de un adolescente y contar con su autorización previa, no lo considera un problema crítico ni un motivo para cambiar de proveedor, resaltando la responsabilidad y confiabilidad del conductor.
En cuanto a mejoras al sistema actual, Gabriela está completamente a favor de que el colegio implemente su propio sistema de transporte escolar, respaldado por una aplicación digital que permita monitorear el trayecto en tiempo real. Considera que sería una forma efectiva de asegurar que los estudiantes llegan bien a su destino y retornan sin incidentes. Además, resalta que muchas familias no tienen la posibilidad de recoger personalmente a sus hijos y dependen del transporte contratado.
Está dispuesta a pagar un costo adicional por un servicio así, siempre que venga respaldado por el colegio, que considera más preparado que los grupos de padres para seleccionar personal capacitado y prudente. Subraya que, así como confían en las escuelas para contratar buenos docentes, también deberían poder confiar en que contraten buenos conductores.
Finalmente, considera que lo más importante en una solución tecnológica de este tipo es:
   - Confirmar la llegada del alumno al colegio y su retorno al hogar.
   - Notificaciones automáticas en caso de desvíos o emergencias.
   - Gestión directa desde la institución, para mayor confianza y profesionalismo.

![Imagen extraída del video de entrevistas](src/img/cap2/EntrevistaGabriela.png)

\newpage

**Entrevista #2**

\begin{table}[H]
\begin{center}
\begin{tabular}{|p{5cm}|p{6cm}|}
\hline
\textbf{Nombre y Apellido}    & Zoila Lescano Nureña \\ \hline
\textbf{Edad}                 & 43 años                   \\ \hline
\textbf{Ubicación geográfica} & Trujillo, La libertad \\ \hline
\textbf{Ocupación}            & Obstetra \\ \hline
\textbf{Relación con la educación} & Madre de cuatro hijos (tres en primaria y una bebé) \\ \hline
\textbf{Tiempo de entrevista} & 39:23 - 45:15             \\ \hline
\end{tabular}
\end{center}
\end{table}

**Resumen de la entrevista**

Zoila Lescano Nureña es madre de cuatro hijos, tres de ellos actualmente cursando primaria. En el pasado, sus hijos utilizaron movilidad escolar tradicional, compartida con otros estudiantes. Sin embargo, cambió a un servicio de taxi particular exclusivo para sus tres hijos debido a preocupaciones por la logística y los horarios inflexibles de la movilidad escolar.
Según Zoila, las movilidades compartidas recogían a los niños muy temprano y los devolvían a casa muy tarde, debido a la necesidad de recoger a varios estudiantes en diferentes puntos. Esta situación le generaba preocupación diaria, y por ello optó por una alternativa más personalizada y eficiente.
Actualmente, el servicio de taxi contratado ofrece una experiencia altamente satisfactoria:

   - El conductor informa detalladamente los horarios de recogida y llegada.
   - La familia cuenta con comunicación directa constante.
   - Considera que la seguridad, puntualidad y trato son excelentes.

Aunque se siente tranquila con la situación actual, Zoila apoya la idea de implementar tecnología adicional para monitorear los desplazamientos escolares. En particular, valoraría una aplicación conectada a dispositivos como pulseras escaneables que envíen alertas al celular en tiempo real sobre:

   - Abordaje y bajada del transporte.
   - Notificaciones de incidentes o retrasos.
   - Seguimiento de ruta sin necesidad de comunicación directa con el conductor.

Además, considera que esta solución debería ser promovida e implementada por el colegio como parte de su compromiso con la seguridad estudiantil. Sugiere que esté disponible para las familias que quieran adoptarla, destacando que no todos los padres tienen el tiempo ni los medios para estar al tanto constantemente del transporte de sus hijos.
Zoila estaría dispuesta a pagar un costo adicional por este servicio digital, siempre que garantice mayor tranquilidad, especialmente en contextos de inseguridad o posibles emergencias. También propone que la aplicación incorpore una señal de alarma o alerta que los niños puedan activar si algo inusual ocurre durante el trayecto.

![Imagen extraída del video de entrevistas](src/img/cap2/EntrevistaZoila.png)

\newpage

**Entrevista #3**

\begin{table}[H]
\begin{center}
\begin{tabular}{|p{5cm}|p{6cm}|}
\hline
\textbf{Nombre y Apellido}    & Hayle Ascoy Varas \\ \hline
\textbf{Edad}                 & 40 años                   \\ \hline
\textbf{Ubicación geográfica} & Paiján, Ascope, La Libertad \\ \hline
\textbf{Ocupación}            & Docente \\ \hline
\textbf{Relación con la educación} & Madre de una niña en tercer grado de primaria \\ \hline
\textbf{Tiempo de entrevista} & 45:15 - 51:52             \\ \hline
\end{tabular}
\end{center}
\end{table}

**Resumen de la entrevista**

Hayle Ascoy Varas, docente y madre de una niña de tercer grado, utiliza movilidad escolar privada de lunes a viernes. Aunque el servicio es funcional y el conductor es una persona en quien confía por su buen trato y responsabilidad, Hayle manifiesta una preocupación constante por la falta de seguimiento en tiempo real del traslado de su hija. La comunicación depende exclusivamente del celular del chofer, quien no siempre responde de inmediato, lo que la obliga a insistir para confirmar si su hija ha llegado al colegio o a casa.
Ha experimentado situaciones de incertidumbre debido a retrasos ocasionados por fallas mecánicas o falta de gasolina, sin previo aviso. Si bien califica el servicio actual como más seguro que en el pasado, afirma que dejaría de usarlo si la puntualidad se ve afectada o si pierde transparencia en la comunicación directa.
En un intento anterior por monitorear a su hija, utilizó un reloj GPS, pero dejó de hacerlo por restricciones del colegio y porque el dispositivo era fácilmente manipulado por la niña. Actualmente, no utiliza aplicaciones escolares específicas, y se comunica con el colegio únicamente vía WhatsApp con tutoras o la secretaría.
Hayle estaría dispuesta a pagar hasta 100 soles mensuales por una aplicación que brinde más seguridad y control, siempre que sea de calidad. Considera importante que esta incluya funciones como:
   - Notificaciones automáticas de embarque y desembarque.
   - Seguimiento en tiempo real de la ruta.
   - Alertas de paradas o incidencias no programadas.
Cree firmemente que el colegio debería ser quien gestione la aplicación, ya que esto garantizaría un control compartido y mayor confianza institucional. Para ella, la implementación de este tipo de solución sería una muestra concreta del compromiso del colegio con la seguridad y bienestar emocional tanto de estudiantes como de sus familias.

![Imagen extraída del video de entrevistas](src/img/cap2/EntrevistaHayle.png)

\newpage

### Evaluaciones según heurísticas 

::: box
**Segmento Objetivo 1:** Directivos escolares o personal administrativo
:::

**Perfil Demográfico**

- **Edades:** Entre 32 y 55 años, con un promedio estimado de 46.3 años.  

- **Ubicación Geográfica:** Todos los entrevistados pertenecen al distrito de Paiján, provincia de Ascope, La Libertad (Perú).  

- **Cargos ocupados:**
  - Directora de institución educativa privada  

  - Docente y asesor tecnológico  

  - Promotora educativa  

Este segmento representa a profesionales con amplia experiencia en la gestión educativa, en su mayoría con roles de liderazgo o soporte tecnológico dentro de las instituciones. Su perspectiva combina conocimiento administrativo, contacto directo con padres de familia y comprensión de los problemas logísticos cotidianos.


**Experiencia y Conocimientos sobre Transporte Escolar**

Los directivos entrevistados muestran un conocimiento claro y directo sobre la situación actual del transporte escolar en sus instituciones, aunque ninguna de ellas gestiona un sistema institucional de transporte. La logística del traslado de estudiantes es responsabilidad exclusiva de los padres, quienes contratan servicios de movilidad de forma independiente. Esto genera una serie de limitaciones y problemas recurrentes:

- **Ausencia de supervisión institucional:** Las instituciones no participan en la selección de choferes, control de rutas, ni en protocolos de seguridad o asistencia al abordar y descender.
- **Falta de control ante emergencias:** No existe un plan o solución inmediata cuando un estudiante necesita regresar a casa por enfermedad u otro imprevisto durante el horario escolar.
- **Inseguridad y desorganización:** Se reportan problemas como estudiantes que no son recogidos, falta de comunicación efectiva con los transportistas, fallas mecánicas, e incluso situaciones más graves como alumnos que terminan en otra ciudad.
- **Ausencia de herramientas tecnológicas:** Aunque algunas instituciones utilizan sistemas de control de ingreso (como photochips), no existe ningún mecanismo de monitoreo del transporte escolar ni de control de asistencia en las unidades.

En general, los entrevistados reconocen que la situación actual no garantiza ni la seguridad ni la puntualidad, y que los padres no se sienten plenamente tranquilos con el sistema informal de transporte escolar vigente.


**Herramientas y Tecnología Actual**

Actualmente, las instituciones del segmento no cuentan con tecnología dedicada al monitoreo o gestión del transporte escolar. Sin embargo, algunos elementos tecnológicos se usan de manera limitada y en contextos distintos:

- **Herramientas existentes:**
   - Control de asistencia con photochip: En una institución, los estudiantes registran su ingreso con un sistema de marcación electrónica, permitiendo identificar ausencias de manera temprana.
   - Comunicación básica: La interacción con padres y transportistas se realiza principalmente por teléfono o WhatsApp, de forma manual y reactiva.
   - Registro de incidencias: Se lleva a cabo de manera verbal o informal, sin plataformas estandarizadas.

- **Brechas tecnológicas:**
   - No existe un sistema digital que permita monitorear el abordaje o descenso de estudiantes.
   - No hay plataforma institucional que gestione rutas, asistencia, ni alertas automatizadas.
   - El registro y control del transporte es completamente manual y externo a las instituciones.

**Intereses y Necesidades Tecnológicas**

Todos los entrevistados coincidieron en la importancia de implementar soluciones tecnológicas que permitan gestionar de forma segura y eficiente el transporte escolar.

- **Necesidades principales identificadas:**
   - Monitoreo en tiempo real del trayecto de los estudiantes
   - Registro digital de embarque y desembarque (códigos de barras o QR)
   - Notificaciones automáticas a los padres
   - Confirmación diaria por parte de los padres sobre si el alumno asistirá o no (evitando confusiones o ausencias imprevistas).
   - Panel administrativo que brinde visibilidad al personal del colegio sobre:
      - Alumnos presentes en movilidad
      - Rutas y choferes asignados
      - Incidentes o desviaciones en tiempo real


- **Valor percibido:**
   - Mayor seguridad y tranquilidad para las familias
   - Imagen institucional moderna y confiable
   - Apoyo a la gestión interna del colegio (administración, psicología, personal auxiliar)

- **Sobre la viabilidad económica:**

   - El costo es un obstáculo potencial, pero los entrevistados creen que los padres estarían dispuestos a pagar si el valor en seguridad es claro y el precio razonable.


**Preferencias y Comportamientos**

A pesar de no contar con sistemas digitales actualmente, los directivos muestran una actitud abierta, receptiva y proactiva hacia nuevas soluciones tecnológicas, siempre que sean:

- Fáciles de implementar  

- Comprensibles para los padres  

- Accesibles económicamente  

- **Comportamientos actuales:**
   - Gestión manual y reactiva mediante llamadas y WhatsApp
   - Supervisión parcial sin control al subir/bajar de la movilidad
   - Ausencia de protocolos ante emergencias durante el traslado

- **Cambios que buscan:**
   - Automatización del proceso de abordaje/desembarque con trazabilidad
   - Comunicación en tiempo real con los padres
   - Sistemas preventivos, no solo reactivos ante incidentes

En esencia, estos actores educativos buscan una solución que combine tecnología con simplicidad, que les permita mejorar la seguridad sin complejizar la rutina diaria, y que transforme un sistema informal en uno institucional y confiable.

\newpage

**Estadísticas y Porcentajes**


![Creado en Excel](src/img/cap2/grafico1.png){ height=45% }

![Creado en Excel](src/img/cap2/grafico2.png){ height=45% }  

\newpage                                     

![Creado en Excel](src/img/cap2/grafico3.png){ height=40% }

![Creado en Excel](src/img/cap2/grafico4.png){ height=40% }

\newpage

**Análisis de datos**

Todos los directivos entrevistados indicaron que el transporte escolar es gestionado de forma externa por los padres, sin participación de la institución educativa. Esta situación genera preocupaciones frecuentes por la falta de control, puntualidad y seguridad.

El 33.3% de las instituciones cuenta con un sistema digital de asistencia, mientras que el 66.7% no utiliza ninguna herramienta tecnológica para registrar el ingreso escolar, lo que limita el control y la prevención de incidentes.

Respecto al acceso digital, Windows es el sistema operativo más utilizado (100%), lo que sugiere una familiaridad general con entornos convencionales de oficina.

En cuanto a dispositivos móviles, Android es el preferido por el 66.7% de los entrevistados, mientras que el 33.3% utiliza iOS, lo que muestra una ligera predominancia de accesibilidad sobre exclusividad.

El navegador web más usado es Google Chrome (66.7%), seguido de Microsoft Edge (33.3%), reforzando la tendencia hacia herramientas de uso masivo y compatibles con múltiples plataformas educativas.

Las funcionalidades tecnológicas más valoradas para un futuro sistema de gestión del transporte escolar incluyen:

   - Monitoreo en tiempo real (GPS) y notificaciones automáticas a los padres (ambas mencionadas por el 100% de los entrevistados).
   - Registro digital de embarque y desembarque, confirmación diaria de asistencia por parte de los padres y paneles administrativos, todos con una alta frecuencia de mención.
   - También se valora la posibilidad de generar historiales o reportes de trayectos para revisión institucional.


::: note 
Este análisis revela que los directivos escolares tienen una percepción clara de las limitaciones actuales del sistema de transporte escolar, especialmente en términos de seguridad y control. A pesar de la falta de implementación tecnológica actual, existe una alta disposición a adoptar herramientas digitales, siempre que estas sean accesibles, intuitivas y contribuyan al bienestar de los estudiantes y la tranquilidad de los padres.
Una solución digital de transporte bien diseñada podría no solo mejorar la logística, sino también fortalecer la imagen institucional y fidelizar a las familias mediante confianza y modernización.
:::

\newpage

::: box
**Segmento Objetivo 2:** Padres de familia con hijos en edad escolar
:::


**Perfil Demográfico**

- **Edad promedio:** 45 años  

- **Ubicación geográfica:** Mayoritariamente en las provincias de Trujillo y Ascope, departamento de La Libertad, Perú.  

- **Ocupación predominante:** Profesionales activas, principalmente en el área de la salud (obstetricia) y la docencia.  

- **Relación con el sistema educativo:** Madres de estudiantes en nivel primario y secundario, con participación activa en la supervisión del entorno escolar y toma de decisiones sobre movilidad.

Este grupo representa un perfil de madres altamente comprometidas con la seguridad y puntualidad en el traslado escolar de sus hijos. Sus decisiones están guiadas por la experiencia directa, criterios de confianza interpersonal, y una creciente expectativa hacia herramientas tecnológicas que profesionalicen el sistema de transporte escolar.

**Experiencia y Conocimientos sobre Transporte Escolar**

Las entrevistadas han transitado por diferentes modalidades de movilidad escolar, desde servicios compartidos (combi escolar) hasta servicios exclusivos (taxis contratados directamente). La elección de un modelo sobre otro responde a experiencias acumuladas que destacan fortalezas y limitaciones relevantes:

- **Problemas comunes en la movilidad compartida:**  
  - Recojos demasiado tempranos y retornos fuera de horario.
  - Recorridos extensos y falta de personalización.
  - Comunicación deficiente o inexistente sobre retrasos o percances.

- **Motivos de migración hacia transporte exclusivo:**  
  - Mayor control del horario.
  - Relación directa con el conductor.
  - Sensación de mayor seguridad y atención personalizada.

- **Percepción de confiabilidad:**  
  - A pesar de confiar en sus actuales proveedores, las madres reconocen que esta seguridad está basada exclusivamente en la relación interpersonal, sin respaldo institucional ni tecnología que garantice trazabilidad o monitoreo.

- **Situaciones críticas reportadas:**  
  - Fallas mecánicas, demoras no informadas, paradas no justificadas y ausencia de canales formales de reporte o respuesta.



**Herramientas y Tecnología Actual**

En el entorno doméstico y profesional, las entrevistadas hacen uso cotidiano de tecnología, principalmente a través de dispositivos móviles con sistema operativo Android. Sin embargo, este uso no se traduce en una integración efectiva con el entorno educativo ni con la movilidad escolar:

- **Dispositivos tecnológicos utilizados:**  
  - Smartphones (Samsung Galaxy predominante, sistema Android).

- **Herramientas de comunicación:**  
  - WhatsApp como canal informal entre padres, tutores y choferes.
  - Llamadas telefónicas directas en caso de emergencias o dudas.

- **Intentos de implementación tecnológica:**  
  - Una entrevistada intentó utilizar un reloj GPS infantil, pero fue restringido por la institución escolar y resultó inefectivo por manipulación del menor.

- **Limitaciones identificadas:**  
  - Falta de aplicaciones escolares dedicadas al monitoreo del transporte.
  - No existen sistemas automatizados de embarque, llegada o descenso.
  - Total ausencia de confirmaciones o alertas institucionales sobre el estado del trayecto o la asistencia del estudiante.


**Intereses y Necesidades Tecnológicas**

Existe un consenso claro sobre el interés y la apertura hacia soluciones tecnológicas que ofrezcan mayor visibilidad, trazabilidad y tranquilidad a las familias.

- **Requerimientos clave identificados:**
   - Monitoreo en tiempo real del trayecto escolar.
   - Notificaciones automáticas sobre subida, bajada, llegada, desvíos y emergencias.
   - Registro digital de embarque y desembarque mediante códigos o sensores.
   - Confirmación diaria de asistencia gestionada desde el hogar.
   - Historiales o bitácoras de trayectos para consulta y análisis posterior.
   - Botón de emergencia o alerta para uso por parte del estudiante en caso de urgencia.

- **Preferencias de gestión:**
   - Las entrevistadas consideran indispensable que el colegio sea el ente encargado de la implementación, gestión y supervisión de la tecnología y el personal del transporte escolar.
   - La participación institucional es percibida como un factor de garantía, profesionalismo y respaldo, frente a modelos gestionados informalmente por grupos de padres.

- **Disposición económica:**
   - Existe disposición general a asumir un costo adicional si el sistema garantiza seguridad, eficiencia y respaldo formal.
   - Se menciona un rango aceptable de pago mensual que puede alcanzar los S/100 soles si el valor percibido justifica la inversión.



**Preferencias y Comportamientos Observados**

Las entrevistadas presentan comportamientos orientados a la supervisión activa del traslado escolar, aunque carecen de herramientas formales para hacerlo.

- **Conductas comunes:**

   - Seguimiento manual mediante llamadas y mensajes al chofer.

   - Tolerancia a modificaciones en rutas o puntos de recojo si existe confianza previa.

   - Evaluación continua de la puntualidad y confiabilidad del servicio.

- **Criterios de cambio de servicio:**

   - Incumplimiento reiterado de horarios.

   - Falta de comunicación ante imprevistos.

   - Ausencia de trazabilidad.

- **Elementos prioritarios en una solución ideal:**

   - Automatización de procesos críticos como embarque y notificación de llegada.

   - Gestión institucional centralizada que permita reportes, control y respuestas rápidas.

   - Sistema fácil de usar, tanto para padres como para personal educativo.


**Estadísticas y Porcentajes**


![Creado en Excel](src/img/cap2/grafico1S2.png)

![Creado en Excel](src/img/cap2/grafico2S2.png)

![Creado en Excel](src/img/cap2/grafico3S2.png)

\newpage


**Análisis de Datos**

Las madres entrevistadas utilizan servicios de transporte escolar privado (movilidad compartida o taxi exclusivo), y coinciden en que, si bien actualmente no enfrentan grandes incidentes, la falta de seguimiento en tiempo real genera inseguridad y preocupación.

El 100% de las entrevistadas confía principalmente en la relación personal con el conductor, ya que no utilizan apps escolares ni sistemas institucionales para hacer seguimiento del transporte.

Asimismo, el 100% considera que el monitoreo digital debería estar gestionado por el colegio, lo cual reflejaría mayor compromiso institucional, profesionalismo en la selección del personal y respaldo en caso de emergencias.

Respecto a su disposición económica, todas están abiertas a pagar un monto adicional por una solución digital que brinde seguridad y control, siempre que esté correctamente respaldada por la institución educativa.

En cuanto a sus herramientas actuales:

- El sistema operativo más utilizado es Android (100%), lo que sugiere una fuerte afinidad con dispositivos de fácil acceso y uso común.

- Google Chrome fue el navegador mencionado con más frecuencia (66.7%), mientras que el 33.3% no especificó navegador, lo que puede deberse a menor uso activo de plataformas web escolares.


Las funcionalidades tecnológicas más mencionadas para una aplicación ideal incluyen:

- Monitoreo en tiempo real (GPS) y notificaciones automáticas a los padres (ambas mencionadas por el 100%).

- Registro digital de embarque/desembarque y confirmación diaria desde la app, con una frecuencia del 66.7%.

- También se valoraron herramientas innovadoras como una alerta de emergencia activada por el niño y la posibilidad de que el sistema sea gestionado institucionalmente.


::: note
Este análisis muestra que los padres de familia valoran altamente la seguridad, la puntualidad y el control durante el traslado escolar, y aunque confían en sus proveedores actuales, reconocen que la tecnología puede ofrecer un nivel de tranquilidad mucho más robusto y automatizado.
Existe una clara expectativa de que el colegio sea el actor responsable en implementar soluciones digitales, lo cual no solo fortalecería la confianza de las familias, sino también proyectaría una imagen institucional comprometida con el bienestar emocional y físico de sus estudiantes.
:::

\newpage

## Video About-the-Product 

Para construir una solución realmente útil, hablamos directamente con quienes la usarán. A través de entrevistas, recolectamos información clave sobre su día a día, sus necesidades, frustraciones y cómo se relacionan con la tecnología. Esta información nos permitió entender sus emociones y comportamientos, y así diseñar una experiencia pensada realmente para ellos.

![Recurso extraído de Canva](src/img/cap6/video-about-the-product-introduccion.png)

::: warn
Para acceder al video del producto, haga click en la [URL](https://upcedupe-my.sharepoint.com/:v:/g/personal/u202210059_upc_edu_pe/EWO4I1TkuVdCnZbW0aswNssBgLRcrsjVJa2rl-7IQv-QoA?e=2KDzPp&nav=eyJyZWZlcnJhbEluZm8iOnsicmVmZXJyYWxBcHAiOiJTdHJlYW1XZWJBcHAiLCJyZWZlcnJhbFZpZXciOiJTaGFyZURpYWxvZy1MaW5rIiwicmVmZXJyYWxBcHBQbGF0Zm9ybSI6IldlYiIsInJlZmVycmFsTW9kZSI6InZpZXcifX0%3D)
:::

![Recurso extraído de Microsoft Stream](src/img/cap6/video-about-the-product-tb2.png){ heigth=50% }

\newpage

# Conclusiones

## Conclusiones y recomendaciones

1. **Gestión de Configuración Impecable:** Hemos concluido que la base del proyecto se sustenta en una Gestión de Configuración de Software (SCM) excepcionalmente bien definida. La estandarización de entornos, librerías y versiones de SDK asegura la reproducibilidad y minimiza los problemas de "funciona en mi máquina". Esto establece un pilar de estabilidad y profesionalismo desde el inicio.

2. **Adopción Rigurosa de Metodologías Ágiles:** El equipo ha demostrado una aplicación rigurosa y transparente de las metodologías ágiles. La planificación detallada de los Sprints, la gestión visual a través de tableros Kanban y el desglose de tareas en Historias de Usuario (US) y Work Items (WI) con estimaciones, evidencian un control total sobre el flujo de trabajo, promoviendo la previsibilidad y la entrega continua de valor.

3. **Cultura de Calidad Guiada por Comportamiento (BDD):** Destacamos el profundo compromiso con la calidad, que va más allá de las pruebas tradicionales. La implementación extensiva del Desarrollo Guiado por Comportamiento (BDD) a través de Gherkin sirve como un "contrato" claro entre los requisitos de negocio y la implementación técnica, asegurando que el software haga lo correcto de la manera correcta.

4. **Arquitectura Políglota y Orientada a Propósito:** La elección de un stack tecnológico diversificado (React, Angular, Flutter, Spring Boot, Python) no es casual, sino una decisión arquitectónica deliberada. Observamos que se ha aplicado la filosofía de "usar la mejor herramienta para cada tarea", lo que permite optimizar cada componente del sistema (landing, app de admin, app móvil, servicios) de forma independiente y eficiente.

5. **Diseño Arquitectónico Formal y Documentado:** El proyecto no solo se ha construido, sino que se ha diseñado con previsión. El uso de modelos como C4 con Structurizr y diagramas con Mermaid demuestra un esfuerzo consciente por planificar y comunicar la arquitectura del sistema. Esto facilita la comprensión, la escalabilidad y el mantenimiento a largo plazo.

6. **Automatización del Despliegue como Pilar Fundamental (DevOps):** Hemos notado una fuerte orientación hacia las prácticas DevOps. La configuración de pipelines de CI/CD, el uso de contenedores con Docker y el despliegue automatizado en plataformas como Vercel y Netlify son indicativos de un enfoque moderno que busca agilidad, seguridad y fiabilidad en las entregas.

7. **Validación del Problema a través de la Voz del Usuario:** Consideramos que la realización de entrevistas de validación con los segmentos objetivo ha sido el acto más estratégico del proyecto. Estas no solo confirmaron las hipótesis, sino que pusieron de manifiesto los "dolores" reales (inseguridad, falta de control, ansiedad) que RutaKids se propone resolver, dotando al proyecto de un propósito claro y validado.

8. **Conexión Directa entre Funcionalidades y Necesidades Reales:** A raíz de la validación, concluimos que las funcionalidades propuestas no son arbitrarias. Características como el monitoreo en tiempo real, las notificaciones de embarque y la gestión centralizada desde el colegio responden directamente a las preocupaciones expresadas por padres y directivos, lo que garantiza una alta probabilidad de adopción y satisfacción.

9. **Proceso de Diseño de Experiencia de Usuario Formalizado:** El uso de herramientas como UxPresia para mapas de historias y Figma para prototipos interactivos demuestra que la experiencia de usuario (UX/UI) ha sido una disciplina central en el proceso, y no una ocurrencia tardía. Esto asegura que las interfaces sean intuitivas y estén alineadas con los flujos de trabajo de los usuarios finales.

10. **Cultura de Documentación Exhaustiva y Práctica:** El equipo ha cultivado una excelente cultura de la documentación. Desde la especificación de APIs con Swagger (OpenAPI) hasta la documentación de componentes con Storybook y la justificación de librerías, se ha creado un ecosistema de información que facilita la integración, la colaboración y la incorporación de nuevos miembros al equipo.

11. Estandarización del Código para la Cohesión del Proyecto: La definición de guías de estilo, el uso de linters y la adopción de "Conventional Commits" son cruciales en un proyecto con múltiples tecnologías. Hemos concluido que estas convenciones unifican la base del código, mejorando drásticamente su legibilidad y mantenibilidad, y facilitando la revisión entre pares.

12. **Trazabilidad Completa de Requisito a Despliegue:** Uno de los logros más notables es la trazabilidad completa que se puede seguir a lo largo del proyecto. Es posible rastrear una Historia de Usuario desde el backlog, pasando por sus pruebas en Gherkin, su implementación en una rama feature/, sus commits específicos, hasta su despliegue final. Este nivel de control es característico de equipos de alto rendimiento.

13. **Colaboración Efectiva y Distribuida:** La evidencia presentada (gráficos de red, actividad en Kanban, asignación de roles) pinta la imagen de un equipo altamente colaborativo y bien organizado. La distribución de responsabilidades, con líderes y colaboradores por aspecto, fomenta el ownership y asegura que todas las áreas del proyecto avancen en paralelo de forma coordinada.

14. **Validación de la Viabilidad del Modelo de Negocio:** Las entrevistas no solo validaron el producto, sino también su potencial de negocio. La disposición explícita de ambos segmentos de usuarios a pagar por una solución de este tipo proporciona una validación temprana del modelo de negocio, posicionando a RutaKids no solo como un proyecto técnico exitoso, sino como un producto potencialmente sostenible.

15. **Visión Holística y Ejecución Integral:** En resumen, nuestra conclusión final es que el proyecto RutaKids representa un ejemplo de ejecución holística. El equipo ha demostrado una capacidad sobresaliente para integrar la gestión de proyectos, el diseño de UX, la ingeniería de software, la garantía de calidad y la validación de negocio en un proceso cohesivo y bien documentado, culminando en una solución que es a la vez robusta técnicamente y profundamente humana.

\newpage

# Video About the team

Durante el Sprint 3, el equipo de desarrollo de RutaKids elaboró un video en el que se presenta a los integrantes del equipo, sus roles dentro del proyecto, y las principales tareas ejecutadas durante el desarrollo de las funcionalidades planificadas.

Este video tiene como objetivo evidenciar el trabajo colaborativo, la organización durante el ciclo de vida del proyecto, y la ejecución de entregables clave como la integración del dispositivo IoT, el despliegue de la app móvil, la aplicación web y los microservicios backend.

::: warn
Para visualizar el video del equipo, haga click en el siguiente enlace[URL](https://upcedupe-my.sharepoint.com/:v:/g/personal/u202210059_upc_edu_pe/EbIdiH15C_dFtJvMA56Xtj4Byo71TNlPM0LJ-4kdQrmoBw?e=bYu0Go&nav=eyJyZWZlcnJhbEluZm8iOnsicmVmZXJyYWxBcHAiOiJTdHJlYW1XZWJBcHAiLCJyZWZlcnJhbFZpZXciOiJTaGFyZURpYWxvZy1MaW5rIiwicmVmZXJyYWxBcHBQbGF0Zm9ybSI6IldlYiIsInJlZmVycmFsTW9kZSI6InZpZXcifX0%3D)
:::

::: warn
URL: https://tinyurl.com/aboutTheTeamRutaKids
:::


![Imagen extraída del Video About the team](src/img/cap6/About-the-team.png)

\newpage

# Anexos 

**Recursos del Proyecto RutaKids**

- **Video About the product**
https://tinyurl.com/rkATP

- **Video About the team**
https://tinyurl.com/rkATTeam

- **Repositorios de Código**

  - **Organización LlantaTech (Github):**
  https://github.com/orgs/LlantaTech/repositories

  - **Microservicios Backend (REST API):**
  https://github.com/LlantaTech/ruta-kids-microservicios

  - **Frontend Web:**
  https://github.com/LlantaTech/RutaKids-WebApp

  - **Frontend Landing Page:**
  https://github.com/LlantaTech/RutaKids-LandingPage


- **Despliegues Web**

  - **Landing Page RutaKids:**
  https://llantatech.org.pe/

  - **Aplicación Web Admin:**
  https://rutakids.llantatech.org.pe/

- **Prototipado y Diseño UI/UX**

  - Diseño de Aplicación Móvil en Figma:
  https://tinyurl.com/designRutaKids


- **Documentación y Tecnologías**

  - **Spring Boot Docs:**
  https://docs.spring.io/spring-boot/index.html

  - **Spring Security:**
  https://docs.spring.io/spring-boot/reference/web/spring-security.html#page-title

  - **Spring Data JPA:**
  https://spring.io/projects/spring-data-jpa

  - **JWT (jsonwebtoken NPM):**
  https://www.npmjs.com/package/jsonwebtoken

  - **PubSubClient (MQTT para Arduino):**
  https://pubsubclient.knolleary.net/

  - **Mosquitto MQTT Broker:**
  https://mosquitto.org/documentation/

  - **WiFiClient (Arduino):**
  https://www.arduino.cc/en/Reference/WiFiClient


# Bibliografía
