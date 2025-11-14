---
id: entornos-de-desarrollo
sidebar_position: 2
title: Entornos de Desarrollo
toc_max_heading_level: 3
---

## UD1.- Desarrollo de software

### 1.- Software y programa. Tipos de software.

El software es el conjunto de programas informáticos que actúan sobre el hardware para ejecutar lo que el usuario desee. Según su **función**, se distinguen tres **tipos de software**: 

|Software|¿Qué es?|
| ------ | ------ |
| De sistema | Software base que ha de estar instalado y configurado en nuestro ordenador para que las aplicaciones puedan ejecutarse y funcionar (sistema operativo) |
| De programación | Conjunto de herramientas que nos permiten desarrollar programas informáticos (editores de texto/código, compiladores, intérpretes, IDEs) |
| Aplicaciones | Conjunto de programas que tienen una finalidad más o menos concreta (procesadores de textos, las hojas de cálculo, videojuegos) |

Un **programa** es un conjunto de instrucciones escritas en un lenguaje de programación, que indican a la máquina que operaciones realizar sobre unos determinados datos.

### 2.- Relación Hardware - Software

La relación entre **hardware** (dispositivos físicos) y **software** (programas) en un ordenador es **inseparable**: el software se ejecuta sobre el hardware, y el hardware necesita el software para operar. La arquitectura fundamental de los ordenadores modernos se basa en los conceptos establecidos por **John Von Neumann** en 1946.

**Desde el punto de vista del sistema operativo**

El **sistema operativo** actúa como el **intermediario** esencial entre el hardware y las aplicaciones. Es el encargado de **coordinar el hardware** durante el funcionamiento del ordenador. Controla la asignación de **recursos hardware** que necesitan las aplicaciones para ejecutarse, y lo hace de forma "oculta" para las aplicaciones y el usuario.

**Desde el punto de vista de las aplicaciones**

Una **aplicación** es un conjunto de programas escritos en algún **lenguaje de programación**. El **hardware**, sin embargo, solo puede interpretar **señales eléctricas** que se traducen en **secuencias de 0 y 1**. Para que el ordenador pueda ejecutar el código de la aplicación, es necesario un **proceso de traducción** del lenguaje de programación a código binario. 

### 3.- Fases a seguir en el desarrollo del software

El **desarrollo de software** es el proceso completo que abarca desde la concepción inicial de una idea hasta que el programa está implementado y funcionando en el ordenador.

Para construir software fiable y de calidad, es obligatorio seguir una serie de **etapas o pasos**. Cumplir rigurosamente con estas fases garantiza que los programas sean eficientes, seguros y que satisfagan las necesidades de los usuarios finales.

Es crucial **dedicar los recursos necesarios a las primeras etapas** (análisis y diseño). Si se avanza a las fases finales con errores en el diseño o análisis, estos se propagarán por todo el proyecto, resultando en un producto final de mala calidad.

**Fases del desarrollo del software**

|Fase|Tareas|
|---|---|
|Análisis| Analizar las necesidades del sistema y consensuar los requisitos funcionales y no funcionales (ANÁLISIS DE REQUISITOS), sirviendo como base inamovible para el resto del proyecto |
|Diseño| Dividir el sistema en partes, determinar su función, crear los algoritmos necesarios y elegir las herramientas de codificación |
|Codificación y compilación| Escribir e implementar el código fuente y compilarlo para obtener los ficheros en código máquina |
|Pruebas| Enlazar los elementos programados, comprobar que el sistema funciona correctamente y que cumple todos los requisitos antes de ser entregado |
|Explotación| Instalar, configurar y probar la aplicación en los equipos del cliente (entorno de preproducción o pruebas) antes de pasar el producto a producción |
|Mantenimiento| Contacto con el cliente para actualizar y modificar la aplicación, generando nuevas versiones del producto a futuro |
|Documentación| Tarea continua a lo largo de todo el ciclo de vida del proyecto, donde se registra y se guarda toda la información relevante de cada etapa |

#### 3.1.- Análisis

La fase de **análisis** es la **primera y más importante** del proyecto, ya que su éxito depende de la calidad y el detalle con que se especifiquen los requisitos. Es la fase más **complicada** porque no está automatizada y recae en gran medida en la habilidad del analista.

El objetivo principal es definir las necesidades del sistema. Es crucial mantener una **buena comunicación** con el cliente para asegurar que la aplicación cumpla sus expectativas.

De esta fase se obtienen **dos documentos** clave:

1. **Documento de especificación de requisitos software (ERS)**
    - Detalla exhaustivamente lo que el sistema debe hacer.
    - Incluye la planificación de reuniones, objetivos prioritarios y la gestión de contingencias.
    - **Requisitos funcionales:** Describen las **funciones** que realizará la aplicación, incluyendo la respuesta a todas las entradas y el comportamiento ante situaciones inesperadas (ej., leer códigos de barras, detallar facturas, controlar *stock*).
    - **Requisitos no funcionales:** Describen **cómo** funcionará la aplicación, incluyendo criterios de calidad, rendimiento y cumplimiento (ej., tiempos de respuesta, color del hardware, cumplimiento de normativas o certificaciones, facilidad de uso de la interfaz).

2. **Documento de diseño de arquitectura**
    - Describe la **estructura relacional global** del sistema.
    - Especifica lo que debe hacer cada una de sus partes y cómo se conectan.
    - Aunque es una salida del análisis, a veces se genera como la primera tarea de la fase de diseño. 

#### 3.2.- Diseño

La fase de **diseño** se aborda después de que el análisis ha definido los requisitos del sistema (el "qué hacer"). Su objetivo es determinar **cómo** se implementará la solución, creando un **modelo funcional-estructural** de los requisitos.

En esta fase se planifica la estructura del *software* y se toman decisiones técnicas fundamentales:

- **Estructuración:** se **divide el sistema en partes** y se definen las **relaciones** entre ellas.
- **Funcionalidad por parte:** se decide la función exacta que tendrá cada una de esas partes o módulos.
- **Decisiones técnicas:** se seleccionan herramientas y tecnologías clave, tales como:
    - Definición de las **entidades y relaciones** de las bases de datos.
    - Selección del **lenguaje de programación**.
    - Selección del **sistema gestor de base de datos**.

*(Nota: Aunque la arquitectura a veces se trata en el análisis, a menudo se considera una tarea inicial del diseño).*

De la fase de diseño se obtienen dos documentos principales:

1. **Documento de diseño del software:** recoge toda la información sobre las decisiones estructurales y técnicas mencionadas.
2. **Plan de pruebas:** define la estrategia general para la fase de pruebas posterior, sin entrar aún en los detalles de las mismas.

Las organizaciones que invierten más en sus diseños suelen ser las que experimentan un mayor crecimiento. 

Aquí tienes el resumen de las fases de codificación y compilación del desarrollo de software:

#### 3.3. Codificación

La **codificación** es la fase de **programación** donde se toma la información detallada del análisis y el diseño y se traduce a un **código fuente** (instrucciones paso a paso) utilizando un **lenguaje de programación** elegido.

Esta tarea es realizada por el **programador** y debe cumplir de forma exhaustiva con todos los requisitos definidos en las fases anteriores. 

Las características deseables de un buen código fuente son:

1. **Modularidad:** Que esté dividido en trozos pequeños.
2. **Corrección:** Que haga exactamente lo que se le pide.
3. **Fácil de leer:** Para facilitar su desarrollo y mantenimiento futuro.
4. **Eficiencia:** Que utilice bien los recursos del sistema.
5. **Portabilidad:** Que pueda ser implementado en cualquier equipo.

#### 3.4. Compilación

El **código fuente** (escrito en un lenguaje de alto nivel) no es directamente ejecutable por la máquina, por lo que debe ser **traducido** a **lenguaje máquina** (código binario) para que el ordenador lo entienda y ejecute.

El proceso de traducción de código fuente a código ejecutable se realiza de dos formas:

1. **Compilación:**
    - La traducción se realiza sobre **todo el código fuente en un solo paso**.
    - Se crea un **código objeto** intermedio que luego debe ser enlazado.
    - El *software* encargado es el **compilador**.

2. **Interpretación:**
    - La traducción del código fuente se realiza **línea a línea** y se ejecuta **simultáneamente**.
    - **No existe código objeto intermedio**.
    - El *software* encargado es el **intérprete**.
    - Aunque el proceso es más lento que la compilación, es recomendable para programadores inexpertos, ya que ofrece una detección de errores más detallada.


#### 3.5.- Pruebas

Una vez que se obtiene el *software*, la fase de **pruebas** es imprescindible para asegurar la **validación y verificación** del producto construido. Generalmente, las pruebas se realizan utilizando un **conjunto seleccionado y predefinido de datos de prueba**, que incluyen datos límite a los que la aplicación es sometida. 

Se distinguen dos tipos de pruebas:

1. **Pruebas unitarias**
    - Consisten en probar, una a una, las **diferentes partes o módulos** del *software* de manera **separada e independiente**.
    - Como resultado, se genera un **documento de procedimiento de pruebas** que compara los resultados obtenidos con los **resultados esperados**, previamente definidos en el plan de la fase de diseño.
    - Un ejemplo de entorno de pruebas unitarias para Java es **JUnit**.

2. **Pruebas de integración**
    - Se realizan después de que cada programa individual ha pasado sus pruebas unitarias.
    - Consisten en la **puesta en común** de todos los programas desarrollados para comprobar que funcionan correctamente **en conjunto** como un sistema completo.
    - Al igual que en las unitarias, se genera un **documento de procedimiento de pruebas de integración** para comparar los resultados obtenidos con los esperados.

#### 3.6.- Explotación

La **explotación** es la fase en la que el *software*, una vez verificado y documentado, se entrega a los usuarios finales. Aunque algunos autores la agrupan con el mantenimiento, se diferencia por el momento en que se realiza.

La explotación abarca tres pasos clave:

1. **Instalación**
    - Los programas se transfieren al equipo final del cliente.
    - Es recomendable que los futuros usuarios estén presentes para entender el proceso.
    - En este momento se suelen realizar las **Beta Test**, que son las pruebas finales que se llevan a cabo directamente en los equipos del cliente y con sus cargas de trabajo habituales.

2. **Configuración**
    - Se asignan los **parámetros de funcionamiento normal** de la empresa para que la aplicación sea operativa.
    - La configuración puede ser realizada por los fabricantes (lo más aconsejable para *software* a medida), por los propios usuarios (siguiendo una guía), o programarse para que sea **automática** tras la instalación.

3. **Producción normal**
    - Una vez instalado y configurado, el *software* pasa a manos de los usuarios finales y comienza el **funcionamiento** o la **explotación** normal de la aplicación. 

Es fundamental que todo esté completamente preparado antes de este punto, ya que la presentación al cliente es el **momento crítico** del proyecto.

#### 3.7.- Mantenimiento

La etapa de **mantenimiento** es la **más larga** de todo el ciclo de vida del *software* y se define como el proceso de **control, mejora y optimización** del producto. Es necesario porque el *software* debe actualizarse y evolucionar para adaptarse a las mejoras del *hardware* y afrontar nuevas situaciones o corregir errores que siempre surgen.

Por esta razón, se pacta un servicio de mantenimiento con el cliente, el cual conlleva un coste temporal y económico. 

Los cambios que hacen necesario el mantenimiento del *software* se clasifican en cuatro tipos:

- **Perfectivos:** Enfocados en **mejorar la funcionalidad** interna y la eficiencia del *software*.
- **Evolutivos:** Implican la adición de **nuevos requisitos** o funcionalidades propuestas por el cliente (haciendo evolucionar el producto).
- **Adaptativos:** Modificaciones o actualizaciones necesarias para **adaptarse a cambios externos**, como nuevas tendencias del mercado, nuevos componentes de *hardware* o nuevas condiciones de organismos reguladores.
- **Correctivos:** Necesarios para **resolver y corregir errores** o defectos que hayan sido detectados en el *software*.

#### 3.8.- Documentación

La **documentación** no debe considerarse una etapa separada, sino una **labor constante** que acompaña a todas las fases del ciclo de vida del *software*. Es crucial para proporcionar información a los usuarios, permitir futuras revisiones, y facilitar el paso claro y definido de una etapa a otra. También es imprescindible para la **reutilización** de módulos de código en otras aplicaciones.

La documentación se clasifica según su destinatario final:

| Tipo de guía | Destinatario | Aspectos reflejados | Objetivo |
| --- | --- | --- | --- |
| Técnicas | Personal técnico (analistas y programadores) | Diseño, codificación de programas y pruebas realizadas | Facilitar el desarrollo, realizar correcciones y permitir el **mantenimiento futuro** |
| De uso | Usuarios finales (clientes) | Descripción de la funcionalidad, forma de ejecución, ejemplos de uso, requisitos de *software* y solución de problemas | Dar a los usuarios toda la información necesaria para **utilizar la aplicación** |
| De instalación | Personal informático responsable de la instalación | Puesta en marcha, explotación y seguridad del sistema | Garantizar que la **implantación** de la aplicación se realice de forma segura, confiable y precisa |

El **fracaso en grandes proyectos de *software*** es notable: solo el **26% tiene éxito**, mientras que la mayoría (74%) o bien requiere modificaciones drásticas o fracasa por completo. La causa principal es la **mala planificación y gestión** de las etapas iniciales, ya que los errores cometidos al principio se **propagan en cascada** al resto del desarrollo. 

### 4.- Ciclos de vida del software

El **ciclo de vida del *software*** es el conjunto de fases, procesos y actividades requeridas para planificar, desarrollar, probar, integrar, explotar y mantener un producto *software*.

La necesidad de un ciclo de vida surgió debido a los inconvenientes del desarrollo individualizado y sin planificación, tales como: desconocimiento del progreso y calidad, falta de flexibilidad ante cambios, dependencia del programador y riesgo de no cumplir con las necesidades del cliente.

Implementar un ciclo de vida aporta valor y calidad al producto final, ofreciendo varias ventajas:

- **Detección temprana de defectos** mediante controles sistemáticos.
- **Control de costes y plazos** gracias al seguimiento del proceso.
- **Documentación formal y estandarizada** que facilita la comunicación.
- Mayor **visibilidad y control** para la gestión del proyecto.
- **Guía** clara para el personal de desarrollo, minimizando la necesidad de rehacer trabajo.

Los modelos de ciclos de vida más conocidos son:

1. **Modelo en cascada**

Es el modelo **clásico**, pero es casi **utópico** y solo aplicable a **pequeños desarrollos**.
    - Las etapas se suceden **sin retorno posible**.
    - Cualquier error en fases iniciales es **insubsanable** más adelante.
    - Requiere conocimiento **absoluto y previo** de todos los requerimientos.
    - No permite modificaciones ni actualizaciones una vez iniciado.

2. **Modelo en cascada con realimentación**

Es uno de los modelos **más utilizados** y proviene del modelo en cascada.
    - Introduce la posibilidad de **retornar a etapas anteriores** para corregir, modificar o depurar aspectos.
    - **Idóneo** para proyectos **rígidos** (pocos cambios, poco evolutivos) y con **requisitos claros**.
    - Si se esperan muchos cambios, no es el más recomendable.

3. **Modelos evolutivos**

Tienen en cuenta la naturaleza cambiante del *software* y se distinguen dos variantes:

- **Modelo iterativo incremental:**
    - Basado en el modelo en cascada con realimentación, donde las fases se **repiten y refinan**.
    - Cada **iteración** cubre una parte de los requisitos, generando **versiones parciales y crecientes** del producto (incrementos). La versión obtenida es el punto de partida para la siguiente.
    - Permite una **evolución temporal** del producto, reflejando la práctica actual de lanzar versiones en lugar de productos completos.

- **Modelo en espiral:**
    - Combina el modelo incremental con el modelo en cascada.
    - El *software* se construye en versiones que mejoran y aumentan su funcionalidad en cada vuelta. Es un modelo **complejo**.
    - **Características:** Se divide en **seis regiones de tareas** (Comunicación, Planificación, **Análisis de riesgos**, Representación, Codificación y Explotación, y Evaluación del cliente). Se adapta completamente a la naturaleza evolutiva del *software* y **reduce riesgos** proactivamente.

4. **Modelos ágiles**

- Son metodologías modernas y **muy flexibles** que ganan gran presencia en el desarrollo.
- Están muy centrados en la **satisfacción del cliente** y permiten la aparición de **nuevos requisitos** incluso durante el desarrollo.
- El desarrollo es **incremental**, con **incrementos cortos** y fases que se **solapan**.
- La **comunicación** entre el equipo y el cliente es **constante**. Un ejemplo conocido es **Scrum**. 

### 5.- Herramientas de apoyo al desarrollo del software

Las herramientas informáticas se utilizan para **automatizar tareas** en las etapas del desarrollo de *software*, con el fin de aumentar la **fiabilidad** y **reducir el tiempo y los costes**. Esto permite a los desarrolladores centrarse en los requisitos y el análisis, que son las principales causas de los fallos.

Las **Herramientas CASE** (*Computer Aided Software Engineering*) son aplicaciones diseñadas para automatizar las fases del desarrollo de *software*.

**Objetivos y beneficios:**

- **Mejorar la productividad y calidad** del proceso y del resultado final.
- Mejorar la **planificación** y darle **agilidad** al proceso.
- Permitir la **reutilización** de partes del *software*.
- Hacer que las aplicaciones respondan a **estándares**.
- Facilitar la tarea del **mantenimiento**.
- Mejorar la visualización de las fases de desarrollo de forma **gráfica**.

Estas herramientas pueden ayudar en tareas como el diseño, la codificación a partir de la apariencia visual y la detección de errores.

Las herramientas CASE se clasifican según las fases del ciclo de vida del *software* en las que ofrecen ayuda:

| Clasificación | Fases del ciclo de vida | Tareas de apoyo |
| :--- | :--- | :--- |
| U-CASE (*Upper CASE*) | Planificación y análisis de requisitos | Ayuda en la definición y gestión inicial del proyecto |
| M-CASE (*Middle CASE*) | Análisis y diseño | Apoyo en la modelización de la estructura del sistema |
| L-CASE (*Lower CASE*) | Codificación, pruebas y documentación | Programación, detección de errores, depuración de programas y generación de documentación |

Algunos ejemplos de herramientas CASE libres son **ArgoUML**, **Use Case Maker** y **ObjectBuilder**. 

### 6.- Frameworks

Un **Framework** es una **estructura de ayuda** o plataforma *software* que permite a los programadores desarrollar proyectos sin empezar desde cero. Define programas de soporte, bibliotecas, lenguaje interpretado y otros recursos que facilitan la creación y unión de los diferentes módulos de un proyecto.

El uso de un *framework* permite dedicar más tiempo al **análisis de requerimientos** y las **especificaciones técnicas**, ya que las tareas más laboriosas y detalladas de programación ya están resueltas. 

**Ventajas**: 
- **Desarrollo rápido** de *software*.
- **Reutilización** de partes de código en otras aplicaciones.
- Diseño **uniforme** del *software*.
- **Portabilidad** de aplicaciones (los *bytecodes* generados pueden ejecutarse sobre cualquier máquina virtual).

**Inconvenientes**:
- Gran **dependencia** del código respecto al *framework* (cambiar de *framework* implica reescribir gran parte de la aplicación).
- El uso y la **implementación** del *framework* consumen bastantes **recursos** del sistema.

**Ejemplos de frameworks**:
- **.NET:** Utilizado para desarrollar aplicaciones en Windows. Incluye *Visual Studio .NET* para la construcción de aplicaciones y el *.NET Framework* para su ejecución.
- **Spring:** Un conjunto de bibliotecas (*API's*) para el desarrollo y ejecución de aplicaciones en **Java**.
- **Qt:** Un *framework* **multiplataforma** para el lenguaje **C++**, aunque admite adaptaciones a otros lenguajes.
- **Angular:** Un *framework* de **Javascript** centrado en el desarrollo de **aplicaciones web**.

### 7.- Lenguajes de programación

Un **lenguaje de programación** es un idioma creado de forma artificial, compuesto por un conjunto de **símbolos y normas** que se usan para obtener un **código** que el *hardware* de la computadora puede entender y ejecutar. Son los instrumentos esenciales que permiten comunicarnos con el ordenador para que realice las tareas necesarias.

La elección del lenguaje es crucial, ya que cada uno está enfocado a diferentes tipos de tareas y áreas de programación. Esta decisión se toma típicamente durante la fase de **diseño** del proyecto, basándose en los **requerimientos del cliente**.

**Componentes de un lenguaje de programación**

- **Alfabeto:** el conjunto de **símbolos** permitidos para escribir código.
- **Sintaxis:** las **normas de construcción** que rigen cómo deben combinarse los símbolos del lenguaje.
- **Semántica:** el **significado** de las construcciones, es decir, las acciones válidas que el *hardware* realizará. 

#### 7.1.- Características de los lenguajes de programación

Los lenguajes de programación han evolucionado para facilitar la labor del programador, pasando de ser directamente interpretables por la máquina a ser más cercanos al razonamiento humano.

**Lenguaje máquina**
* **Instrucciones:** combinaciones de unos y ceros (código binario).
* **Traducción:** es el **único** lenguaje que el ordenador entiende **directamente** (no necesita traducción).
* **Portabilidad:** **no es portable**; es único para cada tipo de procesador.
* **Uso:** fue el primer lenguaje, pero ya **no se utiliza** para programar.

**Lenguaje ensamblador**
* **Instrucciones:** utiliza **mnemotécnicos** (instrucciones complejas) en lugar de unos y ceros.
* **Traducción:** **necesita traducción** al lenguaje máquina para ejecutarse.
* **Características:** sus sentencias hacen referencia a la **ubicación física** de los archivos en el equipo. Es difícil de utilizar.

**Lenguajes de alto nivel (basados en código)**
* **Instrucciones:** usan sentencias y órdenes derivadas del **idioma inglés**, siendo más cercanos al **razonamiento humano**.
* **Traducción:** **necesitan traducción** al lenguaje máquina.
* **Uso:** son los lenguajes que **se utilizan hoy día**, aunque su uso tiende a disminuir.

**Lenguajes visuales**
* **Instrucciones:** están sustituyendo a los lenguajes basados en código. Se programa **gráficamente usando el ratón** y diseñando directamente la apariencia (*look and feel*) del *software*.
* **Código:** el código fuente correspondiente **se genera automáticamente**.
* **Traducción:** **necesitan traducción** al lenguaje máquina.
* **Portabilidad:** son **completamente portables** de un equipo a otro. 

#### 7.2.- Clasificación de los lenguajes de programación

La elección del lenguaje de programación depende de las características del problema a resolver. Los lenguajes se clasifican según varios criterios:

**Según la cercanía al lenguaje humano**

| Tipo de Lenguaje | Características | Inconvenientes |
| :--- | :--- | :--- |
| **Alto nivel** | Traducen los algoritmos a un lenguaje fácil de entender para el programador. Son **portables** (no orientados a una máquina específica) | Las instrucciones **no son directamente ejecutables** por la máquina, requieren traducción |
| **Bajo nivel** | Aprovechan al máximo los recursos del ordenador | **No portables** (adaptados a la máquina específica) y difíciles de manejar |
| > *Lenguaje máquina* | Programación directa con 0s y 1s | Muy difícil de programar y corregir errores |
| > *Lenguaje ensamblador* | Primer nivel de abstracción; usa **mnemotécnicos**, pero está conceptualmente cercano al *hardware* | Difícil de usar y dependiente de las características del *hardware* |

**Según su forma de ejecución**

La ejecución depende de si el programa, que no está en lenguaje máquina, necesita una traducción completa o una traducción paso a paso:

- **Lenguajes compilados:** se traducen completamente al lenguaje máquina mediante un **compilador**, generando un **nuevo fichero ejecutable**. Una vez traducido, no necesita volverse a compilar si no hay cambios. Un inconveniente es que el programa no puede ejecutarse hasta que no esté **libre de errores**. (Ej.: C, Pascal).
- **Lenguajes interpretados:** el programa es traducido y ejecutado **instrucción a instrucción** cada vez que se quiere ejecutar, usando un **intérprete**. No genera un fichero ejecutable. La ventaja es que permite ejecutar hasta que se encuentra una instrucción errónea. (Ej.: Basic).
- **Lenguajes intermediarios (Híbridos):** combinan compilación e interpretación (ej. Java). Primero, el código fuente se compila a un **lenguaje intermedio** (*bytecode*), y luego este archivo intermedio es traducido (interpretado) a lenguaje máquina en cada ejecución por la Máquina Virtual.

**Tipos de código y proceso de traducción**

| Tipo de Código | Descripción | Generación |
| :--- | :--- | :--- |
| Código fuente | Escrito por el programador en un lenguaje de alto nivel. **No ejecutable** directamente por la máquina. Se obtiene tras diseñar un algoritmo en pseudocódigo | Puede ser **abierto** (disponible para estudio/modificación) o **cerrado** (sin permiso de edición) |
| Código objeto | **Código intermedio** (generalmente *bytecode*). No es ejecutable por la computadora ni inteligible por el ser humano | Se obtiene del código fuente mediante un **compilador**, solo si está libre de errores sintácticos |
| Código ejecutable | El **código máquina** final, directamente inteligible y ejecutable por la computadora | Se obtiene al **enlazar** los archivos de código objeto con rutinas y bibliotecas (mediante un *linker* o enlazador). En lenguajes puramente compilados, se obtiene directamente del código fuente | 

**Otras clasificaciones**

- **Lenguajes imperativos:** Describen **paso a paso** el conjunto de instrucciones (algoritmo) para cambiar el estado del programa y hallar la solución. (Ej.: C, Java, PHP).
- **Lenguajes declarativos:** Las sentencias **describen el problema** que se quiere solucionar, pero no las instrucciones detalladas para hacerlo. (Ej.: Lógicos como Prolog, Algebraicos como SQL, Funcionales como Haskell).

- **Según la técnica de programación:**
    - **Estructurados** (Ej.: Pascal, C).
    - **Orientados a objetos (POO)** (Ej.: C++, Java, C#).
    - **Visuales** (Permiten programar gráficamente; Ej.: Visual Basic .Net).

A pesar de la cantidad de lenguajes, **Java, C, C++, PHP y Visual Basic** concentran alrededor del 60% del interés de la comunidad informática global.

##### 7.2.1.- Lenguajes de programación estructurados

La **programación estructurada** es una técnica fundamental que sentó las bases para el desarrollo de lenguajes más modernos, como los orientados a objetos.

Se define como una técnica para escribir programas que permite usar solo **tres tipos de estructuras de control** o sentencias:

1.  **Sentencias secuenciales**
2.  **Sentencias selectivas** (condicionales)
3.  **Sentencias repetitivas** (iteraciones o bucles)

Los lenguajes basados en esta técnica se denominan **lenguajes de programación estructurados**. Su principal éxito fue su **sencillez** para construir y leer programas.

La programación estructurada evolucionó hacia la **programación modular**, que aplicaba la técnica de "divide y vencerás" separando el código en trozos llamados **módulos** con funcionalidades concretas y reutilizables. 

| Ventajas | Inconvenientes |
| :--- | :--- |
| Los programas son **fáciles de leer**, sencillos y rápidos | El programa se concentra en un **único bloque**, lo que lo hace difícil de manejar si crece demasiado |
| El **mantenimiento** de los programas es sencillo | **No permite la reutilización eficaz de código**, pues todo está concentrado |
| La estructura del programa es **sencilla y clara** | Fue sustituida por la modular para mejorar la funcionalidad |

##### 7.2.2.- Lenguajes de programación orientados a objetos (POO)

La **Programación Orientada a Objetos (POO)** surgió como solución a las limitaciones de la programación estructurada en proyectos grandes. En lugar de ver el programa como una secuencia de instrucciones, la POO lo trata como un **conjunto de objetos independientes** que colaboran entre sí para realizar acciones.

**Características principales**

- **Clase:** plano o plantilla que define un conjunto de objetos con características similares. (Ejemplo: la clase *Persona*).
- **Objeto:** **instancia concreta** de una clase. (Ejemplo: *Noa* o *Valeria* son objetos de la clase *Persona*).
- **Atributos (Propiedades):** definen las **características** que tiene cada objeto de una clase (Ejemplo: el atributo *edad* tiene un valor específico para cada persona).
- **Métodos:** corresponden a las **acciones** que los objetos pueden realizar. Contienen el código que implementa la acción. (Ejemplo: el método *Saludar* en la clase *Persona*).
- **Envío de mensajes:** mecanismo por el cual los objetos se comunican entre sí mediante **llamadas a los métodos**, provocando un cambio en el estado de los objetos.
- **Reutilización:** el código se vuelve **más reutilizable**.
- **Depuración:** es más fácil **localizar y corregir errores** dentro de una clase específica que en un programa completo.

Además de los elementos básicos, la POO incluye conceptos avanzados como:

* **Abstracción**
* **Encapsulamiento**
* **Polimorfismo**
* **Herencia**

*La POO es menos intuitiva que la programación estructurada inicialmente.* 

Ejemplos de lenguajes orientados a objetos son: **Java, C++, C#, Ada** y **VB.NET**.

### 8. Máquinas virtuales

Una **máquina virtual (MV)** es un tipo especial de *software* cuya misión principal es **separar el funcionamiento de una aplicación de los componentes *hardware* instalados**.

Actúa como una capa de *software* de bajo nivel, haciendo de **puente** entre el *bytecode* (código intermedio u objeto) de la aplicación y el *hardware* físico del equipo.

El uso de máquinas virtuales es esencial en lenguajes como Java (lenguajes intermediarios), garantizando la **portabilidad** de las aplicaciones, lo que significa que pueden ejecutarse en cualquier equipo independientemente de sus características físicas.

- **Portabilidad:** aísla la aplicación de los detalles físicos del equipo, permitiendo que el *bytecode* se ejecute universalmente.
- **Gestión de memoria:** se encarga de **reservar memoria** para los objetos creados y **liberar la memoria** no utilizada (garbage collection).
- **Comunicación con el *hardware*:** se comunica con el sistema donde está instalada (huésped) para controlar los dispositivos *hardware* implicados en los procesos.
- **Seguridad:** la MV **verifica todo el *bytecode*** antes de su ejecución y **protege las direcciones de memoria** para asegurar el cumplimiento de las normas de seguridad de las aplicaciones. 

#### 8.1.- Entornos de ejecución

Un **entorno de ejecución** es un servicio de *software* (a veces parte del sistema operativo, otras veces independiente) que actúa como la **base *software*** para que los programas puedan ejecutarse. El tiempo que un programa tarda en ejecutarse se denomina **runtime**.

El entorno funciona como un **intermediario** clave entre el lenguaje fuente y el sistema operativo para ejecutar aplicaciones. 

**Componentes y funciones**

El entorno de ejecución está compuesto por la **máquina virtual (MV)** y las **API's (bibliotecas de clases estándar)**. Estos dos componentes se distribuyen conjuntamente, ya que deben ser compatibles entre sí.

Durante el *runtime*, los entornos se encargan de varias tareas esenciales:

- **Gestión de memoria:** configurar la memoria principal disponible para el sistema.
- **Enlace:** conectar los archivos del programa con las **bibliotecas** (*subprogramas que ya existen*) y con los **subprogramas** que han sido creados específicamente para el programa.
- **Depuración:** comprobar si existen **errores semánticos** en el lenguaje. (Los errores sintácticos se detectan previamente en la compilación).

Es importante notar que el entorno de ejecución solo permite **ejecutar** programas; para **desarrollar** nuevas aplicaciones, se requiere un **entorno de desarrollo**.

#### 8.2.- Java Runtime Environment (JRE)

El **Java Runtime Environment (JRE)** es el **entorno en tiempo de ejecución de Java**. Es un conjunto de utilidades que permite que los programas escritos en Java se ejecuten sobre **cualquier tipo de plataforma**, garantizando la portabilidad del *software*.

El JRE está formado por dos componentes principales que son distribuidos conjuntamente, ya que deben ser consistentes entre sí:

1.  **Máquina Virtual Java (JVM)**: Es el programa que se encarga de **interpretar** el código de la aplicación escrito en Java (*bytecode*).
2.  **Bibliotecas de clase estándar**: Estas bibliotecas implementan la **API de Java** (*Application Programming Interface*), que proporciona las funcionalidades esenciales para que la aplicación pueda funcionar.

Aquí tienes el resumen de las sentencias de control de la programación estructurada:

### Anexo I. Sentencias de control de la programación estructurada.

La programación estructurada se basa en el uso de solo tres tipos de sentencias o estructuras de control para escribir programas de forma clara y sencilla:

1. **Sentencias secuenciales**: se ejecutan una tras otra en el orden exacto en que han sido escritas.

    ```c title="Ejemplo en C"
    printf (“declaración de variables”);
    int numero_entero;
    espacio=espacio_inicio + veloc*tiempo;
    ```

2. **Sentencias selectivas (condicionales)**: permiten evaluar una condición. Se ejecuta un bloque de acciones si la condición es verdadera y, opcionalmente, otro bloque si es falsa.

    - **`if`:** señala la condición a evaluar.
    - **`then`:** acciones a ejecutar si la condición es cierta (se omite en C).
    - **`else`:** acciones a ejecutar si la condición es falsa.

    ```c title="Ejemplo en C"
    if (a >= b)
        c = a - b;
    else
        c = a + b;
    ```

3. **Sentencias repetitivas (iteraciones o bucles)**: hacen que una serie de acciones se repitan mientras o **hasta que una determinada condición deje de ser cierta (o se cumpla).

    - **`while`:** marca el comienzo del bucle, seguido de la condición de parada (o continuación).
    - **`do` / `done`:** marcan el inicio y el fin de las acciones a repetir (se omiten en C, se usan llaves `{}`).

    ```c title="Ejemplo en C"
    int num = 0;
    while (num <= 10) { 
       printf("Repetición numero %d\n", num);
        num = num + 1; 
    };
    ```

## UD2.- Instalación y uso de entornos de desarrollo