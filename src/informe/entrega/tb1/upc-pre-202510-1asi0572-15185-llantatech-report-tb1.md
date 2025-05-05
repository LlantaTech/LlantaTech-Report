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
  @kalbach2016,
  @tarzijan2019,
  @lin2024,
  @rijgersberg2025,
  @igartua2019desconexion,
  @jiang2024pervasive,
  @kaspersky_privacy,
  @collave2024datos,
  @rajput2021,
  @boyd2021,
  @richardson2020,
  @toussaint2020,
  @brown2021,
  @angular2024,
  @freeman2022,
  @edutransport2020,
  @skole2020,
  @satgeo2020,
  @allride2020,
  @ubusschool2020,
  @tilkov2017,
  @pilgrim2021
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

**Registro de Versiones del Informe**

\begin{longtable}{|c|c|c|p{6cm}|}
  \hline
  \textbf{Versión} & \textbf{Fecha} & \textbf{Autor} & \textbf{Descripción de Modificación} \\
  \hline
  tb1 & 25/04/2025 & Ortega Huaraca, Abel & Ayudé con la estructura del informe en general. Respecto a los puntos específicos, contribuí con la elaboración del \textit{Solution Profile}, \textit{Startup Profile}, Segmentos objetivo, \textit{User Stories} y una introducción para los \textit{Requirements Specification}. \\
  \hline
  tb1 & 25/04/2025 & Ramos Rios, Belén del Rocio & Realicé el análisis competitivo, estrategias frente a competidores, entrevistas (diseño, registro y análisis) y los apartados de \textit{Requirements Specification} incluyendo \textit{To-Be Scenario Mapping}, \textit{Impact Mapping} y \textit{Product Backlog}. \\
  \hline
  tb1 & 25/04/2025 & Vilchez Rios, Mateo Alejandro & Elaboré los apartados de \textit{Lean UX Process} dentro del \textit{Solution Profile} y la sección de \textit{Solution Software Design} incluyendo \textit{Strategic-Level Domain-Driven Design} y \textit{EventStorming}. \\
  \hline
  tb1 & 25/04/2025 & Avila Asto, Alex Ramon Alberto & Desarrollé la sección de \textit{Software Architecture}, incluyendo \textit{Context Mapping}, \textit{Candidate Context Discovery}, \textit{Domain Message Flows Modeling}, \textit{Bounded Context Canvases} y la definición de las capas de la arquitectura a nivel de contexto (Domain, Interface, Application e Infrastructure Layer). \\
  \hline
\end{longtable}

\newpage

***Project Report Collaboration Insights***

**TB1:**

::: warn
Para acceder los insights de este proyecto, haga click a la [URL](https://github.com/LlantaTech/LlantaTech-Report/pulse)
:::

**Tablero Kanban:**

![Organización LlantaTech, imagen extraída de Github](src/img/cap6/insights-kanban-todo-1.png){ width=85% }

**Kanban List:**

![Organización LlantaTech, imagen extraída de Github](src/img/cap6/insights-kanban-list-1.png){ width=85% }

\newpage

**Network Graph:**

![Organización LlantaTech, imagen extraída de Github](src/img/cap6/insights-network-graph-1.png){ width=85% }

**Traffic Map:**

![Organización LlantaTech, imagen extraída de Github](src/img/cap6/insights-traffic-1.png){ width=85% }

\newpage


***Student Outcome***

El curso contribuye al cumplimiento del ***Student Outcome ABET:*** *ABET-EAC - Student Outcome 5*

* **Criterio:** *La capacidad de funcionar efectivamente en un equipo cuyos miembros juntos proporcionan liderazgo, crean un entorno de colaboración e inclusivo, establecen objetivos, planifican tareas y cumplen objetivos*.

En el siguiente cuadro se describe las acciones realizadas y enunciadas de conclusiones por parte del grupo, que permiten sustentar el haber alcanzado el logro de ***ABET - EAC - Student Outcome 5.***


\begin{longtable}{|p{4cm}|p{6cm}|p{5cm}|}
\hline
\multicolumn{1}{|c|}{\textbf{Criterio Específico}} & \multicolumn{1}{c|}{\textbf{Acciones Realizadas}} & \multicolumn{1}{c|}{\textbf{Conclusiones}} \\
\hline
\endfirsthead
\parbox[t]{4cm}{
\textit{Trabaja en equipo para proporcionar liderazgo en forma conjunta}
} 
&  
\parbox[t]{6cm}{
\textbf{TB1:} \\
\textbf{Abel Angel Ortega Huaraca} \\
Propuse que dividiéramos el proyecto en entregas parciales semanales y organicé la primera reunión de planificación. Asimismo, compartí ejemplos externos para ilustrar la conexión correcta. \\
\textbf{Belén del Rocio Ramos Rios} \\
Organicé el espacio de trabajo compartido en Google Drive y sugerí la creación de una carpeta de “Recursos” donde subimos artículos y ejemplos que nos ayudaron a mejorar nuestro análisis. \\
\textbf{Mateo Alejandro Vilchez Rios} \\
Propuse el uso de Trello para visualizar las tareas pendientes y completadas, y tomé la iniciativa de revisar que todos los entregables estuvieran bien enlazados entre sí. \\
\textbf{Alex Avila Asto} \\
Me encargué de coordinar las reuniones técnicas donde discutimos cómo debía ser la arquitectura del sistema. Expliqué al grupo el flujo de eventos entre los contextos de dominio, asegurando que todos comprendieran cómo interactuaban las diferentes partes del sistema antes de escribir la documentación. \\
}
&
\parbox[t]{5cm}{
\textbf{TB1:} \\
A lo largo del desarrollo del proyecto, se evidenció un liderazgo compartido y una colaboración activa entre todos los integrantes del equipo. Cada miembro asumió responsabilidades clave que aportaron significativamente a la organización y avance del trabajo. Desde la planificación inicial, la estructuración del entorno colaborativo, el seguimiento de tareas, hasta las discusiones técnicas sobre la arquitectura del sistema, cada aporte reflejó iniciativa y compromiso con los objetivos comunes. Esta distribución equitativa del liderazgo permitió que las decisiones se tomaran de forma consensuada y que cada integrante guiara al grupo en distintos momentos según sus fortalezas, lo que fortaleció la cohesión y eficiencia del equipo.
} \\ 
\hline

\parbox[t]{4cm}{
\textit{Crea un entorno colaborativo e inclusivo, establece metas, planifica tareas y cumple objetivos}
}
&  
\parbox[t]{6cm}{
\textbf{TB1:} \\
\textbf{Abel Angel Ortega Huaraca} \\
Propuse una dinámica basada en entregas parciales semanales que nos permitió identificar errores de forma temprana y distribuir mejor la carga de trabajo. Esto ayudó a mantener un flujo de avance ordenado y fomentó la participación continua de todos los miembros. \\
\textbf{Belén del Rocio Ramos Rios} \\
Elaboré un cronograma detallado con fechas internas de revisión y entrega, lo cual sirvió como guía para mantener el ritmo de trabajo constante. Este cronograma fue compartido y ajustado en función del consenso del grupo, promoviendo así una planificación inclusiva. \\
\textbf{Mateo Alejandro Vilchez Rios} \\
Me encargué de coordinar reuniones periódicas de seguimiento donde revisamos el estado de avance de cada integrante. Estas sesiones nos ayudaron a mantenernos alineados con los objetivos establecidos y asegurar que cada entrega se integrara de forma coherente. \\
\textbf{Alex Avila Asto} \\
Supervisé que las entregas técnicas se ajustaran al cronograma general del equipo y que los aportes individuales se integraran correctamente. Me aseguré de que la estructura y secuencia de los entregables mantuvieran consistencia, reforzando así la calidad final del proyecto. \\
}
&
\parbox[t]{5cm}{
\textbf{TB1:} \\
A lo largo del desarrollo del proyecto, el equipo demostró una sólida capacidad para crear un entorno colaborativo e inclusivo, en el que todos los miembros participaron activamente en la planificación, el establecimiento de metas y el cumplimiento de los objetivos. La propuesta de entregas parciales por parte de Abel permitió una distribución equilibrada del trabajo y una identificación oportuna de posibles errores, mientras que el cronograma interno gestionado por Belén promovió una planificación estructurada y transparente. Mateo reforzó la coordinación mediante reuniones periódicas que mantuvieron al equipo alineado, y Alex aseguró que los entregables técnicos respetaran tanto los tiempos como la coherencia del sistema. Cada una de estas acciones no solo favoreció la eficiencia del grupo, sino que también fortaleció el compromiso de los integrantes y la integración de sus aportes. La planificación colectiva y la comunicación constante contribuyeron a un ambiente de trabajo equitativo, donde se valoraron tanto las ideas individuales como los acuerdos comunes. \\
} \\
\hline
\end{longtable}


\newpage

# Capítulo I: Introducción

## Startup Profile

### Descripción de la Startup

***LLantaTech:*** **Innovación y Confianza en el Transporte Escolar**

LLantaTech es una startup peruana comprometida con la innovación en la gestión y la seguridad del transporte escolar en colegios privados, apoyándose en tecnologías avanzadas de Internet de las Cosas (IoT) y plataformas digitales de última generación. Nos especializamos en diseñar soluciones integrales que, más allá de optimizar rutas y recursos, sitúan la confianza de las familias y el bienestar de los estudiantes como ejes centrales de nuestro desarrollo. Nuestros sistemas de análisis de datos en tiempo real facilitan la toma de decisiones proactiva y el cumplimiento de los más exigentes estándares de calidad y normativas del sector. Con un firme compromiso por la privacidad y la protección de la información, proporcionamos herramientas intuitivas que empoderan a las instituciones educativas, a los operadores de transporte y a los padres de familia, garantizando transparencia total en cada trayecto. En LLantaTech, creemos en la colaboración constante con nuestros clientes para co-crear mejoras continuas, generando un impacto social positivo y redefiniendo los estándares de seguridad y eficiencia en el transporte escolar peruano.

![LLantaTech logo](src/img/logo/llantatech-logo.png)

::: box 
**Misión**

Brindar a colegios privados y a las familias herramientas tecnológicas robustas que optimicen la gestión del transporte escolar, fortalezcan la seguridad de los estudiantes y fomenten la confianza de todos los actores involucrados.
:::

::: box
**Visión**

Ser reconocidos a nivel nacional e internacional como líderes en soluciones de transporte escolar basadas en IoT, estableciendo nuevos estándares de excelencia, innovación y responsabilidad social.
:::

\newpage

### Perfiles de integrantes del equipo

Nuestro equipo está conformado por individuos apasionados y comprometidos, cada uno aportando sus habilidades únicas para lograr nuestros objetivos de manera efectiva y colaborativa. Aquí se muestran a nuestros miembros clave:

\definecolor{mybackground}{HTML}{eed6d1}

\begin{tcolorbox}[colframe=mybackground, colback=mybackground, boxrule=0.8mm, width=\textwidth, sharp corners]
{
\begin{minipage}[c]{0.3\textwidth}
\includegraphics[width=\linewidth]{src/img/integrantes/abel.jpg}
\end{minipage}
\hfill
\begin{minipage}[c]{0.65\textwidth}
\textbf{Abel Angel Ortega Huaraca} \\
\textit{Ingeniero de Software} \\
Me considero una persona responsable y comprometida en las funciones que se me designe. Conforme a mis habilidades, puedo adaptarme rápidamente al equipo y al ritmo de trabajo. Asimismo, puedo contribuir con información y soluciones a través de una exhaustiva investigación para los problemas que el proyecto presente.
\end{minipage}
}
\end{tcolorbox}

\begin{tcolorbox}[colframe=mybackground, colback=mybackground, boxrule=0.8mm, width=\textwidth, sharp corners]
{
\begin{minipage}[c]{0.3\textwidth}
\includegraphics[width=\linewidth]{src/img/integrantes/alex.jpg}
\end{minipage}
\hfill
\begin{minipage}[c]{0.65\textwidth}
\textbf{Alex Avila Asto} \\
\textit{Ingeniero de Software} \\
Soy una persona con buenas habilidades y adaptabilidad para todo lo relacionado a TI. Manejo un set robusto de tecnologías como C++, SQL, Java, Kotlin, etc. Por lo que puedo aportar al equipo con mis conocimientos técnicos y brindar soporte si lo amerita. 
\end{minipage}
}
\end{tcolorbox}

\begin{tcolorbox}[colframe=mybackground, colback=mybackground, boxrule=0.8mm, width=\textwidth, sharp corners]
{
\begin{minipage}[c]{0.3\textwidth}
\includegraphics[width=\linewidth]{src/img/integrantes/belen.jpg}
\end{minipage}
\hfill
\begin{minipage}[c]{0.65\textwidth}
\textbf{Belen del Rocio Ramos Rios} \\
\textit{Ingeniera de Software} \\
Soy estudiante del séptimo ciclo de la carrera de Ingeniería de Software. A lo largo de mi formación, he adquirido conocimientos en diversos lenguajes de programación como Java, C++, SQL y recientemente Kotlin. También tengo experiencia en el uso de frameworks como Spring Boot para el desarrollo backend, y Vue, Angular y Flutter para el desarrollo frontend. Me considero una persona comprometida, con habilidades para el trabajo en equipo y siempre dispuesta a dar lo mejor de mí en cada proyecto que emprendo.
\end{minipage}
}
\end{tcolorbox}

\begin{tcolorbox}[colframe=mybackground, colback=mybackground, boxrule=0.8mm, width=\textwidth, sharp corners]
{
\begin{minipage}[c]{0.3\textwidth}
\includegraphics[width=\linewidth, height=\linewidth, keepaspectratio=false]{src/img/integrantes/mateo.jpg}
\end{minipage}
\hfill
\begin{minipage}[c]{0.65\textwidth}
\textbf{Mateo Alejandro Vilchez Rios} \\
\textit{Ingeniero de Software} \\
Soy estudiante de la carrera de Ingeniería de Software cursando actualmente el 7mo ciclo. Me considero una persona eficiente, disciplinada y responsable. Poseo conocimientos Java, JavaScript y TypeScript. Manejo de Base de Datos relacionales. Conocimientos en Frameworks como Angular y Spring. Me comprometo a brindar todo el apoyo necesario para cumplir con todos los requerimientos.
\end{minipage}
}
\end{tcolorbox}

\newpage

## Solution Profile

En la era de la hiperconectividad y las crecientes exigencias de seguridad, el transporte escolar enfrenta retos cada vez más complejos. Los métodos tradicionales de supervisión —basados en registros manuales, comunicación puntual y seguimiento reactivo— resultan insuficientes para garantizar la tranquilidad de las familias y el cumplimiento de los estándares de calidad por parte de las instituciones educativas y las empresas de transporte.

Frente a este escenario, es imprescindible adoptar un enfoque integral que combine innovación tecnológica y procesos colaborativos. El perfil de solución de LLantaTech se enmarca en esta visión: busca ofrecer un modelo escalable y flexible que facilite la gestión proactiva del transporte escolar, mejore la visibilidad de cada trayecto y promueva la rendición de cuentas en todos los niveles operativos.

Nuestra propuesta se fundamenta en la integración de tecnologías emergentes con plataformas digitales intuitivas, con el objetivo de optimizar la planificación, fortalecer la comunicación entre actores y elevar los estándares de seguridad y eficiencia. De esta manera, LLantaTech aspira a redefinir la forma en que colegios, operadores de transporte y familias interactúan con el servicio de traslado de estudiantes, construyendo un entorno de confianza y excelencia operativa.

![Recurso extraído de Canva](src/img/cap1/solution.png)

\newpage

### Antecedentes y problemática

RutaKids es una startup peruana enfocada en ofrecer soluciones tecnológicas para mejorar la seguridad y eficiencia del transporte escolar en colegios privados. Actualmente se encuentra en fase de desarrollo, trabajando en una plataforma digital que permitirá a los padres monitorear en tiempo real el trayecto de sus hijos, a los colegios gestionar sus rutas y asistencias, y a los operadores de transporte organizar sus unidades. Se están diseñando las primeras versiones funcionales de la app y el dashboard, así como realizando validaciones con usuarios reales para asegurar que el producto responda a necesidades concretas.


::: info
***What***

RutaKids es una plataforma digital compuesta por una app móvil y un sistema web que permite gestionar, monitorear y comunicar todo lo relacionado con el transporte escolar. Su objetivo es brindar seguridad a los padres, eficiencia a los colegios y organización a los operadores.
:::

::: info
***Why***

Porque los métodos tradicionales para supervisar el transporte escolar son ineficientes, generan desconfianza y no ofrecen trazabilidad. RutaKids responde a la necesidad de digitalizar este servicio para garantizar la seguridad de los estudiantes y optimizar la operación de colegios y transportistas.
:::

::: info
***Where***

Inicialmente en colegios privados de Lima Metropolitana, con proyección de expansión a otras ciudades del país conforme se valide el modelo. La plataforma es accesible desde cualquier dispositivo con conexión a internet.
:::

::: info
***When***

La fase de desarrollo ya está en marcha. Se proyecta iniciar pruebas piloto durante el próximo ciclo escolar y escalar la solución de forma progresiva en el primer año.
:::

::: info
***Who***

Un equipo multidisciplinario que lidera la creación de RutaKids, compuesto por desarrolladores, diseñadores UX, expertos en educación, y personal técnico que trabaja en conjunto con colegios y operadores reales durante la etapa de validación.
:::

::: attn
***How***

Mediante el desarrollo de una app para padres y operadores, un panel web para colegios, e integración con dispositivos de rastreo GPS. Se seguirán prácticas de diseño centrado en el usuario y validaciones iterativas para garantizar la adopción del sistema.

:::

::: attn
***How Much***

RutaKids funcionará bajo un modelo de suscripción mensual. Se ofrecerá un plan piloto gratuito, un plan básico escalable y un plan premium con funciones avanzadas como reportes personalizados y soporte extendido. El presupuesto inicial incluye el desarrollo tecnológico, pruebas con usuarios, instalación de GPS y mantenimiento del sistema.
:::

\newpage

### *Lean UX Process.*

![Recurso extraído de Google](src/img/cap1/LeanUXProcess.png)

#### *Lean UX Problem Statements.*

::: note

***Problem Statement***

- Hemos observado que los padres de familia no se sienten completamente seguros ni informados sobre el trayecto de sus hijos al utilizar el servicio de transporte escolar, lo que genera ansiedad, llamadas constantes al colegio y desconfianza en el sistema educativo.
¿Cómo podríamos mejorar la visibilidad en tiempo real y la comunicación con los padres para que nuestro servicio aumente la confianza, reduzca el tiempo de respuesta ante incidentes y eleve la satisfacción en al menos un 30%?\newline

- Hemos observado que las instituciones educativas privadas aún gestionan el transporte escolar mediante procesos manuales y canales de comunicación no integrados, lo que causa ineficiencias operativas, baja trazabilidad y riesgos en el cumplimiento de normas de seguridad.
¿Cómo podríamos mejorar la planificación de rutas y el monitoreo operativo para que los colegios gestionen el transporte de manera un 40% más eficiente y alineada a los estándares normativos?\newline

- Hemos observado que los operadores de transporte escolar no cuentan con herramientas digitales integradas para la gestión diaria de sus flotas, lo que conlleva a desorganización, rutas ineficientes y problemas de comunicación con padres y colegios.
¿Cómo podríamos ofrecer una solución que facilite la gestión proactiva de rutas y responsabilidades, para que los operadores puedan optimizar recursos y profesionalizar su servicio?\newline

- Hemos observado que el sistema actual de transporte escolar en colegios privados no cumple adecuadamente con las necesidades de seguridad, coordinación y monitoreo en tiempo real, lo que ocasiona desconfianza en las familias, sobrecarga administrativa en los colegios y exposición a riesgos operativos.
¿Cómo podríamos mejorar la eficiencia, transparencia y seguridad de la gestión del transporte escolar para que todos los actores involucrados se beneficien y nuestra plataforma se convierta en el nuevo estándar nacional de movilidad estudiantil segura?
:::

\newpage

#### *Lean UX Assumptions.*

***Business Assumptions***

**1. El cliente necesita** garantizar la seguridad, trazabilidad y puntualidad en el traslado escolar de los estudiantes, sin depender de procesos manuales o comunicación informal.

**2. Las necesidades del cliente se resolverán mediante** una plataforma digital con tecnología IoT que permita el monitoreo en tiempo real de las movilidades escolares, alertas automatizadas y reportes inteligentes.

**3. Los clientes son (o serán)** instituciones educativas privadas, padres de familia preocupados por la seguridad de sus hijos y operadores de transporte escolar que desean digitalizar sus procesos.

**4. El cliente quiere** confianza, visibilidad en tiempo real y simplicidad **de nuestro servicio**, asegurando que puedan reaccionar a tiempo ante cualquier eventualidad durante el trayecto escolar.

**5. El cliente también puede obtener** una mejora significativa en la eficiencia operativa, reducción de incidentes no reportados y cumplimiento normativo mediante la automatización de procesos y trazabilidad completa del servicio.

**6. Obtendré mi base de clientes mediante** alianzas con colegios privados, programas piloto gratuitos, y campañas en redes sociales dirigidas a padres y operadores.

**7. Ganaré dinero mediante** suscripciones mensuales o anuales para colegios y operadores, además de servicios adicionales premium para padres como notificaciones personalizadas y acceso extendido al historial de rutas.

**8. Mi principal competencia son** sistemas GPS genéricos, soluciones locales poco especializadas, y el uso tradicional de planillas, WhatsApp o llamadas para el seguimiento del transporte escolar.

**9. Superaremos a la competencia mediante** una solución específica para el ecosistema escolar peruano, con enfoque en seguridad, facilidad de uso, integración de IoT y cumplimiento con las normativas del sector educativo.

**10. Mi mayor riesgo es** que las instituciones educativas o los operadores no adopten la solución por falta de presupuesto, desconocimiento del valor agregado o resistencia al cambio tecnológico.

**11. Solucionaremos el riesgo mediante** demostraciones prácticas, soporte técnico continuo, acompañamiento en la implementación y evidencia del retorno de inversión desde los primeros meses de uso.

**12. ¿Cuáles son las suposiciones que, si se demuestran falsas, harán que el proyecto fracase?**

- Los colegios están dispuestos a adoptar tecnología para optimizar su sistema de transporte.
    
- Los padres realmente valoran la visibilidad y seguridad en tiempo real del traslado escolar.  
  
- Los operadores están dispuestos a digitalizar sus procesos si cuentan con capacitación y soporte adecuados.
\newline

***Business Outcomes***

- **Esperamos lograr un aumento del 30% en la percepción de seguridad por parte de los padres de familia.** Medido a través de encuestas antes y después del uso del sistema.

- **Esperamos reducir en un 40% el tiempo que los colegios invierten en planificar rutas de transporte.** Como indicador de eficiencia operativa directa.

- **Esperamos reducir en un 50% los incidentes no reportados o comunicados tardíamente.** Gracias al monitoreo en tiempo real y las alertas automáticas.

- **Queremos alcanzar al menos 15 colegios clientes en los primeros 12 meses.** Lo cual reflejará validación del modelo y su necesidad en el mercado.

- **Anticipamos una disminución del 35% en las llamadas de padres al colegio para consultar sobre el paradero del alumno.** Como señal de mayor confianza y transparencia del sistema.

- **Buscamos lograr que el 70% de las rutas activas estén digitalizadas en los primeros 3 meses de implementación.** Para evaluar adopción efectiva de la solución.

- **Proyectamos una tasa de retención superior al 25% entre colegios y operadores tras el primer ciclo escolar completo.** Como medida de sostenibilidad del producto.

- **Queremos que al menos el 90% de los choferes usen la app diariamente durante el primer mes de implementación.** Indicador de aceptación del sistema por parte del usuario operativo.\newline

***User Assumptions***

**1. ¿Quién es el usuario?**  

Padres de familia con hijos en colegios privados, directores o administradores escolares responsables de logística, y operadores de transporte escolar (choferes y supervisores).


**2. ¿Dónde encajaría nuestro producto en la vida (o trabajo) del usuario?**  

- Para los padres: en su rutina diaria, al momento de dejar o recoger a sus hijos, y al monitorear su ubicación en tiempo real desde el trabajo o casa.  
  
- Para el colegio: durante la planificación de rutas, control de asistencia y respuesta ante incidentes.  
  
- Para los operadores: en la gestión diaria del transporte, organización de rutas y coordinación con colegios y padres.

**3. ¿Qué problemas resuelve el producto para el usuario?**  

- Falta de visibilidad sobre el trayecto del alumno.  
  
- Comunicación tardía o inexistente en caso de desvíos o retrasos.  
  
- Desorganización y exceso de carga administrativa en la gestión del transporte escolar.  
  
- Inseguridad percibida por padres sobre el sistema de movilidad escolar.

**4. ¿En qué contexto utiliza el usuario el producto?**  

- Los padres acceden desde su celular durante el día para revisar notificaciones o localizar a sus hijos.  

- El colegio lo usa como plataforma de gestión diaria y monitoreo de flotas.  
  
- Los operadores acceden desde una app móvil antes y durante cada ruta.

**5. ¿Qué características son esenciales para el usuario? ¿Y por qué?**  

- **Ubicación en tiempo real**: los padres quieren saber dónde están sus hijos. 
   
- **Alertas automáticas de llegada y salida**: reduce la necesidad de llamar o preguntar. 
   
- **Dashboard de control para el colegio**: facilita la supervisión y planificación.  
  
- **Registro automático de asistencia**: mejora la trazabilidad.  
  
- **Interfaz simple e intuitiva**: todos los actores deben usarla sin necesidad de capacitación técnica avanzada.


**6. ¿Cómo debería verse y comportarse el producto?** 

- Diseño limpio, moderno y accesible desde cualquier dispositivo.  
  
- Navegación clara y rápida, con flujos sencillos para cada tipo de usuario.  
  
- La app debe abrirse y cargar la ubicación en segundos.  
  
- Debe emitir notificaciones discretas pero efectivas.  
  
- El administrador debe tener acceso inmediato a reportes y visualización de rutas.\newline

***User Outcomes***

- **Los padres quieren sentirse tranquilos** sabiendo que sus hijos están seguros durante el trayecto escolar, gracias a la visibilidad en tiempo real desde su celular.

- **Los colegios quieren reducir su carga operativa** automatizando la gestión de rutas, la asistencia y la comunicación con los padres, logrando una gestión más eficiente y moderna.

- **Los operadores de transporte quieren profesionalizar su servicio**, usando herramientas digitales que les permitan organizar mejor sus rutas, responder ante imprevistos y mejorar su relación con colegios y familias.

- **Los padres esperan recibir alertas inmediatas y confiables**, sin tener que llamar al colegio o depender de grupos de WhatsApp para saber si su hijo llegó bien.

- **Los usuarios valoran una solución fácil de usar**, que no requiera capacitación avanzada y funcione bien en dispositivos móviles de uso común.

- **Los directivos escolares desean contar con reportes visuales y automáticos**, que les permitan tomar decisiones informadas y cumplir con normativas del sector educativo.

- **Todos los usuarios esperan mayor transparencia**, trazabilidad y rapidez en la comunicación respecto al transporte escolar, mejorando la confianza en el sistema.

- **Los usuarios buscan una experiencia fluida**, sin errores ni demoras, que les permita integrarla fácilmente en su rutina diaria (desde la app o el panel web).\newline


***Features Assumptions***

**1. Visibilidad en tiempo real (Tracking GPS):**

- **Suposición:** Si los padres pueden ver la ubicación del vehículo en tiempo real, se sentirán más tranquilos y reducirán las llamadas al colegio.
  
- **Riesgo:** Si el tracking no es preciso o falla frecuentemente, los padres perderán confianza en la plataforma y volverán a métodos informales de consulta.


**2. Alertas automáticas de llegada y salida:**

- **Suposición:** Las notificaciones automáticas permitirán a los padres mantenerse informados sin necesidad de intervenir activamente.
  
- **Riesgo:** Si las alertas llegan con retraso o no son claras, los padres podrían considerarlas poco útiles y desactivar la función, perdiendo valor clave del producto.


**3. Registro automático de asistencia (RFID/NFC):**

- **Suposición:** Automatizar el registro de ingreso y salida de los estudiantes aumentará la seguridad y facilitará la trazabilidad para colegios y padres.
  
- **Riesgo:** Si el sistema no reconoce correctamente a los alumnos o es lento, se perderá confianza en su fiabilidad y será reemplazado por procesos manuales.


**4. Dashboard para colegios:**

- **Suposición:** Un panel de control centralizado facilitará la gestión de rutas, la visualización de reportes y la toma de decisiones operativas.
  
- **Riesgo:** Si el dashboard es complejo o poco intuitivo, el personal administrativo evitará usarlo y se limitarán sus beneficios.

**5. Aplicación móvil para padres y conductores:**

- **Suposición:** Una app con navegación simple y clara permitirá a los padres monitorear fácilmente y a los choferes operar sin distracciones ni errores.
  
- **Riesgo:** Si la app presenta fallos, consume muchos datos o requiere dispositivos de gama alta, su adopción será baja.


**6. Sistema de notificaciones configurables:**

- **Suposición:** Dar control al usuario sobre qué alertas recibir y cuándo aumentará la satisfacción y percepción de personalización.
  
- **Riesgo:** Si el sistema de configuración es complejo o no cumple con lo prometido, generará frustración y desuso de las notificaciones.

**7. Generación de reportes automáticos:**

- **Suposición:** Los colegios valorarán tener reportes listos para reuniones, auditorías o decisiones internas.
  
- **Riesgo:** Si los reportes no son claros, exportables o personalizables, se percibirán como inútiles y no se justificaría el valor del sistema.


**8. Integración con plataformas educativas o sistemas escolares:**

- **Suposición:** La posibilidad de integrarse con otros sistemas institucionales facilitará la adopción por parte de colegios ya digitalizados.
  
- **Riesgo:** Si la integración técnica es complicada o limitada, el sistema será considerado poco flexible o difícil de implementar.\newline

#### *Lean UX Hypothesis Statements.*

::: tip

**1. Creemos que lograremos** aumentar la satisfacción de los padres en un 30%. **Si** los padres preocupados por la seguridad de sus hijos **obtienen** visibilidad en tiempo real del trayecto escolar **con** una aplicación móvil intuitiva y notificaciones automáticas de llegada y salida.\newline

**2. Creemos que lograremos** reducir en un 40% la carga operativa en los colegios. **Si** los administradores escolares **obtienen** un dashboard centralizado para gestionar rutas, asistencia y reportes **con** una plataforma digital accesible y automatizada.\newline

**3. Creemos que lograremos** incrementar la adopción del sistema en un 25% durante el primer año. **Si** los colegios y operadores de transporte **obtienen** una solución flexible, con soporte técnico y demostraciones prácticas **con** planes accesibles y personalización para su realidad operativa.\newline

**4. Creemos que lograremos** disminuir en un 50% los incidentes no reportados. **Si** los padres y el personal del colegio **obtienen** alertas automáticas y acceso inmediato a la ubicación de las movilidades **con** tecnología IoT conectada a la plataforma.\newline

**5. Creemos que lograremos** lograr una tasa de retención superior al 25% tras el primer ciclo escolar. **Si** colegios y operadores que implementan la plataforma **obtienen** mejoras medibles en eficiencia, confianza de los padres y cumplimiento normativo **con** funcionalidades personalizadas y soporte continuo.
:::

\newpage

#### Lean UX Canvas.

![Artefacto creado en Figma [URL](https://www.figma.com/design/K3gw63Gdzr8KOgE32BgreJ/Lean-UX-Canvas-Template-by-Jeff-Gothelf-(Community)?node-id=0-1&t=q5cZNvpSyA30WQQd-1)](src/img/cap1/LeanUXCanvas.pdf) 

\newpage

## Segmentos objetivo.

En esta sección se identifican los segmentos objetivos clave a los que está dirigida la solución de RutaKids. A través del análisis de variables demográficas, educativas y conductuales, se definen los perfiles de usuarios que interactúan con el sistema de transporte escolar. Este enfoque permite diseñar una solución centrada en las personas, asegurando que cada funcionalidad responda a las necesidades reales de padres, personal escolar y operadores de transporte.

![Artefacto creado en Figma [URL](https://www.figma.com/design/K3gw63Gdzr8KOgE32BgreJ/Lean-UX-Canvas-Template-by-Jeff-Gothelf--Community-?node-id=2015-2&t=urisk948grqgcqCL-1)](src/img/cap1/SegmentoObjetivo1.pdf) 

![Artefacto creado en Figma [URL](https://www.figma.com/design/K3gw63Gdzr8KOgE32BgreJ/Lean-UX-Canvas-Template-by-Jeff-Gothelf--Community-?node-id=2015-2&t=urisk948grqgcqCL-1)](src/img/cap1/SegmentoObjetivo2.pdf) 

\newpage

# Capítulo II: Requirements Elicitation & Analysis

Antes de construir una solución tecnológica efectiva, es esencial entender a fondo el problema, a los usuarios y el entorno en el que la solución será implementada. Este capítulo presenta el proceso de Requirements Elicitation & Analysis, una fase crítica en el desarrollo de soluciones centradas en el usuario. Aquí se identifican y analizan las necesidades del público objetivo, se estudia a la competencia y se utilizan técnicas como entrevistas, mapeo de tareas y escenarios para definir con claridad los requisitos funcionales y no funcionales del sistema. La información obtenida en esta etapa servirá como base sólida para el diseño e implementación de un producto alineado con las expectativas del mercado y con alto impacto en su adopción y uso.

## Competidores.

![Recurso extraído de Canva](src/img/cap2/competidores-introduccion.png)

En un mercado donde la seguridad escolar, la eficiencia operativa y la comunicación con los padres se han convertido en prioridades fundamentales, contar con herramientas tecnológicas ya no es una opción, sino una necesidad. Por ello, es imprescindible realizar un análisis detallado de las soluciones existentes, que permita identificar áreas de mejora, oportunidades de diferenciación y enfoques innovadores capaces de posicionar a RutaKids como una opción estratégica para las instituciones educativas que buscan modernizar sus servicios de transporte.

\newpage

**Competidores:**

- ***Ultravision:*** Este servicio ofrece una solución modular para el control y seguimiento de transporte escolar mediante GPS y dispositivos embarcados. Sus herramientas permiten gestionar estudiantes en tiempo real, emitir alertas y generar reportes detallados de asistencia y rutas. Está orientado principalmente a instituciones que buscan trazabilidad y control de flotas.

![Imagen extraída de Ultravision [(URL)](https://www.ulvisions.com/es/ultravision-school-bus-solution)](src/img/cap2/ultravision-landing.png)

\vspace{1em}

- ***CalAmp:*** Es una empresa internacional especializada en soluciones de telemetría y gestión de flotas. Aunque su enfoque no es exclusivamente escolar, su plataforma permite el monitoreo en tiempo real de vehículos, alertas automáticas y reportes de desempeño, siendo utilizada por operadores de transporte escolar a gran escala.

![Imagen extraída de CalAmp [(URL)](https://www.calamp.com/es/)](src/img/cap2/calAmp-landing.png)


\newpage

- ***Satgeo:*** Es una plataforma latinoamericana orientada al control del transporte escolar. Integra una aplicación para padres, panel de administración para instituciones educativas y funciones automatizadas de asistencia. Su enfoque regional le permite adaptarse fácilmente a contextos locales.

![Imagen extraída de Satgeo [(URL)](https://satgeo.com/control-de-estudiantes)](src/img/cap2/satgeo-landing.png)
\vspace{1em}

- ***BusWhere:*** Es una solución enfocada en el rastreo de autobuses escolares. Ofrece una aplicación para padres y un sistema de visualización en la nube para escuelas, que permite conocer en tiempo real la ubicación de los estudiantes. Se destaca por su interfaz simple, alertas de llegada y experiencia amigable.

![Imagen extraída de BusWhere [(URL)]( https://www.buswhere.com/es/solutions-for-schools )](src/img/cap2/buswhere-landing.png)

\newpage

### Análisis competitivo.

Tras haber identificado a los principales actores en el ámbito del transporte escolar inteligente, se presenta a continuación un análisis comparativo que permite evaluar sus propuestas de valor. Este análisis se enfoca en aspectos clave como el enfoque de mercado, funcionalidades principales, diferenciadores y grado de especialización. La finalidad es identificar patrones, ventajas competitivas y posibles áreas de oportunidad que orienten el posicionamiento estratégico de nuestra solución.

![](src/img/cap2/analisisCompetitivo_1.png)

![](src/img/cap2/analisisCompetitivo_2.png)

![](src/img/cap2/analisisCompetitivo_3.png)

\newpage

### Estrategias y tácticas frente a competidores.

En el dinámico entorno empresarial actual, la formulación de estrategias efectivas requiere una comprensión profunda de las capacidades internas de la organización y de las condiciones del entorno. 

\begin{quote}
Según Tarziján (2019), la formulación de la estrategia comienza con el análisis del entorno de la empresa desde el punto de vista de debilidades, fortalezas, oportunidades y amenazas, evaluando la preparación de la empresa para competir en el mercado. 
\end{quote}

\vspace{1em}

Este enfoque permite a las organizaciones identificar oportunidades de diferenciación, anticipar los movimientos de la competencia y tomar decisiones fundamentadas para asegurar su sostenibilidad y crecimiento.

En el caso de RutaKids, una solución tecnológica orientada al transporte escolar seguro y eficiente, el análisis competitivo previamente desarrollado ha permitido comprender mejor el posicionamiento de los actores clave del mercado, así como detectar espacios estratégicos aún poco explotados.

Sobre esta base, se presentan a continuación las estrategias competitivas clave y las tácticas específicas propuestas para fortalecer la posición de RutaKids, tanto frente a la competencia actual como ante las exigencias emergentes del sector.

\vspace{1em}

**Estrategias competitivas para** ***RutaKids***

\vspace{1em}

::: box
**Innovación tecnológica centrada en la seguridad escolar:**
:::

**Estrategia:** *RutaKids*  debe consolidarse como una solución más allá del rastreo vehicular tradicional, posicionándose como un ecosistema tecnológico que automatiza procesos críticos como la asistencia estudiantil, el control de ingreso y el monitoreo predictivo de rutas. Anticiparse a las demandas del sistema educativo digital será clave para mantener su ventaja competitiva.

**Tácticas propuestas:**

   - Incorporar funcionalidades avanzadas como geocercas inteligentes, alertas automatizadas y análisis de comportamiento de rutas.
  
   - Invertir en I+D para desarrollar módulos complementarios de control escolar y generación de reportes para autoridades educativas.

   - Establecer un ciclo de actualizaciones periódicas basado en retroalimentación de usuarios (padres, instituciones, transportistas).

\vspace{2em}

::: box
**Segmentación según perfil institucional:**
:::
   
**Estrategia:** La propuesta de *RutaKids* debe adaptarse a distintos perfiles del sector educativo: desde pequeñas instituciones rurales hasta redes educativas privadas o municipalidades. La flexibilidad funcional y comercial es clave para responder a sus diversas realidades operativas.



**Tácticas propuestas:**

   - Diseñar planes escalables ajustados al número de estudiantes, unidades vehiculares o zonas geográficas.
  
   - Adaptar rutas, calendarios y funcionalidades según las particularidades culturales y logísticas de cada región.
  
   - Desarrollar campañas diferenciadas según el público objetivo: directores, asociaciones de padres, municipios o empresas de transporte.

\vspace{2em}

::: box
**Construcción de redes y alianzas estratégicas:**
:::
   
**Estrategia:** *RutaKids* debe fortalecer su presencia a través de alianzas con actores clave del ecosistema educativo y tecnológico, que le permitan ampliar su alcance, aumentar su credibilidad y facilitar procesos de adopción institucional.

**Tácticas propuestas:**

   - Establecer convenios con UGELs, DREs y gobiernos locales para implementación en zonas piloto.
  
   - Integrarse con operadores de transporte escolar mediante acuerdos de uso conjunto de plataforma.

   - Vincularse con soluciones EdTech existentes para ofrecer paquetes integrados (gestión escolar, pagos, comunicaciones).

\newpage

::: box
**Escalamiento regional con visión latinoamericana:**
:::
   
**Estrategia:** Una vez consolidada su presencia en el mercado nacional, *RutaKids* debe proyectarse hacia mercados latinoamericanos con necesidades similares de modernización y digitalización del transporte escolar.

**Tácticas propuestas:**

   - Realizar estudios comparativos para identificar países con alto potencial de adopción (como Bolivia, Ecuador o Colombia).
  
   - Asegurar la adecuación de la plataforma a marcos normativos y culturales de cada país.
  
   - Aplicar un modelo de expansión progresiva basado en aliados comerciales o distribuidores locales.

\newpage

**Tácticas Específicas para para el Fortalecimiento de *RutaKids***

\vspace{1em}

::: box
**Marketing Diferenciado y Posicionamiento Estratégico**
:::

**Táctica:**  
Desarrollar una identidad de marca clara y confiable que refleje el compromiso de RutaKids con la seguridad escolar y la transformación digital, destacando sus beneficios tecnológicos y sociales frente a la competencia.

**Acciones:**

  - Crear contenido audiovisual y gráfico que ilustre, desde casos reales, el impacto positivo del sistema en la comunidad educativa.

  - Participar en eventos del sector educativo y tecnológico para aumentar visibilidad institucional y generar alianzas estratégicas.

  - Adaptar los mensajes de comunicación según el perfil del usuario (padres, colegios, transportistas), destacando el valor específico para cada grupo.

\vspace{2em}

::: box
**Monitoreo Competitivo Continuo**
:::

**Táctica:**  
Establecer un sistema sistemático de vigilancia del entorno competitivo para anticipar cambios en el mercado, identificar oportunidades de innovación y ajustar la estrategia de RutaKids en tiempo real.

**Acciones:**

  - Comparar periódicamente precios, funcionalidades y propuestas de valor de competidores locales y regionales.

  - Analizar tendencias emergentes en tecnología educativa y movilidad escolar para detectar innovaciones aplicables.
  
  - Realizar sesiones de benchmarking cada trimestre para revisar la posición de RutaKids y actualizar su hoja de ruta comercial y técnica.

\newpage

::: box
**Optimización continua de la experiencia de usuario (UX)**
:::

**Táctica:** Priorizar la mejora continua de la experiencia de usuario en sus plataformas digitales, garantizando interfaces intuitivas, accesibles y funcionales para todos los actores involucrados: padres, instituciones educativas y transportistas.  

**Acciones:**

   - Establecer canales permanentes de retroalimentación dentro de la aplicación, permitiendo recoger sugerencias, reportes de errores y valoraciones del uso.

   - Realizar pruebas de usabilidad periódicas con usuarios reales de diferentes perfiles socioeducativos, considerando variables como edad, nivel de alfabetización digital y contexto urbano o rural.

   - Ajustar la interfaz gráfica y la arquitectura de navegación con base en los resultados obtenidos, incorporando elementos visuales claros y accesibles, así como funciones simplificadas para usuarios con menor familiaridad tecnológica.

\vspace{2em}

::: box
**Estructuración flexible de precios y modelos comerciales**
:::

**Táctica:** Implementar un modelo de precios adaptable que se ajuste a las capacidades presupuestales y necesidades funcionales de los distintos tipos de instituciones educativas.

**Acciones:**

   - Diseñar planes escalables que se ajusten a variables como el número de estudiantes, unidades vehiculares o características del servicio contratado.

   - Establecer esquemas de descuentos por contratación anual, licencias por volumen o implementación a nivel de red educativa.

   - Considerar la introducción de un modelo freemium con funcionalidades básicas disponibles sin costo durante un periodo limitado, como estrategia de entrada para instituciones que aún evalúan la solución.

\newpage

::: box
**Fortalecimiento de la fidelización institucional y del vínculo con los usuarios:**
:::

**Táctica:** Implementar una estrategia orientada a consolidar relaciones de largo plazo con las instituciones educativas y las familias usuarias del servicio.

**Acciones:**

   - Diseñar e implementar un programa de referidos institucionales, ofreciendo beneficios económicos o acceso a funciones premium a aquellas escuelas que recomienden RutaKids a otras entidades educativas.

   - Brindar capacitaciones periódicas y soporte técnico activo al personal administrativo y operativo, promoviendo un uso eficiente y sostenido de la plataforma.

   - Establecer un sistema de comunicaciones personalizadas que incluya reportes mensuales, alertas relevantes y sugerencias prácticas para mejorar la experiencia de uso en función del perfil del usuario (padres, directores o transportistas).


\newpage

## Entrevistas.
Las entrevistas están diseñadas para recolectar tanto información objetiva (edad, zona de residencia, ocupación, uso de tecnología) como subjetiva (motivaciones, frustraciones, percepción de seguridad), fundamentales para la construcción de arquetipos (User Personas), Empathy Maps y Journey Maps.

![Recurso extraído de Canva](src/img/cap2/entrevistas-introduccion.png)

::: note
Para acceder al video de las entrevistas, haga click en la [URL](https://upcedupe-my.sharepoint.com/:v:/g/personal/u202210059_upc_edu_pe/EV28HExaIsFIh22vN6-VY-sBzdw5JApHhMXCx5KyLMdBPQ?nav=eyJyZWZlcnJhbEluZm8iOnsicmVmZXJyYWxBcHAiOiJTdHJlYW1XZWJBcHAiLCJyZWZlcnJhbFZpZXciOiJTaGFyZURpYWxvZy1MaW5rIiwicmVmZXJyYWxBcHBQbGF0Zm9ybSI6IldlYiIsInJlZmVycmFsTW9kZSI6InZpZXcifX0%3D&e=X20C3t)
:::

\newpage

### Diseño de entrevistas.

Para el diseño de las entrevistas se definieron dos segmentos objetivo con perfiles claramente diferenciados: Padres de familia con hijos en edad escolar y Directivos escolares o personal administrativo. 

::: box
**Segmento Objetivo 1:** Directivos escolares o personal administrativo
:::

**Objetivo:**

Explorar el rol real del colegio en la movilidad escolar, identificar brechas de control y comunicación, y conocer la apertura institucional hacia soluciones tecnológicas que podrían profesionalizar el servicio.


**Perfil general**

1) ¿Podría indicarnos su nombre, edad y cargo dentro de la institución?

2) ¿En qué distrito se ubica el colegio y qué tipo de gestión tiene (pública, privada, parroquial, comunitaria)?

**Gestión actual del transporte escolar**

3) ¿Cómo está organizado actualmente el transporte escolar en su colegio? ¿Quiénes definen y gestionan los aspectos clave como rutas, horarios y selección de choferes?

4) ¿Qué grado de participación tiene la institución en ese proceso? ¿El colegio interviene directamente o actúa más como facilitador?

5) ¿Cómo se asegura el colegio de que los alumnos lleguen y regresen correctamente? ¿Se registra de alguna forma esta información?

6) ¿Qué herramientas o canales utilizan para coordinar el servicio (por ejemplo, WhatsApp, Excel, llamadas)? ¿Han intentado implementar alguna solución digital?

7) ¿Qué problemas o limitaciones han identificado con el modelo actual (por ejemplo, falta de trazabilidad, dependencia del chofer, poca coordinación)?


**Comunicación con familias y manejo de incidentes**

8) ¿Cómo se informa a los padres sobre retrasos, cambios de ruta o emergencias? ¿Quién suele encargarse de comunicar estas situaciones?

9) ¿Se presentan con frecuencia incidentes o reclamos relacionados al transporte? ¿En qué casos suele intervenir el colegio?

10) ¿Qué tan tranquilos cree que se sienten los padres con el sistema actual? ¿Le han transmitido preocupaciones?

**Interés y apertura hacia soluciones tecnológicas**

11) ¿Han evaluado antes alguna solución digital para mejorar la coordinación del transporte? ¿Cuál fue su experiencia?

12) ¿Qué funcionalidades considera prioritarias en una plataforma para la movilidad escolar?
   - Seguimiento del bus en tiempo real
   - Notificaciones automáticas de subida/bajada
   - Registro de asistencia
   - Reportes para la institución
   - Panel de control para padres y colegio


13) ¿Qué beneficios cree que una app así traería a su comunidad educativa?

14) ¿Qué obstáculos ve para su implementación (por ejemplo, acceso a internet, costos, resistencia de padres o choferes)?

\newpage

::: box
**Segmento Objetivo 2:** Padres de familia con hijos en edad escolar
:::

**Objetivo:**  
Entender cómo los padres viven la experiencia del transporte escolar, sus niveles de confianza, frustraciones actuales, apertura a soluciones digitales y disposición a pagar por servicios que mejoren seguridad y tranquilidad.

**Perfil general** 

1) ¿Cuál es tu nombre, edad y ocupación?

2) ¿Cuántos hijos tienes y en qué niveles educativos están?

3) ¿Usan actualmente movilidad escolar? ¿Cuántos días a la semana?

**Comunicación y seguimiento actual**  

4) ¿Cómo te enteras si tu hijo(a) llegó al colegio o a casa?

5)  ¿Quién suele avisarte si hay algún retraso o imprevisto con el transporte?

6) ¿En qué momento del día sueles preocuparte más por la movilidad escolar: al dejarlo/a, al recogerlo/a o en todo momento?

7) ¿Cuál ha sido la situación más preocupante que has vivido con la movilidad escolar?

**Percepción del servicio actual** 

8) ¿Cómo calificarías el servicio de movilidad actual en cuanto a seguridad, puntualidad y comunicación? (0 al 10, justifica)

9) ¿Qué es lo que menos te gusta o lo que cambiarías de inmediato?


**Uso y apertura a tecnología** 

10) ¿Qué tipo de celular usas actualmente? (Marca/modelo si sabes, y si es Android o iPhone)

11) ¿Usas apps regularmente para comunicarte con el colegio? ¿Cuáles y para qué?

12) ¿Te gustaría poder seguir el trayecto de tu hijo(a) en tiempo real? ¿Por qué?

13) Si pudieras recibir alertas automáticas (subida, bajada, llegada), ¿te sería útil o sientes que sería demasiado?

**Confianza y percepción de seguridad** 

14) ¿Qué es lo que más te genera desconfianza en el sistema actual?

15) ¿Qué tendría que pasar para que dejaras de usar la movilidad actual?

16) ¿Confías más en el chofer, la institución, o en algún sistema de control adicional?

**Valor percibido y disposición de pago** 

17) Si una solución digital te brindara tranquilidad, ¿estarías dispuesto/a a pagar por ella?

18) ¿Qué características tendría que tener para que sientas que vale lo que cuesta?

19) ¿Prefieres que lo gestione directamente el colegio o que sea una opción contratada por los padres?

20) Imagina el sistema de movilidad ideal:
  - ¿Cómo te informaría?
  - ¿Qué verías en tu celular?
  - ¿Qué podrías controlar tú?


\newpage

### Registro de entrevistas.

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

### Análisis de entrevistas.

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

**Estadísticas y Porcentajes**


![Creado en Excel](src/img/cap2/grafico1.png)

![Creado en Excel](src/img/cap2/grafico2.png)

![Creado en Excel](src/img/cap2/grafico3.png)

![Creado en Excel](src/img/cap2/grafico4.png)

\newpage

**Análisis de datos**

-Todos los directivos entrevistados indicaron que el transporte escolar es gestionado de forma externa por los padres, sin participación de la institución educativa. Esta situación genera preocupaciones frecuentes por la falta de control, puntualidad y seguridad.

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


## Needfinding.

Para garantizar que las soluciones propuestas respondan efectivamente a los problemas reales de los usuarios, resultó fundamental comprender a fondo sus necesidades, contextos y comportamientos. En un contexto donde el transporte escolar enfrenta retos crecientes debido a las demandas de seguridad y eficiencia, era imprescindible adoptar un enfoque de investigación centrado en el usuario que permitiera identificar oportunidades de innovación genuina. Durante esta etapa de needfinding, se llevó a cabo una exploración detallada mediante técnicas como la observación directa, entrevistas semiestructuradas y la aplicación de herramientas de empatía. Este proceso no solo nos permitió detectar las tareas clave, frustraciones, expectativas y objetivos de los distintos actores involucrados (padres, estudiantes, colegios y operadores de transporte), sino también descubrir tensiones ocultas y necesidades latentes que no siempre son explícitas en interacciones superficiales.

A partir de la información recolectada, se desarrollaron perfiles de usuario que capturan las características esenciales de nuestros grupos de interés. Asimismo, la elaboración de mapas de empatía nos permitió comprender mejor los pensamientos, emociones, preocupaciones y aspiraciones de los usuarios frente al servicio de transporte escolar. Complementariamente, a través de customer journeys se mapeó la experiencia completa de los usuarios, identificando momentos críticos de fricción y oportunidad a lo largo del proceso de traslado.

![Imagen extraída de Canva](src/img/cap2/intro_needfinding.png)

\newpage

### User Personas.
Presentamos perfiles representativos de nuestros usuarios objetivos. Estos arquetipos nos ayudan a diseñar centrados en sus motivaciones, frustraciones y objetivos.

**User Persona 1 - Segmento Tutor/Padre Apoderado**

Esteban representa a los padres que buscan seguridad, puntualidad y confianza en el servicio de transporte escolar.

![User Persona 1 - Recurso de Figma](https://i.postimg.cc/5tVd8BDb/user-person-esteban.png)

\newpage

**User Persona 2 - Segmento Administrador Educativo**

Carolina representa a las administradoras que necesitan eficiencia, control y visibilidad en la gestión del transporte escolar.

![User Persona 2 - Recurso de Figma](https://i.postimg.cc/GmYnB77X/user-person-carolina.png)

\newpage

### User Task Matrix.

Se mapea la relación entre los usuarios y sus tareas principales. Esto nos permite priorizar funcionalidades clave del sistema según las necesidades del segmento.

![User Task Matrix - Recurso de Miro](https://i.postimg.cc/JnKLrs6m/task-matrix.png)

\newpage

### User Journey Mapping.

Visualizamos el recorrido actual de cada usuario con el servicio. Esta herramienta permite identificar puntos de dolor, emociones y oportunidades de mejora.

**User Journey – Esteban (Padre de familia)**
Muestra cómo Esteban experimenta el servicio día a día, destacando momentos críticos como la espera o la llegada del bus.

![User Journey Mapping 1 - Recurso de Miro](https://i.postimg.cc/vHCdZFz1/user-journey-esteban.png){ width=90% }

**User Journey – Carolina (Administradora)**
Refleja las acciones y frustraciones que Carolina enfrenta al gestionar manualmente el transporte escolar.

![User Journey Mapping 2 - Recurso de Miro](https://i.postimg.cc/ZKWSmKrt/user-journey-carolina.png){ width=90% }

\newpage

### Empathy Mapping.

Ayuda a profundizar en la perspectiva emocional y racional de cada usuario: lo que piensa, siente, ve, escucha, dice y hace.

**Empathy Map – Esteban**

Nos permite entender el entorno emocional de Esteban frente a la seguridad y control del transporte escolar.

![Empathy Mapping 1 - Recurso de Miro](https://i.postimg.cc/Y2nHTmLz/empathy-esteban.png)

\newpage

**Empathy Map – Carolina**

Expone las preocupaciones, necesidades y entorno de Carolina como gestora del sistema de transporte.

![Empathy Mapping 2 - Recurso de Miro](https://i.postimg.cc/BbVfFdfV/empathy-carolina.png)

\newpage

### As-is Scenario Mapping.

Describe cómo es actualmente la experiencia del usuario sin una solución tecnológica centralizada. Se evidencian fricciones, ineficiencias y oportunidades.

**As-Is Scenario – Esteban**

Esteban enfrenta incertidumbre en los horarios y poca información en tiempo real.

![As-is Scenario Mapping 1 - Recurso de Miro](https://i.postimg.cc/tJTHY9w6/as-is-esteban.png){ width=75% }

**As-Is Scenario – Carolina**

Carolina gestiona procesos con llamadas y hojas de cálculo, con baja automatización.

![As-is Scenario Mapping 2 - Recurso de Miro](https://i.postimg.cc/50fJWBmn/as-is-carolina.png){ width=75% }

\newpage

## Ubiquitous Language.

- **Alumno**: Niño o niña que utiliza el servicio de transporte escolar. Es quien porta la Tarjeta RFID y genera eventos de abordaje y descenso. (Sinónimos: Estudiante, Niño)

- **Padre de Familia**: Persona responsable del Alumno (padre, madre o apoderado) que recibe notificaciones y puede gestionar permisos. (Sinónimos: Padre, Madre, Apoderado)

- **Conductor**: Chofer designado para una Unidad de Transporte; interactúa con la app Conductor y valida abordajes/desabordajes. (Sinónimos: Chofer)

- **Administrador Escolar**: Personal de la institución que configura Rutas, Paradas, Alumnos y Conductores y supervisa reportes. (Sinónimos: Admin, Colegio)

- **Tarjeta RFID**: Tarjeta (o llavero) pasiva, asignada de forma única a un Alumno para autenticarse al acercarla al Lector.

- **Lector RFID**: Dispositivo IoT instalado en la Unidad que lee la Tarjeta RFID y envía eventos en tiempo real.

- **Unidad de Transporte**: Vehículo escolar identificado por placa y código interno, equipado con Lector RFID y GPS.

- **App RutaKids Conductor**: Aplicación móvil vinculada a la Unidad; muestra la lista de Alumnos por Parada y confirma incidentes.

- **Backend RutaKids**: Plataforma en la nube que procesa eventos, reglas de negocio y persiste datos.

- **Panel de Control**: Interfaz web para Administradores Escolares y Operadores de Flota.

- **Ruta**: Conjunto ordenado de Paradas asociadas a una Institución y un Horario recurrente.

- **Parada**: Punto geográfico donde se recoge o deja Alumnos. Incluye ventana de tiempo y lista de Alumnos asignados.

- **Trayecto**: Ejecución diaria de una Ruta en una fecha concreta.

- **Horario**: Reglas de recurrencia de la Ruta (días laborables, hora de inicio y fin estimada).

- **Alumno Abordó Unidad**: Evento emitido cuando un Alumno validó su Tarjeta y subió a la Unidad.

- **Alumno Descendió Unidad**: Evento emitido cuando un Alumno validó su Tarjeta al salir de la Unidad.

- **Tarjeta No Reconocida**: Evento emitido cuando se leyó un UID no asociado a ningún Alumno.

- **Incidencia Reportada**: Evento emitido cuando el Conductor registra un evento anómalo (retraso, avería, etc.).

- **Cambio De Ruta Programado**: Evento emitido cuando un Admin modificó la configuración de una Ruta.

- **Registrar Alumno**: Comando para crear la Entidad Alumno y vincular al Padre de Familia.

- **Asignar Tarjeta**: Comando para asociar Tarjeta RFID a Alumno.

- **Programar Ruta**: Comando para crear o actualizar una Ruta, su Horario y Paradas.

- **Marcar Abordaje**: Comando para forzar confirmación manual de abordaje (modo fallback).

- **Enviar Notificación**: Comando para avisar a Padres de Familia sobre un Evento.

- **Servicio De Autenticación RFID**: Servicio que valida UID, levanta Eventos y asegura consistencia.

- **Servicio De Notificaciones**: Servicio que orquesta avisos (push, correo, SMS) a Padres de Familia y Admins.

- **Servicio De Rutas**: Servicio que calcula tiempos estimados, detecta desvíos y actualiza Estado de Trayecto.

- **Servicio De Reportes**: Servicio que genera KPIs: puntualidad, asistencia y uso de Rutas.

- **Estado de Trayecto**: Secuencia Pendiente → EnCurso → Finalizado / Cancelado.

- **Rol**: Identidades posibles en el sistema: Alumno, Padre de Familia, Conductor, Administrador Escolar, Operador de Flota.

- **Modo de Notificación**: Tipos de aviso soportados: Push, SMS, Email.

- **Incidencia**: Registro de evento no deseado (retraso, exceso de velocidad, ruta cambiada).

\newpage

# Capítulo III: Requirements Specification

La sección de Especificación de Requisitos tiene como objetivo describir de forma clara y detallada las necesidades funcionales y no funcionales que debe cumplir el sistema para garantizar su correcto desarrollo y funcionamiento. Esta especificación actúa como un acuerdo formal entre los desarrolladores y las partes interesadas, estableciendo una base común de entendimiento sobre lo que se espera del sistema.

Los requisitos presentados en esta sección se han recopilado a través de investigaciones con usuarios, entrevistas con los interesados y análisis de los procesos actuales. Están organizados de manera que reflejan tanto las necesidades del usuario como la viabilidad técnica. Este documento servirá como guía durante todas las etapas del ciclo de vida del proyecto: diseño, implementación, pruebas y mantenimiento.

![Recurso extraído de Canva](src/img/cap3/requirements-specification-intro.png)

\newpage

## To-Be Scenario Mapping.

**To-Be Scenario – Marco (Padre de familia)**

Con la solución digital, Marco tiene información en tiempo real, alertas personalizadas y tranquilidad al saber que su hijo está seguro.

![To-be Scenario Mapping 1 - Recurso de Miro](https://i.postimg.cc/vZRHS6CS/to-be-esteban.png)

En el escenario futuro, Marco deja atrás la incertidumbre del día a día. La tecnología le permite monitorear fácilmente la rutina de su hijo, recibir notificaciones relevantes y tomar decisiones informadas de forma inmediata. La solución no solo mejora su experiencia como padre, sino que también fortalece su confianza en el entorno que rodea a su familia. Esto representa un cambio significativo respecto al escenario actual, en el que la falta de información y control genera ansiedad y preocupación constante.

\newpage

**To-Be Scenario – Carolina (Administradora)**

Carolina ahora gestiona rutas, asistencia y comunicaciones desde una plataforma centralizada, reduciendo el caos operativo y ganando eficiencia.

![To-be Scenario Mapping 2 - Recurso de Miro](https://i.postimg.cc/fTSRKvq9/to-be-carolina.png)

En este escenario futuro, Carolina cuenta con una plataforma digital unificada que le permite supervisar y coordinar todas las operaciones logísticas en un solo lugar. Ya no necesita depender de múltiples canales o procesos manuales: puede gestionar rutas, controlar la asistencia del personal y mantener una comunicación fluida con padres y conductores de forma eficiente. Esta solución le permite enfocarse en la toma de decisiones estratégicas y mejora significativamente la productividad del equipo administrativo.

\newpage 

## User Stories.

### Administrador educativo

***Epics*** **y** ***User Stories:***

\begin{longtable}{|m{5cm}|m{10cm}|}
\hline
\textbf{EP01 (Gestión de cuentas de administrador educativo)} & \textbf{Como} administrador educativo, \textbf{quiero} registrarme, iniciar sesión y gestionar mi cuenta institucional \textbf{para} acceder de manera segura a la plataforma web y administrar el sistema de transporte escolar. \\
\hline
US01 & Registro de cuenta institucional \\
\hline
US02 & Confirmación de cuenta del administrador \\
\hline
US03 & Verificación de cuenta por parte del sistema \\
\hline
US04 & Inicio de sesión del administrador educativo \\
\hline
US05 & Recuperación de contraseña \\
\hline
US06 & Gestión de perfil administrativo \\
\hline
US07 & Cierre de sesión segura \\
\hline
\textbf{EP02 (Gestión de flotas y zonas)} & \textbf{Como} administrador educativo, \textbf{quiero} gestionar la información de vehículos y zonas geográficas \textbf{para} optimizar las rutas de transporte escolar y garantizar cobertura efectiva. \\
\hline
US01 & Registro y edición de vehículos \\
\hline
US02 & Definición y mapeo de zonas \\
\hline
US03 & Visualización geoespacial de zonas y rutas \\
\hline
US04 & Asignación de vehículos a rutas específicas \\
\hline
US05 & Desactivación temporal de unidades fuera de servicio \\
\hline
\textbf{EP03 (Gestión de conductores y estudiantes)} & \textbf{Como} administrador educativo, \textbf{quiero} gestionar la información de conductores y estudiantes \textbf{para} asegurar que las rutas se asignen correctamente y optimizar la seguridad del transporte escolar. \\
\hline
US01 & Registro y actualización de conductores \\
\hline
US02 & Registro y asignación de pulseras RFID a estudiantes \\
\hline
US03 & Asignación de conductores y estudiantes a rutas específicas \\
\hline
US04 & Verificación de disponibilidad de conductores \\
\hline
US05 & Control de cambios de última hora en la asignación de conductores y estudiantes \\
\hline
\textbf{EP04 (Integración IoT y captura de datos)} & \textbf{Como} administrador educativo, \textbf{quiero} integrar tecnologías IoT para el monitoreo en tiempo real de las flotas de transporte \textbf{para} optimizar la seguridad, eficiencia y control de las rutas de transporte escolar. \\
\hline
US01 & Monitoreo de posición y velocidad en tiempo real de vehículos \\
\hline
US02 & Monitoreo de temperatura interna de los vehículos \\
\hline
US03 & Seguimiento de unidades de transporte para verificar salida y llegada \\
\hline
US04 & Monitoreo de estudiantes que no abordaron la unidad \\
\hline
US05 & Verificación de rutas alternativas en caso de desvíos \\
\hline
US06 & Visualización de unidades en ruta para gestionar desviaciones o retrasos \\
\hline
\textbf{EP05 (Notificaciones y Alertas)} & \textbf{Como} administrador educativo, \textbf{quiero} recibir notificaciones y alertas en tiempo real sobre los eventos y condiciones críticas de las unidades de transporte \textbf{para} poder tomar decisiones rápidas y garantizar la seguridad y eficiencia del servicio. \\
\hline
US01 & Alerta de temperatura fuera de rango \\
\hline
US02 & Alerta de retrasos o desviaciones en las rutas \\
\hline
US03 & Alerta de estudiantes no abordando la unidad \\
\hline
US04 & Notificación automática ante cambios de ruta o posibles retrasos \\
\hline
US05 & Alerta por fallo de equipo en el vehículo (GPS, RFID, sensores, etc.) \\
\hline
US06 & Notificación cuando la unidad ha completado el recorrido \\
\hline
\textbf{EP06 (Reportes y Analítica)} & \textbf{Como} administrador educativo, \textbf{quiero} generar y analizar reportes e indicadores \textbf{para} evaluar el desempeño del transporte escolar y apoyar la toma de decisiones. \\
\hline
US01 & Reporte de tiempos de ruta y cumplimiento \\
\hline
US02 & Estadísticas de abordaje por estudiante \\
\hline
US03 & Exportación de datos históricos en Excel/PDF \\
\hline
US04 & Reporte de incidencias críticas \\
\hline
US05 & Programación de envíos automáticos de reportes \\
\hline
US06 & Filtrado y segmentación de datos históricos \\
\hline
\textbf{EP07 (Plataforma Web de Administración)} & \textbf{Como} administrador educativo, \textbf{quiero} acceder a herramientas de administración centralizadas \textbf{para} configurar, monitorear y asegurar el correcto funcionamiento de la plataforma. \\
\hline
US01 & Dashboard con KPIs clave \\
\hline
US02 & Gestión de roles y permisos \\
\hline
US03 & Configuración de parámetros globales \\
\hline
US04 & Registro de auditoría de actividad \\
\hline
US05 & Configuración de notificaciones y alertas \\
\hline
US06 & Personalización del dashboard \\
\hline
\end{longtable}

\newpage

***User Stories:***

\begin{longtable}{|p{1cm}|p{3cm}|p{4cm}|p{5cm}|p{1cm}|}
\hline
\multicolumn{1}{|c|}{\textbf{ID}} & \multicolumn{1}{c|}{\textbf{Título}} & \multicolumn{1}{c|}{\textbf{Descripción}} & \multicolumn{1}{c|}{\textbf{Criterios de Aceptación}} & \multicolumn{1}{c|}{\textbf{Epic}} \\
\hline
US01 & Registro de cuenta institucional & \textbf{Como} administrador educativo, \textbf{quiero} crear una cuenta institucional proporcionando mi nombre completo, correo institucional y contraseña, \textbf{para} acceder de manera segura a la plataforma web. & 
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Creación exitosa de cuenta}\\
\textbf{Dado que} el administrador accede al formulario de registro\\
\textbf{cuando} ingresa nombre, correo institucional válido y contraseña que cumple los requisitos\\
\textbf{entonces} el sistema crea la cuenta, envía un correo de confirmación y redirige al administrador al dashboard de bienvenida.\\[0.2em]

\textbf{Escenario 2: Campos obligatorios vacíos}\\
\textbf{Dado que} el administrador accede al formulario de registro\\
\textbf{cuando} no completa los campos obligatorios (nombre, correo o contraseña)\\
\textbf{entonces} el sistema muestra mensajes de error indicando los campos faltantes.\\[0.2em]

\textbf{Escenario 3: Correo institucional inválido}\\
\textbf{Dado que} el administrador ingresa un correo que no pertenece al dominio institucional\\
\textbf{cuando} intenta enviar el formulario de registro\\
\textbf{entonces} el sistema muestra un mensaje de error indicando que el correo debe ser del dominio oficial.\\[0.2em]
\end{tabular}
& EP01 \\
\hline
US02 & Confirmación de cuenta del administrador & \textbf{Como} administrador educativo, \textbf{quiero} confirmar mi cuenta a través de un enlace enviado a mi correo institucional, \textbf{para} verificar mi identidad y activar mi acceso al sistema. & 
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Confirmación exitosa}\\
\textbf{Dado que} el administrador ha recibido un correo de confirmación con un token válido\\
\textbf{cuando} hace clic en el enlace de confirmación\\
\textbf{entonces} el sistema activa su cuenta, muestra un mensaje de éxito y lo redirige a la página de inicio de sesión.\\[0.2em]

\textbf{Escenario 2: Token inválido}\\
\textbf{Dado que} el administrador hace clic en un enlace con un token incorrecto o modificado\\
\textbf{cuando} el sistema procesa el token\\
\textbf{entonces} muestra un mensaje de error indicando “Enlace inválido” y ofrece la opción de reenviar el correo de confirmación.\\[0.2em]

\textbf{Escenario 3: Token expirado}\\
\textbf{Dado que} el administrador hace clic en un enlace cuya validez ha expirado\\
\textbf{cuando} el sistema detecta la expiración del token\\
\textbf{entonces} muestra un mensaje de “Enlace expirado” y permite solicitar un nuevo correo de confirmación.\\[0.2em]
\end{tabular}
& EP01 \\
\hline
US03 & Verificación de cuenta por parte del sistema & \textbf{Como} administrador educativo, \textbf{quiero} que el sistema verifique automáticamente la validez de mi cuenta, \textbf{para} asegurarme de que mi información esté correctamente registrada y no haya problemas para acceder a la plataforma. & 
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Verificación exitosa}\\
\textbf{Dado que} el administrador ha completado el registro y confirmado su cuenta\\
\textbf{cuando} el sistema verifica que la cuenta está activa y con información válida\\
\textbf{entonces} el administrador accede sin problemas al sistema, y se le muestra el dashboard de administración.\\[0.2em]

\textbf{Escenario 2: Verificación fallida por falta de confirmación}\\
\textbf{Dado que} el administrador se encuentra en el proceso de registro\\
\textbf{cuando} el sistema detecta que la cuenta no ha sido confirmada\\
\textbf{entonces} el sistema muestra un mensaje de advertencia indicando que el correo de confirmación aún no ha sido validado.\\[0.2em]

\textbf{Escenario 3: Verificación fallida por datos incorrectos}\\
\textbf{Dado que} el administrador ha ingresado información incorrecta durante el registro (como un correo no institucional)\\
\textbf{cuando} el sistema verifica los datos registrados\\
\textbf{entonces} muestra un mensaje de error indicando que la cuenta no se puede activar debido a la información inválida.\\[0.2em]
\end{tabular}
& EP01 \\
\hline
US04 & Inicio de sesión del administrador educativo & \textbf{Como} administrador educativo, \textbf{quiero} iniciar sesión de manera segura en la plataforma utilizando mis credenciales (correo electrónico y contraseña), \textbf{para} acceder a las funcionalidades de administración del sistema de transporte escolar de manera eficiente. & 
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Inicio de sesión exitoso}\\
\textbf{Dado que} el administrador ingresa correctamente su correo electrónico y contraseña\\
\textbf{cuando} el sistema valida las credenciales\\
\textbf{entonces} el administrador accede exitosamente a la plataforma y se le redirige al dashboard de administración.\\[0.2em]

\textbf{Escenario 2: Intento de inicio de sesión con credenciales incorrectas}\\
\textbf{Dado que} el administrador ingresa un correo electrónico o contraseña incorrectos\\
\textbf{cuando} el sistema verifica las credenciales\\
\textbf{entonces} el sistema muestra un mensaje de error indicando que las credenciales no son válidas y solicita al administrador que las ingrese nuevamente.\\[0.2em]

\textbf{Escenario 3: Intento de inicio de sesión con cuenta bloqueada}\\
\textbf{Dado que} el administrador intenta acceder a la plataforma con una cuenta bloqueada\\
\textbf{cuando} el sistema detecta que la cuenta está bloqueada o desactivada\\
\textbf{entonces} el sistema muestra un mensaje indicando que la cuenta ha sido bloqueada y proporciona instrucciones sobre cómo desbloquearla.\\[0.2em]
\end{tabular}
& EP01 \\

\hline
US05 & Recuperación de contraseña & \textbf{Como} administrador educativo, \textbf{quiero} poder recuperar mi contraseña a través de un correo electrónico, \textbf{para} poder acceder nuevamente a mi cuenta si la olvido. & 
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Recuperación de contraseña exitosa}\\
\textbf{Dado que} el administrador ha solicitado la recuperación de su contraseña a través del correo electrónico\\
\textbf{cuando} el administrador ingresa la dirección de correo electrónico asociada a su cuenta y hace clic en "Recuperar contraseña"\\
\textbf{entonces} el sistema envía un enlace de recuperación al correo electrónico del administrador para permitirle restablecer la contraseña.\\[0.2em]

\textbf{Escenario 2: Intento de recuperación con un correo no registrado}\\
\textbf{Dado que} el administrador intenta recuperar la contraseña utilizando una dirección de correo electrónico que no está registrada en el sistema\\
\textbf{cuando} el sistema verifica la dirección de correo electrónico\\
\textbf{entonces} el sistema muestra un mensaje indicando que el correo electrónico no está asociado a ninguna cuenta y sugiere al administrador que verifique la dirección.\\[0.2em]
\end{tabular}
& EP01 \\

\hline
US06 & Gestión de perfil administrativo & \textbf{Como} administrador educativo, \textbf{quiero} poder editar y actualizar mi perfil (como datos de contacto, cargo, etc.), \textbf{para} mantener mi información actualizada en la plataforma. & 
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Edición de perfil exitosa}\\
\textbf{Dado que} el administrador ha accedido a la sección de gestión de perfil\\
\textbf{cuando} el administrador actualiza sus datos (como dirección de correo, número de contacto, cargo, etc.)\\
\textbf{entonces} el sistema guarda los cambios y muestra un mensaje de confirmación de que la actualización se ha realizado correctamente.\\[0.2em]

\textbf{Escenario 2: Intento de actualización con campos vacíos}\\
\textbf{Dado que} el administrador intenta actualizar su perfil\\
\textbf{cuando} deja campos obligatorios en blanco (como nombre o correo electrónico)\\
\textbf{entonces} el sistema muestra un mensaje de error indicando que los campos obligatorios deben completarse antes de guardar los cambios.\\[0.2em]

\textbf{Escenario 3: Visualización de perfil actualizado}\\
\textbf{Dado que} el administrador ha realizado cambios en su perfil\\
\textbf{cuando} el administrador regresa a la página principal de gestión de su cuenta\\
\textbf{entonces} el sistema muestra la información de perfil actualizada, reflejando los cambios realizados.\\[0.2em]
\end{tabular}
& EP01 \\

\hline
US07 & Cierre de sesión segura & \textbf{Como} administrador educativo, \textbf{quiero} cerrar sesión de manera segura en la plataforma, \textbf{para} garantizar que mi cuenta esté protegida y no quede abierta a accesos no autorizados. & 
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Cierre de sesión exitoso}\\
\textbf{Dado que} el administrador ha decidido cerrar sesión\\
\textbf{cuando} el administrador hace clic en el botón de "Cerrar sesión"\\
\textbf{entonces} el sistema cierra la sesión y redirige al administrador a la página de inicio de sesión, mostrando un mensaje de confirmación de que la sesión fue cerrada correctamente.\\[0.2em]

\textbf{Escenario 2: Intento de acceder sin haber cerrado sesión}\\
\textbf{Dado que} el administrador ha cerrado sesión\\
\textbf{cuando} el administrador intenta acceder a una página protegida de la plataforma sin volver a iniciar sesión\\
\textbf{entonces} el sistema redirige al administrador a la página de inicio de sesión, indicando que la sesión ha expirado.\\[0.2em]

\textbf{Escenario 3: Cierre de sesión con múltiples dispositivos}\\
\textbf{Dado que} el administrador tiene la sesión abierta en varios dispositivos\\
\textbf{cuando} el administrador cierra sesión en uno de los dispositivos\\
\textbf{entonces} la sesión se cierra solo en ese dispositivo, mientras que los demás dispositivos continúan con la sesión activa.\\[0.2em]
\end{tabular}
& EP01 \\

\hline
US01 & Registro y edición de vehículos & \textbf{Como} administrador educativo, \textbf{quiero} registrar y editar los datos de cada vehículo (placa, modelo, capacidad y estado operativo), \textbf{para} mantener un catálogo actualizado y fiable de la flota. & 
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Registro exitoso de vehículo}\\
\textbf{Dado que} el administrador accede al formulario de registro de vehículos\\
\textbf{cuando} ingresa placa única, modelo, capacidad numérica y estado operativo válido\\
\textbf{entonces} el sistema guarda el nuevo vehículo y muestra un mensaje de confirmación.\\[0.2em]

\textbf{Escenario 2: Placa duplicada}\\
\textbf{Dado que} el administrador ingresa una placa que ya existe en el sistema\\
\textbf{cuando} envía el formulario de registro\\
\textbf{entonces} el sistema muestra un error indicando que la placa ya está registrada y no crea un duplicado.\\[0.2em]

\textbf{Escenario 3: Edición exitosa de vehículo}\\
\textbf{Dado que} el administrador selecciona un vehículo existente y modifica sus datos\\
\textbf{cuando} ingresa valores válidos en los campos y guarda los cambios\\
\textbf{entonces} el sistema actualiza la información y muestra un mensaje de confirmación.\\
\end{tabular}
& EP02 \\

\hline
US02 & Definición y mapeo de zonas & \textbf{Como} administrador educativo, \textbf{quiero} definir y mapear zonas de recogida y entrega en un mapa interactivo, \textbf{para} optimizar la cobertura y asignar rutas con precisión. & 
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Creación exitosa de zona}\\
\textbf{Dado que} el administrador accede a la sección de zonas\\
\textbf{cuando} ingresa un nombre de zona y dibuja un polígono válido en el mapa\\
\textbf{entonces} el sistema guarda la zona y la muestra en el mapa con su nombre.\\[0.2em]

\textbf{Escenario 2: Polígono inválido}\\
\textbf{Dado que} el administrador dibuja un polígono con menos de tres puntos o con intersecciones propias\\
\textbf{cuando} intenta guardar la zona\\
\textbf{entonces} el sistema muestra un mensaje de error indicando que el polígono no es válido.\\[0.2em]

\textbf{Escenario 3: Edición de zona existente}\\
\textbf{Dado que} el administrador selecciona una zona ya creada\\
\textbf{cuando} modifica su nombre o ajusta el polígono en el mapa y guarda los cambios\\
\textbf{entonces} el sistema actualiza la zona y refleja los cambios en el mapa.\\
\end{tabular}
& EP02 \\

\hline
US03 & Visualización geoespacial de zonas y rutas & \textbf{Como} administrador educativo, \textbf{quiero} visualizar todas las zonas de recogida y entrega y sus rutas asociadas en un mapa interactivo, \textbf{para} detectar posibles solapamientos, huecos de cobertura o áreas no cubiertas. & 
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Visualización correcta de zonas y rutas}\\
\textbf{Dado que} el administrador accede al mapa interactivo\\
\textbf{cuando} se cargan las zonas y sus rutas asociadas en el mapa\\
\textbf{entonces} el sistema muestra todas las zonas y rutas de manera precisa y clara, con un código de colores para diferenciarlas.\\[0.2em]

\textbf{Escenario 2: Solapamientos en zonas}\\
\textbf{Dado que} el administrador ve las zonas y sus rutas en el mapa\\
\textbf{cuando} dos zonas tienen solapamientos en sus límites o rutas\\
\textbf{entonces} el sistema resalta el área de solapamiento y muestra un mensaje de advertencia indicando el solapamiento.\\[0.2em]

\textbf{Escenario 3: Huecos de cobertura}\\
\textbf{Dado que} el administrador observa las zonas en el mapa\\
\textbf{cuando} existe una zona sin rutas asociadas o una ruta que no cubre completamente una zona\\
\textbf{entonces} el sistema resalta el área sin cobertura y sugiere una posible acción para corregirlo.\\[0.2em]

\end{tabular}
& EP02 \\

\hline
US04 & Asignación de vehículos a rutas específicas & \textbf{Como} administrador educativo, \textbf{quiero} asignar vehículos específicos a rutas definidas, \textbf{para} tener un control operacional directo sobre qué unidad se utiliza en cada recorrido y facilitar la trazabilidad en caso de incidentes. & 
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Asignación de vehículo a ruta}\\
\textbf{Dado que} el administrador está visualizando las rutas disponibles\\
\textbf{cuando} selecciona una ruta y elige un vehículo disponible de la flota\\
\textbf{entonces} el sistema asigna correctamente el vehículo a la ruta seleccionada y muestra la información actualizada en la vista.\\[0.2em]

\textbf{Escenario 2: Verificación de la asignación de vehículo a ruta}\\
\textbf{Dado que} el administrador ha asignado un vehículo a una ruta\\
\textbf{cuando} el administrador consulta la ruta asignada\\
\textbf{entonces} el sistema muestra claramente qué vehículo está asignado a esa ruta, incluyendo la placa y el modelo del vehículo.\\[0.2em]

\textbf{Escenario 3: Desasignación de vehículo de ruta}\\
\textbf{Dado que} el administrador desea cambiar la asignación de un vehículo\\
\textbf{cuando} el administrador selecciona una ruta y desasigna el vehículo actual\\
\textbf{entonces} el sistema elimina la asignación del vehículo de esa ruta y lo muestra como disponible para otras rutas.\\[0.2em]
\end{tabular}
& EP02 \\

\hline
US05 & Desactivación temporal de unidades fuera de servicio & \textbf{Como} administrador educativo, \textbf{quiero} desactivar temporalmente vehículos fuera de servicio, \textbf{para} evitar su asignación errónea a rutas mientras se mantiene su información en el sistema para futuras referencias y reactivación. & 
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Desactivación de vehículo fuera de servicio}\\
\textbf{Dado que} un vehículo requiere mantenimiento o no está operativo\\
\textbf{cuando} el administrador selecciona el vehículo en el sistema y lo marca como fuera de servicio\\
\textbf{entonces} el vehículo se desactiva temporalmente y no aparece como disponible para asignación en las rutas.\\[0.2em]

\textbf{Escenario 2: Verificación de desactivación de vehículo}\\
\textbf{Dado que} el administrador ha desactivado un vehículo\\
\textbf{cuando} consulta la lista de vehículos disponibles\\
\textbf{entonces} el vehículo aparece marcado como fuera de servicio y no está disponible para ser asignado a nuevas rutas.\\[0.2em]

\textbf{Escenario 3: Reactivación de vehículo fuera de servicio}\\
\textbf{Dado que} un vehículo ha sido desactivado temporalmente\\
\textbf{cuando} el administrador selecciona el vehículo y lo marca como disponible nuevamente\\
\textbf{entonces} el vehículo se reactiva y aparece como disponible para ser asignado a nuevas rutas.\\[0.2em]
\end{tabular}
& EP02 \\
\hline
US01 & Registro y actualización de conductores & \textbf{Como} administrador educativo, \textbf{quiero} registrar nuevos conductores y actualizar sus datos de contacto, número de licencia y estado operativo, \textbf{para} mantener un personal actualizado y garantizar la correcta asignación de rutas. & 
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Registro exitoso de conductor}\\
\textbf{Dado que} el administrador accede al formulario de conductores\\
\textbf{cuando} ingresa nombre completo, correo, teléfono y número de licencia válidos\\
\textbf{entonces} el sistema guarda el nuevo conductor y muestra un mensaje de confirmación.\\[0.2em]

\textbf{Escenario 2: Licencia duplicada o inválida}\\
\textbf{Dado que} el administrador ingresa un número de licencia ya existente o mal formado\\
\textbf{cuando} envía el formulario de registro\\
\textbf{entonces} el sistema muestra un mensaje de error indicando “Número de licencia inválido o duplicado”.\\[0.2em]

\textbf{Escenario 3: Actualización exitosa de datos}\\
\textbf{Dado que} el administrador selecciona un conductor existente\\
\textbf{cuando} modifica sus datos (contacto, licencia, estado) y guarda los cambios\\
\textbf{entonces} el sistema actualiza la información y muestra un mensaje de “Perfil actualizado”.\\[0.2em]
\end{tabular}
& EP03 \\

\hline

US02 & Registro y asignación de pulseras RFID a estudiantes & \textbf{Como} administrador educativo, \textbf{quiero} registrar a los estudiantes en el sistema y asignarles pulseras RFID con un identificador único, \textbf{para} vincular cada niño con su dispositivo de control y gestionar su transporte de manera más eficiente. & 
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Registro de estudiante exitoso}\\
\textbf{Dado que} el administrador accede al formulario de registro de estudiante\\
\textbf{cuando} ingresa los datos del estudiante (nombre, grado, etc.) y asigna una pulsera RFID\\
\textbf{entonces} el sistema guarda los datos del estudiante junto con el identificador RFID y confirma el registro.\\[0.2em]

\textbf{Escenario 2: Intento de asignación de pulsera duplicada}\\
\textbf{Dado que} el administrador intenta asignar una pulsera RFID ya asignada a otro estudiante\\
\textbf{cuando} el sistema detecta la duplicación\\
\textbf{entonces} el sistema muestra un mensaje de error indicando “Pulsera RFID ya asignada”.\\[0.2em]

\textbf{Escenario 3: Registro sin pulsera RFID}\\
\textbf{Dado que} el administrador está registrando un estudiante\\
\textbf{cuando} no asigna una pulsera RFID al estudiante\\
\textbf{entonces} el sistema muestra un mensaje de advertencia indicando que se debe asignar una pulsera RFID.\\[0.2em]
\end{tabular}
& EP03 \\

\hline
US03 & Asignación de conductores y estudiantes a rutas específicas & \textbf{Como} administrador educativo, \textbf{quiero} asignar conductores y estudiantes a rutas específicas en el sistema, \textbf{para} asegurar que cada unidad opere con el personal y pasajeros correctos y optimizar la seguridad del transporte escolar. & 
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Asignación exitosa}\\
\textbf{Dado que} el administrador se encuentra en la interfaz de asignación de rutas\\
\textbf{cuando} selecciona una ruta y asigna un conductor disponible junto con los estudiantes correspondientes\\
\textbf{entonces} el sistema guarda la asignación y muestra una confirmación exitosa de la operación.\\[0.2em]

\textbf{Escenario 2: Intento de asignación con datos incompletos}\\
\textbf{Dado que} el administrador está asignando una ruta\\
\textbf{cuando} omite seleccionar al menos un conductor o uno o más estudiantes\\
\textbf{entonces} el sistema muestra un mensaje de error indicando “Debe asignar un conductor y al menos un estudiante para continuar”.\\[0.2em]

\textbf{Escenario 3: Validación de conflicto en asignación}\\
\textbf{Dado que} el administrador intenta asignar un conductor o estudiante que ya se encuentra asignado a otra ruta en el mismo horario\\
\textbf{cuando} el sistema detecta el conflicto de asignación\\
\textbf{entonces} el sistema muestra un mensaje de advertencia indicando “El conductor/estudiante ya se encuentra asignado a otra ruta en este horario” y no permite la asignación duplicada.\\[0.2em]
\end{tabular}
& EP03 \\
\hline
US04 & Verificación de disponibilidad de conductores & \textbf{Como} administrador educativo, \textbf{quiero} verificar la disponibilidad de los conductores antes de asignarlos a una ruta, \textbf{para} evitar conflictos de horario y asegurar una gestión eficiente del personal y la flota. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Conductor disponible}\\
\textbf{Dado que} el administrador accede al panel de asignación de rutas\\
\textbf{cuando} consulta la disponibilidad de un conductor específico\\
\textbf{entonces} el sistema muestra que el conductor está disponible y permite su asignación.\\[0.2em]

\textbf{Escenario 2: Conductor ya asignado}\\
\textbf{Dado que} el administrador consulta la disponibilidad de un conductor\\
\textbf{cuando} el sistema detecta que el conductor ya está asignado a otra ruta en el mismo horario\\
\textbf{entonces} el sistema muestra una advertencia de “Conductor no disponible” e impide su asignación.\\[0.2em]

\textbf{Escenario 3: Filtro por disponibilidad general}\\
\textbf{Dado que} el administrador desea asignar un conductor a una nueva ruta\\
\textbf{cuando} utiliza un filtro para mostrar solo conductores disponibles\\
\textbf{entonces} el sistema muestra una lista actualizada de conductores sin asignación en ese horario.\\[0.2em]
\end{tabular}
& EP03 \\

\hline
US05 & Control de cambios de última hora en la asignación de conductores y estudiantes & \textbf{Como} administrador educativo, \textbf{quiero} realizar cambios de última hora en la asignación de conductores y estudiantes, \textbf{para} asegurar la continuidad del servicio ante imprevistos sin afectar el resto de la programación. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Reasignación rápida de conductor}\\
\textbf{Dado que} un conductor asignado a una ruta reporta una ausencia inesperada\\
\textbf{cuando} el administrador selecciona otro conductor disponible\\
\textbf{entonces} el sistema actualiza la asignación de forma inmediata y notifica el cambio.\\[0.2em]

\textbf{Escenario 2: Cambio de estudiante de ruta}\\
\textbf{Dado que} un estudiante no podrá abordar en su ruta habitual por razones operativas\\
\textbf{cuando} el administrador lo reasigna a otra ruta disponible\\
\textbf{entonces} el sistema actualiza la información y vincula su RFID a la nueva unidad.\\[0.2em]

\textbf{Escenario 3: Registro de cambios realizados}\\
\textbf{Dado que} se realizan modificaciones en las asignaciones\\
\textbf{cuando} el sistema guarda el historial de cambios\\
\textbf{entonces} los administradores pueden revisar qué cambios se hicieron, por quién y cuándo.\\[0.2em]
\end{tabular}
& EP03 \\

\hline
US01 & Monitoreo en tiempo real de posición y velocidad de vehículos & \textbf{Como} administrador educativo, \textbf{quiero} conocer la posición y velocidad en tiempo real de cada vehículo, \textbf{para} monitorear sus rutas y detectar posibles retrasos o desvíos oportunamente. & 
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Visualización de datos en tiempo real}\\
\textbf{Dado que} el administrador accede al panel de monitoreo\\
\textbf{cuando} selecciona un vehículo específico\\
\textbf{entonces} el sistema muestra la ubicación actual y la velocidad en tiempo real del vehículo.\\[0.2em]

\textbf{Escenario 2: Detección de desviación de ruta}\\
\textbf{Dado que} un vehículo se encuentra fuera de su ruta predefinida\\
\textbf{cuando} el sistema detecta la desviación\\
\textbf{entonces} se genera una alerta automática para notificar al administrador.\\[0.2em]

\textbf{Escenario 3: Monitoreo continuo sin interrupciones}\\
\textbf{Dado que} el administrador visualiza el panel de monitoreo\\
\textbf{cuando} el vehículo se desplaza por su ruta\\
\textbf{entonces} el sistema actualiza de forma continua y sin fallos la posición y velocidad del vehículo.
\end{tabular}
& EP04 \\

\hline
US02 & Monitoreo de temperatura interna de los vehículos & \textbf{Como} administrador educativo, \textbf{quiero} monitorear remotamente la temperatura interna de los vehículos, \textbf{para} asegurarme de que las condiciones sean seguras para los pasajeros. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Visualización de temperatura actual}\\
\textbf{Dado que} el supervisor accede al panel de monitoreo de temperatura\\
\textbf{cuando} selecciona un vehículo en operación\\
\textbf{entonces} el sistema muestra la temperatura interna actual en tiempo real.\\[0.2em]

\textbf{Escenario 2: Alerta por temperatura fuera de rango}\\
\textbf{Dado que} la temperatura interna del vehículo supera los límites establecidos\\
\textbf{cuando} el sistema detecta esta condición anómala\\
\textbf{entonces} se genera una alerta visual y sonora en el panel de monitoreo.\\[0.2em]

\textbf{Escenario 3: Historial de temperatura}\\
\textbf{Dado que} el supervisor desea verificar condiciones pasadas\\
\textbf{cuando} accede al historial de temperatura de un vehículo\\
\textbf{entonces} el sistema muestra un gráfico con los valores registrados durante los recorridos anteriores.
\end{tabular}
& EP04 \\

\hline
US03 & Seguimiento de unidades de transporte para verificar salida y llegada & \textbf{Como} administrador educativo, \textbf{quiero} visualizar en tiempo real qué unidades ya han partido para recoger a los estudiantes y qué unidades ya han llegado al centro educativo, \textbf{para} hacer un seguimiento eficiente del estado de las rutas y asegurarme de que todos los estudiantes han sido recogidos o entregados. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Visualización de estado de unidades}\\
\textbf{Dado que} el administrador accede al panel de seguimiento de rutas\\
\textbf{cuando} el sistema detecta que una unidad ha iniciado su recorrido o ha llegado al colegio\\
\textbf{entonces} el estado de la unidad cambia a “En ruta” o “Llegó al destino” en tiempo real.\\[0.2em]

\textbf{Escenario 2: Confirmación de llegada al colegio}\\
\textbf{Dado que} una unidad ha llegado al colegio\\
\textbf{cuando} el GPS registra la ubicación correspondiente al centro educativo\\
\textbf{entonces} el sistema actualiza automáticamente el estado a “Llegado” y registra la hora de llegada.\\[0.2em]

\textbf{Escenario 3: Generación de reporte de estados diarios}\\
\textbf{Dado que} el administrador desea revisar la operación diaria\\
\textbf{cuando} solicita un resumen de actividad del día\\
\textbf{entonces} el sistema genera un reporte indicando qué unidades salieron, a qué hora, y si llegaron correctamente al colegio.
\end{tabular}
& EP04 \\

\hline
US04 & Monitoreo de estudiantes que no abordaron la unidad & \textbf{Como} administrador educativo, \textbf{quiero} hacer un seguimiento de qué estudiantes no abordaron la unidad, \textbf{para} tomar acciones inmediatas y asegurarme de que todos los estudiantes estén siendo transportados de forma segura. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Identificación de estudiantes ausentes}\\
\textbf{Dado que} el sistema tiene registrados los estudiantes asignados a una ruta\\
\textbf{cuando} el lector RFID no detecta el ingreso de un estudiante asignado\\
\textbf{entonces} el sistema marca automáticamente al estudiante como “No abordó” y notifica al administrador.\\[0.2em]

\textbf{Escenario 2: Visualización en tiempo real de estudiantes faltantes}\\
\textbf{Dado que} el administrador accede al panel de ruta\\
\textbf{cuando} la unidad inicia su recorrido\\
\textbf{entonces} el panel muestra en tiempo real qué estudiantes han abordado y quiénes no.\\[0.2em]

\textbf{Escenario 3: Generación de alerta por estudiante no abordado}\\
\textbf{Dado que} un estudiante no abordó la unidad\\
\textbf{cuando} la unidad continúa su ruta sin detectarlo\\
\textbf{entonces} el sistema envía una alerta al administrador indicando el nombre del estudiante y su punto de recojo.
\end{tabular}
& EP04 \\

\hline
US05 & Verificación de rutas alternativas en caso de desvíos & \textbf{Como} administrador educativo, \textbf{quiero} verificar y gestionar rutas alternativas en tiempo real cuando una unidad se desvía de su ruta prevista, \textbf{para} garantizar que los estudiantes lleguen a su destino de manera segura y a tiempo frente a imprevistos. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Notificación de desvío detectado}\\
\textbf{Dado que} una unidad se desvía de su ruta establecida\\
\textbf{cuando} el sistema detecta el cambio de trayectoria vía GPS\\
\textbf{entonces} se genera una notificación en el panel del administrador indicando la unidad afectada y su nueva ubicación.\\[0.2em]

\textbf{Escenario 2: Sugerencia de rutas alternativas}\\
\textbf{Dado que} el sistema detecta un desvío\\
\textbf{cuando} hay rutas alternativas disponibles\\
\textbf{entonces} el sistema sugiere automáticamente rutas alternativas al administrador para evaluación y aprobación.\\[0.2em]

\textbf{Escenario 3: Confirmación de nueva ruta}\\
\textbf{Dado que} el administrador aprueba una ruta alternativa\\
\textbf{cuando} selecciona la nueva trayectoria en el sistema\\
\textbf{entonces} el sistema actualiza la ruta de seguimiento y notifica a los dispositivos correspondientes sobre el nuevo trayecto.
\end{tabular}
& EP04 \\
\hline
US06 & Visualización de unidades en ruta para gestionar desviaciones o retrasos & \textbf{Como} administrador educativo, \textbf{quiero} visualizar en tiempo real todas las unidades en ruta, \textbf{para} detectar rápidamente desviaciones o retrasos y tomar decisiones oportunas que aseguren el cumplimiento de los horarios y la seguridad de los estudiantes. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Visualización en tiempo real de unidades activas}\\
\textbf{Dado que} el administrador accede al panel de monitoreo\\
\textbf{cuando} se muestran todas las unidades actualmente en recorrido\\
\textbf{entonces} el sistema presenta en un mapa interactivo la ubicación, velocidad y estado de cada unidad.\\[0.2em]

\textbf{Escenario 2: Alerta por retraso detectado}\\
\textbf{Dado que} una unidad excede el tiempo estimado para un punto de control\\
\textbf{cuando} el sistema compara el tiempo real con el tiempo programado\\
\textbf{entonces} se genera una alerta visual y sonora en el panel del administrador indicando un posible retraso.\\[0.2em]

\textbf{Escenario 3: Notificación de desvío de ruta}\\
\textbf{Dado que} una unidad se desvía de su ruta asignada\\
\textbf{cuando} el sistema detecta una trayectoria no planificada\\
\textbf{entonces} se notifica al administrador con la nueva ubicación de la unidad y posibles causas del desvío (tráfico, desvío manual, etc.).
\end{tabular}
& EP04 \\

\hline
US01 & Alerta de temperatura fuera de rango & \textbf{Como} administrador educativo, \textbf{quiero} recibir alertas en tiempo real cuando la temperatura interna de un vehículo se salga de los parámetros establecidos, \textbf{para} tomar medidas inmediatas que garanticen la seguridad y el confort de los estudiantes durante el transporte. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Recepción de alerta por alta temperatura}\\
\textbf{Dado que} la temperatura interna de una unidad supera el umbral máximo permitido\\
\textbf{cuando} el sistema de monitoreo detecta este valor anómalo\\
\textbf{entonces} el administrador educativo recibe una notificación en su panel de control y en su dispositivo móvil.\\[0.2em]

\textbf{Escenario 2: Recepción de alerta por baja temperatura}\\
\textbf{Dado que} la temperatura interna desciende por debajo del umbral mínimo aceptado\\
\textbf{cuando} se registra esta condición en el sensor del vehículo\\
\textbf{entonces} se emite una alerta inmediata con los datos del vehículo afectado.\\[0.2em]

\textbf{Escenario 3: Consulta del historial de alertas térmicas}\\
\textbf{Dado que} el administrador quiere revisar incidentes anteriores relacionados con la temperatura\\
\textbf{cuando} accede a la sección de historial de alertas\\
\textbf{entonces} el sistema muestra un listado con fecha, unidad, valor de temperatura y acción tomada.
\end{tabular}
& EP05 \\

\hline
US02 & Alerta de retrasos o desviaciones en las rutas & \textbf{Como} administrador educativo, \textbf{quiero} recibir alertas inmediatas cuando una unidad de transporte experimente retrasos o se desvíe de la ruta establecida, \textbf{para} poder coordinar con el conductor y tomar decisiones rápidas que minimicen el impacto en el servicio y garanticen la llegada segura y oportuna de los estudiantes. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Alerta por retraso en la ruta}\\
\textbf{Dado que} una unidad excede el tiempo estimado de llegada a un punto planificado\\
\textbf{cuando} el sistema detecta el retraso basado en la comparación con el horario predefinido\\
\textbf{entonces} el administrador recibe una notificación con los detalles del vehículo y el retraso detectado.\\[0.2em]

\textbf{Escenario 2: Alerta por desvío de ruta}\\
\textbf{Dado que} una unidad sale del recorrido autorizado\\
\textbf{cuando} el sistema de geolocalización detecta que el vehículo ha tomado una vía no planificada\\
\textbf{entonces} se emite una alerta automática al panel del administrador con el mapa y ubicación actual.\\[0.2em]

\textbf{Escenario 3: Coordinación tras alerta}\\
\textbf{Dado que} se ha generado una alerta por desviación o retraso\\
\textbf{cuando} el administrador accede a la alerta desde el panel\\
\textbf{entonces} puede comunicarse directamente con el conductor y visualizar rutas alternativas sugeridas por el sistema.
\end{tabular}
& EP05 \\

\hline
US03 & Alerta de estudiantes no abordando la unidad & \textbf{Como} administrador educativo, \textbf{quiero} recibir alertas en tiempo real cuando un estudiante asignado a una ruta no aborde la unidad, \textbf{para} poder tomar medidas inmediatas como contactar al conductor o a los padres, y así garantizar la seguridad de todos los estudiantes. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Alerta automática de no abordaje}\\
\textbf{Dado que} un estudiante asignado a una unidad no es registrado como presente\\
\textbf{cuando} el sistema detecta que el estudiante no ha sido marcado como abordado al llegar al punto de recogida\\
\textbf{entonces} se genera una alerta inmediata para el administrador con los datos del estudiante y la unidad correspondiente.\\[0.2em]

\textbf{Escenario 2: Comunicación con el conductor}\\
\textbf{Dado que} se ha recibido una alerta de no abordaje\\
\textbf{cuando} el administrador accede al panel de incidentes\\
\textbf{entonces} puede comunicarse directamente con el conductor para confirmar la ausencia del estudiante.\\[0.2em]

\textbf{Escenario 3: Registro del incidente}\\
\textbf{Dado que} un estudiante no ha abordado y se ha confirmado la situación\\
\textbf{cuando} el administrador documenta el evento\\
\textbf{entonces} el sistema registra el incidente con fecha, hora y acciones tomadas, quedando disponible para auditoría futura.
\end{tabular}
& EP05 \\

\hline
US04 & Notificación automática ante cambios de ruta o posibles retrasos & \textbf{Como} administrador educativo, \textbf{quiero} recibir notificaciones automáticas cuando un vehículo experimente cambios de ruta o posibles retrasos, \textbf{para} poder gestionar de manera proactiva las rutas y tomar decisiones para minimizar el impacto en los horarios de transporte. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Notificación de cambio de ruta}\\
\textbf{Dado que} un vehículo ha sido desviado de su ruta planificada debido a un imprevisto\\
\textbf{cuando} el sistema detecta el cambio de ruta\\
\textbf{entonces} se envía una notificación automática al administrador, informando sobre el cambio y la nueva ruta.\\[0.2em]

\textbf{Escenario 2: Notificación de retraso}\\
\textbf{Dado que} un vehículo ha experimentado un retraso debido a condiciones de tráfico o problemas mecánicos\\
\textbf{cuando} el sistema detecta que el retraso ha superado el umbral predefinido\\
\textbf{entonces} se genera una alerta de retraso que se envía al administrador con la información relevante del vehículo.\\[0.2em]

\textbf{Escenario 3: Gestión proactiva}\\
\textbf{Dado que} se ha recibido una notificación de cambio de ruta o retraso\\
\textbf{cuando} el administrador recibe la alerta\\
\textbf{entonces} el administrador puede tomar decisiones, como notificar a los padres o ajustar las rutas de otros vehículos si es necesario.\\[0.2em]
\end{tabular}
& EP05 \\

\hline
US05 & Alerta por fallo de equipo en el vehículo (GPS, RFID, sensores, etc.) & \textbf{Como} administrador educativo, \textbf{quiero} recibir una alerta inmediata en caso de fallo de equipos en los vehículos, como el GPS, RFID o sensores, \textbf{para} poder tomar medidas rápidas y garantizar que el control de las rutas y la seguridad de los estudiantes no se vean comprometidos. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Alerta por fallo en el GPS}\\
\textbf{Dado que} el GPS de un vehículo ha dejado de funcionar correctamente\\
\textbf{cuando} el sistema detecta la falla en el GPS\\
\textbf{entonces} se envía una alerta al administrador indicando el fallo y el vehículo afectado.\\[0.2em]

\textbf{Escenario 2: Alerta por fallo en el lector RFID}\\
\textbf{Dado que} el lector RFID del vehículo no está funcionando\\
\textbf{cuando} el sistema detecta que el lector RFID está inactivo\\
\textbf{entonces} se genera una notificación para que el administrador pueda gestionar el problema rápidamente.\\[0.2em]

\textbf{Escenario 3: Alerta por fallo en el sensor de temperatura}\\
\textbf{Dado que} el sensor de temperatura del vehículo ha dejado de funcionar\\
\textbf{cuando} el sistema detecta que el sensor no está operando correctamente\\
\textbf{entonces} se envía una notificación al administrador sobre el fallo del sensor de temperatura.\\[0.2em]
\end{tabular}
& EP05 \\

\hline
US06 & Notificación cuando la unidad ha completado el recorrido & \textbf{Como} administrador educativo, \textbf{quiero} recibir una notificación cuando una unidad haya completado su recorrido (tanto la ruta hacia el colegio como el retorno a casa) \textbf{para} poder gestionar eficientemente la programación de las unidades, evitando retrasos y asegurando que las unidades estén disponibles para nuevas asignaciones. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Notificación de llegada al colegio}\\
\textbf{Dado que} la unidad ha llegado al colegio para dejar a los estudiantes\\
\textbf{cuando} la unidad termina su recorrido hacia el colegio\\
\textbf{entonces} el sistema envía una notificación al administrador indicando que la unidad ha completado su recorrido.\\[0.2em]

\textbf{Escenario 2: Notificación de regreso a casa}\\
\textbf{Dado que} la unidad ha terminado su recorrido de regreso a casa\\
\textbf{cuando} la unidad termina su recorrido de regreso a la casa de los estudiantes\\
\textbf{entonces} el sistema envía una notificación al administrador indicando que la unidad ha completado su recorrido.\\[0.2em]

\textbf{Escenario 3: Gestión de unidades disponibles para nuevas asignaciones}\\
\textbf{Dado que} una unidad ha completado su recorrido y está lista para una nueva asignación\\
\textbf{cuando} la unidad termina su recorrido y se encuentra disponible\\
\textbf{entonces} el administrador recibe una alerta notificando que la unidad ha completado el recorrido y está lista para la siguiente asignación.\\[0.2em]
\end{tabular}
& EP05 \\

\hline
US01 & Reporte de tiempos de ruta y cumplimiento & \textbf{Como} administrador educativo, \textbf{quiero} generar reportes de tiempos de ruta y cumplimiento, \textbf{para} evaluar el desempeño de la flota y apoyar la toma de decisiones basadas en datos operativos. & 
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Generación exitosa del reporte}\\
\textbf{Dado que} el administrador accede al módulo de reportes\\
\textbf{cuando} selecciona un rango de fechas y parámetros específicos\\
\textbf{entonces} el sistema genera un reporte detallado que muestra los tiempos de ruta y el grado de cumplimiento de cada recorrido.\\[0.2em]

\textbf{Escenario 2: Visualización de incumplimientos}\\
\textbf{Dado que} existen desviaciones o retrasos en las rutas\\
\textbf{cuando} el administrador revisa el reporte generado\\
\textbf{entonces} el sistema destaca los casos de incumplimiento, permitiendo identificar rápidamente las áreas de mejora.\\[0.2em]

\textbf{Escenario 3: Exportación del reporte}\\
\textbf{Dado que} el administrador necesita compartir o archivar la información\\
\textbf{cuando} selecciona la opción de exportar el reporte\\
\textbf{entonces} el sistema genera un archivo descargable en formato Excel o PDF con todos los datos del reporte.
\end{tabular}
& EP06 \\

\hline
US02 & Estadísticas de abordaje por estudiante & \textbf{Como} administrador educativo, \textbf{quiero} obtener estadísticas de abordaje por estudiante, \textbf{para} detectar patrones de retraso o ausencias y tomar acciones preventivas que mejoren la eficiencia del transporte escolar. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Generación exitosa de estadísticas}\\
\textbf{Dado que} el administrador accede al módulo de reportes\\
\textbf{cuando} selecciona la opción de estadísticas de abordaje por estudiante y define un rango de fechas\\
\textbf{entonces} el sistema genera y muestra un reporte detallado con indicadores de abordaje, incluyendo retrasos y ausencias.\\[0.2em]

\textbf{Escenario 2: Identificación de patrones repetitivos}\\
\textbf{Dado que} ciertos estudiantes presentan ausencias o retrasos de forma recurrente\\
\textbf{cuando} se visualiza el reporte generado\\
\textbf{entonces} el sistema resalta automáticamente aquellos casos, facilitando su identificación para la toma de decisiones.\\[0.2em]

\textbf{Escenario 3: Exportación del reporte}\\
\textbf{Dado que} el administrador requiere analizar o compartir la información\\
\textbf{cuando} selecciona la opción de exportar el reporte\\
\textbf{entonces} el sistema genera un archivo descargable en formato Excel o PDF con todas las estadísticas de abordaje.
\end{tabular}
& EP06 \\

\hline
US03 & Exportación de datos históricos en Excel/PDF & \textbf{Como} responsable de calidad, \textbf{quiero} exportar datos históricos en formatos Excel o PDF, \textbf{para} presentarlos en auditorías o juntas directivas y facilitar la toma de decisiones estratégicas basadas en datos históricos. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Exportación exitosa de datos históricos}\\
\textbf{Dado que} el responsable de calidad accede al módulo de reportes\\
\textbf{cuando} selecciona la opción de exportar datos históricos y define el rango de fechas\\
\textbf{entonces} el sistema genera un archivo Excel o PDF con todos los datos solicitados.\\[0.2em]

\textbf{Escenario 2: Formato adecuado para auditorías}\\
\textbf{Dado que} el archivo exportado debe ser adecuado para auditorías y presentaciones\\
\textbf{cuando} el responsable de calidad abre el archivo exportado\\
\textbf{entonces} los datos están organizados de manera clara y profesional, listos para ser presentados en auditorías o juntas directivas.\\[0.2em]

\textbf{Escenario 3: Verificación de datos exportados}\\
\textbf{Dado que} el responsable de calidad necesita asegurarse de que los datos exportados sean correctos\\
\textbf{cuando} abre el archivo exportado\\
\textbf{entonces} puede verificar que todos los datos históricos correspondientes al rango de fechas seleccionado están correctamente reflejados en el archivo.
\end{tabular}
& EP06 \\

\hline
US04 & Reporte de incidencias críticas & \textbf{Como} administrador del sistema, \textbf{quiero} generar reportes de incidencias críticas, \textbf{para} consolidar y analizar eventos como alertas de temperatura, desviaciones de ruta o fallos de equipo, con el fin de identificar patrones recurrentes y focalizar acciones de mejora continua en la gestión de transporte escolar. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Generación de reporte de incidencias críticas}\\
\textbf{Dado que} el administrador accede a la sección de reportes de incidencias críticas\\
\textbf{cuando} selecciona el rango de fechas y los tipos de incidencias a analizar\\
\textbf{entonces} el sistema genera un reporte consolidado con los eventos críticos seleccionados, detallando cada incidencia por tipo y fecha.\\[0.2em]

\textbf{Escenario 2: Análisis de patrones de incidencias}\\
\textbf{Dado que} el reporte contiene incidencias críticas,\\
\textbf{cuando} el administrador revisa el reporte\\
\textbf{entonces} puede identificar patrones recurrentes en las incidencias y determinar áreas específicas para aplicar acciones correctivas.\\[0.2em]

\textbf{Escenario 3: Exportación del reporte de incidencias críticas}\\
\textbf{Dado que} el administrador necesita compartir el reporte con otros miembros del equipo\\
\textbf{cuando} el administrador elige la opción de exportar el reporte\\
\textbf{entonces} el sistema permite exportar el reporte en formatos como PDF o Excel para su distribución y análisis adicional. 
\end{tabular}
& EP06 \\

\hline
US05 & Programación de envíos automáticos de reportes & \textbf{Como} administrador del sistema, \textbf{quiero} programar envíos automáticos de reportes, \textbf{para} automatizar la distribución periódica de reportes (diarios, semanales o mensuales) a los responsables, garantizando que la información llegue a tiempo sin necesidad de intervención manual. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Programación de envío automático de reportes}\\
\textbf{Dado que} el administrador desea enviar reportes periódicamente\\
\textbf{cuando} el administrador configura la periodicidad (diaria, semanal o mensual) y los destinatarios del reporte\\
\textbf{entonces} el sistema programará el envío automático de los reportes en los intervalos establecidos.\\[0.2em]

\textbf{Escenario 2: Confirmación de programación de reportes}\\
\textbf{Dado que} el administrador ha configurado la programación de envíos automáticos\\
\textbf{cuando} el administrador guarda la configuración de la programación\\
\textbf{entonces} el sistema mostrará una notificación confirmando que los envíos automáticos han sido correctamente programados.\\[0.2em]

\textbf{Escenario 3: Modificación de la programación de reportes}\\
\textbf{Dado que} el administrador desea cambiar la programación de los envíos de reportes\\
\textbf{cuando} el administrador modifica la frecuencia o los destinatarios de los reportes\\
\textbf{entonces} el sistema actualizará la programación de los envíos automáticos según los nuevos parámetros establecidos.\\[0.2em]
\end{tabular}
& EP06 \\

\hline
US06 & Filtrado y segmentación de datos históricos & \textbf{Como} administrador del sistema, \textbf{quiero} filtrar y segmentar datos históricos por ruta, vehículo, conductor o rango de fechas, \textbf{para} optimizar el análisis detallado y la preparación de informes personalizados para auditorías o reuniones de gestión. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Filtrado de datos históricos por ruta}\\
\textbf{Dado que} el administrador necesita analizar los datos de una ruta específica\\
\textbf{cuando} el administrador selecciona una ruta y aplica el filtro\\
\textbf{entonces} el sistema mostrará solo los datos históricos relacionados con esa ruta.\\[0.2em]

\textbf{Escenario 2: Filtrado de datos históricos por vehículo}\\
\textbf{Dado que} el administrador desea analizar los datos de un vehículo específico\\
\textbf{cuando} el administrador selecciona un vehículo y aplica el filtro\\
\textbf{entonces} el sistema mostrará solo los datos históricos relacionados con ese vehículo.\\[0.2em]

\textbf{Escenario 3: Filtrado de datos históricos por conductor}\\
\textbf{Dado que} el administrador desea revisar el desempeño de un conductor\\
\textbf{cuando} el administrador selecciona un conductor y aplica el filtro\\
\textbf{entonces} el sistema mostrará solo los datos históricos relacionados con ese conductor.\\[0.2em]
\end{tabular}
& EP06 \\

\hline
US01 & Dashboard con KPIs clave & \textbf{Como} administrador educativo, \textbf{quiero} acceder a un dashboard que muestre KPIs clave (número de rutas activas, incidencias, temperatura media, etc.), \textbf{para} monitorear la operación del transporte escolar de un vistazo y tomar decisiones basadas en datos en tiempo real. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Visualización del dashboard}\\
\textbf{Dado que} el administrador accede a la plataforma web\\
\textbf{cuando} ingresa al módulo de administración\\
\textbf{entonces} el sistema muestra un dashboard con KPIs actualizados en tiempo real, incluyendo número de rutas activas, incidencias registradas y temperatura media de las unidades.\\[0.2em]

\textbf{Escenario 2: Actualización en tiempo real}\\
\textbf{Dado que} se registran nuevos eventos en el sistema (por ejemplo, incidencias o cambios en las rutas)\\
\textbf{cuando} el administrador visualiza el dashboard\\
\textbf{entonces} el sistema actualiza automáticamente los KPIs para reflejar la situación actual.\\[0.2em]

\textbf{Escenario 3: Personalización del dashboard}\\
\textbf{Dado que} el administrador tiene necesidades específicas de información\\
\textbf{cuando} utiliza las opciones de configuración del dashboard\\
\textbf{entonces} el sistema permite personalizar la visualización de KPIs según preferencias (por ejemplo, mostrar o ocultar ciertos indicadores).
\end{tabular}
& EP07 \\

\hline
US02 & Gestión de roles y permisos & \textbf{Como} administrador educativo, \textbf{quiero} gestionar los roles y permisos de los usuarios (coordinadores, supervisores, etc.), \textbf{para} delegar responsabilidades con seguridad y asegurarme de que cada usuario solo tenga acceso a la información y funciones necesarias para su rol. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Asignación de roles}\\
\textbf{Dado que} soy un administrador con privilegios para gestionar usuarios\\
\textbf{cuando} accedo al módulo de gestión de roles\\
\textbf{entonces} puedo asignar un rol a cada usuario (coordinador, supervisor, etc.), permitiendo el acceso correspondiente a funcionalidades específicas de la plataforma.\\[0.2em]

\textbf{Escenario 2: Edición de permisos de usuario}\\
\textbf{Dado que} tengo un usuario con permisos predefinidos\\
\textbf{cuando} accedo a la configuración de permisos de un usuario\\
\textbf{entonces} puedo modificar los permisos para permitir o restringir el acceso a ciertas funciones de la plataforma, como el monitoreo de rutas o la generación de reportes.\\[0.2em]

\textbf{Escenario 3: Eliminar un rol o usuario}\\
\textbf{Dado que} soy administrador de la plataforma\\
\textbf{cuando} decido eliminar un rol o usuario\\
\textbf{entonces} puedo eliminar el acceso de ese rol o usuario de la plataforma de forma segura, asegurando que no tenga acceso a ninguna función después de la eliminación.\\[0.2em]
\end{tabular}
& EP07 \\

\hline
US03 & Configuración de parámetros globales & \textbf{Como} administrador educativo, \textbf{quiero} configurar parámetros globales (como los umbrales de temperatura, la frecuencia de reporte GPS, etc.), \textbf{para} adaptar el sistema a las políticas internas de la institución y asegurar el funcionamiento adecuado de la plataforma. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Configuración de umbrales de temperatura}\\
\textbf{Dado que} soy un administrador con privilegios para configurar parámetros\\
\textbf{cuando} accedo a la sección de configuración de umbrales de temperatura\\
\textbf{entonces} puedo establecer un valor mínimo y máximo para la temperatura dentro de los vehículos, de modo que el sistema me notifique si se supera cualquier umbral configurado.\\[0.2em]

\textbf{Escenario 2: Configuración de frecuencia de reporte GPS}\\
\textbf{Dado que} soy administrador y quiero personalizar la frecuencia de los reportes GPS\\
\textbf{cuando} accedo a la configuración de la frecuencia de reporte GPS\\
\textbf{entonces} puedo establecer un intervalo de tiempo para la actualización de la ubicación de los vehículos en el sistema.\\[0.2em]

\textbf{Escenario 3: Configuración de alertas automáticas}\\
\textbf{Dado que} soy administrador y quiero configurar alertas automáticas\\
\textbf{cuando} accedo a la sección de alertas automáticas\\
\textbf{entonces} puedo establecer condiciones para recibir notificaciones, como cuando un vehículo se desvía de la ruta planificada.\\[0.2em]
\end{tabular}
& EP07 \\

\hline
US04 & Registro de auditoría de actividad & \textbf{Como} administrador educativo, \textbf{quiero} llevar un registro de auditoría de todas las acciones realizadas por los administradores y supervisores (como la creación/edición de usuarios, cambios en rutas, ajustes de parámetros), \textbf{para} garantizar la trazabilidad y el cumplimiento de normativas internas. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Registro de ajustes de parámetros}\\
\textbf{Dado que} soy un administrador y ajusto los parámetros globales del sistema\\
\textbf{cuando} guardo la nueva configuración de parámetros\\
\textbf{entonces} el sistema registra la acción en el historial de auditoría, detallando los parámetros modificados y el usuario responsable de la acción.\\[0.2em]

\textbf{Escenario 2: Acceso al historial de auditoría}\\
\textbf{Dado que} soy un administrador con privilegios para acceder al historial de auditoría\\
\textbf{cuando} accedo a la sección de auditoría en el sistema\\
\textbf{entonces} puedo visualizar un registro detallado de todas las acciones realizadas, con opciones para filtrar por tipo de acción, usuario y otros criterios relevantes.\\[0.2em]

\textbf{Escenario 3: Notificación de acciones no autorizadas}\\
\textbf{Dado que} un supervisor o administrador realiza una acción no autorizada\\
\textbf{cuando} la acción es registrada en el historial de auditoría\\
\textbf{entonces} el sistema genera una notificación para alertar a los administradores responsables de la supervisión de la acción no autorizada.
\end{tabular}
& EP07 \\

\hline
US05 & Configuración de notificaciones y alertas & \textbf{Como} administrador educativo, \textbf{quiero} configurar qué tipos de notificaciones y alertas deseo recibir, por qué canal (correo electrónico, SMS, notificación push) y con qué umbrales, \textbf{para} adaptar la comunicación del sistema a los procesos internos de la institución. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Configuración de tipos de alertas}\\
\textbf{Dado que} soy un administrador con acceso a la configuración de notificaciones\\
\textbf{cuando} ingreso a la sección de tipos de alertas en el sistema\\
\textbf{entonces} puedo seleccionar qué tipos de eventos (temperatura fuera de rango, desviaciones de ruta, fallos de equipo, etc.) deseo recibir como notificación.\\[0.2em]

\textbf{Escenario 2: Selección de canales de notificación}\\
\textbf{Dado que} he seleccionado los tipos de alertas que deseo recibir\\
\textbf{cuando} configuro el canal de envío\\
\textbf{entonces} puedo elegir entre correo electrónico, SMS o notificaciones push, y guardar mis preferencias para cada tipo de alerta.\\[0.2em]

\textbf{Escenario 3: Definición de umbrales personalizados}\\
\textbf{Dado que} quiero personalizar cuándo se activa una alerta\\
\textbf{cuando} ingreso al módulo de configuración de umbrales\\
\textbf{entonces} puedo definir valores específicos (por ejemplo, temperatura máxima de 28°C, retraso superior a 10 minutos) que disparen las notificaciones correspondientes.\\[0.2em]
\end{tabular}
& EP07 \\

\hline
US06 & Personalización del dashboard & \textbf{Como} administrador educativo, \textbf{quiero} personalizar el dashboard seleccionando qué widgets visualizar, su orden y frecuencia de actualización, \textbf{para} adaptar la interfaz a las prioridades específicas de mi institución y mejorar la usabilidad del sistema. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Selección de widgets del dashboard}\\
\textbf{Dado que} estoy visualizando el dashboard de administración\\
\textbf{cuando} ingreso al modo de personalización\\
\textbf{entonces} puedo seleccionar los widgets que deseo visualizar, como incidencias, rutas activas, estado de vehículos, estadísticas de abordaje, etc.\\[0.2em]

\textbf{Escenario 2: Reordenamiento de widgets}\\
\textbf{Dado que} he seleccionado los widgets de mi interés\\
\textbf{cuando} arrastro los elementos en la interfaz\\
\textbf{entonces} puedo reorganizarlos para que los más importantes estén visibles en la parte superior del dashboard.\\[0.2em]

\textbf{Escenario 3: Guardado de configuración personalizada}\\
\textbf{Dado que} he personalizado el dashboard a mis necesidades\\
\textbf{cuando} guardo los cambios\\
\textbf{entonces} el sistema almacena mi configuración para que se mantenga en futuras sesiones.\\[0.2em]
\end{tabular}
& EP07 \\

\hline

\end{longtable}

\newpage

### Tutor legal o familiar

***Epics*** **y** ***User Stories:***

\begin{longtable}{|m{5cm}|m{10cm}|}
\hline
\textbf{EP01 (Gestión de Cuentas de Padres)} & \textbf{Como} tutor legal, \textbf{quiero} gestionar mi cuenta de manera segura, para acceder a la aplicación móvil y administrar el seguimiento del transporte de mi hijo. \\
\hline
US01 & Registro e Inicio de Sesión \\
\hline
US02 & Recuperación de Contraseña \\
\hline
US03 & Edición de Perfil \\
\hline
US04 & Gestión de Dispositivos de Notificación \\
\hline
\textbf{EP02 (Seguimiento en Tiempo Real)} & \textbf{Como} tutor legal, \textbf{quiero} conocer la ubicación y el progreso de la ruta de transporte de mi hijo en tiempo real, para poder organizarme y estar informado. \\
\hline
US01 & Ubicación en Vivo del Vehículo \\
\hline
US02 & Consulta de Ruta Planificada \\
\hline
US03 & Estimación de Tiempo Restante \\
\hline
\textbf{EP03 (Notificaciones y Alertas)} & \textbf{Como} tutor legal, \textbf{quiero} recibir alertas y notificaciones sobre los eventos críticos del viaje de mi hijo, para asegurarme de que todo esté en orden durante el trayecto. \\
\hline
US01 & Notificación de Abordaje \\
\hline
US02 & Notificación de Llegada \\
\hline
US03 & Alerta por Desvío o Retraso \\
\hline
US04 & Alerta de Temperatura Insegura \\
\hline
\textbf{EP04 (Supervisión Visual)} & \textbf{Como} tutor legal, \textbf{quiero} tener acceso en tiempo real a la transmisión de video desde la cámara a bordo, para poder supervisar el viaje de mi hijo en todo momento. \\
\hline
US01 & Supervisión en Tiempo Real (Ida) \\
\hline
US02 & Supervisión en Tiempo Real (Regreso) \\
\hline
\textbf{EP05 (Historial y Reportes Personales)} & \textbf{Como} tutor legal, \textbf{quiero} tener acceso al historial de viajes y eventos pasados de mi hijo, para poder revisar patrones de comportamiento y reportar cualquier anomalía. \\
\hline
US01 & Historial de Rutas Diarias \\
\hline
US02 & Log de Eventos Recientes \\
\hline
US03 & Exportación de Historial \\
\hline
\textbf{EP06 (Preferencias y Configuración)} & \textbf{Como} tutor legal, \textbf{quiero} poder personalizar mi experiencia en la aplicación móvil, para ajustarla a mis necesidades y preferencias personales. \\
\hline
US01 & Selección de Notificaciones por Hijo \\
\hline
US02 & Definición de Horarios de Silencio \\
\hline
US03 & Personalización de Idioma y Tema \\
\hline
\textbf{EP07 (Soporte y Comunicación)} & \textbf{Como} tutor legal, \textbf{quiero} poder comunicarme con el conductor o el administrador, y reportar incidencias, para resolver cualquier problema que surja durante el trayecto. \\
\hline
US01 & Comunicación Directa con el Conductor \\
\hline
US02 & Reporte de Incidencias con Evidencia \\
\hline
US03 & Acceso a Ayuda y Preguntas Frecuentes \\
\hline
\end{longtable}

\newpage

***User Stories:***

\begin{longtable}{|p{1cm}|p{3cm}|p{4cm}|p{5cm}|p{1cm}|}
\hline
\multicolumn{1}{|c|}{\textbf{ID}} & \multicolumn{1}{c|}{\textbf{Título}} & \multicolumn{1}{c|}{\textbf{Descripción}} & \multicolumn{1}{c|}{\textbf{Criterios de Aceptación}} & \multicolumn{1}{c|}{\textbf{Epic}} \\
\hline
US01 & Registro e Inicio de Sesión & \textbf{Como} tutor legal, \textbf{quiero} registrarme e iniciar sesión con mi cuenta, \textbf{para} acceder de forma segura a la aplicación móvil y administrar el seguimiento del transporte de mi hijo. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Registro exitoso}\\
\textbf{Dado que} accedo al formulario de registro en la aplicación móvil\\
\textbf{cuando} ingreso mis datos personales (nombre, correo electrónico, número de teléfono) y creo una contraseña segura\\
\textbf{entonces} el sistema valida mi información, crea mi cuenta y me dirige a la pantalla de inicio.\\[0.2em]

\textbf{Escenario 2: Inicio de sesión exitoso}\\
\textbf{Dado que} ya poseo una cuenta registrada\\
\textbf{cuando} ingreso mis credenciales correctas (correo electrónico y contraseña) en el formulario de inicio de sesión\\
\textbf{entonces} el sistema autentica mi identidad y me permite acceder a la aplicación móvil.\\[0.2em]

\textbf{Escenario 3: Error en registro por datos incompletos o inválidos}\\
\textbf{Dado que} intento registrarme\\
\textbf{cuando} omito algún campo obligatorio o ingreso datos en formato incorrecto\\
\textbf{entonces} el sistema muestra mensajes de error específicos indicando la necesidad de completar o corregir la información ingresada.\\[0.2em]
\end{tabular}
& EP01 \\

\hline
US02 & Recuperación de Contraseña & \textbf{Como} tutor legal, \textbf{quiero} recuperar mi contraseña vía correo o SMS, \textbf{para} restablecer el acceso en caso de olvido y seguir utilizando la aplicación sin inconvenientes. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Solicitud de recuperación exitosa}\\
\textbf{Dado que} he olvidado mi contraseña\\
\textbf{cuando} selecciono la opción “¿Olvidaste tu contraseña?” en la pantalla de inicio de sesión\\
\textbf{y} proporciono mi correo electrónico o número de teléfono registrado\\
\textbf{entonces} el sistema envía un enlace o código de verificación para restablecer la contraseña.\\[0.2em]

\textbf{Escenario 2: Ingreso de nueva contraseña}\\
\textbf{Dado que} recibí el enlace o código de recuperación\\
\textbf{cuando} accedo al formulario correspondiente\\
\textbf{y} establezco una nueva contraseña válida\\
\textbf{entonces} el sistema actualiza la contraseña y me permite iniciar sesión con la nueva clave.\\[0.2em]

\textbf{Escenario 3: Error por correo o número no registrado}\\
\textbf{Dado que} intento recuperar mi contraseña\\
\textbf{cuando} ingreso un correo electrónico o número de teléfono no registrado en el sistema\\
\textbf{entonces} el sistema muestra un mensaje de error indicando que no se encuentra ninguna cuenta asociada.\\[0.2em]
\end{tabular}
& EP01 \\

\hline
US03 & Edición de Perfil & \textbf{Como} tutor legal, \textbf{quiero} editar mi perfil (datos de contacto) y la información de mis hijos (grado, pulsera RFID), \textbf{para} mantener toda la información actualizada y garantizar una correcta gestión del transporte. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Edición de datos de contacto exitosa}\\
\textbf{Dado que} accedo a la sección de perfil desde la aplicación móvil\\
\textbf{cuando} modifico mis datos de contacto como correo electrónico o número de teléfono\\
\textbf{entonces} el sistema guarda los cambios y muestra un mensaje de confirmación.\\[0.2em]

\textbf{Escenario 2: Edición de información del hijo}\\
\textbf{Dado que} deseo actualizar la información de mi hijo\\
\textbf{cuando} cambio el grado escolar o actualizo el identificador de su pulsera RFID\\
\textbf{entonces} el sistema almacena la nueva información correctamente.\\[0.2em]

\textbf{Escenario 3: Validación de campos obligatorios}\\
\textbf{Dado que} estoy editando mi perfil o la información de mi hijo\\
\textbf{cuando} dejo campos obligatorios vacíos o ingreso datos inválidos\\
\textbf{entonces} el sistema muestra mensajes de advertencia solicitando corrección antes de guardar.\\[0.2em]
\end{tabular}
& EP01 \\

\hline
US04 & Gestión de Dispositivos de Notificación & \textbf{Como} tutor legal, \textbf{quiero} gestionar mis dispositivos de notificación (push, email, SMS), \textbf{para} elegir cómo y cuándo recibir alertas sobre el transporte de mi hijo. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Configuración de canal de notificación preferido}\\
\textbf{Dado que} accedo a la configuración de notificaciones en la aplicación móvil\\
\textbf{cuando} selecciono uno o más canales como push, email o SMS\\
\textbf{entonces} el sistema guarda mis preferencias y las usa para futuras alertas.\\[0.2em]

\textbf{Escenario 2: Desactivación de un canal específico}\\
\textbf{Dado que} ya no deseo recibir notificaciones por un canal específico\\
\textbf{cuando} desactivo dicho canal desde la configuración\\
\textbf{entonces} el sistema deja de enviar notificaciones por ese medio.\\[0.2em]

\textbf{Escenario 3: Personalización de tipos de alertas}\\
\textbf{Dado que} deseo recibir solo ciertos tipos de alertas (abordaje, llegada, temperatura)\\
\textbf{cuando} selecciono mis preferencias dentro de la aplicación\\
\textbf{entonces} el sistema me notificará solo sobre los eventos seleccionados.\\[0.2em]
\end{tabular}
& EP01 \\

\hline
US01 & Ubicación en Vivo del Vehículo & \textbf{Como} tutor legal, \textbf{quiero} ver la posición en vivo del vehículo que transporta a mi hijo, \textbf{para} estimar su hora de llegada y estar preparado ante cualquier eventualidad. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Visualización de la ubicación en tiempo real}\\
\textbf{Dado que} tengo acceso a la aplicación móvil como padre registrado\\
\textbf{cuando} ingreso a la sección de seguimiento\\
\textbf{entonces} el sistema muestra un mapa con la ubicación actual del vehículo en movimiento.\\[0.2em]

\textbf{Escenario 2: Actualización automática de la ubicación}\\
\textbf{Dado que} estoy visualizando el mapa de seguimiento\\
\textbf{cuando} el vehículo avanza por su ruta\\
\textbf{entonces} la ubicación se actualiza automáticamente cada cierto intervalo de tiempo (ej. cada 10 segundos).\\[0.2em]

\textbf{Escenario 3: Indicador del estudiante a bordo}\\
\textbf{Dado que} estoy visualizando la ubicación del vehículo\\
\textbf{cuando} mi hijo ha abordado o descendido del vehículo\\
\textbf{entonces} el sistema indica el estado del estudiante (a bordo / descendido) junto al ícono del vehículo.\\[0.2em]
\end{tabular}
& EP02 \\

\hline
US02 & Consulta de Ruta Planificada & \textbf{Como} tutor legal, \textbf{quiero} consultar la ruta planificada y el progreso del recorrido, \textbf{para} saber por dónde va el vehículo y cuánto falta para que llegue a su destino. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Visualización de ruta planificada}\\
\textbf{Dado que} tengo acceso a la aplicación móvil\\
\textbf{cuando} ingreso a la sección de seguimiento\\
\textbf{entonces} se muestra la ruta completa planificada del vehículo, incluyendo puntos de abordaje y destino final.\\[0.2em]

\textbf{Escenario 2: Progreso de la ruta en porcentaje}\\
\textbf{Dado que} estoy visualizando la ruta del vehículo\\
\textbf{cuando} el vehículo avanza a lo largo de su trayecto\\
\textbf{entonces} el sistema muestra un indicador del porcentaje de ruta completado en tiempo real.\\[0.2em]

\textbf{Escenario 3: Resaltado de tramos recorridos y pendientes}\\
\textbf{Dado que} estoy viendo el mapa con la ruta\\
\textbf{cuando} el vehículo avanza\\
\textbf{entonces} los tramos recorridos se resaltan con un color distinto al de los tramos pendientes.\\[0.2em]
\end{tabular}
& EP02 \\

\hline
US03 & Estimación de Tiempo Restante & \textbf{Como} tutor legal, \textbf{quiero} recibir la estimación de tiempo restante hasta el punto de recogida o entrega de mi hijo, \textbf{para} poder organizarme mejor y estar preparado a tiempo. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Visualización del tiempo estimado de llegada}\\
\textbf{Dado que} estoy en la aplicación móvil y consulto el estado del vehículo\\
\textbf{cuando} selecciono el punto de recogida o entrega de mi hijo\\
\textbf{entonces} el sistema muestra la hora estimada de llegada del vehículo.\\[0.2em]

\textbf{Escenario 2: Actualización dinámica del tiempo restante}\\
\textbf{Dado que} el vehículo está en movimiento\\
\textbf{cuando} hay cambios en el tráfico o desvíos\\
\textbf{entonces} la estimación de tiempo se actualiza automáticamente en la aplicación.\\[0.2em]

\textbf{Escenario 3: Notificación de proximidad}\\
\textbf{Dado que} el vehículo está próximo al punto de recogida o entrega\\
\textbf{cuando} está a menos de 5 minutos de distancia\\
\textbf{entonces} recibo una notificación indicando que el vehículo está cerca.\\[0.2em]
\end{tabular}
& EP02 \\

\hline
US01 & Notificación de Abordaje & \textbf{Como} tutor legal, \textbf{quiero} recibir una notificación cuando mi hijo aborde la unidad, \textbf{para} saber que ha subido correctamente al vehículo y estar tranquilo durante el viaje. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Notificación exitosa de abordaje}\\
\textbf{Dado que} el sistema detecta la lectura exitosa de la pulsera RFID de mi hijo al abordar la unidad\\
\textbf{cuando} se registra el evento en el sistema\\
\textbf{entonces} recibo de inmediato una notificación en mi dispositivo móvil indicando “Abordaje exitoso: [Nombre del estudiante] ha subido a la unidad”.\\[0.2em]

\textbf{Escenario 2: Notificación en caso de retraso en el registro}\\
\textbf{Dado que} mi hijo aborda la unidad, pero la lectura RFID se demora por cuestiones técnicas\\
\textbf{cuando} el sistema eventualmente procesa la lectura\\
\textbf{entonces} recibo una notificación tardía indicando el abordaje y se me informa del retraso en la actualización.\\[0.2em]

\textbf{Escenario 3: Manejo de error en la lectura}\\
\textbf{Dado que} ocurre un error en la lectura de la pulsera RFID al abordar\\
\textbf{cuando} el sistema no puede confirmar el abordaje automáticamente\\
\textbf{entonces} recibo una notificación de “Abordaje pendiente” solicitando que se verifique manualmente el estado del estudiante.
\end{tabular}
& EP03 \\

\hline
US02 & Notificación de Llegada & \textbf{Como} tutor legal, \textbf{quiero} recibir una notificación cuando mi hijo llegue al colegio o a casa, \textbf{para} confirmar su arribo seguro y tener tranquilidad sobre el cumplimiento del recorrido. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Notificación de llegada al colegio}\\
\textbf{Dado que} la unidad llega al punto de destino (colegio) y se detecta la bajada del estudiante mediante su pulsera RFID\\
\textbf{cuando} se registra la salida del vehículo y la lectura de la pulsera\\
\textbf{entonces} recibo una notificación que indica “Llegada confirmada: [Nombre del estudiante] ha llegado al colegio”.\\[0.2em]

\textbf{Escenario 2: Notificación de llegada a casa}\\
\textbf{Dado que} mi hijo está retornando del colegio y el vehículo llega al punto de bajada en casa\\
\textbf{cuando} se registra la lectura RFID al bajar de la unidad\\
\textbf{entonces} recibo una notificación que indica “Llegada confirmada: [Nombre del estudiante] ha llegado a casa”.\\[0.2em]

\textbf{Escenario 3: Fallo en la detección de bajada}\\
\textbf{Dado que} mi hijo llega al destino pero el sistema no detecta la bajada\\
\textbf{cuando} no se recibe lectura RFID al descender\\
\textbf{entonces} recibo una notificación de alerta indicando “No se ha confirmado la bajada de [Nombre del estudiante], por favor verifique el estado”.
\end{tabular}
& EP03 \\

\hline
US03 & Alerta por Desvío o Retraso & \textbf{Como} tutor legal, \textbf{quiero} recibir una alerta si el vehículo se desvía de la ruta o sufre un retraso significativo, \textbf{para} estar informado de cualquier incidencia que pueda afectar la seguridad o puntualidad del trayecto de mi hijo. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Alerta por desvío de ruta}\\
\textbf{Dado que} el vehículo escolar está siguiendo una ruta planificada\\
\textbf{cuando} el sistema detecta que se ha desviado significativamente del trayecto autorizado\\
\textbf{entonces} recibo una notificación indicando “Alerta: Desvío detectado en la ruta del vehículo de [Nombre del estudiante]”.\\[0.2em]

\textbf{Escenario 2: Alerta por retraso significativo}\\
\textbf{Dado que} el vehículo está en tránsito hacia el colegio o hacia casa\\
\textbf{cuando} el tiempo estimado de llegada se ve superado en más de 10 minutos respecto al plan inicial\\
\textbf{entonces} recibo una notificación que indica “Alerta: Retraso en el trayecto del vehículo de [Nombre del estudiante]”.\\[0.2em]

\textbf{Escenario 3: Confirmación de resolución de incidente}\\
\textbf{Dado que} se ha enviado una alerta por desvío o retraso\\
\textbf{cuando} el sistema detecta que el vehículo ha retomado su ruta o se ha normalizado el tiempo estimado\\
\textbf{entonces} recibo una notificación indicando “Actualización: La unidad de [Nombre del estudiante] ha retomado su ruta con normalidad”.
\end{tabular}
& EP03 \\

\hline
US04 & Alerta de Temperatura Insegura & \textbf{Como} tutor legal, \textbf{quiero} recibir una alerta si la temperatura interna del vehículo sale de los rangos seguros, \textbf{para} asegurarme del confort y la seguridad de mi hijo durante el trayecto. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Alerta por temperatura alta}\\
\textbf{Dado que} el sistema monitorea constantemente la temperatura dentro del vehículo\\
\textbf{cuando} la temperatura interna supera los 30°C\\
\textbf{entonces} recibo una notificación que indica “Alerta: Temperatura elevada en la unidad de [Nombre del estudiante]”.\\[0.2em]

\textbf{Escenario 2: Alerta por temperatura baja}\\
\textbf{Dado que} el sistema detecta condiciones térmicas inusuales dentro del vehículo\\
\textbf{cuando} la temperatura interna desciende por debajo de los 15°C\\
\textbf{entonces} recibo una notificación que indica “Alerta: Temperatura baja en la unidad de [Nombre del estudiante]”.\\[0.2em]

\textbf{Escenario 3: Confirmación de temperatura normalizada}\\
\textbf{Dado que} se ha enviado una alerta por temperatura insegura\\
\textbf{cuando} el sistema detecta que la temperatura vuelve al rango seguro (15°C a 30°C)\\
\textbf{entonces} recibo una notificación indicando “Actualización: Temperatura normalizada en la unidad de [Nombre del estudiante]”.
\end{tabular}
& EP03 \\

\hline
US01 & Supervisión en Tiempo Real (Ida) & \textbf{Como} tutor legal, \textbf{quiero} ver en tiempo real el video de la cámara instalada en la unidad durante el trayecto de ida, \textbf{para} supervisar las condiciones del viaje y asegurarme de que mi hijo se encuentre en un ambiente seguro. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Acceso a la transmisión en vivo}\\
\textbf{Dado que} he iniciado sesión en la aplicación móvil\\
\textbf{cuando} selecciono la opción de supervisión en tiempo real para el trayecto de ida\\
\textbf{entonces} el sistema muestra la transmisión en vivo de la cámara a bordo del vehículo.\\[0.2em]

\textbf{Escenario 2: Calidad y estabilidad de la transmisión}\\
\textbf{Dado que} estoy visualizando la transmisión en vivo\\
\textbf{cuando} la conexión es estable y la cámara opera correctamente\\
\textbf{entonces} la imagen se muestra en alta calidad y con mínimo retraso, permitiéndome supervisar el viaje de forma clara.\\[0.2em]

\textbf{Escenario 3: Notificación de fallo en la transmisión}\\
\textbf{Dado que} la transmisión en vivo presenta problemas (pérdida de conexión, imagen borrosa, etc.)\\
\textbf{cuando} el sistema detecta un fallo en la transmisión\\
\textbf{entonces} recibo una notificación indicando “Problema en la transmisión en tiempo real”, invitándome a verificar la conexión o contactar soporte técnico.
\end{tabular}
& EP04 \\

\hline
US02 & Supervisión en Tiempo Real (Regreso) & \textbf{Como} tutor legal, \textbf{quiero} ver en tiempo real el video de la cámara instalada en la unidad durante el trayecto de regreso, \textbf{para} asegurarme del bienestar de mi hijo y supervisar las condiciones del viaje de regreso a casa. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Acceso a la transmisión en vivo}\\
\textbf{Dado que} he iniciado sesión en la aplicación móvil\\
\textbf{cuando} selecciono la opción de supervisión en tiempo real para el trayecto de regreso\\
\textbf{entonces} el sistema muestra la transmisión en vivo de la cámara a bordo del vehículo.\\[0.2em]

\textbf{Escenario 2: Calidad y estabilidad de la transmisión}\\
\textbf{Dado que} estoy visualizando la transmisión en vivo\\
\textbf{cuando} la conexión es estable y la cámara funciona correctamente\\
\textbf{entonces} la imagen se muestra en alta calidad y con mínimo retraso, permitiéndome supervisar el viaje de regreso sin inconvenientes.\\[0.2em]

\textbf{Escenario 3: Notificación de fallo en la transmisión}\\
\textbf{Dado que} la transmisión en vivo presenta problemas (pérdida de conexión, imagen borrosa, etc.)\\
\textbf{cuando} el sistema detecta un fallo en la transmisión\\
\textbf{entonces} recibo una notificación indicando “Problema en la transmisión en tiempo real”, sugiriéndome verificar la conexión o contactar soporte técnico.
\end{tabular}
& EP04 \\

\hline
US01 & Historial de Rutas Diarias & \textbf{Como} tutor legal, \textbf{quiero} consultar el historial de rutas diarias de mi hijo, \textbf{para} revisar su puntualidad y los recorridos anteriores, asegurándome de que todo transcurra como estaba planificado. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Consulta de historial de rutas diarias}\\
\textbf{Dado que} he iniciado sesión en la aplicación móvil\\
\textbf{cuando} accedo a la sección de historial de rutas diarias\\
\textbf{entonces} el sistema muestra una lista de las rutas realizadas por el vehículo con las fechas y horarios correspondientes.\\[0.2em]

\textbf{Escenario 2: Filtrado por fecha o rango de fechas}\\
\textbf{Dado que} quiero revisar las rutas realizadas en un periodo específico\\
\textbf{cuando} aplico un filtro de fechas (por ejemplo, una semana o mes)\\
\textbf{entonces} el sistema muestra solo las rutas realizadas en ese periodo de tiempo seleccionado.\\[0.2em]

\textbf{Escenario 3: Visualización de detalles del recorrido}\\
\textbf{Dado que} estoy revisando el historial de una ruta específica\\
\textbf{cuando} selecciono una ruta en particular\\
\textbf{entonces} el sistema muestra detalles del recorrido, incluyendo la hora de inicio, hora de finalización, puntos de recogida y entrega, y cualquier incidencia registrada (retrasos, desvíos, etc.).\\[0.2em]
\end{tabular}
& EP05 \\

\hline
US02 & Log de Eventos Recientes & \textbf{Como} tutor legal, \textbf{quiero} ver un log de eventos (abordaje, llegada, alertas) de los últimos X días, \textbf{para} detectar posibles problemas recurrentes y garantizar el bienestar de mi hijo durante el trayecto. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Consulta de log de eventos recientes}\\
\textbf{Dado que} he iniciado sesión en la aplicación móvil\\
\textbf{cuando} accedo a la sección de log de eventos recientes\\
\textbf{entonces} el sistema muestra un listado de los eventos de los últimos X días, con detalles como la hora, tipo de evento (abordaje, llegada, alertas) y cualquier incidencia registrada.\\[0.2em]

\textbf{Escenario 2: Filtrado por tipo de evento}\\
\textbf{Dado que} quiero revisar eventos de un tipo específico\\
\textbf{cuando} aplico un filtro de tipo de evento (por ejemplo, solo abordajes o solo alertas)\\
\textbf{entonces} el sistema muestra solo los eventos correspondientes al tipo seleccionado.\\[0.2em]

\textbf{Escenario 3: Filtrado por rango de fechas}\\
\textbf{Dado que} quiero revisar los eventos dentro de un rango de fechas específico\\
\textbf{cuando} aplico un filtro de fechas (por ejemplo, los últimos 3 días)\\
\textbf{entonces} el sistema muestra los eventos ocurridos dentro de ese periodo de tiempo seleccionado.\\[0.2em]
\end{tabular}
& EP05 \\

\hline
US03 & Exportación de Historial & \textbf{Como} tutor legal, \textbf{quiero} exportar o compartir el historial de rutas y eventos (en formato PDF/CSV), \textbf{para} presentarlo al colegio o a la empresa de transporte si surge alguna incidencia y tener un registro formal. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Exportación de historial a PDF}\\
\textbf{Dado que} he accedido al historial de rutas y eventos\\
\textbf{cuando} selecciono la opción para exportar el historial a PDF\\
\textbf{entonces} el sistema genera un archivo PDF con los detalles del historial de rutas y eventos, y lo pone disponible para descargar o compartir.\\[0.2em]

\textbf{Escenario 2: Exportación de historial a CSV}\\
\textbf{Dado que} he accedido al historial de rutas y eventos\\
\textbf{cuando} selecciono la opción para exportar el historial a CSV\\
\textbf{entonces} el sistema genera un archivo CSV con los detalles del historial de rutas y eventos, y lo pone disponible para descargar o compartir.\\[0.2em]

\textbf{Escenario 3: Error al exportar historial}\\
\textbf{Dado que} intento exportar el historial a PDF o CSV\\
\textbf{cuando} ocurre un error durante la exportación\\
\textbf{entonces} el sistema muestra un mensaje de error indicando que la exportación no se pudo completar y sugiere intentar nuevamente.\\[0.2em]
\end{tabular}
& EP05 \\

\hline
US01 & Selección de Notificaciones por Hijo & \textbf{Como} tutor legal, \textbf{quiero} seleccionar para cuál de mis hijos quiero recibir notificaciones, \textbf{para} evitar recibir alertas innecesarias y personalizar mi experiencia en la aplicación móvil. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Visualización de lista de hijos}\\
\textbf{Dado que} tengo varios hijos registrados en mi perfil\\
\textbf{cuando} accedo a la sección de preferencias y notificaciones\\
\textbf{entonces} el sistema muestra una lista de todos mis hijos con opciones para activar o desactivar notificaciones individualmente.\\[0.2em]

\textbf{Escenario 2: Selección y deselección de notificaciones}\\
\textbf{Dado que} deseo personalizar las notificaciones recibidas\\
\textbf{cuando} marco o desmarco la opción de notificaciones para cada hijo en la lista\\
\textbf{entonces} el sistema guarda automáticamente mi selección y actualiza mis preferencias para que reciba alertas sólo para los hijos seleccionados.\\[0.2em]

\textbf{Escenario 3: Confirmación de actualización de preferencias}\\
\textbf{Dado que} he realizado cambios en la selección de notificaciones\\
\textbf{cuando} finalizo el proceso de configuración\\
\textbf{entonces} el sistema muestra un mensaje de confirmación (“Preferencias actualizadas con éxito”) y las futuras notificaciones se envían conforme a mis ajustes.
\end{tabular}
& EP06 \\

\hline
US02 & Definición de Horarios de Silencio & \textbf{Como} tutor legal, \textbf{quiero} definir horarios de silencio (modo "No molestar"), \textbf{para} no recibir notificaciones fuera del rango permitido y evitar interrupciones en mis momentos de descanso o concentración. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Configuración de horario de silencio}\\
\textbf{Dado que} accedo a la sección de preferencias de notificaciones en la aplicación móvil\\
\textbf{cuando} selecciono la opción de "Horarios de Silencio" y establezco la franja horaria deseada\\
\textbf{entonces} el sistema guarda la configuración y desactiva automáticamente las notificaciones durante ese intervalo.\\[0.2em]

\textbf{Escenario 2: Confirmación de activación del modo silencio}\\
\textbf{Dado que} he configurado un horario de silencio\\
\textbf{cuando} la hora actual se encuentra dentro de la franja de silencio definida\\
\textbf{entonces} la aplicación deja de enviar notificaciones y muestra un indicador que confirma que el modo "No molestar" está activado.\\[0.2em]

\textbf{Escenario 3: Desactivación automática fuera del horario de silencio}\\
\textbf{Dado que} el horario de silencio ha finalizado\\
\textbf{cuando} el sistema detecta que la hora actual supera el rango configurado\\
\textbf{entonces} el modo "No molestar" se desactiva automáticamente y las notificaciones vuelven a enviarse normalmente.\\[0.2em]
\end{tabular}
& EP06 \\

\hline
US03 & Personalización de Idioma y Tema & \textbf{Como} tutor legal, \textbf{quiero} cambiar el idioma y el tema (claro/oscuro) de la aplicación, \textbf{para} adaptar la interfaz a mis preferencias personales y mejorar mi experiencia de uso. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Cambio de idioma}\\
\textbf{Dado que} estoy en la pantalla de configuración de la aplicación\\
\textbf{cuando} selecciono el idioma de preferencia en el menú desplegable (ej. español, inglés, etc.)\\
\textbf{entonces} el idioma de la aplicación se actualiza inmediatamente y todas las pantallas se muestran en el nuevo idioma seleccionado.\\[0.2em]

\textbf{Escenario 2: Cambio de tema}\\
\textbf{Dado que} estoy en la pantalla de configuración de la aplicación\\
\textbf{cuando} selecciono el tema (claro u oscuro) que prefiero\\
\textbf{entonces} la interfaz de la aplicación cambia al tema seleccionado y se ajusta visualmente a la preferencia.\\[0.2em]

\textbf{Escenario 3: Confirmación de cambios}\\
\textbf{Dado que} he cambiado el idioma y el tema\\
\textbf{cuando} guardo los cambios\\
\textbf{entonces} el sistema muestra un mensaje de confirmación indicando “Idioma y tema actualizados con éxito” y la interfaz se adapta de acuerdo a las preferencias seleccionadas.\\[0.2em]
\end{tabular}
& EP06 \\

\hline
US01 & Comunicación Directa con el Conductor & \textbf{Como} tutor legal, \textbf{quiero} enviar un mensaje o realizar una llamada al conductor desde la aplicación, \textbf{para} resolver dudas o coordinar imprevistos durante el trayecto. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Enviar mensaje al conductor}\\
\textbf{Dado que} estoy en la pantalla de seguimiento de mi hijo\\
\textbf{cuando} selecciono la opción de "Comunicación con el conductor" y elijo "Enviar mensaje"\\
\textbf{entonces} se abre una ventana de chat donde puedo escribir mi mensaje y enviarlo directamente al conductor.\\[0.2em]

\textbf{Escenario 2: Realizar llamada al conductor}\\
\textbf{Dado que} estoy en la pantalla de seguimiento de mi hijo\\
\textbf{cuando} selecciono la opción de "Comunicación con el conductor" y elijo "Llamar al conductor"\\
\textbf{entonces} se realiza la llamada telefónica al conductor a través de la aplicación, utilizando el número de contacto del conductor.\\[0.2em]

\textbf{Escenario 3: Confirmación de mensaje enviado}\\
\textbf{Dado que} he enviado un mensaje al conductor\\
\textbf{cuando} el mensaje es entregado\\
\textbf{entonces} la aplicación muestra una notificación de confirmación indicando “Mensaje enviado con éxito al conductor” en la pantalla de chat.\\[0.2em]
\end{tabular}
& EP07 \\

\hline
US02 & Reporte de Incidencias con Evidencia & \textbf{Como} tutor legal, \textbf{quiero} reportar una incidencia (retraso, mal funcionamiento del sensor, etc.) con foto o video, \textbf{para} que el colegio pueda tomar acciones basadas en la evidencia proporcionada. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Reporte de incidencia con foto}\\
\textbf{Dado que} estoy en la pantalla de seguimiento de mi hijo y observo una incidencia (como un retraso o mal funcionamiento del sensor)\\
\textbf{cuando} selecciono la opción "Reportar incidencia" y elijo "Adjuntar foto"\\
\textbf{entonces} la aplicación me permite tomar una foto y enviarla junto con una descripción del problema, generando un reporte para el colegio.\\[0.2em]

\textbf{Escenario 2: Reporte de incidencia con video}\\
\textbf{Dado que} estoy en la pantalla de seguimiento de mi hijo y observo una incidencia\\
\textbf{cuando} selecciono la opción "Reportar incidencia" y elijo "Adjuntar video"\\
\textbf{entonces} la aplicación me permite grabar un video y enviarlo junto con una descripción del problema, generando un reporte para el colegio.\\[0.2em]

\textbf{Escenario 3: Confirmación de reporte enviado}\\
\textbf{Dado que} he enviado un reporte de incidencia con foto o video\\
\textbf{cuando} el reporte es enviado correctamente\\
\textbf{entonces} la aplicación muestra una notificación de confirmación indicando “Incidencia reportada con éxito” en la pantalla de reporte.\\[0.2em]
\end{tabular}
& EP07 \\

\hline
US03 & Acceso a Ayuda y Preguntas Frecuentes & \textbf{Como} tutor legal, \textbf{quiero} acceder a una sección de ayuda y preguntas frecuentes, \textbf{para} resolver rápidamente mis dudas sobre el funcionamiento de la app. &
\begin{tabular}[t]{@{}p{5cm}@{}}
\textbf{Escenario 1: Acceso a la sección de ayuda}\\
\textbf{Dado que} estoy en la pantalla principal de la aplicación\\
\textbf{cuando} selecciono la opción de "Ayuda" en el menú principal\\
\textbf{entonces} la aplicación me redirige a la sección de ayuda y preguntas frecuentes, donde puedo ver una lista de preguntas comunes y sus respuestas.\\[0.2em]

\textbf{Escenario 2: Búsqueda de una pregunta específica}\\
\textbf{Dado que} estoy en la sección de preguntas frecuentes\\
\textbf{cuando} utilizo la barra de búsqueda para escribir una palabra clave relacionada con mi duda\\
\textbf{entonces} la aplicación muestra una lista de preguntas relacionadas con la búsqueda, para que pueda encontrar rápidamente la respuesta.\\[0.2em]

\textbf{Escenario 3: Acceso a información detallada de una pregunta}\\
\textbf{Dado que} estoy en la sección de preguntas frecuentes\\
\textbf{cuando} selecciono una pregunta de la lista\\
\textbf{entonces} la aplicación muestra una respuesta detallada con información adicional sobre cómo resolver el problema o gestionar la función relacionada.\\[0.2em]
\end{tabular}
& EP07 \\

\hline

\end{longtable}

\newpage

## Impact Mapping.

El Impact Map es una herramienta estratégica que ayuda a identificar y mejorar las características de una aplicación para cumplir con un objetivo empresarial específico. Partiendo de un objetivo clave, se determinan los comportamientos necesarios de los usuarios, las acciones que deben realizar en la aplicación, y las características que habilitarán esas acciones. Luego, se evalúa el impacto potencial de cada característica en el cumplimiento del objetivo y se desarrolla un plan de acción detallado,
alineando así las acciones de los usuarios con los objetivos estratégicos de la empresa.

**Segmento Objetivo 1**

![Artefacto creado en UXPressia](src/img/cap3/ImpactMapping1.png)

\newpage

**Segmento Objetivo 2**

![Artefacto creado en UXPressia](src/img/cap3/ImpactMapping2.png)

\newpage

## Product Backlog.

Una de las técnicas más utilizadas para estimar el esfuerzo necesario para completar cada tarea es la escala de Fibonacci, la cual permite asignar puntos de historia de manera proporcional a la complejidad y tiempo requerido. 

\vspace{1em}

\begin{quote}
Como señala Smith (2020), esta escala no lineal facilita la identificación de tareas que requieren un mayor esfuerzo, lo que resulta en una planificación más precisa y eficiente.
\end{quote}

\vspace{1em}

A continuación, se presentan la tablas de nuestros *Product Backlog* para cada segmento objetivo, demostrando cómo se alinean nuestros recursos con las necesidades más urgentes de nuestros usuarios.

**Administrador educativo:**

\begin{longtable}{|c|p{4cm}|p{7cm}|c|}
\hline
\multicolumn{1}{|c|}{\textbf{ID}} & \multicolumn{1}{c|}{\textbf{Título}} & \multicolumn{1}{c|}{\textbf{Descripción}} & \multicolumn{1}{c|}{\textbf{Story Points}} \\
\hline

DS05 & Control de cambios de última hora en la asignación de conductores y estudiantes & \textbf{Como} administrador educativo, \textbf{quiero} realizar cambios de última hora en la asignación de conductores y estudiantes, \textbf{para} asegurar la continuidad del servicio ante imprevistos sin afectar el resto de la programación. & 13 \\
\hline
ES01 & Monitoreo en tiempo real de posición y velocidad de vehículos & \textbf{Como} administrador educativo, \textbf{quiero} conocer la posición y velocidad en tiempo real de cada vehículo, \textbf{para} monitorear sus rutas y detectar posibles retrasos o desvíos oportunamente. & 13 \\
\hline
ES05 & Verificación de rutas alternativas en caso de desvíos & \textbf{Como} administrador educativo, \textbf{quiero} verificar y gestionar rutas alternativas en tiempo real cuando una unidad se desvía de su ruta prevista, \textbf{para} garantizar que los estudiantes lleguen a su destino de manera segura y a tiempo frente a imprevistos. & 13 \\
\hline
HS01 & Dashboard con KPIs clave & \textbf{Como} administrador educativo, \textbf{quiero} acceder a un dashboard que muestre KPIs clave (número de rutas activas, incidencias, temperatura media, etc.), \textbf{para} monitorear la operación del transporte escolar de un vistazo y tomar decisiones basadas en datos en tiempo real. & 13 \\
\hline

CS02 & Definición y mapeo de zonas & \textbf{Como} administrador educativo, \textbf{quiero} definir y mapear zonas de recogida y entrega en un mapa interactivo, \textbf{para} optimizar la cobertura y asignar rutas con precisión. & 8 \\
\hline
CS03 & Visualización geoespacial de zonas y rutas & \textbf{Como} administrador educativo, \textbf{quiero} visualizar todas las zonas de recogida y entrega y sus rutas asociadas en un mapa interactivo, \textbf{para} detectar posibles solapamientos, huecos de cobertura o áreas no cubiertas. & 8 \\
\hline
DS02 & Registro y asignación de pulseras RFID a estudiantes & \textbf{Como} administrador educativo, \textbf{quiero} registrar a los estudiantes en el sistema y asignarles pulseras RFID con un identificador único, \textbf{para} vincular cada niño con su dispositivo de control y gestionar su transporte de manera más eficiente. & 8 \\
\hline
DS03 & Asignación de conductores y estudiantes a rutas específicas & \textbf{Como} administrador educativo, \textbf{quiero} asignar conductores y estudiantes a rutas específicas en el sistema, \textbf{para} asegurar que cada unidad opere con el personal y pasajeros correctos y optimizar la seguridad del transporte escolar. & 8 \\
\hline
ES02 & Monitoreo de temperatura interna de los vehículos & \textbf{Como} administrador educativo, \textbf{quiero} monitorear remotamente la temperatura interna de los vehículos, \textbf{para} asegurarme de que las condiciones sean seguras para los pasajeros. & 8 \\
\hline
ES03 & Seguimiento de unidades de transporte para verificar salida y llegada & \textbf{Como} administrador educativo, \textbf{quiero} visualizar en tiempo real qué unidades ya han partido para recoger a los estudiantes y qué unidades ya han llegado al centro educativo, \textbf{para} hacer un seguimiento eficiente del estado de las rutas y asegurarme de que todos los estudiantes han sido recogidos o entregados. & 8 \\
\hline
ES04 & Monitoreo de estudiantes que no abordaron la unidad & \textbf{Como} administrador educativo, \textbf{quiero} hacer un seguimiento de qué estudiantes no abordaron la unidad, \textbf{para} tomar acciones inmediatas y asegurarme de que todos los estudiantes estén siendo transportados de forma segura. & 8 \\
\hline
ES06 & Visualización de unidades en ruta para gestionar desviaciones o retrasos & \textbf{Como} administrador educativo, \textbf{quiero} visualizar en tiempo real todas las unidades en ruta, \textbf{para} detectar rápidamente desviaciones o retrasos y tomar decisiones oportunas que aseguren el cumplimiento de los horarios y la seguridad de los estudiantes. & 8 \\
\hline
GS01 & Reporte de tiempos de ruta y cumplimiento & \textbf{Como} administrador educativo, \textbf{quiero} generar reportes de tiempos de ruta y cumplimiento, \textbf{para} evaluar el desempeño de la flota y apoyar la toma de decisiones basadas en datos operativos. & 8 \\
\hline
GS04 & Reporte de incidencias críticas & \textbf{Como} administrador del sistema, \textbf{quiero} generar reportes de incidencias críticas, \textbf{para} consolidar y analizar eventos como alertas de temperatura, desviaciones de ruta o fallos de equipo, con el fin de identificar patrones recurrentes y focalizar acciones de mejora continua en la gestión de transporte escolar. & 8 \\
\hline
GS05 & Programación de envíos automáticos de reportes & \textbf{Como} administrador del sistema, \textbf{quiero} programar envíos automáticos de reportes, \textbf{para} automatizar la distribución periódica de reportes (diarios, semanales o mensuales) a los responsables, garantizando que la información llegue a tiempo sin necesidad de intervención manual. & 8 \\
\hline
HS02 & Gestión de roles y permisos & \textbf{Como} administrador educativo, \textbf{quiero} gestionar los roles y permisos de los usuarios (coordinadores, supervisores, etc.), \textbf{para} delegar responsabilidades con seguridad y asegurarme de que cada usuario solo tenga acceso a la información y funciones necesarias para su rol. & 8 \\
\hline
HS04 & Registro de auditoría de actividad & \textbf{Como} administrador educativo, \textbf{quiero} llevar un registro de auditoría de todas las acciones realizadas por los administradores y supervisores (como la creación/edición de usuarios, cambios en rutas, ajustes de parámetros), \textbf{para} garantizar la trazabilidad y el cumplimiento de normativas internas. & 8 \\
\hline
HS06 & Personalización del dashboard & \textbf{Como} administrador educativo, \textbf{quiero} personalizar el dashboard seleccionando qué widgets visualizar, su orden y frecuencia de actualización, \textbf{para} adaptar la interfaz a las prioridades específicas de mi institución y mejorar la usabilidad del sistema. & 8 \\
\hline

CS01 & Registro y edición de vehículos & \textbf{Como} administrador educativo, \textbf{quiero} registrar y editar los datos de cada vehículo (placa, modelo, capacidad y estado operativo), \textbf{para} mantener un catálogo actualizado y fiable de la flota. & 5 \\
\hline
CS04 & Asignación de vehículos a rutas específicas & \textbf{Como} administrador educativo, \textbf{quiero} asignar vehículos específicos a rutas definidas, \textbf{para} tener un control operacional directo sobre qué unidad se utiliza en cada recorrido y facilitar la trazabilidad en caso de incidentes. & 5 \\
\hline
DS01 & Registro y actualización de conductores & \textbf{Como} administrador educativo, \textbf{quiero} registrar nuevos conductores y actualizar sus datos de contacto, número de licencia y estado operativo, \textbf{para} mantener un personal actualizado y garantizar la correcta asignación de rutas. & 5 \\
\hline
DS04 & Verificación de disponibilidad de conductores & \textbf{Como} administrador educativo, \textbf{quiero} verificar la disponibilidad de los conductores antes de asignarlos a una ruta, \textbf{para} evitar conflictos de horario y asegurar una gestión eficiente del personal y la flota. & 5 \\
\hline
FS01 & Alerta de temperatura fuera de rango & \textbf{Como} administrador educativo, \textbf{quiero} recibir alertas en tiempo real cuando la temperatura interna de un vehículo se salga de los parámetros establecidos, \textbf{para} tomar medidas inmediatas que garanticen la seguridad y el confort de los estudiantes durante el transporte. & 5 \\
\hline
FS02 & Alerta de retrasos o desviaciones en las rutas & \textbf{Como} administrador educativo, \textbf{quiero} recibir alertas inmediatas cuando una unidad de transporte experimente retrasos o se desvíe de la ruta establecida, \textbf{para} poder coordinar con el conductor y tomar decisiones rápidas que minimicen el impacto en el servicio y garanticen la llegada segura y oportuna de los estudiantes. & 5 \\
\hline
FS03 & Alerta de estudiantes no abordando la unidad & \textbf{Como} administrador educativo, \textbf{quiero} recibir alertas en tiempo real cuando un estudiante asignado a una ruta no aborde la unidad, \textbf{para} poder tomar medidas inmediatas como contactar al conductor o a los padres, y así garantizar la seguridad de todos los estudiantes. & 5 \\
\hline
FS04 & Notificación automática ante cambios de ruta o posibles retrasos & \textbf{Como} administrador educativo, \textbf{quiero} recibir notificaciones automáticas cuando un vehículo experimente cambios de ruta o posibles retrasos, \textbf{para} poder gestionar de manera proactiva las rutas y tomar decisiones para minimizar el impacto en los horarios de transporte. & 5 \\
\hline
FS05 & Alerta por fallo de equipo en el vehículo (GPS, RFID, sensores, etc.) & \textbf{Como} administrador educativo, \textbf{quiero} recibir una alerta inmediata en caso de fallo de equipos en los vehículos, como el GPS, RFID o sensores, \textbf{para} poder tomar medidas rápidas y garantizar que el control de las rutas y la seguridad de los estudiantes no se vean comprometidos. & 5 \\
\hline
GS02 & Estadísticas de abordaje por estudiante & \textbf{Como} administrador educativo, \textbf{quiero} obtener estadísticas de abordaje por estudiante, \textbf{para} detectar patrones de retraso o ausencias y tomar acciones preventivas que mejoren la eficiencia del transporte escolar. & 5 \\
\hline
GS03 & Exportación de datos históricos en Excel/PDF & \textbf{Como} responsable de calidad, \textbf{quiero} exportar datos históricos en formatos Excel o PDF, \textbf{para} presentarlos en auditorías o juntas directivas y facilitar la toma de decisiones estratégicas basadas en datos históricos. & 5 \\
\hline
GS06 & Filtrado y segmentación de datos históricos & \textbf{Como} administrador del sistema, \textbf{quiero} filtrar y segmentar datos históricos por ruta, vehículo, conductor o rango de fechas, \textbf{para} optimizar el análisis detallado y la preparación de informes personalizados para auditorías o reuniones de gestión. & 5 \\
\hline
HS03 & Configuración de parámetros globales & \textbf{Como} administrador educativo, \textbf{quiero} configurar parámetros globales (como los umbrales de temperatura, la frecuencia de reporte GPS, etc.), \textbf{para} adaptar el sistema a las políticas internas de la institución y asegurar el funcionamiento adecuado de la plataforma. & 5 \\
\hline
HS05 & Configuración de notificaciones y alertas & \textbf{Como} administrador educativo, \textbf{quiero} configurar qué tipos de notificaciones y alertas deseo recibir, por qué canal (correo electrónico, SMS, notificación push) y con qué umbrales, \textbf{para} adaptar la comunicación del sistema a los procesos internos de la institución. & 5 \\
\hline

CS05 & Desactivación temporal de unidades fuera de servicio & \textbf{Como} administrador educativo, \textbf{quiero} desactivar temporalmente vehículos fuera de servicio, \textbf{para} evitar su asignación errónea a rutas mientras se mantiene su información en el sistema para futuras referencias y reactivación. & 3 \\
\hline
FS06 & Notificación cuando la unidad ha completado el recorrido & \textbf{Como} administrador educativo, \textbf{quiero} recibir una notificación cuando una unidad haya completado su recorrido (tanto la ruta hacia el colegio como el retorno a casa), \textbf{para} poder gestionar eficientemente la programación de las unidades, evitando retrasos y asegurando que las unidades estén disponibles para nuevas asignaciones. & 3 \\
\hline
US01 & Registro de cuenta institucional & \textbf{Como} administrador educativo, \textbf{quiero} crear una cuenta institucional proporcionando mi nombre completo, correo institucional y contraseña, \textbf{para} acceder de manera segura a la plataforma web. & 3 \\
\hline
US05 & Recuperación de contraseña & \textbf{Como} administrador educativo, \textbf{quiero} poder recuperar mi contraseña a través de un correo electrónico, \textbf{para} poder acceder nuevamente a mi cuenta si la olvido. & 3 \\
\hline
US06 & Gestión de perfil administrativo & \textbf{Como} administrador educativo, \textbf{quiero} poder editar y actualizar mi perfil (como datos de contacto, cargo, etc.), \textbf{para} mantener mi información actualizada en la plataforma. & 3 \\
\hline

US02 & Confirmación de cuenta del administrador & \textbf{Como} administrador educativo, \textbf{quiero} confirmar mi cuenta a través de un enlace enviado a mi correo institucional, \textbf{para} verificar mi identidad y activar mi acceso al sistema. & 2 \\
\hline
US03 & Verificación de cuenta por parte del sistema & \textbf{Como} administrador educativo, \textbf{quiero} que el sistema verifique automáticamente la validez de mi cuenta, \textbf{para} asegurarme de que mi información esté correctamente registrada y no haya problemas para acceder a la plataforma. & 2 \\
\hline
US04 & Inicio de sesión del administrador educativo & \textbf{Como} administrador educativo, \textbf{quiero} iniciar sesión de manera segura en la plataforma utilizando mis credenciales (correo electrónico y contraseña), \textbf{para} acceder a las funcionalidades de administración del sistema de transporte escolar de manera eficiente. & 2 \\
\hline

US07 & Cierre de sesión segura & \textbf{Como} administrador educativo, \textbf{quiero} cerrar sesión de manera segura en la plataforma, \textbf{para} garantizar que mi cuenta esté protegida y no quede abierta a accesos no autorizados. & 1 \\
\hline

\end{longtable}

\newpage

**Tutor legal o familiar**


\begin{longtable}{|c|p{4cm}|p{7cm}|c|}
\hline
\multicolumn{1}{|c|}{\textbf{ID}} & \multicolumn{1}{c|}{\textbf{Título}} & \multicolumn{1}{c|}{\textbf{Descripción}} & \multicolumn{1}{c|}{\textbf{Story Points}} \\
\hline

ES01 & Supervisión en Tiempo Real (Ida) & \textbf{Como} tutor legal, \textbf{quiero} ver en tiempo real el video de la cámara instalada en la unidad durante el trayecto de ida, \textbf{para} supervisar las condiciones del viaje y asegurarme de que mi hijo se encuentre en un ambiente seguro. & 13 \\
\hline
ES02 & Supervisión en Tiempo Real (Regreso) & \textbf{Como} tutor legal, \textbf{quiero} ver en tiempo real el video de la cámara instalada en la unidad durante el trayecto de regreso, \textbf{para} asegurarme del bienestar de mi hijo y supervisar las condiciones del viaje de regreso a casa. & 13 \\
\hline

CS01 & Ubicación en Vivo del Vehículo & \textbf{Como} tutor legal, \textbf{quiero} ver la posición en vivo del vehículo que transporta a mi hijo, \textbf{para} estimar su hora de llegada y estar preparado ante cualquier eventualidad. & 8 \\
\hline
DS03 & Alerta por Desvío o Retraso & \textbf{Como} tutor legal, \textbf{quiero} recibir una alerta si el vehículo se desvía de la ruta o sufre un retraso significativo, \textbf{para} estar informado de cualquier incidencia que pueda afectar la seguridad o puntualidad del trayecto de mi hijo. & 8 \\
\hline
DS04 & Alerta de Temperatura Insegura & \textbf{Como} tutor legal, \textbf{quiero} recibir una alerta si la temperatura interna del vehículo sale de los rangos seguros, \textbf{para} asegurarme del confort y la seguridad de mi hijo durante el trayecto. & 8 \\
\hline
HS01 & Comunicación Directa con el Conductor & \textbf{Como} tutor legal, \textbf{quiero} enviar un mensaje o realizar una llamada al conductor desde la aplicación, \textbf{para} resolver dudas o coordinar imprevistos durante el trayecto. & 8 \\
\hline
HS02 & Reporte de Incidencias con Evidencia & \textbf{Como} tutor legal, \textbf{quiero} reportar una incidencia (retraso, mal funcionamiento del sensor, etc.) con foto o video, \textbf{para} que el colegio pueda tomar acciones basadas en la evidencia proporcionada. & 8 \\
\hline

US01 & Registro e Inicio de Sesión & \textbf{Como} tutor legal, \textbf{quiero} registrarme e iniciar sesión con mi cuenta, \textbf{para} acceder de forma segura a la aplicación móvil y administrar el seguimiento del transporte de mi hijo. & 5 \\
\hline
US02 & Recuperación de Contraseña & \textbf{Como} tutor legal, \textbf{quiero} recuperar mi contraseña vía correo o SMS, \textbf{para} restablecer el acceso en caso de olvido y seguir utilizando la aplicación sin inconvenientes. & 5 \\
\hline
CS02 & Consulta de Ruta Planificada & \textbf{Como} tutor legal, \textbf{quiero} consultar la ruta planificada y el progreso del recorrido, \textbf{para} saber por dónde va el vehículo y cuánto falta para que llegue a su destino. & 5 \\
\hline
CS03 & Estimación de Tiempo Restante & \textbf{Como} tutor legal, \textbf{quiero} recibir la estimación de tiempo restante hasta el punto de recogida o entrega de mi hijo, \textbf{para} poder organizarme mejor y estar preparado a tiempo. & 5 \\
\hline
FS03 & Exportación de Historial & \textbf{Como} tutor legal, \textbf{quiero} exportar o compartir el historial de rutas y eventos (en formato PDF/CSV), \textbf{para} presentarlo al colegio o a la empresa de transporte si surge alguna incidencia y tener un registro formal. & 5 \\
\hline

US03 & Edición de Perfil & \textbf{Como} tutor legal, \textbf{quiero} editar mi perfil (datos de contacto) y la información de mis hijos (grado, pulsera RFID), \textbf{para} mantener toda la información actualizada y garantizar una correcta gestión del transporte. & 3 \\
\hline
US04 & Gestión de Dispositivos de Notificación & \textbf{Como} tutor legal, \textbf{quiero} gestionar mis dispositivos de notificación (push, email, SMS), \textbf{para} elegir cómo y cuándo recibir alertas sobre el transporte de mi hijo. & 3 \\
\hline
DS01 & Notificación de Abordaje & \textbf{Como} tutor legal, \textbf{quiero} recibir una notificación cuando mi hijo aborde la unidad, \textbf{para} saber que ha subido correctamente al vehículo y estar tranquilo durante el viaje. & 3 \\
\hline
DS02 & Notificación de Llegada & \textbf{Como} tutor legal, \textbf{quiero} recibir una notificación cuando mi hijo llegue al colegio o a casa, \textbf{para} confirmar su arribo seguro y tener tranquilidad sobre el cumplimiento del recorrido. & 3 \\
\hline
FS01 & Historial de Rutas Diarias & \textbf{Como} tutor legal, \textbf{quiero} consultar el historial de rutas diarias de mi hijo, \textbf{para} revisar su puntualidad y los recorridos anteriores, asegurándome de que todo transcurra como estaba planificado. & 3 \\
\hline
FS02 & Log de Eventos Recientes & \textbf{Como} tutor legal, \textbf{quiero} ver un log de eventos (abordaje, llegada, alertas) de los últimos X días, \textbf{para} detectar posibles problemas recurrentes y garantizar el bienestar de mi hijo durante el trayecto. & 3 \\
\hline

GS01 & Selección de Notificaciones por Hijo & \textbf{Como} tutor legal, \textbf{quiero} seleccionar para cuál de mis hijos quiero recibir notificaciones, \textbf{para} evitar recibir alertas innecesarias y personalizar mi experiencia en la aplicación móvil. & 2 \\
\hline
GS02 & Definición de Horarios de Silencio & \textbf{Como} tutor legal, \textbf{quiero} definir horarios de silencio (modo "No molestar"), \textbf{para} no recibir notificaciones fuera del rango permitido y evitar interrupciones en mis momentos de descanso o concentración. & 2 \\
\hline
GS03 & Personalización de Idioma y Tema & \textbf{Como} tutor legal, \textbf{quiero} cambiar el idioma y el tema (claro/oscuro) de la aplicación, \textbf{para} adaptar la interfaz a mis preferencias personales y mejorar mi experiencia de uso. & 2 \\
\hline
HS03 & Acceso a Ayuda y Preguntas Frecuentes & \textbf{Como} tutor legal, \textbf{quiero} acceder a una sección de ayuda y preguntas frecuentes, \textbf{para} resolver rápidamente mis dudas sobre el funcionamiento de la app. & 2 \\
\hline

\end{longtable}

\newpage

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

\newpage

# Bibliografía
