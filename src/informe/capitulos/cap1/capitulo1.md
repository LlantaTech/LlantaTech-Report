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


