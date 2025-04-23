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

# Capítulo II: Requirements Elicitation & Analysis

Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.

\newpage

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

Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.

\newpage

### Diseño de entrevistas.

Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.

\newpage

### Registro de entrevistas.

Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.

\newpage

### Análisis de entrevistas.

Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.

\newpage

## Needfinding.

Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.

\newpage

### User Personas.

Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.

\newpage

### User Task Matrix.

Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.

\newpage

### User Journey Mapping.

Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.

\newpage

### Empathy Mapping.

Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.

\newpage

### As-is Scenario Mapping.

Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.

\newpage

## Ubiquitous Language.

Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.
