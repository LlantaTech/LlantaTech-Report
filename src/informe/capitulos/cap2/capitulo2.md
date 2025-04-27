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

# Capítulo II: Requirements Elicitation & Analysis

Antes de construir una solución tecnológica efectiva, es esencial entender a fondo el problema, a los usuarios y el entorno en el que la solución será implementada. Este capítulo presenta el proceso de Requirements Elicitation & Analysis, una fase crítica en el desarrollo de soluciones centradas en el usuario. Aquí se identifican y analizan las necesidades del público objetivo, se estudia a la competencia y se utilizan técnicas como entrevistas, mapeo de tareas y escenarios para definir con claridad los requisitos funcionales y no funcionales del sistema. La información obtenida en esta etapa servirá como base sólida para el diseño e implementación de un producto alineado con las expectativas del mercado y con alto impacto en su adopción y uso.

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
