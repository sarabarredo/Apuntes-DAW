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