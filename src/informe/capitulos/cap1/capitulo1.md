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

**Registro de Versiones del Informe**

\begin{longtable}{|c|c|c|p{6cm}|}
  \hline
  \textbf{Versión} & \textbf{Fecha} & \textbf{Autor} & \textbf{Descripción de Modificación} \\
  \hline
  tb1 & 25/04/2025 & Ortega Huaraca, Abel & Ayudé con la estructura del informe en general. Respecto a los puntos específicos, contribuí con la elaboración del \textit{Solution Profile}, \textit{Startup Profile}, Segmentos objetivo, \textit{User Stories} y una introducción para los \textit{Requirements Specification}. \\
  \hline
  tb1 & 25/04/2025 & Ramos Rios, Belén del Rocio & completar \\
  \hline
  tb1 & 25/04/2025 & Vilchez Rios, Mateo Alejandro & completar \\
  \hline
  tb1 & 25/04/2025 & Avila Asto, Alex Ramon Alberto & completar \\
  \hline
\end{longtable}

\newpage

***Project Report Collaboration Insights***

::: warn
Para mayor información, haga click en la [URL](https://github.com/orgs/LlantaTech/projects/2) 
:::

:::caution
Faltan colocar imagenes
:::

**TB1:**

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
FALTA COMPLETAR \\
\textbf{Belen del Rocio Ramos Rios} \\
FALTA COMPLETAR \\
\textbf{Mateo Alejandro Vilchez Rios} \\
FALTA COMPLETAR \\
\textbf{Alex Avila Asto} \\
FALTA COMPLETAR
\\} 
&
\parbox[t]{5cm}{
\textbf{TB1:} \\
FALTA COMPLETAR \\
} \\ 

\hline

\parbox[t]{4cm}{
\textit{Crea un entorno colaborativo e inclusivo, establece metas, planifica tareas y cumple objetivos}
}
&  
\parbox[t]{6cm}{
\textbf{TB1:} \\
\textbf{Abel Angel Ortega Huaraca} \\
FALTA COMPLETAR \\
\textbf{Belen del Rocio Ramos Rios} \\
FALTA COMPLETAR \\
\textbf{Mateo Alejandro Vilchez Rios} \\
FALTA COMPLETAR \\
\textbf{Alex Avila Asto} \\
FALTA COMPLETAR \\}
&
\parbox[t]{5cm}{
\textbf{TB1:} \\
FALTA COMPLETAR \\
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
Soy estudiante del sexto ciclo de la carrera de Ingeniería de Software. A lo largo de mi formación, he adquirido conocimientos en diversos lenguajes de programación, como Java, C++, y SQL. Además, manejo frameworks como Spring Boot para el desarrollo backend, y tanto Vue como Angular para el desarrollo frontend.
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
Soy estudiante de la carrera de Ingeniería de Software cursando actualmente el 6to ciclo. Me considero una persona eficiente, disciplinada y responsable. Poseo conocimientos básicos en C++, Java y JavaScript. Manejo de Base de Datos relacionales. Conocimientos en Frameworks como Angular y Spring. Me comprometo a brindar todo el apoyo necesario para cumplir con todos los requerimientos.
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

Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.

\newpage

### Lean UX Process.

Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.

\newpage

#### Lean UX Problem Statements.

Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.

\newpage

#### Lean UX Assumptions.

Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.

\newpage

#### Lean UX Hypothesis Statements.

Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.

\newpage

#### Lean UX Canvas.

Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.

\newpage

## Segmentos objetivo.

Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.


