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

# Capítulo V: Solution UI/UX Design

La experiencia del usuario es uno de los pilares más importantes para el éxito de RutaKids, dado que involucra a múltiples actores como padres, colegios y operadores de transporte. Esta sección presenta el diseño UX/UI propuesto para cada uno de los productos digitales que forman parte de nuestra solución. Se incluyen desde las guías de estilo y decisiones de arquitectura de información, hasta wireframes, mockups, user flows y prototipos interactivos. Todo el diseño se ha planteado pensando en la simplicidad, claridad y accesibilidad, asegurando una navegación intuitiva, consistente y centrada en el usuario. La propuesta busca maximizar el valor percibido y reducir la fricción en la experiencia diaria de cada segmento objetivo.


## Style Guidelines.

![Artefacto creado en Figma](src/img/cap5/cover.png)

Las directrices de estilo cumplen un papel clave en garantizar una identidad visual coherente en todos los productos de RutaKids. Estas pautas nos permiten mantener consistencia en los elementos gráficos, facilitando una experiencia clara y uniforme para los usuarios. A continuación, se detallan las guías generales y específicas aplicadas en cada plataforma.


\newpage

### General Style Guidelines.

En el diseño de productos digitales, la estética no es solo una cuestión de apariencia, sino una herramienta estratégica para facilitar la interacción del usuario. Un lenguaje visual bien definido, que incluya criterios claros sobre identidad de marca, esquema de colores, tipografía y tono comunicacional, contribuye a que la experiencia sea coherente, fluida y significativa.

\vspace{1em}

\begin{quote}
Rijgersberg (2025) argumenta que reducir la complejidad visual y estructurar la información de manera accesible disminuye la carga cognitiva, permitiendo que los usuarios avancen con claridad hacia sus objetivos. Bajo esta lógica, la simplicidad no implica ausencia de diseño, sino decisiones intencionales orientadas a la funcionalidad.
\end{quote}

\vspace{1em}

Por eso, contar con principios de diseño sólidos no solo mejora la accesibilidad y la eficiencia del producto, sino que también habilita su evolución en distintos contextos y dispositivos. Así, se construye una identidad visual adaptable, al servicio tanto de la experiencia del usuario como de la narrativa de la organización.

\vspace{2em}


**Branding:**

*Rutakids* es una solución tecnológica pensada para brindar seguridad y control en el transporte escolar. Su identidad visual refleja confianza, cercanía y modernidad, valores clave para padres y colegios. La plataforma busca simplificar la experiencia de seguimiento escolar a través de una interfaz clara, accesible y conectada en tiempo real.
Cada elemento del branding (colores, tipografía y estilo visual) está diseñado para reforzar la misión de *RutaKids*: ofrecer tranquilidad a las familias y eficiencia a las instituciones, con una experiencia intuitiva y coherente en todos sus canales digitales.


\vspace{2em}


**Logotipo:**

El logotipo de *RutaKids* fue diseñado para representar visualmente los valores fundamentales de la solución: movimiento, seguridad y tecnología accesible. Su símbolo principal es una rueda estilizada en movimiento, lo cual hace alusión directa al concepto de transporte escolar eficiente y monitoreado en tiempo real.
La elección del color azul vibrante busca transmitir confianza, profesionalismo y tranquilidad, mientras que las formas redondeadas del logotipo refuerzan la cercanía y la facilidad de uso que caracterizan a la plataforma. Además, se han definido variantes del logotipo para asegurar su correcta adaptación en diferentes fondos y contextos, sin comprometer la legibilidad ni la identidad visual del producto.

![Artefacto creado en Figma](src/img/cap5/LogoStyle.png)

\vspace{1em}

**Iconografía de la Aplicación**

La iconografía de *RutaKids* se basa en el uso del imagotipo de la marca (una rueda estilizada en movimiento) como símbolo principal en su versión para dispositivos móviles. Este elemento mantiene la coherencia gráfica de la marca al tiempo que asegura versatilidad y reconocimiento en pantallas reducidas. Además, para garantizar su legibilidad y funcionalidad, se desarrollaron distintas variantes del ícono, adaptables a diferentes fondos y contextos de uso. Su forma simplificada y su alto contraste permiten una fácil identificación desde la pantalla de inicio de cualquier dispositivo, reforzando la presencia visual de *RutaKids* dentro de su ecosistema digital.



![Artefacto creado en Figma](src/img/cap5/Icon_App.png)

\vspace{1em}


**Colores**

La paleta de colores de *RutaKids* está estructurada en dos grupos principales: los colores utilizados en la interfaz de usuario y aquellos aplicados en las variantes del logotipo e iconos. Esta clasificación permite mantener una coherencia visual sólida, adaptando el uso del color según su función en la experiencia del usuario y en la identidad de marca.

- **Colores Principales (Interfaz de la Aplicación)**

  Estos colores se aplican en la landing page, la aplicación web y la app móvil. Su selección busca optimizar la legibilidad, facilitar la navegación y establecer jerarquías visuales claras.
    
  - **Azul (#2979FF):** Color principal de acento, utilizado en botones, enlaces, íconos activos y llamadas a la acción. Simboliza tecnología, dinamismo y confiabilidad, atributos clave para una plataforma tecnológica dirigida al entorno infantil y familiar. Su intensidad favorece la visibilidad y guía la atención del usuario hacia las zonas de interacción.
  
  - **Blanco (#FFFFFF):** Funciona como fondo predominante en la interfaz. Su neutralidad permite maximizar la claridad, mejorar la percepción del contenido y generar una sensación de amplitud visual. Es fundamental para evitar la saturación cromática y facilitar la lectura en distintos dispositivos.
  
  - **Gris (#93868A):** Aplicado en textos secundarios, descripciones, etiquetas y componentes del dashboard. Este tono contribuye a una organización jerárquica de la información, diferenciando elementos sin provocar distracción visual. Su uso estratégico mejora la legibilidad y evita el contraste excesivo.
  
  - **Negro (#000000):** Utilizado en títulos, encabezados y textos primarios. Su alto contraste frente al blanco garantiza máxima legibilidad, especialmente en contenido textual de alta relevancia. Además, refuerza el énfasis visual y aporta un carácter formal a la estructura gráfica

  
  ![Artefacto creado en Figma](src/img/cap5/PrimaryColors.png)


- **Colores Secundarios (Variantes de Logos e Iconos)**

  Estos tonos de azul se emplean para asegurar que el logotipo y los íconos mantengan su visibilidad y coherencia visual en diferentes fondos y dispositivos. Las variantes permiten adaptar la marca sin perder identidad.

  - **Azul (#256CE4):** Empleado principalmente en variantes del logotipo sobre fondos claros. Ofrece buena visibilidad sin generar un contraste excesivo, manteniendo una apariencia amigable y moderna.
  
  - **Azul (#205EC6):** Alternativa versátil que proporciona equilibrio visual entre contraste y presencia de marca. Es útil para contextos digitales y materiales impresos donde se requiere mantener una estética sobria sin perder fuerza gráfica.
  
  - **Azul Oscuro (#123672):** Aplicado sobre fondos oscuros o saturados. Este tono profundo refuerza la elegancia, seriedad y profesionalismo de la marca, siendo apropiado para presentaciones formales, documentación institucional o entornos corporativos.
  
  ![Artefacto creado en Figma](src/img/cap5/SecondColors.png)


**Tipografía**

La identidad tipográfica de *RutaKids* ha sido cuidadosamente definida para asegurar legibilidad, jerarquía visual y consistencia en todas sus plataformas: landing page, aplicación web y aplicación móvil. Se emplean diferentes fuentes según el entorno, adaptadas a las necesidades visuales y funcionales de cada interfaz.

1. ***Landing Page***

- ***DM Sans* (Google Fonts)**
  
  - Pesos utilizados: *Bold, Medium, Regular, Italic*
  
  DM Sans es la tipografía principal utilizada en la landing page de RutaKids. Su diseño limpio y geométrico facilita la lectura tanto en títulos como en cuerpos de texto. La versión Bold se aplica a encabezados principales, Medium en párrafos destacados, y Regular e Italic en textos complementarios o citas.

  ![Artefacto creado en Figma](src/img/cap5/Typography_DMSans_landing.png)


- ***Space Grotesk* (Google Fonts)**
  
  - Peso utilizado: *Regular*
  
  Space Grotesk se utiliza de manera puntual en elementos destacados, como subtítulos o frases clave. Su estilo contemporáneo y ligeramente técnico aporta una personalidad moderna al diseño general de la landing page.

  ![Artefacto creado en Figma](src/img/cap5/Typography_SpaceGrotesk_landing.png)


2. **Aplicación Web**

- ***Outfit* (Google Fonts)**
  
  - Peso utilizado: *Bold, Medium, Regular*
  
  *Outfit* es la fuente principal empleada en la interfaz web. Su estructura sencilla y bien espaciada la hace ideal para entornos digitales centrados en la usabilidad. El peso Bold se asigna a títulos, Medium a subtítulos y elementos intermedios, y Regular al contenido general del sistema.

  ![Artefacto creado en Figma](src/img/cap5/Typography_Outfit_web.png)


3. **Aplicación Movil**

- ***Poppins* (Google Fonts)**
  
  - Peso utilizado: *Bold, Medium, Regular*
  
   *Poppins* es la tipografía principal de la app móvil. Su diseño geométrico y moderno contribuye a una interfaz clara y coherente. La versión Bold se utiliza para títulos y acciones clave, aportando énfasis visual. Medium se aplica en subtítulos y encabezados secundarios, manteniendo una jerarquía visual sólida. Y regular es ideal para el cuerpo del texto, asegurando una lectura fluida y accesible.

  ![Artefacto creado en Figma](src/img/cap5/Typography_Poppins_app.png)

\newpage

**Tonos de Comunicación**

El tono de voz de *RutaKids* fue cuidadosamente definido para alinearse con los valores del proyecto: seguridad, confiabilidad y eficiencia. Dado que se trata de una solución orientada al seguimiento de estudiantes en transporte escolar, la comunicación debe ser clara, profesional y empática. Por ello, se eligieron cuatro atributos clave que guían el estilo comunicativo en todas las plataformas y puntos de contacto:

- **Neutral:** Se emplea un lenguaje objetivo y sin juicios, especialmente útil en mensajes informativos, técnicos o institucionales. Este tono permite que la información sea comprendida sin ambigüedades ni interpretaciones subjetivas, ideal para notificaciones automatizadas o estados del sistema.

- **Formal:** Se emplea una redacción cuidada y profesional, adecuada para un entorno donde participan instituciones educativas y familias.  Este tono se aplica en secciones como configuraciones, paneles administrativos o documentación, donde se requiere precisión y credibilidad. Aporta seriedad y estructura sin resultar distante.

- **Respetuoso:** La comunicación se construye desde el respeto hacia todos los usuarios, considerando que se trata de un servicio vinculado al cuidado de menores. Este tono se refleja en el lenguaje empleado en interfaces, correos, mensajes de error o ayuda, evitando cualquier forma invasiva o autoritaria.

- **Objetivo:** Utilizado principalmente en situaciones críticas o informativas, este tono se enfoca en presentar los hechos de forma concisa y sin adornos. Es ideal para notificaciones de llegada/salida, alertas de seguridad, confirmaciones y registros. Aporta precisión y rapidez en la toma de decisiones.

La combinación de estos tonos permite que RutaKids mantenga una comunicación funcional, empática y profesional, fortaleciendo la experiencia del usuario y consolidando la confianza en la solución.

![Artefacto creado en Figma](src/img/cap5/ToneOfVoice.png)

\vspace{1em}

**Eslogan**

El eslogan de RutaKids, “Seguridad que te acompaña”, expresa de manera clara el propósito de la plataforma: ofrecer protección y acompañamiento continuo a los estudiantes durante sus trayectos escolares. Con un tono cercano y directo, transmite la tranquilidad que sienten padres y colegios al saber que cada viaje está monitoreado.
La palabra “acompaña” destaca el compromiso de la marca con una presencia constante, mientras que “seguridad” refuerza su enfoque en el bienestar infantil.

![Artefacto creado en Figma](src/img/cap5/Eslogan.png)


\newpage

### Web, Mobile and IoT Style Guidelines.

![Artefacto creado en Figma](src/img/cap5/cover2.png)

Esta sección ilustra cómo se aplican los principios generales de estilo dentro de cada interfaz de usuario del sistema RutaKids. A través de componentes visuales como grillas, botones, formularios y más, se establece una experiencia coherente para las aplicaciones web, móviles (padres y choferes) y el dispositivo IoT.
Cada componente documentado cumple una función específica para facilitar la interacción de los distintos tipos de usuarios con el sistema, por lo tanto, su correcta implementación y coherencia visual son claves para garantizar accesibilidad, claridad y eficiencia.
Puedes complementar cada bloque con mockups, capturas de pantalla o ejemplos visuales correspondientes.

1. **Sistema de Grillas (*Grid System*)**

- **Propósito**

  El sistema de grillas es el esqueleto visual que sostiene toda la experiencia de usuario. Su función es establecer un orden lógico y visualmente armónico en la disposición de los elementos en pantalla. 

  Al definir una grilla flexible y adaptativa, garantizamos que los contenidos sean legibles, accesibles y coherentes, independientemente del dispositivo utilizado. 

  En un sistema como *RutaKids* (que abarca interfaces para administración, uso cotidiano en movilidad y visualización de datos IoT) establecer una grilla clara y bien definida es esencial para mantener una experiencia consistente y profesional.

- **Justificación de las decisiones de diseño**

  Para definir las resoluciones y columnas, se tomaron como referencia los siguientes criterios:

  - Estándares de diseño responsive ampliamente adoptados, como los establecidos por *Material Design* y *Bootstrap* (12 columnas para escritorio, reducción progresiva para móviles).

  - Análisis de los dispositivos más utilizados por los distintos perfiles de usuarios de *RutaKids*, obtenido a partir de entrevistas y encuestas realizadas durante la fase de investigación, en las que se indagó sobre el acceso y frecuencia de uso de dispositivos móviles, tablets y computadoras portátiles.

  - Escenarios de uso específicos: 
    - La interfaz del chofer debe ser simple, táctil y sin distracciones.  
    - La del padre debe ser clara, emocional y centrada en el seguimiento.  
    - La web debe soportar administración avanzada.

- **Configuración técnica adoptada**

  A continuación, se muestra una tabla con las configuraciones técnicas definidas para cada tipo de plataforma:

  
\begin{longtable}{|c|c|c|c|c|}
\hline
\textbf{Plataforma} & \textbf{Resolución} & \textbf{Columnas} & \textbf{Gutter (px)} & \textbf{Ancho de columna (px)} \\
\hline
\endfirsthead
\hline
\textbf{Plataforma} & \textbf{Resolución} & \textbf{Columnas} & \textbf{Gutter (px)} & \textbf{Ancho de columna (px)} \\
\hline
\endhead
Web HD & 1440 $\times$ 1024 & 12 & 30 & 65 \\
\hline
Web Estándar & 1024 $\times$ 1024 & 12 & 30 & 50 \\
\hline
Tablet & 768 $\times$ 1024 & 6 & 30 & 88 \\
\hline
Smartphone & 320 $\times$ 1024 & 2 & 30 & 130 \\
\hline
\end{longtable}

Estas configuraciones permiten que el contenido se distribuya de forma eficiente y visualmente armónica en cada contexto de uso.

- **Aplicación por plataforma**

  - **Aplicación Web (Administración):** Permite una estructura modular y detallada para tablas, formularios y paneles de control, maximizando el uso del espacio sin perder claridad.


  - **App Móvil (Padres):** Favorece el uso de componentes tipo card, centrados en legibilidad, jerarquía visual y navegación intuitiva.


  - **App Móvil (Chofer):** Usa una grilla simplificada con botones e información espaciada, optimizada para su uso en movimiento y condiciones de visibilidad variables.


  - **IoT:** Si bien el dispositivo no tiene pantalla, sus eventos se reflejan visualmente en interfaces web y móviles que respetan esta estructura.


![Artefacto creado en Figma](src/img/cap5/Grid.png)

\newpage

2. **Botones y Enlaces (*Buttons & Links*)**

- **Propósito**

  Los botones y enlaces son puntos clave de interacción en cualquier interfaz. Representan las intenciones del usuario: avanzar, retroceder, confirmar, editar o salir. Un buen diseño de botones no solo comunica visualmente su función, sino que también debe ser accesible, jerárquico y reconocible en todos los estados (activo, inactivo, al pasar el cursor, etc.).

  En un sistema como *RutaKids*, que combina usuarios con distintos niveles de familiaridad tecnológica (administradores, padres y choferes), los botones deben ser universales, comprensibles y consistentes en todas las plataformas.

- **Criterios de diseño evaluados para definir los botones**

  Las siguientes decisiones se tomaron con base en análisis de usabilidad, buenas prácticas de diseño y pruebas con usuarios:

  - **Jerarquía visual clara:** Se definieron tres tipos de botones según su prioridad: **Primario** (acción principal), **Secundario** (acciones alternativas) y **Ghost** (acciones pasivas o complementarias).

  - **Tamaños escalables:** *Small*, *Medium* y *Large*, para adaptarse a distintos contextos (tablas, formularios, pantallas táctiles o pantallas reducidas).

  - **Estados de interacción definidos:** Cada botón tiene estados diferenciados para indicar interacción (*hover*, *focus*, *active*, *disabled*). Esto permite al usuario tener retroalimentación visual inmediata.

  - **Compatibilidad responsive:** Los botones deben escalar correctamente según el dispositivo y respetar las reglas del grid.

  - **Tipografía, relleno y espaciado:** Ajustado según proporciones legibles y cómodas al tacto (padding vertical/horizontal según tamaño, tamaño de fuente proporcional).

- **Configuración técnica adoptada**

\begin{longtable}{|c|c|c|c|}
\hline
\textbf{Tamaño} & \textbf{Padding vertical} & \textbf{Padding horizontal} & \textbf{Font size} \\
\hline
\endfirsthead
\hline
\textbf{Tamaño} & \textbf{Padding vertical} & \textbf{Padding horizontal} & \textbf{Font size} \\
\hline
\endhead
Small & 12 px & 24 px & 14 px \\
\hline
Medium & 14 px & 32 px & 16 px \\
\hline
Large & 16 px & 48 px & 18 px \\
\hline
\end{longtable}

- **Tipos de botón:**

  - **Primario:** Alto contraste, usado para llamadas a la acción principales.
  - **Secundario:** Color neutro, para acciones complementarias.
  - **Ghost:** Botón sin fondo, usado para acciones menos frecuentes.

- **Estados definidos y su función en la experiencia del usuario:**

  - **Default:** Estado por defecto del botón. Muestra cómo luce cuando está disponible para ser presionado. Es el estado de reposo, sin interacción.
  - **Hover:** Estado visible cuando el usuario pasa el cursor sobre el botón (en interfaces web). Permite anticipar que el botón es interactivo, mejorando la respuesta cognitiva.
  - **Active:** Estado momentáneo cuando el botón es presionado. Aporta retroalimentación inmediata que confirma al usuario que su acción fue reconocida.
  - **Focus:** Estado que indica que el botón ha sido seleccionado por teclado (por ejemplo, con la tecla “Tab”). Este estado mejora la navegación accesible, especialmente en interfaces web.
  - **Disabled:** Estado en el que el botón está inactivo o no disponible. Suele verse atenuado, sin permitir clic ni interacción. Es útil para guiar al usuario y evitar errores (por ejemplo, cuando aún no ha completado un formulario).

- **Aplicación por plataforma**

  - **Aplicación Web (Administración):**  Los botones se usan en formularios, dashboards, acciones de navegación y operaciones CRUD (crear, editar, eliminar, exportar). El tamaño Medium es el más frecuente por precisión con el mouse. El botón Primario se reserva para acciones importantes (ej. “Guardar”, “Asignar”). El estado “hover” es clave para usuarios acostumbrados a interfaces de escritorio.

  - **App Móvil (Padres):**  Se priorizan botones Large o Medium, con iconos y etiquetas claras. Botones como “Ver estado del hijo” o “Configurar alertas” deben ser de fácil acceso y tener colores familiares. Los estados como “focus” o “active” están optimizados para interfaces táctiles.


  - **App Móvil (Chofer):**  Aquí los botones deben ser grandes, de alto contraste y accesibles con una sola mano. Acciones como “Iniciar ruta” o “Confirmar subida” requieren respuesta visual y táctil inmediata.


![Artefacto creado en Figma](src/img/cap5/Button_Link.png)


\newpage

3. **Campos de Entrada (*Input Fields*)**

- **Propósito**

  Los campos de entrada son puntos de contacto fundamentales entre el usuario y el sistema. A través de ellos se recopila información clave como nombres, correos, rutas, preferencias o comentarios.

  En un ecosistema como *RutaKids* —que involucra padres, choferes y personal administrativo—, el diseño claro y accesible de estos campos garantiza que los datos sean introducidos correctamente y sin fricciones, reduciendo errores y mejorando la experiencia general.

  Un input mal diseñado puede generar dudas, causar errores de validación o entorpecer el flujo natural de interacción. Por eso, cada campo debe comunicar visualmente su propósito, su estado y su contexto.

- **Criterios de diseño evaluados para definir los campos de entrada**

  - **Claridad visual y jerarquía de información:** Se definieron distintos tipos de campos (con etiqueta, con ícono, con texto de ayuda, etc.) que ayudan al usuario a comprender qué se espera introducir en cada caso.

  - **Retroalimentación inmediata:** Se incorporaron estados que comunican si el campo está activo, lleno, con error o deshabilitado. Esto mejora la accesibilidad y reduce la frustración.

  - **Compatibilidad con dispositivos táctiles y de escritorio:** Los tamaños y espacios están pensados para permitir interacción precisa tanto con mouse como con dedo.

  - **Soporte para validaciones visuales:** Colores, iconos y mensajes de ayuda permiten identificar errores de manera no intrusiva.

  - **Uso mínimo e intencional:** Solo se muestran campos cuando son estrictamente necesarios, alineándose con el principio de simplicidad.

- **Tipos de campo definidos**

\begin{longtable}{|c|p{10cm}|}
\hline
\textbf{Tipo} & \textbf{Uso previsto} \\
\hline
\endfirsthead
\hline
\textbf{Tipo} & \textbf{Uso previsto} \\
\hline
\endhead
Texto simple & Entradas generales como nombre, correo, etc. \\
\hline
Ícono a la derecha & Mostrar información adicional o acción contextual (ej. ver contraseña). \\
\hline
Etiquetado & Reforzar el significado del campo mediante texto flotante o persistente. \\
\hline
Texto asistivo & Mostrar mensajes de ayuda, tips o reglas de validación. \\
\hline
Redimensionable & Permitir expansión del campo para textos largos. \\
\hline
\end{longtable}

- **Estados definidos y su propósito**

\begin{longtable}{|c|p{10cm}|}
\hline
\textbf{Estado} & \textbf{Función} \\
\hline
\endfirsthead
\hline
\textbf{Estado} & \textbf{Función} \\
\hline
\endhead
Normal & Campo vacío, sin interacción aún. Indica que puede recibir datos. \\
\hline
Focus & Se activa cuando el usuario hace clic o toca el campo. Ayuda a ubicar visualmente el punto de entrada. \\
\hline
Error (Status color) & Indica que la información ingresada no es válida o falta algo obligatorio. Debe ser visualmente claro y accesible. \\
\hline
Disabled & Campo no editable. Útil para mostrar información fija o condicionar flujos dependientes. \\
\hline
\end{longtable}

- **Aplicación por plataforma**

  - **Aplicación Web (Administradores):** Inputs utilizados para formularios de creación y edición de rutas, estudiantes, conductores y configuraciones. Se hace uso extensivo de validaciones, etiquetas y mensajes de error.

  - **App Móvil (Padres):** Uso limitado. Principalmente para edición de datos personales, cambio de contraseña, contactos de emergencia o configuración de alertas. Deben ser inputs simples, con etiquetas claras y suficiente espacio para el dedo.

  - **App Móvil (Chofer):** Inputs mínimos. Se usan, por ejemplo, para confirmar un código de ruta o agregar una nota. La prioridad es rapidez y legibilidad, evitando el uso innecesario del teclado.

![Artefacto creado en Figma](src/img/cap5/Input_fields.png)

\newpage

4. **Diálogos Emergentes (*Dialogs*)**

- **Propósito**

  Los diálogos emergentes son elementos que interrumpen temporalmente la navegación para llamar la atención sobre una acción importante, confirmar decisiones críticas o mostrar mensajes urgentes.

  En un entorno como *RutaKids*, donde las acciones pueden tener implicaciones de seguridad (ej. registrar a un estudiante en una ruta o cancelar un viaje), los diálogos cumplen un rol clave en la prevención de errores y la toma de decisiones informadas.

  También ayudan a simplificar la interfaz principal, mostrando información relevante solo cuando se necesita.

- **Criterios de diseño evaluados para definir los diálogos**

  - **Claridad y enfoque:** Cada diálogo debe tener un mensaje claro, sin distracciones ni elementos innecesarios. Se recomienda incluir un título, un mensaje breve y acciones principales.

  - **Accesibilidad visual y jerarquía de botones:** Se mantiene un orden lógico en las acciones (ej. botón principal a la derecha), y se da prioridad visual al botón más recomendable.

  - **Compatibilidad responsive:** Los diálogos se adaptan a distintos tamaños de pantalla, desde móviles pequeños hasta pantallas de escritorio, asegurando visibilidad y usabilidad.

  - **Tamaños escalables:** Se definen tamaños de diálogos desde *xs* hasta *xl*, para ajustarse a la cantidad de información que deben mostrar y al tipo de acción.

  - **Retroalimentación inmediata:** Tras una acción (confirmar, cerrar, guardar), se activa una notificación o cambio de estado para validar que la interacción fue procesada.

- **Tamaños disponibles**

\begin{longtable}{|c|p{10cm}|}
\hline
\textbf{Tamaño} & \textbf{Uso recomendado} \\
\hline
\endfirsthead
\hline
\textbf{Tamaño} & \textbf{Uso recomendado} \\
\hline
\endhead
XS & Mensajes de alerta, confirmaciones simples \\
\hline
SM & Acciones rápidas o formularios mínimos \\
\hline
MD & Diálogos estándar con uno o dos campos \\
\hline
LG & Formularios de edición o múltiples acciones \\
\hline
XL & Visualización de datos extensos (ej. historial, detalles de ruta) \\
\hline
\end{longtable}

- **Aplicación por plataforma**

  - **Aplicación Web (Administradores):** Se utilizan para confirmar eliminación de rutas o estudiantes, editar datos, cargar archivos o mostrar advertencias. Deben ser claros y no ocupar más del 80% del *viewport*. Acciones como “Guardar”, “Cancelar” y “Eliminar” deben estar bien jerarquizadas.

  - **App Móvil (Padres):** Se activan al realizar acciones importantes como activar alertas, cambiar notificaciones o salir de la cuenta. Deben ocupar un área contenida de la pantalla, con botones táctiles accesibles y texto de fácil lectura.

  - **App Móvil (Chofer):** Se emplean para confirmar inicio/finalización de ruta o alertas relacionadas al escaneo RFID. El diálogo debe poder resolverse con un solo toque, y ser visible incluso bajo luz solar (contraste alto).

  - **IoT:** El lector RFID no genera diálogos físicos, pero sus eventos pueden activar diálogos automáticos en la interfaz web o móvil conectada, por ejemplo, cuando ocurre un error de escaneo o se detecta un registro duplicado.

![Artefacto creado en Figma](src/img/cap5/Dialog.png)

\newpage
5. **Pestañas de Navegación (*Tabs*)**

- **Propósito**

  Las pestañas son un componente esencial para organizar contenido jerárquico o categorizado dentro de una misma vista. Su función principal es facilitar la navegación entre secciones relacionadas sin recargar la interfaz ni obligar al usuario a cambiar de pantalla.

  En el contexto de *RutaKids*, donde distintas interfaces presentan múltiples vistas (ej. rutas, estudiantes, historial, configuración), el uso de tabs permite acceder rápidamente a cada una sin comprometer claridad ni eficiencia.

- **Criterios de diseño para definir las tabs**

  - **Eficiencia de navegación:** Las tabs mejoran la exploración sin sacrificar contexto. Son ideales para contenido agrupado pero frecuentemente consultado.

  - **Adaptabilidad:** Se contemplaron versiones horizontales y verticales, según la plataforma y espacio disponible.

  - **Escenarios de movilidad:** Se priorizó el diseño táctil en pantallas pequeñas y la visibilidad del estado activo. En móviles, las tabs *scrollables* permiten más opciones sin saturar el ancho.

  - **Visibilidad del estado activo:** Se definió un subrayado visual claro, junto a íconos opcionales para ayudar al reconocimiento.

  - **Patrones consistentes con Angular/Daxa y Material Design:** Se siguen principios establecidos para garantizar cohesión entre componentes, rendimiento y accesibilidad.

- **Variantes disponibles**

\begin{longtable}{|c|c|p{9cm}|}
\hline
\textbf{Orientación} & \textbf{Tipos} & \textbf{Características principales} \\
\hline
\endfirsthead
\hline
\textbf{Orientación} & \textbf{Tipos} & \textbf{Características principales} \\
\hline
\endhead
Horizontal & Standard & 2–4 pestañas visibles, sin scroll. \\
\hline
Horizontal & Scrollable & Permite desplazamiento si hay muchas secciones. \\
\hline
Horizontal & Full Width & Las tabs se ajustan al ancho total del contenedor. \\
\hline
Vertical & Standard & Organización tipo menú lateral, ideal para configuración. \\
\hline
Vertical & Scrollable & Utilizado cuando hay múltiples categorías anidadas. \\
\hline
Vertical & Full Height & Ocupa toda la altura disponible del contenedor. \\
\hline
\end{longtable}

- **Aplicación por plataforma**

  - **Aplicación Web (Administradores):** Usadas principalmente para gestionar múltiples vistas relacionadas, como “Rutas | Estudiantes | Choferes | Configuración”. Se prefiere el modo horizontal en dashboards y vertical en paneles laterales (ej. ajustes).

  - **App Móvil (Padres):** Las pestañas permiten cambiar entre funcionalidades como seguimiento del estudiante, historial, configuración, etc. El uso de scroll horizontal es útil para no saturar pantallas pequeñas. El estado activo debe ser muy visible y los íconos ayudan al reconocimiento.

  - **App Móvil (Chofer):** Secciones como “Mapa de ruta | Lista de alumnos | Alertas” pueden estar distribuidas mediante tabs. Deben ser grandes, con alta legibilidad y acción táctil optimizada.


![Artefacto creado en Figma](src/img/cap5/Tabs.png)

\newpage

6. **Rutas de Navegación (*Breadcrumbs*)**

- **Propósito**

  Las rutas de navegación (o *breadcrumbs*) son un patrón de interfaz clave para mejorar la orientación del usuario dentro de estructuras jerárquicas. Permiten visualizar la ubicación actual dentro del sistema y facilitan el regreso a niveles anteriores sin necesidad de depender de menús laterales o botones de retroceso.

  En plataformas como la aplicación web de *RutaKids*, donde la navegación puede profundizar varios niveles (por ejemplo, Administración > Rutas > Bus 5 > Lista de estudiantes), este patrón aporta claridad estructural y reduce la carga cognitiva del usuario.

- **Criterios de diseño y elección**

  - **Jerarquía visual clara:** Se diseñó una separación entre cada nivel mediante íconos y estilos tipográficos. La ruta completa debe ser legible de un vistazo, con un enfoque especial en el último nivel (ubicación actual).

  - **Adaptabilidad:** En pantallas más pequeñas o rutas muy largas, se contempla el colapso automático de secciones intermedias con puntos suspensivos (“...”) para mantener la limpieza visual.

  - **Consistencia visual:** Los *breadcrumbs* utilizan la misma tipografía y colorimetría que el resto del sistema, integrándose fluidamente en cualquier sección del dashboard o módulo administrativo.

  - **Íconos opcionales:** El uso de íconos contextuales junto al texto (por ejemplo, un ícono de autobús junto a "Bus 5") ayuda a identificar secciones rápidamente y mejora la experiencia para usuarios frecuentes.

  - **Consideraciones de accesibilidad:** Cada *breadcrumb* es un enlace interactivo con soporte para lectores de pantalla y navegación por teclado.

- **Aplicación por plataforma**

\begin{longtable}{|c|p{11cm}|}
\hline
\textbf{Plataforma} & \textbf{Uso y propósito} \\
\hline
\endfirsthead
\hline
\textbf{Plataforma} & \textbf{Uso y propósito} \\
\hline
\endhead
Web App & Esencial en vistas de administración profunda (ej. ver historial de un estudiante en una ruta específica). Mejora el flujo de navegación para gestores y personal del colegio. \\
\hline
App Padres & Su uso es limitado o nulo, ya que la navegación se mantiene más plana e intuitiva. Se prioriza la navegación por *tabs* y *cards*. \\
\hline
App Chofer & No se implementa debido a la simplicidad de navegación y al enfoque de accesos directos. \\
\hline
IoT & No aplica, dado que el lector no posee una interfaz visual con navegación jerárquica. \\
\hline
\end{longtable}

![Artefacto creado en Figma](src/img/cap5/Breadcrumbs.png)

\newpage

7. **Componentes IoT**

- **Propósito**

  Los componentes IoT en *RutaKids* se centran en una interacción sencilla, segura y eficiente entre los estudiantes, el conductor y el sistema digital. Aunque el lector RFID no cuenta con una pantalla táctil, genera respuestas visuales y sonoras que deben interpretarse de forma inmediata, tanto por el chofer como por los sistemas conectados (apps móvil y web).

  Este tipo de componentes debe ser diseñado con base en patrones perceptuales altamente reconocibles (colores, sonidos, vibraciones) y tener una representación digital coherente en las interfaces.

- **Decisiones de diseño y funcionalidad**

  **A. Dispositivo RFID (Interacción física)**

  El lector RFID es un dispositivo autónomo que registra la subida y bajada de los estudiantes al escanear sus pulseras. Su lenguaje visual se compone de:

  - **Luces de estado (LEDs):**
    - **Verde:** Escaneo exitoso (subida/bajada registrada).
    - **Rojo:** Pulsera inválida o error en el escaneo.
    - **Azul:** En espera de escaneo (modo activo, pero sin lectura aún).

  - **Señales sonoras (beeps):**
    - **Beep agudo (1 tono):** Registro exitoso.
    - **Beep grave o doble tono:** Error de lectura o rechazo.

  Estas señales están optimizadas para funcionar incluso en contextos de ruido (por ejemplo, dentro de un bus con estudiantes) y asegurar respuestas inmediatas al conductor.

  **B. Representación digital de la acción del lector**

  Las interfaces de *RutaKids* transforman los datos recibidos desde el dispositivo RFID en información comprensible para padres, choferes y administradores. Se utilizaron componentes como cards, tablas y alertas con códigos de color y jerarquía clara para representar el estado de los escaneos.

- **Aplicación por plataforma**

\begin{longtable}{|c|p{5cm}|p{8cm}|}
\hline
\textbf{Plataforma} & \textbf{Elemento diseñado} & \textbf{Propósito} \\
\hline
\endfirsthead
\hline
\textbf{Plataforma} & \textbf{Elemento diseñado} & \textbf{Propósito} \\
\hline
\endhead
App Chofer & Visualización de mapa interactivo con paradas programadas y ruta en tiempo real & Facilita la navegación del chofer mostrando la ubicación actual del bus, las casas de los estudiantes (paradas) y el destino final (colegio), permitiendo un recorrido ordenado y monitoreado. \\
\hline
App Padres & Card por hijo con estado actual (ej. “En camino”), hora de escaneo y notificación & Ofrece tranquilidad al informar de manera clara y en tiempo real. \\
\hline
Web App & Tabla detallada con registros de escaneo por ruta, fecha, estudiante y estado & Administra el historial de viajes, permite validar reportes y detectar inconsistencias. \\
\hline
IoT (lector) & Luces LED + sonidos (interfaz física) & Permite retroalimentación inmediata para el chofer, sin distracciones. \\
\hline
\end{longtable}

\newpage

## Information Architecture.

![Artefacto creado en Canva](src/img/cap5/InformationArchitecture.png)

La arquitectura de la información (AI) se refiere al proceso de estructuración y categorización del contenido digital con el fin de facilitar su localización y comprensión por parte de los usuarios. Este aspecto es esencial para asegurar una experiencia fluida, especialmente en entornos digitales como aplicaciones móviles, donde la claridad en la organización puede determinar el éxito de la interacción usuario-sistema.


\begin{quote}
De acuerdo con Lin y Zarro (2024), una arquitectura de información bien diseñada “brinda estructura a la experiencia del usuario y actúa como una guía cognitiva que facilita la navegación, reduce la incertidumbre y mejora la eficiencia de uso en sistemas digitales complejos.
\end{quote}

\vspace{1em}

En el desarrollo de RutaKids, se adoptó una estructura centrada en los principales perfiles de usuarios: padres de familia, conductores y gestores de transporte escolar. La intención fue lograr una jerarquía de información comprensible, accesible y coherente que soporte la visualización en tiempo real, la administración de rutas y estudiantes, y la comunicación segura dentro de la aplicación.

A continuación se presentan los mapas generales de arquitectura de información correspondientes a cada tipo de usuario:

**Arquitectura de Información – App Móvil para Padres**

![Artefacto creado en Figma](src/img/cap5/AppPadres.png)

**Arquitectura de Información – App Móvil para Conductores**

![Artefacto creado en Figma](src/img/cap5/AppConductores.png)

**Arquitectura de Información – Plataforma Web para Administradores**

![Artefacto creado en Figma](src/img/cap5/AppWeb.png)


Las secciones siguientes profundizan en los sistemas implementados para organización, etiquetado, navegación y búsqueda, así como en los elementos de SEO (Search Engine Optimization) y ASO (App Store Optimization) que fortalecen la visibilidad del producto.

\newpage

### Organization Systems.

- **Propósito**

  La arquitectura organizativa de un producto digital permite estructurar la información de forma que los usuarios accedan rápida y eficientemente a los contenidos que necesitan. 

  Según Morville y Rosenfeld (2006), “los sistemas de organización son esenciales para transformar el caos en claridad, facilitando que los usuarios comprendan la lógica detrás del contenido digital”. 

  En el caso de *RutaKids*, se han diseñado diversos sistemas de organización visual y estructural adaptados tanto a padres como a administradores educativos.

- **Organización para padres de familia (App móvil)**

  La aplicación móvil muestra la información más relevante sobre el estado de sus hijos y el transporte escolar. La información sigue un modelo jerárquico en su interfaz principal y secuencial en el monitoreo de rutas.

\begin{longtable}{|p{3cm}|p{4.5cm}|p{3.5cm}|p{5cm}|}
\hline
\textbf{Tópico} & \textbf{Sistema de Organización Visual} & \textbf{Categorización Aplicada} & \textbf{Descripción} \\
\hline
\endfirsthead
\hline
\textbf{Tópico} & \textbf{Sistema de Organización Visual} & \textbf{Categorización Aplicada} & \textbf{Descripción} \\
\hline
\endhead
Estado del recorrido & Jerárquico visual & Cronológica & Se presenta primero el nombre del conductor, estado, hora estimada y destino. \\
\hline
Línea de tiempo del viaje & Secuencial (paso a paso) & Cronológica & Refleja el progreso del viaje con puntos y estados temporales en orden. \\
\hline
Historial de viajes & Lista jerárquica ordenada & Cronológica & Permite revisar viajes anteriores organizados por fecha. \\
\hline
Hijos registrados & Jerárquico visual & Por audiencia (por cada hijo) & Cada hijo tiene su propio conjunto de datos visibles en tiempo real. \\
\hline
\end{longtable}

- **Organización para administradores educativos (Plataforma web)**

  La plataforma web está orientada a la administración y seguimiento operativo. Utiliza una estructura modular con categorización por tópicos y por audiencia (vehículos, estudiantes, rutas, conductores).

\begin{longtable}{|p{3cm}|p{3.5cm}|p{3.5cm}|p{4.5cm}|}
\hline
\textbf{Tópico} & \textbf{Sistema de Organización Visual} & \textbf{Categorización Aplicada} & \textbf{Descripción} \\
\hline
\endfirsthead
\hline
\textbf{Tópico} & \textbf{Sistema de Organización Visual} & \textbf{Categorización Aplicada} & \textbf{Descripción} \\
\hline
\endhead
Dashboard & Jerárquico (panel con KPIs) & Por tópico & Muestra métricas clave: rutas activas, incidencias, temperatura, etc. \\
\hline
Gestión de estudiantes & Visual matricial & Por tópico y audiencia (grado/edad) & Clasificación de alumnos por grados escolares y grupos etarios. \\
\hline
Gestión de vehículos y rutas & Jerárquico + secuencial (módulo por pasos) & Por tópico (vehículos, zonas, rutas) & Panel para registro, edición y asignación de unidades a rutas. \\
\hline
Monitoreo en tiempo real & Jerárquico + secuencial & Cronológica y geoespacial & Muestra mapa con rutas, ubicación, velocidad, y eventos críticos. \\
\hline
Reportes e incidencias & Modular & Cronológica / por evento & Acceso a reportes por fecha, tipo de evento (desvíos, alertas térmicas). \\
\hline
\end{longtable}


- **Organización en la Landing Page (Sitio Estático)**

  La landing page está diseñada para atraer y guiar a nuevos usuarios. Utiliza una estructura secuencial, pensada para recorrer la información desde el valor de la app hasta las secciones específicas según audiencia.

\begin{longtable}{|p{3cm}|p{4cm}|p{3.5cm}|p{5cm}|}
\hline
\textbf{Tópico} & \textbf{Organización Visual} & \textbf{Categorización Aplicada} & \textbf{Descripción} \\
\hline
\endfirsthead
\hline
\textbf{Tópico} & \textbf{Organización Visual} & \textbf{Categorización Aplicada} & \textbf{Descripción} \\
\hline
\endhead
Menú principal & Jerárquico visual horizontal & Por tópicos & Inicio, Beneficios, Características, Padres, Colegios, Contáctanos. \\
\hline
Flujo de contenido & Secuencial (scroll vertical guiado) & Por audiencia & Explica beneficios para padres, luego para colegios. \\
\hline
CTA (Call to Action) & Jerárquico visual final & Ninguna & Botones de descarga o contacto resaltados al final. \\
\hline
\end{longtable}

Esta organización garantiza que tanto padres como administradores puedan interactuar de forma clara, eficiente y segura con la plataforma, reduciendo fricción y mejorando la toma de decisiones y la supervisión del servicio de transporte escolar.


\newpage

### Labeling Systems.

6. **Sistemas de Etiquetado**

- **Propósito**

  Los sistemas de etiquetado son fundamentales para la claridad del contenido y la navegación en cualquier producto digital. Una correcta nomenclatura ayuda a los usuarios a comprender de inmediato qué acciones pueden realizar, qué información están observando y qué pasos seguir.

  En *RutaKids*, las etiquetas han sido desarrolladas con un enfoque en simplicidad, consistencia y significado contextual, garantizando una experiencia clara para los distintos tipos de usuarios: padres, administradores y conductores.

- **App móvil – Padres de familia**

\begin{longtable}{|p{4cm}|p{10.5cm}|}
\hline
\textbf{Tópico} & \textbf{Definición} \\
\hline
\endfirsthead
\hline
\textbf{Tópico} & \textbf{Definición} \\
\hline
\endhead
Inicio & Etiqueta utilizada para acceder a la pantalla principal, donde se presenta un resumen del estado del recorrido escolar en tiempo real. \\
\hline
Monitoreo & Abre el mapa con la ubicación actual del vehículo asignado, permitiendo ver el avance de la ruta y el estado del transporte del estudiante. \\
\hline
Historial & Muestra los viajes anteriores del estudiante, organizados por fecha, incluyendo hora de salida, llegada y eventos registrados. \\
\hline
Cuenta & Acceso a la configuración de perfil del padre, donde puede editar datos personales, activar o desactivar notificaciones y cerrar sesión. \\
\hline
\end{longtable}

- **App móvil – Conductores**

\begin{longtable}{|p{4cm}|p{10.5cm}|}
\hline
\textbf{Tópico} & \textbf{Definición} \\
\hline
\endfirsthead
\hline
\textbf{Tópico} & \textbf{Definición} \\
\hline
\endhead
Iniciar ruta & Botón que activa el inicio oficial del recorrido asignado; al presionarlo, se activa la navegación GPS hacia el primer punto de recojo. \\
\hline
Ver en GPS & Redirección automática al sistema de navegación (Google Maps, Waze, etc.) con la ruta preestablecida desde la plataforma. \\
\hline
Finalizar ruta & Permite al conductor cerrar el recorrido una vez completado, registrando hora de llegada y finalizando el monitoreo en tiempo real. \\
\hline
\end{longtable}

\newpage

### SEO Tags and Meta Tags


- **Propósito**

  En la aplicación *RutaKids*, los *SEO Tags* y *Meta Tags* juegan un rol crucial para garantizar la visibilidad del producto tanto en motores de búsqueda como en tiendas de aplicaciones móviles. 

  Aunque el producto incluye una plataforma web y una aplicación móvil, la *landing page* cumple un rol estratégico al actuar como primer punto de contacto para nuevos usuarios, por lo que ha sido optimizada mediante el uso de etiquetas específicas.


- **SEO Tags**

  Los SEO Tags permiten mejorar el posicionamiento de la landing page de *RutaKids* en buscadores como Google, facilitando que padres y colegios interesados encuentren rápidamente el producto. A continuación se muestran algunos ejemplos aplicados:

  - **Title Tag**  
    Especifica el título visible en los resultados de búsqueda.

    ```html
    <title>RutaKids - Seguridad y Monitoreo Escolar en Tiempo Real</title>
    ```

  - **Meta Description**  
    Describe brevemente el contenido de la página.

    ```html
    <meta name="description" content="RutaKids es una plataforma de movilidad escolar con pulseras RFID. Permite a los padres monitorear en tiempo real los recorridos escolares de sus hijos y a los colegios gestionar rutas de forma eficiente." />
    ```

  - **Header Tags**  
    Estructuran jerárquicamente el contenido.

    ```html
    <h1>Movilidad Escolar Inteligente</h1>
    <h2>Monitorea a tus hijos en tiempo real</h2>
    <h3>Gestiona flotas escolares con tecnología RFID</h3>
    ```


- **Meta Tags**

  Los Meta Tags proporcionan información técnica a navegadores y motores de búsqueda, mejorando la experiencia del usuario y el SEO técnico. Algunos utilizados en *RutaKids* son:

  - **Charset Meta Tag**

    ```html
    <meta charset="UTF-8">
    ```

  - **Viewport Meta Tag**

    ```html
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    ```

  - **Robots Meta Tag**

    ```html
    <meta name="robots" content="index, follow">
    ```

  - **Canonical Tag**

    ```html
    <link rel="canonical" href="https://rutakids.com">
    ```


- **Landing Page SEO Tags (para la aplicación móvil)**

  Además de las etiquetas estándar, se han definido etiquetas específicas para promover la aplicación móvil directamente desde la landing page:

  ```html
  <title>RutaKids | Transporte Escolar Seguro y Conectado</title>
  <meta name="description" content="RutaKids permite a padres monitorear a sus hijos durante el transporte escolar mediante pulseras RFID. Disponible para iOS y Android.">
  <meta name="keywords" content="app transporte escolar, seguridad infantil, GPS escolar, pulseras RFID, monitoreo niños">
  <meta name="author" content="LlantaTech">
  <link rel="canonical" href="https://rutakids.com/">
    ```

- **App Store Optimization (ASO)**

  Para aumentar la visibilidad de la aplicación en tiendas como Google Play o App Store, RutaKids aplica estrategias de ASO (App Store Optimization) que incluyen título, descripción, palabras clave y categorías.


\begin{longtable}{|p{4cm}|p{10.5cm}|}
\hline
\textbf{Elemento} & \textbf{Valor propuesto} \\
\hline
\endfirsthead
\hline
\textbf{Elemento} & \textbf{Valor propuesto} \\
\hline
\endhead
App Title & RutaKids: Monitoreo Escolar en Tiempo Real \\
\hline
App Subtitle & Seguridad escolar con tecnología RFID \\
\hline
App Description & Con RutaKids, los padres pueden seguir en tiempo real los recorridos escolares de sus hijos, recibir alertas, revisar historial de viajes y confiar en un sistema seguro con tecnología RFID. Ideal para colegios modernos y comprometidos con la seguridad. \\
\hline
Keywords & transporte escolar, app para padres, seguridad infantil, RFID, monitoreo niños \\
\hline
Developer & LlantaTech \\
\hline
Categoría & Educación / Familias \\
\hline
URL descarga Android & \url{https://play.google.com/store/apps/details?id=com.rutakids} \\
\hline
URL descarga iOS & \url{https://apps.apple.com/app/rutakids/id123456789} \\
\hline
\end{longtable}


El uso estratégico de SEO Tags y Meta Tags en RutaKids no solo mejora la visibilidad en buscadores y redes sociales, sino que también facilita la experiencia del usuario desde el primer contacto con la plataforma. Además, las etiquetas ASO aseguran un buen posicionamiento en las tiendas de aplicaciones, promoviendo así la descarga y uso efectivo del producto.



### Searching Systems.


- **Propósito**

  Los sistemas de búsqueda en productos digitales permiten al usuario navegar grandes volúmenes de información de forma efectiva, evitando pérdida de tiempo y frustración.

  En *RutaKids*, la búsqueda activa está implementada únicamente en la plataforma web de administradores, ya que la aplicación móvil está diseñada para mostrar información personalizada y filtrada automáticamente para los padres de familia.



- **Filtros y herramientas de búsqueda en la Web App**

\begin{longtable}{|p{5cm}|p{9.5cm}|}
\hline
\textbf{Filtro / Función} & \textbf{Definición} \\
\hline
\endfirsthead
\hline
\textbf{Filtro / Función} & \textbf{Definición} \\
\hline
\endhead
Nombre del estudiante & Permite encontrar a un estudiante específico mediante la entrada parcial o completa de su nombre. \\
\hline
Código de pulsera RFID & Filtra directamente por el identificador asignado al estudiante. \\
\hline
Grado escolar / Edad & Muestra únicamente a estudiantes de un grado o grupo etario específico. \\
\hline
Ruta asignada & Filtra a los estudiantes según el recorrido o zona a la que pertenecen. \\
\hline
Nombre del conductor & Permite identificar qué conductor está asignado a una ruta o grupo de estudiantes. \\
\hline
Fecha / rango de fechas & Busca viajes, alertas o registros según el día o periodo seleccionado. \\
\hline
Tipo de alerta & Clasifica las notificaciones (ej. alerta de desvío, abordaje no detectado, temperatura fuera del umbral). \\
\hline
Estado del recorrido & Muestra únicamente registros en estado específico: “en tránsito”, “finalizado”, “no iniciado”. \\
\hline
Búsqueda combinada avanzada & Combina múltiples filtros (ej. por nombre + ruta + fecha) para obtener resultados más precisos. \\
\hline
\end{longtable}



- **Diseño de resultados y experiencia de búsqueda**

  - Resultados ordenados alfabéticamente o por fecha según el módulo.
  - Interfaz con autocompletado en campos de búsqueda (como nombres o placas).
  - Posibilidad de acceder al detalle directamente desde los resultados.
  - Visualización clara en tarjetas o tablas, según el tipo de información.



- **App móvil – Padres de familia**

  En la app móvil, no se requiere una herramienta de búsqueda, ya que toda la información está pre-filtrada por el sistema. Cada padre solo visualiza la información correspondiente a sus hijos y sus viajes.

\begin{longtable}{|p{5cm}|p{9.5cm}|}
\hline
\textbf{Característica} & \textbf{Función} \\
\hline
\endfirsthead
\hline
\textbf{Característica} & \textbf{Función} \\
\hline
\endhead
Vista filtrada por estudiante & Si hay más de un hijo, el sistema separa la información por cada uno. \\
\hline
Historial por fecha & Organiza automáticamente los viajes anteriores por orden cronológico. \\
\hline
Alertas personalizadas & Solo muestra notificaciones relevantes al estudiante registrado. \\
\hline
\end{longtable}



Esta combinación de sistemas asegura que tanto administradores como padres puedan encontrar información crítica sin esfuerzo, optimizando el uso del sistema y mejorando la experiencia general.


\newpage

### Navigation Systems.

- **Propósito**

  Los sistemas de navegación son el conjunto de elementos y patrones que permiten a los usuarios moverse a través del contenido y funcionalidades de una interfaz. Una buena navegación no solo facilita el desplazamiento, sino que también guía, orienta y reduce el esfuerzo cognitivo.

  Como afirman Garrett (2011), “la navegación efectiva proporciona al usuario una sensación de lugar, dirección y control dentro de un producto digital”.

  En *RutaKids*, se implementan sistemas de navegación adaptados a cada tipo de usuario: padres (app móvil), conductores (app móvil simplificada) y administradores escolares (plataforma web). En cada caso, la navegación fue diseñada para ajustarse al nivel de interacción y al contexto de uso.



- **App móvil – Padres de familia**

\begin{longtable}{|p{5cm}|p{9.5cm}|}
\hline
\textbf{Elemento de navegación} & \textbf{Descripción} \\
\hline
\endfirsthead
\hline
\textbf{Elemento de navegación} & \textbf{Descripción} \\
\hline
\endhead
Menú inferior (tab bar) & Contiene accesos directos a: Inicio, Monitoreo, Historial y Cuenta. Visible en toda la app. \\
\hline
Navegación jerárquica & Cada sección permite acceder a pantallas secundarias (por ejemplo, ver detalle del historial). \\
\hline
Retroalimentación visual & Íconos activos con cambio de color al seleccionarse, y notificaciones visibles (campana). \\
\hline
Navegación simplificada & Solo se muestran las funciones relevantes al rol del padre, evitando sobrecarga de opciones. \\
\hline
\end{longtable}



- **App móvil – Conductores**

\begin{longtable}{|p{5cm}|p{9.5cm}|}
\hline
\textbf{Elemento de navegación} & \textbf{Descripción} \\
\hline
\endfirsthead
\hline
\textbf{Elemento de navegación} & \textbf{Descripción} \\
\hline
\endhead
Interfaz de acción directa & La navegación está basada en 2 o 3 botones: Iniciar Ruta, Ver GPS, Finalizar Ruta. \\
\hline
Redirección externa (GPS) & Al iniciar ruta, se abre la app de navegación externa (Google Maps o Waze) automáticamente. \\
\hline
Diseño de una sola vista & La app evita navegación compleja; el conductor solo necesita cumplir un flujo puntual. \\
\hline
\end{longtable}



- **Plataforma Web – Administradores**

\begin{longtable}{|p{5cm}|p{9.5cm}|}
\hline
\textbf{Elemento de navegación} & \textbf{Descripción} \\
\hline
\endfirsthead
\hline
\textbf{Elemento de navegación} & \textbf{Descripción} \\
\hline
\endhead
Menú lateral persistente & Acceso directo a módulos: Dashboard, Estudiantes, Rutas, Monitoreo, Notificaciones, Configuración, etc. \\
\hline
Submenús plegables & Algunas secciones contienen subcategorías, como niveles escolares dentro de "Estudiantes". \\
\hline
Navegación matricial & Vista tipo grid para elementos como grados escolares o rutas disponibles. \\
\hline
Navegación contextual & Acciones como “Editar” o “Asignar ruta” aparecen directamente en el contexto de la información. \\
\hline
Accesos rápidos & Acciones frecuentes resaltadas visualmente (botones flotantes o en tarjetas). \\
\hline
\end{longtable}


\newpage

## Landing Page UI Design.

Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.

\newpage

### Landing Page Wireframe.

Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.

\newpage

### Landing Page Mock-up.

Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.

\newpage

## Applications UX/UI Design.

Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.

\newpage

### Applications Wireframes.

Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.

\newpage

### Applications Wireflow Diagrams.

Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.

\newpage

### Applications Mock-ups.

Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.

\newpage

### Applications User Flow Diagrams.

Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.

\newpage

## Applications Prototyping.

Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.
