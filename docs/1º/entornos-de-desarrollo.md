---
id: entornos-de-desarrollo
sidebar_position: 2
title: Entornos de Desarrollo
toc_max_heading_level: 3
---

## **UD1.- Desarrollo de software**

![Esquema Unidad 1 Entornos de Desarrollo](../../static/img/entornos-de-desarrollo-unidad-1.jpg)

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

## **UD2.- Instalación y uso de entornos de desarrollo**

![Esquema Unidad 2 Entornos de Desarrollo](../../static/img/entornos-de-desarrollo-unidad-2.jpg)

### 1.- Concepto de entorno de desarrollo. Evolución histórica.

Un **Entorno Integrado de Desarrollo (IDE)** es un *software* que agrupa un **conjunto de herramientas de programación** esenciales en una única interfaz gráfica. Aunque la codificación puede hacerse con un editor de texto y un compilador por separado, la mayoría de los programadores usan un IDE para ganar **fiabilidad y tiempo** en los proyectos.

Un IDE típicamente incluye:
    - **Editor de código.**
    - Acceso integrado al **compilador** (botones/menú).
    - Acceso integrado a la **ejecución** del programa.
    - **Depurador** (Debugger).
    - **Constructor de interfaz gráfico** (GUI Builder).

El principal objetivo es proporcionar al programador componentes con una interfaz uniforme, lo que aumenta la **eficiencia** y reduce el tiempo de codificación.

Originalmente, un IDE estaba dedicado a un solo lenguaje, pero las versiones modernas (como **Eclipse**, **NetBeans** y **Microsoft Visual Studio**) suelen ser **compatibles con varios lenguajes** mediante la instalación de *plugins*.

#### 1.1.- Evolución Histórica

El concepto de IDE no existía en las décadas de la **tarjeta perforada**. La programación se realizaba mediante diagramas de flujo y el código se compilaba tras ser introducido al sistema.

| Período | Hito | Detalles |
| :--- | :--- | :--- |
| Primer IDE | El lenguaje **BASIC** fue el primero en utilizar un IDE | Estaba basado exclusivamente en una **consola de comandos** (antes de la interfaz gráfica), pero ya manejaba gestión de archivos, compilación y depuración |
| Años 70 y 80 | El IDE **Maestro** se considera el primer IDE popular | Nació a principios de los 70 y lideró el campo, siendo instalado por miles de programadores |
| Años 90 - Actualidad | Masificación de los sistemas con interfaz gráfica | El uso de los IDE se **ratifica y afianza**, llevando a una vasta oferta de herramientas propietarias y de código abierto (ej., NetBeans, Eclipse) |

### 2.- Funciones de un entorno de desarrollo

| Función | Tareas clave del IDE |
| :--- | :--- |
| Asistencia de Código | **Coloración** de la sintaxis, **auto-completado** de código, y **refactorización** (cambios de legibilidad sin alterar funcionalidad) |
| Detección y Corrección | **Detección de errores de sintaxis** en tiempo real, **identificación automática** de código y **depuración** avanzada (puntos de ruptura, seguimiento de variables) |
| Automatización y Gestión | **Compilación** de proyectos complejos en un solo paso, **generación automática** de herramientas y documentación, y **organización** de archivos fuente/compilados en carpetas |
| Visual y Diseño | Herramientas de **concepción visual** para crear interfaces gráficas (GUI) |
| Control de Proyecto | **Control de versiones** (almacén compartido, soporte a cambios simultáneos), mecanismos de **auto-recuperación** ante errores, y gestión de **plugins** para aumentar funcionalidades |
| Despliegue | **Empaquetar** el *software* para su posterior instalación en el entorno de ejecución | 

### 3.- Entornos integrados libres y propietarios

| Tipo de IDE | Características | Ejemplos |
| :--- | :--- | :--- |
| Libre | Tiene **licencia de uso público** (gratis) | Eclipse, NetBeans, CodeLite, JDeveloper |
| Propietario | Requiere **licencia de pago** | Microsoft Visual Studio, C++ Builder, QtCreator |

**Entornos más relevantes**

| IDE | Licencia | Lenguajes soportados |
| :--- | :--- | :--- |
| NetBeans | Libre | C/C++, Java, JavaScript, PHP, HTML5 |
| Eclipse | Libre | Ada, C/C++, Java, JavaScript, PHP |
| JDeveloper | Libre | Java, HTML, XML, SQL, Javascript, PHP, UML |
| CodeLite | Libre | C/C++, PHP, Node.js |
| IntelliJ | Mixta | Java, Groovy, Python, XML/XSL |
| Microsoft Visual Studio | Propietario | C#, Visual Basic, C++, Python, JavaScript |
| C++ Builder | Propietario | C++ |
| QtCreator | Propietario | C++ (con framework QT) | 

### 4.- Estructura de entornos de desarrollo

Los **IDEs**, ya sean libres o propietarios, se componen de varios elementos clave que definen sus funciones:

| Componente | Funciones principales |
| :--- | :--- |
| Editor de textos | **Resaltado y coloreado de la sintaxis**, auto-completado de código, inserción automática de paréntesis/tabulaciones, y ayuda con parámetros de funciones/métodos |
| Compilador/Intérprete | **Detección de errores** de sintaxis en tiempo real |
| Depurador | **Ejecución del programa paso a paso**, definición de **puntos de ruptura** y **seguimiento de variables**. Permite depuración en servidores remotos |
| Generador automático de herramientas | Herramientas para la **visualización, creación y manipulación de componentes visuales** (interfaces gráficas), además de asistentes y utilidades de gestión de código |
| Interfaz gráfica | Proporciona una interfaz agradable que puede acceder a **bibliotecas y *plugins***, permitiendo programar en **varios lenguajes** con el mismo IDE | 

### 5.- Instalación de entornos integrados de desarrollo

Este apartado trata sobre la instalación del **JDK**, **Netbeans** y **Eclipse**.

### 6.- Configuración y personalización de entornos de desarrollo

La configuración de un entorno de desarrollo se realiza al crear o abrir un proyecto. Los ajustes pueden ser aplicados solo al **proyecto actual** o de forma **global** a todos los proyectos.

Los parámetros configurables abarcan varios aspectos del proyecto y del editor:

- **Organización del proyecto:**
    - Definición de las **carpetas** donde se alojarán los archivos fuente y de prueba (para mantener la estructura ordenada).
    - Descripción de los proyectos para su mejor localización.
- **Gestión del código y la compilación:**
    - Opciones de **compilación** (ej., compilar al grabar, generar información de depuración).
    - Opciones de **generación de documentación**.
    - Opciones de **empaquetado** de la aplicación (ej., nombre del archivo `.jar` y momento del empaquetado).
    - Administración de la plataforma del entorno.
- **Personalización del editor:**
    - Opciones de **formato global** del editor (ej., número de espaciados en las sangrías).
    - Definición del **color** para errores de sintaxis o etiquetas.
    - Configuración del **autocompletado** de código y la inserción automática de código.
    - Opciones de **combinación de teclas** (*shortcuts*). 

### 7.- Gestión de módulos

En entornos de desarrollo como **NetBeans**, se utilizan **módulos** y **plugins** para ampliar las capacidades básicas de la plataforma y facilitar el desarrollo de aplicaciones.

- Un **módulo** es un componente *software* que contiene clases de Java que interactúan con las API del IDE. Se identifica mediante un **manifest file** (archivo especial que lo identifica como módulo).
- Los módulos se pueden construir y desarrollar de forma **independiente**, lo que facilita su **reutilización** e inserción en otras aplicaciones.
- Los módulos permiten que una aplicación sea **extendida** (añadiendo nuevas funcionalidades) o **construida** a partir de componentes con finalidades concretas.
- Existe una gran cantidad de módulos y plugins disponibles, a menudo clasificados por categorías, en la página oficial del IDE. 

Las tareas asociadas a la gestión de módulos incluyen la instalación, desinstalación, desactivación y actualización de los mismos, todo gestionable desde el propio entorno.

#### 7.1.- Añadir

Añadir un módulo o *plugin* dota de **mayor funcionalidad** a los proyectos desarrollados en NetBeans. Existen varias formas de incorporar módulos:

1. **Módulos por defecto:** usar módulos que NetBeans ya instaló.
2. **Creación propia:** desarrollar el módulo uno mismo.
3. **Adición *Off-line*** (Descarga manual):
    - El módulo se descarga desde la web oficial de NetBeans en formato **`.nbm`**.
    - Posteriormente, el *plugin* se **carga e instala** desde dentro del IDE.
4. **Adición *On-line*** (Instalación desde el IDE):
    - Se instalan complementos **sin salir del IDE** ni descargarlos previamente.
    - Este método requiere que el *plugin* **Portal Update Center** esté instalado.

#### 7.2.- Eliminar

Eliminar un módulo o *plugin* se plantea cuando deja de ser útil o el proyecto que lo requería ha finalizado. Es un proceso sencillo que implica encontrar el complemento en la lista de instalados y elegir la acción deseada.

Al eliminar un módulo, siempre se ofrecen dos opciones:
    1. **Desactivar:** el módulo o *plugin* **sigue instalado** físicamente en el sistema, pero su estado cambia a **inactivo** (deja de aparecer y funcionar en el entorno).
    2. **Desinstalar:** el módulo o *plugin* se **elimina físicamente y de forma permanente** del entorno.

#### 7.3.- Funcionalidades

Los módulos y *plugins* se clasifican en varias categorías según el área que mejoran:

- **Lenguajes de programación y bibliotecas:** permiten programar con lenguajes que el IDE no soporta inicialmente.
- **Construcción de código:** facilitan la labor de programación.
- **Edición:** hacen el editor más preciso y cómodo para el programador.
- **Refactorización:** permiten realizar cambios menores en el código para aumentar su legibilidad sin alterar su función.
- **Depuradores:** hacen más eficiente la depuración de programas.
- **Prueba:** incorporan utilidades específicas para el *testing* del *software*.
- **Bases de datos:** ofrecen nuevas funcionalidades para el mantenimiento de las aplicaciones.
- **Aplicaciones web:** integran utilidades específicas para el desarrollo de aplicaciones web.
- **Documentación de aplicaciones:** permiten generar la documentación de los proyectos en el formato deseado.
- **Interfaz gráfica de usuario (GUI):** mejoran la presentación de diversos aspectos del entorno al usuario.
- **Aplicaciones:** añaden nuevas aplicaciones independientes que pueden ser útiles. 

#### 7.4.- Herramientas concretas

NetBeans ofrece una serie de herramientas integradas diseñadas para simplificar el desarrollo de *software*, especialmente en entornos empresariales y web, cubriendo todas las etapas del ciclo de vida:

- **Importador de Proyectos:** permite trabajar con proyectos creados en otros entornos, como **JBuilder**.
- **Servidor de Aplicaciones GlassFish:** proporciona una plataforma completa para el desarrollo y despliegue de **aplicaciones empresariales**.
- **Soporte Java Enterprise Edition (JEE):** asegura el cumplimiento de estándares y mejora el rendimiento para la creación ágil de aplicaciones empresariales.
- **NetBeans Swing GUI Builder:** simplifica la **creación de interfaces gráficas de usuario (GUI)** para aplicaciones cliente, permitiendo el manejo visual sin salir del IDE.
- **NetBeans Profiler:** evalúa la **eficiencia y rendimiento** del *software* de forma inmediata para los usuarios finales.
- **Herramientas XML y Servicios Web:** iIncluye el **Editor WSDL** (para Servicios Web basados en XML) y el **Editor XML Schema Editor** (para refinar la estructura de documentos XML).
- **Seguridad:** asegura la protección de datos mediante herramientas como **Sun Java System Access Manager**.
- **Soporte UML (Beta):** cubre actividades de modelado como clases, comportamiento, interacción y secuencias.
- **Soporte Bidireccional:** permite la **sincronización rápida** de modelos de desarrollo con los cambios en el código a medida que se avanza en las etapas del ciclo de vida de la aplicación. 

### 8.- Uso básico de entornos de desarrollo

La interfaz principal de un IDE como NetBeans se divide en secciones clave para la gestión y la codificación de proyectos:

- **Ventana izquierda (Ventana de proyectos):**
    - Muestra la relación jerárquica de **proyectos, archivos, módulos o clases** abiertos durante la sesión.
    - Cada proyecto contiene sus archivos fuente y bibliotecas.
    - El archivo principal de ejecución en Java suele ser `Main.java* (o la clase que contiene el método principal), siendo recomendable mantener este nombre para facilitar la identificación del punto de inicio del programa.

- **Ventana derecha (Espacio de escritura/Editor):**
    - Es el área principal donde se **escribe el código fuente**.
    - Al crear un nuevo proyecto, muestra automáticamente el esqueleto básico del programa (por ejemplo, la estructura de la clase principal en Java).

- **Barra de Herramientas:**
    - Permite acceder rápidamente a todas las funciones y opciones principales del IDE (ej., guardar, compilar, ejecutar). 

#### 8.1.- Edición de programas

La **ventana de codificación** del IDE es donde se escriben las instrucciones del programa. Mientras se edita el código, NetBeans proporciona varias ayudas clave:

- **Autocompletado de código:** sugiere comandos, métodos y variables a medida que se escribe.
- **Coloración de comandos:** aplica diferentes colores a las palabras reservadas, comentarios y elementos de la sintaxis para facilitar la lectura.
- **Detección de errores en tiempo real:** muestra un **subrayado en rojo** (y un icono visual a la izquierda) cuando detecta un error de sintaxis o de compilación, ofreciendo opciones de depuración y corrección inmediata.

#### 8.2.- Generación de ejecutables

Una vez que el código fuente está escrito en la ventana de edición y **libre de errores de sintaxis**, el proceso para obtener y probar el programa ejecutable sigue estos pasos secuenciales:
    1. **Compilación**
    2. **Depuración**
    3. **Ejecución**

Para ejecutar el programa directamente desde NetBeans, se utiliza el atajo `Shift + F6`. Esto compila y ejecuta el archivo de código que hay abierto.

### 9.- Actualización y mantenimiento de entornos de desarrollo

El **mantenimiento** del entorno de desarrollo es crucial y consiste en mantener todos sus componentes periódicamente **actualizados**.

Las tareas de mantenimiento y actualización se realizan generalmente de forma **online**. En NetBeans, el complemento llamado **Auto Update Services** es el encargado de gestionar y aplicar las continuas revisiones y actualizaciones de todos los *plugins*. Este mismo complemento debe estar instalado para poder realizar la adición de nuevos módulos de forma *on-line* (sin descarga previa).

También es de **vital importancia** realizar **copias de seguridad** de las bases de datos asociadas a los proyectos de forma periódica. Esto asegura que, en caso de un fallo o proceso defectuoso, los proyectos puedan ser **restaurados** a un estado anterior estable y que sean compatibles con futuras versiones del entorno. 

### Anexo I.- Crear, compilar y ejecutar un programa (sin usar IDE)

Este proceso demuestra cómo ejecutar un programa Java utilizando solo un editor de texto y el **JDK**, prescindiendo de un IDE. Para ello, se asume que las variables de entorno **`JAVA_HOME`** y **`PATH`** están configuradas correctamente.

**1. Crear el código fuente**
    - Utiliza un editor de texto (como el Bloc de Notas) para crear un archivo llamado **`Hola.java`**.
    - El nombre del archivo (`Hola.java`) **debe coincidir** con el nombre de la clase pública (`public class Hola`).
    - Guarda el archivo en una ubicación conocida.

    ```java
    public class Hola {
        public static void main(String[ ] args) {
            System.out.println("Hola");
        }
    }
    ```

**2. Abrir el terminal y situarse en la ruta**
    - Abre la línea de comandos.
    - Si no estás en la ruta, usa el comando `cd` para navegar al directorio del archivo.

**3. Compilar el código fuente**
    - Ejecuta el compilador de Java (**`javac`**) sobre el archivo fuente.
        ```bash
        javac Hola.java
        ```
    - **Resultado:** el compilador **`javac`** traduce el código fuente a *bytecode* y genera un nuevo archivo llamado **`Hola.class`**.

**4. Ejecutar el programa**
    - Ejecuta el intérprete de Java (**`java`**) sobre el nombre de la clase compilada (sin la extensión `.class`).
        ```bash
        java Hola
        ```
    - **Resultado:** el intérprete **`java`** traduce y ejecuta el *bytecode* línea a línea, mostrando el mensaje "Hola" en la consola.

:::info Diferencia clave
- `javac` es el **compilador** (genera el archivo `.class`).
- `java` es el **intérprete** (ejecuta el archivo `.class` a código máquina y no genera ningún archivo nuevo).
:::

### Anexo II.- Crear, compilar y ejecutar un programa con varias clases (sin usar IDE)

Este ejercicio demuestra la implementación de un problema utilizando múltiples **clases de Java** (simulando tres actores/objetos: Profesor, Estudiante, Ordenador) y la gestión de la compilación e interpretación sin un IDE.

La solución se estructura en un **proyecto** (`semaforo`) con **paquetes** (`principal` y `clases`), donde cada paquete contiene los ficheros de código fuente (`.java`).

El diseño utiliza conceptos de Programación Orientada a Objetos (POO), especialmente la **Herencia** y la **Comunicación entre objetos**:

| Clase | Paquete | Conceptos clave | Función en el Programa |
| :--- | :--- | :--- | :--- |
| `ClaseColor` | `principal` | Contiene la función **`main`** (inicio del programa). Utiliza `import` para acceder a la clase `Profesor` | Crea el objeto `Profesor` y recibe la respuesta del sistema |
| `Ordenador` | `clases` | Utiliza el método **`Random`** de Java | Devuelve aleatoriamente el color del semáforo (`"rojo"`, `"amarillo"`, `"verde"`) |
| `Persona` | `clases` | **Clase Padre**. No se instancia directamente | Define variables miembro que son **heredadas** por `Estudiante` y `Profesor` (ej., `i_Edad`, `s_Nombre`) |
| `Estudiante` | `clases` | **Hereda** de `Persona` (cláusula `extends`) | Sobrescribe el constructor y define el método `preguntacolor`, el cual crea un objeto `Ordenador` para obtener el color |
| `Profesor` | `clases` | **Hereda** de `Persona`. | Define el método `preguntacolor`, que a su vez **llama** al método `preguntacolor` de la clase `Estudiante` para obtener la respuesta |

Los ficheros de código (`.java`) deben estar organizados en directorios que coincidan con sus declaraciones de **`package`**.

**1. Compilación:**
    - Se inicia desde el directorio raíz del proyecto (ej., `/home/debian/Escritorio/semaforo`).
    - Se utiliza el compilador `javac`, indicando la ruta relativa del fichero principal (`ClaseColor.java`):
        ```bash
        javac principal/ClaseColor.java
        ```
    - **Nota:** al ser clases dependientes entre sí, compilar el fichero principal puede compilar automáticamente los demás. Si no es así, se deben compilar individualmente en orden de dependencia.
    - **Resultado:** se generan los cinco ficheros `bytecode` (`.class`).

**2. Ejecución:**
    - Se utiliza el intérprete **`java`** sobre la ruta relativa de la clase que contiene `main`:
        ```bash
        java principal/ClaseColor
        ```

---

Para distribuir el proyecto como un único archivo comprimido (`.jar`), se usa el programa `jar` incluido en el JDK.

1.  **Crear `MANIFEST.MF`:** se crea un directorio `META-INF` y dentro un fichero `MANIFEST.MF` que indica la clase de inicio (la que contiene `main`):
    ```
    Main-Class: principal.ClaseColor
    ```
    *(Debe incluirse un fin de línea después de la última línea de texto).*
2.  **Generar el archivo `.jar`:** desde la consola, se ejecuta el comando `jar` para empaquetar todos los recursos:
    ```bash
    jar cmf META-INF/MANIFEST.MF semaforo.jar clases/*.class principal/*.class
    ```
3.  **Ejecutar el `.jar`:**
    ```bash
    java -jar semaforo.jar
    ```

El programa `jar` también permite ver el contenido (`jar tf semaforo.jar`) y descomprimirlo (`jar xf semaforo.jar`).

## **UD3.- Diseño y realización de pruebas**

![Esquema Unidad 3 Entornos de Desarrollo](../../static/img/entornos-de-desarrollo-unidad-3.jpg)

### 1.- Planificación de las pruebas

Durante el desarrollo de *software* es inevitable incurrir en errores (de especificación, diseño o codificación). Por ello, es necesario un conjunto de pruebas para asegurar que el producto es **correcto** y **cumple con los requisitos** del usuario.

Las pruebas tienen dos objetivos clave:
    - **Verificación:** comprueba que el sistema se está **construyendo correctamente**; es decir, que cumple con las **condiciones internas** impuestas (ej. el código sigue el diseño).
    - **Validación:** evalúa si el sistema **satisface los requisitos** especificados por el usuario (ej., el producto final hace lo que el cliente pidió).

**Estrategias y proceso de pruebas**

<img src="/img/entornos-de-desarrollo-modelo-espiral.jpg" alt="Representación del modelo en espiral" width="50%" />

Siguiendo una metodología como el **modelo en espiral** , las pruebas se planifican y ejecutan de manera progresiva y secuencial:

1. **Pruebas unitarias:** comienzan con la validación de cada **porción individual** de código.
2. **Pruebas de integración:** ensamblan todas las partes del código para comprobar que su interconexión y funcionamiento conjunto cumplen con lo establecido en la fase de **diseño**.
3. **Prueba de validación:** verifica que el sistema construido cumple con las especificaciones del **análisis de requisitos** de *software*.
4. **Prueba de sistema:** fase final, que verifica el **funcionamiento total** del *software* y su interacción con otros elementos del sistema.

:::info Recomendación
Se recomienda que el **programador evite probar sus propios programas**, ya que la misma persona podría pasar por alto aspectos no considerados durante la codificación.
:::

### 2.- Tipos de prueba

En la Ingeniería del Software, los enfoques fundamentales para realizar pruebas se centran en el conocimiento que se tiene de la estructura interna del código:

* **Prueba de la Caja Negra (*Black Box Testing*):** se prueba la aplicación usando únicamente su **interfaz externa**, sin conocer o preocuparse por su implementación interna. El foco está en verificar que los **resultados de la ejecución son los esperados** para una entrada dada.

* **Prueba de la Caja Blanca (*White Box Testing*):** se prueba la aplicación **desde dentro**, analizando y probando directamente el **código fuente** para localizar **estructuras incorrectas** o **ineficientes** en la implementación. Requiere un conocimiento específico de la lógica interna.

#### 2.1.- Funcionales (pruebas de la caja negra)

Las **pruebas funcionales** siguen el enfoque de la Caja Negra. Tienen como objetivo verificar que la aplicación o componente realiza las **funciones** que se esperan de él, basándose exclusivamente en sus entradas y salidas, sin considerar la estructura interna. Se enfocan en responder: "¿Puede el usuario hacer esto?" o "¿Funciona correctamente esta utilidad?"

Dentro de las pruebas funcionales, se pueden destacar tres tipos de estrategias para la selección de casos de prueba:

* **Particiones equivalentes:** consiste en reducir el número de casos de prueba creando **clases de equivalencia**. Se prueba solo un valor representativo de cada clase, asumiendo que el resultado es extrapolable a todos los demás valores de esa clase.
* **Análisis de valores límite:** se eligen como entradas aquellos valores que se encuentran justo en los **límites de las clases de equivalencia**.
* **Pruebas aleatorias:** consiste en generar un **gran volumen de entradas aleatorias** para alimentar la aplicación (usando generadores de prueba). Es más adecuado para aplicaciones no interactivas. 

#### 2.2.- Pruebas estructurales (pruebas de la caja blanca)

Las **pruebas estructurales** son el conjunto de pruebas de la **Caja Blanca** (*White Box Testing*). Se centran en verificar la **estructura interna** de los componentes de la aplicación, analizando **cómo** se ejecuta el programa, en lugar de solo el resultado (como hacen las pruebas funcionales).

Su función principal es garantizar que:
    - Se ejecutan **todas las instrucciones** del programa.
    - **No existe código no usado** (*código muerto*).
    - Se recorren los **caminos lógicos** del programa.

**Criterios de cobertura lógica**

El cumplimiento de estos criterios determina el nivel de seguridad en la detección de errores y el nivel de **cubrimiento** de la prueba:

| Criterio de cobertura | Ejecución mínima requerida |
| :--- | :--- |
| Cobertura de sentencias | Cada **instrucción** del programa debe ser ejecutada, al menos, una vez |
| Cobertura de decisiones | Cada **prueba lógica** (ej. la condición de un `if`) debe evaluarse al menos una vez a **cierto** y otra a **falso** |
| Cobertura de condiciones | Cada **elemento individual** dentro de una condición compuesta (ej. `x<0` o `y>0`) debe evaluarse a **cierto** y a **falso** al menos una vez |
| Cobertura de condiciones y decisiones | Se cumplen **simultáneamente** los dos criterios anteriores |
| Cobertura de caminos | Se establece que se debe ejecutar al menos una vez cada **secuencia encadenada de sentencias** (*camino*) desde el inicio hasta el fin del programa |

**Cobertura de caminos de prueba**

Debido a que el número de caminos puede ser enorme, este criterio se reduce al **camino prueba**. La variante más rigurosa recomienda probar cada **bucle** de control tres veces:
    1. Sin entrar en su interior (0 veces).
    2. Ejecutándolo una vez.
    3. Ejecutándolo dos veces.

> **CUBRIMIENTO:** tarea realizada por el programador para verificar que todas las funciones, sentencias, decisiones y condiciones son susceptibles de ser ejecutadas y recorridas con éxito.

Existen herramientas (ej. **Clover para Java**) que automatizan y facilitan estas pruebas de cubrimiento.

#### 2.3.- Pruebas de regresión

Las **pruebas de regresión** son la repetición de pruebas realizadas previamente para **verificar** que los cambios (correcciones de errores o nuevas mejoras) no han introducido **efectos no deseados** o **errores adicionales** (*errores colaterales*) en componentes que no fueron modificados. 

- **Momento de ejecución:** deben llevarse a cabo **cada vez** que se realiza un cambio en el sistema.
- **Objetivo:** asegurar que el sistema sigue funcionando correctamente y que la modificación no ha comprometido la integridad de otros componentes.
- **Composición del Conjunto de Pruebas de Regresión:**
    1.  Una **muestra representativa** que ejercite todas las funciones principales del *software*.
    2.  Pruebas que se centran en las funciones que tienen mayor **probabilidad de verse afectadas** por el cambio.
    3.  Pruebas que se centran directamente en los **componentes modificados**.
* **Eficiencia:** para evitar que el número de pruebas crezca excesivamente, el diseño debe ser **selectivo**, incluyendo solo aquellas pruebas que cubran una o más clases de errores en las funciones principales del programa.
* **Métodos:** se pueden realizar **manualmente** (seleccionando un subconjunto de casos) o utilizando **herramientas automáticas**.

### 3.- Procedimientos y casos de prueba

Una **prueba** es la ejecución de un programa bajo condiciones específicas para encontrar errores. Un **caso de prueba** es un artefacto documentado que consta de tres elementos definidos por el IEEE:

    1. Un conjunto de entradas
    2. Condiciones de ejecución
    3. Resultados esperados

Debido a la complejidad de las aplicaciones, es imposible probar todas las combinaciones posibles. Por lo tanto, el diseño de casos de prueba debe buscar un **compromiso** entre los **recursos consumidos** y la **probabilidad de detectar errores**.

Existen tres procedimientos principales para el diseño de casos de prueba:

- **Enfoque Funcional o de Caja Negra:**
    - Se centra en **funciones, entradas y salidas**.
    - Verifica que la salida es correcta sin verificar el proceso interno.
    - Se utilizan técnicas como el **análisis de valores límite** y **clases de equivalencia**.
- **Enfoque Estructural o de Caja Blanca:**
    - Se centra en la **implementación interna** del programa.
    - El objetivo es probar todos los **caminos de ejecución** posibles dentro del código.
- **Enfoque Aleatorio:**
    - Se centra en modelos estadísticos para elaborar casos de prueba.
    - Se utilizan **generadores automáticos** de casos de prueba para alimentar la aplicación con entradas al azar.

### 4.- Herramientas de depuración

Cada IDE suministra herramientas de depuración esenciales para verificar el código y realizar pruebas estructurales y funcionales. 

Durante el desarrollo de *software*, se distinguen dos tipos de errores:

1.  **Errores de compilación (errores de codificación):** son fallos **sintácticos**. Estos errores **impiden que el programa se compile** y el IDE proporciona información inmediata para su corrección.
2.  **Errores lógicos (Bugs):** no impiden la compilación, pero causan que el programa devuelva **resultados erróneos**, termine antes de tiempo, o no termine nunca.

El **depurador** es la herramienta del IDE utilizada para supervisar la ejecución de programas compilados y localizar y eliminar estos **errores lógicos**. Permite suspender la ejecución, examinar y establecer valores de variables, y comprobar resultados de métodos o comparaciones.

#### 4.1.- Puntos de ruptura

Los **puntos de ruptura (*breakpoints*)** son marcadores que se establecen en cualquier **línea de código ejecutable** para detener temporalmente la ejecución del programa:
    - Permiten al programador inspeccionar una parte específica del código sin necesidad de ejecutar el programa completo. Una vez que se alcanza el punto de ruptura, el programa se suspende.
    - El programador puede **examinar las variables** para verificar sus valores y confirmar que son correctos, o iniciar una **ejecución paso a paso** para seguir el camino lógico que toma el programa a partir de ese punto.
    - Se pueden insertar varios puntos de ruptura en un programa y se eliminan con la misma facilidad con la que se insertan.

#### 4.2.- Tipos de ejecución

El depurador de un IDE permite ejecutar un programa de diversas maneras para simplificar la detección de errores lógicos:

- **Ejecución paso a paso (por instrucción):** ejecuta el programa **línea por línea** para verificar el flujo y corregir errores lógicos.
- **Ejecución paso a paso (por procedimiento):** permite saltarse la ejecución interna de un método o función, ejecutándolo por completo y devolviendo solo el **resultado**. Es útil cuando se sabe que el procedimiento ya funciona correctamente y solo interesa el valor que devuelve.
- **Ejecución hasta una instrucción:** el programa se ejecuta normalmente hasta que el cursor lo detiene en una línea específica, a partir de la cual se puede iniciar la depuración paso a paso.
- **Ejecución hasta el final:** ejecuta el programa de forma completa sin detenerse en instrucciones intermedias.

Estos modos se ajustan a las necesidades del momento, permitiendo concentrar el esfuerzo de inspección solo en las partes del código que se sospecha que contienen errores.

#### 4.3.- Examinadores de variables

Los **examinadores de variables** son herramientas fundamentales en el proceso de depuración. Su función es permitir al programador **supervisar los valores** que adquieren las variables y sus tipos a medida que el programa avanza instrucción por instrucción.
    - **Utilidad:** al seguir la ejecución paso a paso, el programador puede comprobar si las variables toman los valores esperados. Si el programa no devuelve el resultado correcto, el examinador ayuda a **localizar la instrucción incorrecta** que causó el desvío.
    - **Implementación:** NetBeans utiliza un panel llamado **Ventana de Inspección**, donde se pueden agregar variables de interés para observar cómo cambian sus valores durante la ejecución del código.

### 5.- Validaciones 

La **validación** es la etapa del proceso de prueba donde interviene de manera decisiva el **cliente**. Su objetivo es determinar si la aplicación desarrollada **satisface los requisitos** establecidos durante la fase de análisis. En esencia, se busca descubrir errores desde la **perspectiva del cliente y de los requisitos funcionales**.

La validación se consigue mediante una serie de **pruebas de caja negra** diseñadas para demostrar la conformidad con los requisitos.

- **Plan de Prueba:** traza y define la **clase general de pruebas** que se llevarán a cabo.
- **Procedimiento de Prueba:** define los **casos de prueba específicos** que intentarán descubrir errores de acuerdo con los requisitos.

Tanto el plan como el procedimiento están diseñados para asegurar que se cumplen todos los **requisitos funcionales**, se alcanzan los **requisitos de rendimiento**, la **documentación es correcta** e inteligible, y se satisfacen otros requisitos como la portabilidad, compatibilidad, recuperación de errores y facilidad de mantenimiento. 

### 6.- Normas de calidad

Los estándares de calidad se utilizan para formalizar y guiar la fase de prueba de *software*. Anteriormente, existía una dispersión de normas que no cubrían todos los aspectos del proceso de prueba.

Antes de la norma unificadora, los estándares clave utilizados eran:

- **Estándares BSI:**
    * **BS 7925-1:** define el **vocabulario** de las pruebas de *software*.
    * **BS 7925-2:** regula las pruebas de los componentes de *software* (junto con IEEE 1008).
- **Estándares IEEE:**
    * **IEEE 829:** define la **documentación** de la prueba de *software*.
    * **IEEE 1008:** regula las **pruebas de unidad** (*unit testing*).
- Otros estándares incluyen Metodología Métrica v3, ISO/IEC 12207 y 15289.

Esta falta de cobertura total en la organización, gestión y pruebas no funcionales motivó el desarrollo de un estándar unificado.

**Norma ISO/IEC 29119 (Unificación)**

La norma **ISO/IEC 29119** fue creada para **unificar** todos los estándares de prueba, proporcionando una estructura completa que cubre **todo el ciclo de vida** de las pruebas (*testing*) para cualquier proyecto de desarrollo o mantenimiento de *software*.

Esta norma abarca desde estrategias organizativas y políticas de prueba hasta la ejecución e informe final.

**Estructura de la norma ISO/IEC 29119**

La norma se compone de **cuatro partes** principales:

| Parte | Contenido | Estándares relacionados |
| :--- | :--- | :--- |
| 1 | **Conceptos y vocabulario**. Introduce conceptos clave, pruebas basadas en riesgo, tipos de prueba (unidad, integración, validación), ciclos de vida, roles y métricas | BS 7925-1 |
| 2 | **Procesos de prueba**. Define la política de la organización, la gestión del proyecto de prueba y los procesos de prueba estática y dinámica | BS 7925-2, IEEE 1008 |
| 3 | **Documentación**. Establece el contenido y las plantillas requeridas para la documentación de las pruebas | IEEE 829 |
| 4 | **Técnicas de prueba**. Describe y ejemplifica las técnicas de prueba: **estáticas** (revisiones, inspecciones) y **dinámicas** (caja negra, caja blanca, y técnicas de pruebas no funcionales como rendimiento y usabilidad) | BS 7925-2 |

### 7.- Pruebas unitarias

Las **pruebas unitarias** tienen como objetivo principal verificar el correcto funcionamiento de la **unidad** (la parte más pequeña y aislada de la aplicación que se puede probar), que puede ser una **función**, **procedimiento** o **método**. El fin es asegurar que cada módulo funciona correctamente por **separado**, antes de la integración.

| Categoría | Requisitos | Ventajas |
| :--- | :--- | :--- |
| Diseño | Automatizables | Fomentan el cambio |
| Ejecución | Repetibles o Reutilizables | Simplifican la integración |
| Cobertura | Completas | Documentan el código |
| Aislamiento | Independientes | Aíslan y acotan errores |
| Estándar | Profesionales | Separación |

#### 7.1.- Herramientas para Java

Existen varios *frameworks* que automatizan la elaboración de pruebas unitarias en Java:

| Herramienta | Base | Características |
| :--- | :--- | :--- |
| JUnit | Estándar de facto | El más extendido y soportado por la mayoría de los IDEs. Utiliza anotaciones de Java desde la versión 4. Soporta múltiples aserciones y organiza pruebas en Suites. |
| TestNG | Inspirado en JUnit y NUnit | Diseñado para cubrir todo tipo de pruebas. Utiliza anotaciones de Java 1.5. Permite distribución de pruebas en máquinas esclavas y organización de métodos en*grupos |
| Jtiger | Framework de código abierto | Utiliza anotaciones de Java para metadatos. Permite la exportación de informes en HTML, XML o texto, e incluye tareas de Ant para automatizar | 

#### 7.2.- Herramientas para otros lenguajes

Existe una amplia gama de *frameworks* de automatización de pruebas unitarias para la mayoría de los lenguajes de programación modernos. Muchos de estos *frameworks* se basan en la arquitectura **xUnit** (el diseño original de JUnit).

| Herramienta | Lenguaje / Plataforma | Características |
| :--- | :--- | :--- |
| CppUnit | C++ | Framework libre basado en xUnit. Puede integrarse con IDEs como Eclipse y utiliza entornos gráficos de ejecución |
| Nunit | Plataforma .NET | Framework de código abierto basado en xUnit. Dispone de expansiones específicas para entornos web y formularios |
| PHPUnit | PHP | Framework principal para realizar pruebas unitarias en PHP |
| SimpleTest | PHP | Entorno de pruebas para aplicaciones PHP |
| FoxUnit | Microsoft Visual FoxPro | Framework OpenSource para pruebas unitarias |
| MOQ | Genérico | Framework especializado en la creación dinámica de objetos simuladores (*mocks*), usados para aislar dependencias durante las pruebas | 

### 8.- Documentación de la prueba

La **documentación de las pruebas** es un requisito indispensable en el desarrollo de aplicaciones. Unas pruebas bien documentadas sirven como base de conocimiento para futuras tareas de comprobación.

Las metodologías modernas (como **Métrica v3**) se basan en los **estándares ANSI/IEEE** sobre verificación y validación de *software* para la documentación. Estos estándares tienen como objetivo facilitar la **comunicación** entre desarrolladores y asegurar que se ha cubierto **todo el proceso de prueba**.

Los documentos que se van a generar son:

| Documento | Etapa | Contenido |
| :--- | :--- | :--- |
| Plan de pruebas | Inicia con el análisis del sistema | Es la planificación general de las pruebas a realizar |
| Especificación del diseño de pruebas | Detalle del plan de pruebas | Define la ampliación y el detalle de la estrategia de pruebas |
| Especificación de un caso de prueba | Detalle del diseño de pruebas | Concreta un conjunto de entradas, condiciones y resultados esperados para un objetivo específico |
| Especificación de procedimiento de prueba | Ejecución | Detalla el modo exacto en que se ejecutarán los casos de prueba |
| Registro de pruebas | Ejecución | Documenta los sucesos que tienen lugar durante la ejecución de las pruebas |
| Informe de incidente de pruebas | Resultados | Se elabora por cada defecto detectado, incidente, o solicitud de mejora |
| Informe sumario de pruebas | Final | Resume las actividades y resultados de prueba vinculados a las especificaciones de diseño |

---

*Fin de la 1ª Evaluación*

---