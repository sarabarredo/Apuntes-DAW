---
id: programacion
sidebar_position: 2
title: Programación
toc_max_heading_level: 3
---

## UD1.- Introducción a la programación

### 1.- Introducción

En esta primera unidad realizaremos un recorrido por los conceptos fundamentales de la programación de aplicaciones. Iniciaremos nuestro camino conociendo con qué vamos a trabajar, qué técnicas podemos emplear y qué es lo que pretendemos conseguir. Continuaremos con el análisis de las diferentes formas de programación existentes, identificaremos qué fases conforman el desarrollo de una aplicación software y avanzaremos detallando las características relevantes de cada uno de los lenguajes de programación disponibles, para posteriormente, realizar una visión general del lenguaje de programación Java. Finalmente, tendremos la oportunidad de conocer con qué herramientas podríamos desarrollar nuestros programas, escogiendo entre una de ellas para ponernos manos a la obra utilizando el lenguaje Java.

### 2.- Programas y programación
#### 2.1.- Buscando una solución

Como en la vida real, la búsqueda y obtención de una solución a un problema determinado, utilizando medios informáticos, se lleva a cabo siguiendo unos pasos fundamentales.

**Resolución de problemas**

| En la vida real | En programación |
|----------|----------|
| Observación de la situación o problema | **Análisis del problema**: requiere que el problema sea definido y comprendido claramente para que pueda ser analizado con todo detalle |
| Pensamos en una o varias posibles soluciones | **Diseño o desarrollo de algoritmos**: se aplican diferentes técnicas y principios para establecer de forma detallada los pasos a seguir para resolver el problema |
| Aplicamos la solución que estimamos más adecuada | **Resolución del algoritmo elegido:** consiste en convertir el algoritmo en programa, ejecutarlo y comprobar que soluciona verdaderamente el problema |

**¿Qué virtudes debería tener nuestra solución?**

Resolver el problema adecuadamente, en un tiempo mínimo y con un uso óptimo de los recursos del sistema. Para conseguirlo, cuando afrontemos la construcción de la solución tendremos que tener en cuenta los siguientes conceptos:

1. **Abstracción:** se trata de realizar un análisis del problema para descomponerlo en problemas más pequeños y de menor complejidad, describiendo cada uno de ellos de manera precisa.

2. **Encapsulación:** consiste en ocultar la información que manejan de los diferentes elementos que forman el sistema.

3. **Modularidad:** se trata de dividir el proyecto en módulos independientes, donde cada uno de ellos tendrá su función correspondiente.

#### 2.2.- Algoritmos y programas

Después de analizar en detalle el problema a solucionar, hemos de diseñar y desarrollar el **algoritmo** adecuado. Un **algoritmo** es secuencia ordenada de pasos, descrita sin ambigüedades, que conducen a la solución de un problema dado. Éstos son independientes de los lenguajes de programación y de los ordenadores donde se ejecutan.

La diferencia entre algoritmo y programa es que, en el segundo, los pasos que permiten resolver el problema deben escribirse en un determinado lenguaje de programación para que puedan ser ejecutados en el ordenador y así obtener la solución.

Características que un algoritmo debe cumplir:

- Ser preciso e indicar el orden de realización paso a paso.  
- Estar definido, si se ejecuta dos o más veces con los mismos datos de entrada, debe obtener el mismo resultado cada vez. Además, debe dar una respuesta a cualquier dato de entrada.  
- Tener un número finito de pasos.

Para representar gráficamente los algoritmos, podemos utilizar diferentes herramientas:

- **Diagramas de flujo:** utiliza símbolos gráficos para la representación del algoritmo. Suele utilizarse en las fases de análisis.  
- **Pseudocódigo:** se basa en el uso de palabras clave en lenguaje natural, constantes, variables, otros objetos, instrucciones y estructuras de programación que expresan de forma escrita la solución del problema. Es la técnica más utilizada.  
- **Tablas de decisión:** en una tabla son representadas las posibles condiciones del problema con sus respectivas acciones. Suele ser una técnica de apoyo al pseudocódigo cuando existen situaciones condicionales complejas.

### 3.- Paradigmas de la programación

Un **Paradigma de programación** es un modelo básico para el diseño y la implementación de programas. Este modelo determinará como será el proceso de diseño y la estructura final del programa. Algunos de ellos son:

- **Programación declarativa:** se basa en el desarrollo de algoritmos aplicando una especificación de un conjunto de condiciones, proposiciones, afirmaciones y restricciones que describen el problema. Las sentencias utilizadas describen el problema que se quiere solucionar, pero no la instrucciones necesarias para llegar a la solución (ej. SQL). Dentro de este paradigma, se encuentran la **programación funcional** y la **programación lógica**. 
- **Programación imperativa:** se basa en el desarrollo de algoritmos detallando de forma clara y específica los comandos a ejecutar para, a través del paso por diferentes estados,  llegar a la solución. Se basa en el uso de variables, tipos de datos, expresiones y estructuras de control del flujo de ejecución (ej. Python, Java...). Dentro de este paradigma se encuentran la **programación no estructurada**, la **programación estructurada**, la **programación orientada a objetos**, la **programación orientada a eventos**...

Puede haber lenguajes de programación que no se clasifiquen únicamente dentro de uno de ellos.

El objetivo que se busca con la aplicación de diferentes enfoques, es el de reducir la dificultad para el desarrollo y mantenimiento de las aplicaciones, mejorar el rendimiento del programador y mejorar la productividad y calidad de los programas.

### 4.- Fases de la programación

Sea cual sea el estilo que escojamos a la hora de automatizar una determinada tarea, debemos realizar el proceso aplicando un método a nuestro trabajo.

El proceso de creación de software puede dividirse en diferentes fases:

1. Resolución del problema.
2. Implementación.
3. Explotación y mantenimiento.

#### 4.1.- Resolución del problema

Para el comienzo de esta fase, es necesario que el problema sea definido y comprendido claramente para que pueda ser analizado con todo detalle. A su vez, la fase de resolución del problema puede dividirse en dos etapas:

a. **Análisis**

    El análisis indicará la especificación de requisitos que se deben cubrir. Se especificarán los procesos y estructuras de datos que se van a emplear. La creación de prototipos será muy útil para saber con mayor exactitud los puntos a tratar.

    El análisis inicial ofrecerá una idea general de lo que se solicita, realizando posteriormente sucesivos refinamientos que servirán para dar respuesta a las siguientes cuestiones:
        
    - ¿Cuál es la información que ofrecerá la resolución del problema?
    - ¿Qué datos son necesarios para resolver el problema? 

b. **Diseño**

    En esta etapa se convierte la especificación realizada en la fase de análisis en un diseño más detallado, indicando el comportamiento o la secuencia lógica de instrucciones capaz de resolver el problema planteado. Estos pasos sucesivos, que indican las instrucciones a ejecutar por la máquina, constituyen el algoritmo.

    Durante la fase de diseño, se plantea la aplicación a desarrollar como una única operación global, y se va descomponiendo en operaciones más sencillas, detalladas y específicas. El nivel de descomposición dependerá del tamaño del problema. En cada nivel de refinamiento, las operaciones identificadas se asignan a módulos separados.

    Hay que tener en cuenta que antes de pasar a la implementación del algoritmo, hemos de asegurarnos que tenemos una solución adecuada. Para ello, todo diseño requerirá de la realización de la **prueba** o **traza del programa**. Este proceso consistirá en un seguimiento paso a paso de las instrucciones del algoritmo utilizando datos concretos. Si la solución aportada tiene errores, tendremos que volver a la fase de análisis para realizar las modificaciones necesarias o tomar un nuevo camino para la solución. Sólo cuando el algoritmo cumpla los requisitos y objetivos especificados en la fase de análisis se pasará a la fase de implementación.

#### 4.2.- Implementación

Si la fase de resolución del problema requiere un especial cuidado en la realización del análisis y el posterior diseño de la solución, la fase de implementación cobra también una especial relevancia. Llevar a la realidad nuestro algoritmo implicará cubrir algunas etapas más que se detallan a continuación.

a. **Codificación**

    Esta etapa consiste en transformar o traducir los resultados obtenidos a un determinado lenguaje de programación. Para comprobar la calidad y estabilidad de la aplicación se han de realizar una serie de pruebas que comprueben las funciones de cada módulo (pruebas unitarias), que los módulos funcionan bien entre ellos (pruebas de interconexión) y que todos funcionan en conjunto correctamente (pruebas de integración).

    Cuando realizamos la traducción del algoritmo al lenguaje de programación debemos tener en cuenta las reglas gramaticales y la sintaxis de dicho lenguaje. Obtendremos entonces el código fuente, lo que normalmente conocemos por programa.

    Pero para que nuestro programa comience a funcionar, antes debe ser traducido a un lenguaje que la máquina entienda. Este proceso de traducción puede hacerse de dos formas, compilando o interpretando el código del programa.

Compilación: Es el proceso por el cual se traducen las instrucciones escritas en un determinado lenguaje de programación a lenguaje que la máquina es capaz de interpretar, nomalmente código binario.

El proceso de compilación se puede llevar a cabo de dos formas:

    A través de un compilador: programa informático que realiza la traducción. Recibe el código fuente, realiza un análisis lexicográfico, semántico y sintáctico, genera un código intermedio no optimizado, optimiza dicho código y finalmente, genera el código objeto/máquina ejecutable en una plataforma específica.
    A través de un Intérprete: programa informático capaz de analizar y ejecutar otros programas, escritos en un lenguaje de alto nivel. Los intérpretes se diferencian de los compiladores en que mientras éstos traducen un programa escrito en un lenguaje de programación al código de máquina del sistema, los intérpretes sólo realizan la traducción a medida que sea necesaria, típicamente, instrucción por instrucción, y normalmente no guardan el resultado de dicha traducción.

Una vez traducido, sea a través de un proceso de compilación o de interpretación, el programa podrá ser ejecutado.

b. **Prueba de ejecución y validación**

    Para esta etapa es necesario implantar la aplicación en el sistema donde va a funcionar, debe ponerse en marcha y comprobar si su funcionamiento es correcto. Utilizando diferentes datos de prueba se verá si el programa responde a los requerimientos especificados, si se detectan nuevos errores, si éstos son bien gestionados y si la interfaz es amigable. Se trata de poner a prueba nuestro programa para ver su respuesta en situaciones difíciles.

    Mientras se detecten errores y éstos no se subsanen no podremos avanzar a la siguiente fase. Una vez corregido el programa y testeado se documentará mediante:
    - Documentación interna: Encabezados, descripciones, declaraciones del problema y comentarios que se incluyen dentro del código fuente.
    - Documentación externa: Son los manuales que se crean para una mejor ejecución y utilización del programa.

#### 4.3.- Explotación

Cuando el programa ya está instalado en el sistema y está siendo de utilidad para los usuarios, decimos que se encuentra en fase de explotación.

Periódicamente será necesario realizar evaluaciones y, si es necesario, llevar a cabo modificaciones para que el programa se adapte o actualice a nuevas necesidades, pudiendo también corregirse errores no detectados anteriormente. Este proceso recibe el nombre de mantenimiento del software.

Será imprescindible añadir una documentación adecuada que facilite al programador la comprensión, uso y modificación de dichos programas.

### 5.- Ciclo de vida del software

El ciclo de vida del software es una sucesión de estados o fases por las cuales pasa un software a lo largo de su vida. El proceso de desarrollo involucra las siguientes etapas:

1. Especificación y Análisis de requisitos.
2. Diseño.
3. Codificación.
4. Pruebas.
5. Instalación y paso a Producción.
6. Mantenimiento.

### 6.- Lenguajes de programación

Un **lenguaje de programación** es un conjunto de reglas sintácticas y semánticas, símbolos y palabras especiales establecidas para la construcción de programas.

Cada lenguaje de programación se basa en una **gramática**, que es un conjunto de reglas aplicables al conjunto de símbolos y palabras especiales del lenguaje de programación para la construcción de sentencias correctas. Esta gramática dispone de:

1. **Léxico**: conjunto finito de símbolos y palabras especiales (vocabulario del lenguaje).
2. **Sintaxis**: posibles combinaciones de los símbolos y palabras especiales (forma de los programas).
3. **Semántica**: significado de cada construcción del lenguaje (acción que se llevará a cabo).

Pueden existir sentencias sintácticamente correctas, pero semánticamente incorrectas. Una característica relevante de los lenguajes de programación es que más de un programador pueda usar un conjunto común de instrucciones que sean comprendidas entre ellos. A través de este conjunto se puede lograr la construcción de un programa de forma colaborativa.

Los lenguajes de programación pueden ser clasificados en función de lo cerca que estén del lenguaje humano o del lenguaje de los ordenadores.

#### 6.1.- Lenguaje máquina

Lenguaje utilizado directamente por el procesador, que consta de un conjunto de instrucciones codificadas en binario. Es el sistema de códigos directamente interpretable por un circuito microprogramable.

Fue el primer lenguaje utilizado para la programación, cada máquina tenía su propio conjunto de instrucciones codificadas en ceros y unos. Cuando un algoritmo está escrito en este tipo de lenguaje, decimos que está en código máquina.

Programar en este tipo de lenguaje presenta los siguientes inconvenientes:

- Cada programa es válido sólo para un tipo de procesador.
- La lectura o interpretación de los programas es extremadamente difícil.
- Los programadores deben memorizar largas combinaciones de ceros y unos.
- Los programadores se encargaban de introducir los códigos binarios en el computador, lo que provocaba largos tiempos de preparación y posibles errores.

Dada su complejidad, fue sustituido por otros lenguajes más sencillos. A pesar de ello, todos los programas deben ser traducidos al lenguaje máquina para para poder ser ejecutados.

#### 6.2.- Lenguaje ensamblador

Es la evolución del lenguaje máquina. Las instrucciones ya no son secuencias binarias, se sustituyen por códigos de operación que describen una operación elemental del procesador. Es un lenguaje de bajo nivel, al igual que el lenguaje máquina, ya que dependen directamente del hardware donde son ejecutados. Normalmente, una instrucción en ensamblador se corresponde con una instrucción de lenguaje máquina.

Mnemotécnico: palabras especiales que sustituyen largas secuencias de ceros y unos, utilizadas para referirse a diferentes operaciones disponibles. En ensamblador, cada instrucción (mnemotécnico) se corresponde a una instrucción del procesador. 

Este lenguaje presenta múltiples dificultades:

- Los programas siguen dependiendo directamente del hardware que los soporta.
- Los programadores deben conocer detalladamente la máquina sobre la que programaban.
- La lectura, interpretación o modificación de los programas sigue siendo difícil.

Todo programa escrito en lenguaje ensamblador necesita de un **intermediario** que realice la traducción de cada una de las instrucciones que componen su código al lenguaje máquina correspondiente. Este intermediario es el **programa ensamblador**. El programa original escrito en lenguaje ensamblador constituye el código fuente y el programa traducido al lenguaje máquina se conoce como programa objeto que será directamente ejecutado por la computadora.

#### 6.3.- Lenguajes compilados

Nacieron para paliar los problemas derivados del lenguaje ensamblador. Algunos ejemplos son Pascal, Fortran, Algol, C, C++, etc.

Al ser lenguajes más cercanos al humano, también se les denomina lenguajes de alto nivel. Son más fáciles de utilizar y comprender, las instrucciones que forman parte de estos lenguajes utilizan palabras y signos reconocibles por el programador.

Ventajas:

- Mucho más fáciles de aprender y de utilizar.
- Reducción de tiempo y costes para desarrollar programas.
- Son independientes del hardware, los programas pueden ejecutarse en diferentes tipos de máquina.
- La lectura, interpretación y modificación de los programas es mucho más sencilla.

Desventajas:

- El código objeto generado es menos eficiente que el código generado en lenguaje ensamblador, a pesar de que los compiladores realizan procesos de optimización del código.
- Un programa escrito en un lenguaje de alto nivel también tiene que traducirse a un código que pueda utilizar la máquina. Los programas traductores que realizan esta operación se llaman **compiladores**.

**Compilador**: programa cuya función consiste en traducir el código fuente de un programa escrito en un lenguaje de alto nivel a lenguaje máquina.

El compilador realizará la traducción y además informará de los posibles errores. Una vez subsanados, se generará el programa traducido a código máquina, conocido como **código objeto**. Este programa aún no podrá ser ejecutado hasta que no se le añadan los módulos de enlace o bibliotecas, durante el proceso de **enlazado**. Una vez finalizado el enlazado, se obtiene el código ejecutable.

#### 6.4.- Lenguajes interpretados

Su ejecución se realiza a través de un **intérprete**. Cada instrucción escrita en un lenguaje interpretado se analiza, traduce y ejecuta tras haber sido verificada. Una vez realizado el proceso por el intérprete, la instrucción se ejecuta, pero no se guarda en memoria.

**Intérprete**: programa traductor de un lenguaje de alto nivel en el que el proceso de traducción y de ejecución se llevan a cabo simultáneamente, es decir, la instrucción se pasa a lenguaje máquina y se ejecuta directamente. No se genera programa objeto, ni programa ejecutable.

Los lenguajes interpretados generan programas de menor tamaño que los generados por un compilador, al no guardar el programa traducido a código máquina. Pero son más lentos, ya que han de ser traducidos durante su ejecución. Por otra parte, necesitan disponer en la máquina del programa intérprete ejecutándose, algo que no es necesario en el caso de un programa compilado, para los que sólo es necesario tener el programa ejecutable para poder utilizarlo.

Ejemplos de lenguajes interpretados son Perl, PHP, Python, JavaScript, etc.

A medio camino entre los lenguajes compilados y los interpretados, existen los lenguajes que podemos denominar **pseudo-compilados** o **pseudo-interpretados**, es el caso de Java. Java puede verse como compilado e interpretado a la vez, ya que su código fuente se compila para obtener el código binario en forma de bytecodes, que son estructuras parecidas a las instrucciones máquina, con la importante propiedad de no ser dependientes de ningún tipo de máquina (se detallarán más adelante). Los ficheros que contienen los bytecodes de Java tienen extensión .class. La Máquina Virtual Java se encargará de interpretar este código y, para su ejecución, lo traducirá a código máquina del procesador en particular sobre el que se esté trabajando.

### 7.- El lenguaje de programación Java

#### 7.1.- ¿Qué y cómo es Java?

Java es un lenguaje de **programación orientado a objetos (POO)**. Fue creado para solucionar problemas que los lenguajes anteriores, como C, no podían manejar eficientemente, especialmente con el crecimiento del volumen del código.

La principal virtud de Java es su **independencia del *hardware***. El código se escribe una sola vez y se puede ejecutar en **cualquier plataforma** gracias a la **Java Virtual Machine (JVM)**. La JVM interpreta el código (llamado *bytecode*) y lo convierte en código específico para el sistema operativo donde se ejecuta.

**Características de Java**

- **Orientado a objetos**: se basa en la división de problemas en objetos con propiedades e interacciones, simplificando el desarrollo.
- **Independiente de la arquitectura**: el *bytecode* generado es universal.
- **Sintaxis**: similar a C y C++.
- **Robustez y seguridad**: realiza comprobaciones del código y restringe el acceso a áreas de memoria delicadas.
- **Distribuido**: preparado para aplicaciones de red (TCP/IP).
- **Bibliotecas**: dispone de un amplio conjunto de estas.

#### 7.2.- Breve historia

Java surgió en **1991** en **Sun Microsystems** con el objetivo de crear un lenguaje independiente del dispositivo, inicialmente para pequeños electrónicos. Se renombró a **Java** en **1995** y se lanzó al público como lenguaje para computadoras. Su filosofía de **independencia de plataforma**, potencia, POO y facilidad para aplicaciones de red lo catapultaron a la popularidad. Un punto clave fue su integración en el navegador **Netscape Navigator 2.0**.

La plataforma Java (Java 2 o posterior) incluye:

1.  El lenguaje de programación Java.
2.  **Java Core:** Un conjunto de bibliotecas estándar.
3.  **Herramientas de Desarrollo (JDK):** Incluye el compilador de *bytecodes*, el depurador, etc.
4.  **Entorno de Ejecución (JRE):** La máquina virtual (JVM) que ejecuta el *bytecodes*.

ariantes de la Plataforma Java:V

* **J2SE (Standard Edition):** Para aplicaciones de escritorio y servidores.
* **J2EE (Enterprise Edition):** Para aplicaciones web empresariales y del lado del servidor.
* **Java FX:** Para crear Aplicaciones de Internet Enriquecidas (RIAs) con interfaz multiplataforma.
* **Java Embedded/Card:** Para sistemas embebidos, IoT, y tarjetas inteligentes, respectivamente.

#### 7.3.- La POO y Java

En Java, el código (**métodos**) y los datos (**estado**) se agrupan en **objetos**. Un objeto es una entidad con comportamiento y estado que permite la **reutilización de código**, reduciendo el tiempo de desarrollo.

* **Clases e Instancias:** Los patrones o tipos de objetos se llaman **clases**, y los objetos creados a partir de ellas son **instancias**.
* **Modelo de Construcción:** La POO funciona como unir "bloques de construcción" (objetos pequeños) para crear estructuras más grandes (programas). 
* **Pilares de la POO:** Java incorpora los tres conceptos principales de la POO:
    * **Encapsulación:** Consiste en ocultar el estado (datos) de un objeto para que solo pueda ser modificado mediante sus operaciones (métodos) definidas. Esto aísla y protege los datos.
    * **Herencia:** Permite que una clase nueva (derivada) extienda la funcionalidad de otra (clase base o superclase), especializándola.
    * **Polimorfismo:** Es la capacidad de que varias clases derivadas de una misma clase base implementen un mismo método de manera diferente (ej. un método `mover` funciona distinto para un pez que para un ave).

#### 7.4.- Independencia de la plataforma y trabajo en red

Java se distingue por estas dos características:

* **Independencia de la Plataforma:** Los programas de Java son ejecutables en **cualquier tipo de *hardware***.
    * El código fuente se compila en **Java Bytecode** (instrucciones simplificadas).
    * Este *bytecode* es interpretado y ejecutado por la **Máquina Virtual Java (JVM)**.
    * La JVM es la única parte dependiente del sistema, ya que está escrita en código nativo de la plataforma.
* **Trabajo en Red:** Java ofrece amplias posibilidades para la comunicación **vía TCP/IP**. Dispone de librerías que facilitan la interacción con protocolos como `http` y `ftp`, simplificando las tareas de programación en red.


#### 7.5.- Seguridad y simplicidad

Además de su independencia de plataforma y capacidad de red, Java es popular por dos virtudes clave:

**1. Seguridad**

- **Eliminación de Accesos Peligrosos:** Prohíbe el acceso a zonas de memoria "sensibles".
- **Verificación de Código:** El *bytecode* es rigurosamente comprobado y verificado para garantizar que todas las operaciones, conversiones y usos de clases sean seguras y no produzcan efectos no deseados.
- **Restricciones:** Java restringe la apertura de archivos locales, la ejecución de aplicaciones nativas de la plataforma y el uso de la máquina como puente para operaciones externas.

Java implementa varias capas de *tests* y restricciones para garantizar un **entorno seguro**.

**2. Simplicidad**

- **Simplificación del Código:** Se eliminaron elementos complejos y propensos a errores presentes en C/C++, como:
    * La aritmética de **punteros**.
    * La gestión manual de la memoria.
    * Los registros y la definición manual de tipos.
- **Gestión Automática de Memoria (Garbage Collector):**
    * Java incluye un **Recolector de Basura (*Garbage Collector*)** que libera al programador de la tarea de gestionar la memoria.
    * Cuando un objeto ya no se utiliza, el entorno Java lo borra automáticamente. Esto permite la reutilización de bloques de memoria y disminuye la **fragmentación de memoria**.

#### 7.6.- Java y los Bytecodes

El código Java logra su independencia de la plataforma gracias a un proceso de dos fases que involucra los **Bytecodes** y la **Máquina Virtual Java (JVM)**.

**1. Generación de Bytecodes**

1.  El código fuente de Java (archivos `.java`) se **precompila**.
2.  El resultado son los **Bytecodes** (archivos `.class`), que son un conjunto de instrucciones de lenguaje máquina **no específicas** de ningún procesador o sistema.

**2. Ejecución a través de la JVM**

- Los Bytecodes deben ser interpretados por la **Máquina Virtual Java (JVM)**.
- La JVM es el intérprete específico para cada plataforma (Windows, Linux, etc.) y se encarga de traducir los Bytecodes a **código nativo** que el *hardware* pueda ejecutar. 
- **Verificación de Seguridad:** Antes de ejecutar, la JVM utiliza un verificador de Bytecodes para asegurar la **integridad del sistema**, comprobando que el código cumple las especificaciones, evita desbordamientos de memoria y realiza operaciones seguras.

En conclusión, para ejecutar un programa Java en cualquier sistema, solo es necesario que este cuente con la JVM adecuada. Este mecanismo es el que garantiza la famosa portabilidad de Java.

### 8.- Programas en Java

#### 8.1.- Estructura de un programa

Todo programa en Java, al ser un lenguaje orientado a objetos, se construye alrededor de clases.

| Elemento | Descripción Clave | Ejemplo |
| :--- | :--- | :--- |
| `public class Clase_Principal` | Es la clase principal que contiene todo el programa. Solo una puede ser `public`. El nombre del archivo (`.java`) debe coincidir con el nombre de esta clase. | `public class MiApp { ... }` |
| `public static void main (String[] args)` | Es el método principal de la aplicación, el primero en ejecutarse. | `main` |
| Bloques de Código | Conjuntos de instrucciones agrupados. Definen el alcance de la clase o método. | `{ instrucciones }` |
| Punto y Coma (`;`) | Es obligatorio. Marca el final de cada instrucción de código. | `System.out.println("Hola");` |
| Comentarios | Anotaciones ignoradas por el compilador, usadas para aclaraciones. | `// Comentario de una línea` o `/* Comentario de bloque */` |

#### 8.2.- El entorno básico de desarrollo Java

Para llevar a la práctica la programación en Java, se requieren herramientas específicas.

- **Java Development Kit (JDK)**. Es el entorno básico y gratuito para construir aplicaciones, *applets* y componentes en Java, cuya función es proveer las herramientas para el desarrollo y prueba de programas. Incluye el **compilador** y el **intérprete**, herramientas esenciales para la precompilación y ejecución del código. 

- **Java Runtime Environment (JRE)**. El JDK incluye una implementación del **JRE**, que es la base para la ejecución de los programas Java, ya que incluye la **Máquina Virtual Java (JVM)**, bibliotecas de clases necesarias y otros archivos de soporte.

En resumen, el **JDK** permite **desarrollar** el programa, y el **JRE** (que viene dentro del JDK) permite **ejecutarlo** en cualquier plataforma mediante la **JVM**.

#### 8.3.- La API de Java

Para acelerar el desarrollo de software, Java incluye un amplio conjunto de bibliotecas. La **API de Java** es una biblioteca de clases orientada a objetos incluida en el **JDK**, que proporciona funcionalidades ya hechas y organizadas en paquetes, permitiendo a los programadores desarrollar programas más rápido mediante la reutilización de código.

#### 8.4.- Afinando la configuración

Para que un sistema operativo pueda compilar y ejecutar programas Java desde la línea de comandos, es necesario realizar ajustes en las variables de entorno para que el sistema sepa dónde encontrar los archivos esenciales.

- **La variable `PATH`**. Le indica al sistema operativo dónde encontrar los programas ejecutables (`javac.exe` para compilar y `java.exe` para ejecutar) cuando se usan desde la línea de comandos. Se debe incluir en esta variable la ruta exacta donde se instaló el **JDK** hasta su directorio `bin`.

- **La variable `CLASSPATH`**. Define las rutas donde el **JDK** debe buscar las **clases** necesarias para ejecutar o compilar un programa. Estas clases incluyen las bibliotecas de la **API de Java** y las clases creadas por el usuario. Las rutas pueden incluir directorios o archivos comprimidos en formato `zip` o `jar` que contengan archivos `.class`. Si esta variable no existe en el sistema, debe ser creada.

#### 8.5.- Codificación, compilación y ejecución de aplicaciones

Una vez que el código fuente de un programa Java está escrito (archivo con extensión `.java`) y el entorno configurado, el proceso para obtener una aplicación ejecutable sigue tres pasos básicos.

**1. Codificación**

Se escribe el código fuente en uno o varios archivos que tienen la extensión **`.java`**.

**2. Compilación**

- Se utiliza el compilador **`javac`**  incluido en el JDK. 
- Se ejecuta desde la línea de comandos usando: `javac archivo.java`
- Si no hay errores, el compilador genera un archivo con el mismo nombre y la extensión **`.class`**. Este archivo contiene el **Bytecode** (código precompilado).
- Si el código fuente tiene múltiples clases, se generará **un archivo `.class` por cada clase**.
- Si el compilador detecta errores, los muestra en el terminal. El programador debe corregirlos antes de que se genere el archivo `.class`.

**3. Ejecución**

- Se utiliza el intérprete **`java`** incluido en el JDK.
- La ejecución solo es posible si el archivo contiene el método **`main`**.
- Se ejecuta desde la línea de comandos usando: `java archivo` (se omite la extensión `.class`).

En resumen: se escribe el código (`.java`), se usa **`javac`** para convertirlo en **Bytecode** (`.class`), y finalmente se usa **`java`** para que el intérprete ejecute la aplicación.

#### 8.6.- Tipos de aplicaciones en Java

| Tipo de Aplicación | Descripción y Características Clave |
| :--- | :--- |
| Aplicaciones de consola | Programas independientes que se ejecutan invocando la **JVM**. Carecen de Interfaz Gráfica de Usuario (GUI); leen y escriben a la entrada/salida estándar. Deben incluir obligatoriamente el método **`main`**. |
| Aplicaciones gráficas | Programas independientes que utilizan bibliotecas con capacidades gráficas (como **Swing**) para crear una GUI. También requieren el método **`main`**. |
| Applets | Programas pequeños incrustados en **páginas web** y que se ejecutan en el navegador del **cliente**. No tienen método `main`. Tienen restricciones de seguridad. |
| Servlets | Componentes del lado del **servidor** (Java EE). Están diseñados para desarrollar aplicaciones web que interactúan con las peticiones recibidas de los clientes. |
| Midlets | Aplicaciones creadas específicamente para la máquina virtual **Java Micro Edition (Java ME)**, destinadas a sistemas de propósito simple o **dispositivos móviles**. |

### 9.- Entornos Integrados de Desarrollo (IDE)

#### 9.1.- ¿Qué son?

Un Entorno Integrado de Desarrollo (IDE) es una aplicación que centraliza todas las herramientas necesarias para el desarrollo de software en un solo programa, ofreciendo una interfaz gráfica amigable. Ofrece funcionalidades que mejoran la productividad, como código fuente coloreado, plantillas y gestión de proyectos.

El IDE es solo una "fachada", ya que **requiere tener instalado el compilador (JDK)** para funcionar. Sin el compilador subyacente, el IDE no puede construir ni ejecutar el programa.

#### 9.2.- IDE's actuales

Existe una amplia variedad de IDEs, tanto gratuitos como de pago. Los más utilizados por la comunidad de programadores Java son **Eclipse**, **IntelliJ IDEA** y **NetBeans**.

| Licencia | Ejemplos |
| :--- | :--- |
| Gratuitos | NetBeans, Eclipse, BlueJ, Jgrasp, Jcreator LE |
| De pago | IntelliJ IDEA, Jbuilder, Jcreator, JDeveloper |

#### 9.3.- El entorno NetBeans

**1. Características**

- Inicialmente centrado en Java, aunque soporta otros lenguajes (C, C++, PHP, Javascript, etc.).
- Proyecto de código abierto de gran éxito, libre y gratuito , con el apoyo de una gran comunidad y empresas.
- Desde su origen como el primer IDE escrito en Java, ha competido con Eclipse para ser la plataforma principal de desarrollo Java.

**2. Capacidades**

- Permite escribir código para diversos lenguajes además de Java.
- Facilita la creación de aplicaciones J2EE al incorporar servidores de aplicaciones (como Glassfish y Tomcat).
- Permite crear aplicaciones Swing de manera sencilla, similar al estilo de otros IDEs visuales.
- Capacidad para crear aplicaciones JME (Java Micro Edition) para dispositivos móviles.

**3. Arquitectura Modular**

- Las aplicaciones en NetBeans se desarrollan a partir de componentes llamados módulos. Un módulo es un archivo Java que contiene clases escritas para interactuar con las APIs de NetBeans.
- Esta arquitectura modular permite que las aplicaciones se extiendan fácilmente con la adición de nuevos módulos desarrollados independientemente.

#### 9.5.- Aspecto del entorno y gestión de proyectos

La vista `Archivos` de NetBeans muestra la estructura del proyecto.

- `src`: contiene el código fuente (.java).
- `build`: contiene los archivos compilados (.class) listos para ejecutar.
- El resto de archivos son de configuración interna de NetBeans y no deben borrarse.

## UD2.- Creación de mi primer programa

### 1. Introducción

Los programas de ordenador son aplicaciones que **resuelven problemas** mediante la ejecución de tareas específicas, como usar el correo electrónico o navegar por internet. Para desarrollar *software*, es crucial elegir un **lenguaje de programación** que se domine y que no imponga limitaciones en el desarrollo multiplataforma.

### 2.- Variables e identificadores

Un programa utiliza **variables** para manejar los datos que se usan en cálculos, informes, o interacciones con el usuario. Una variable es simplemente una **zona de la memoria** del ordenador reservada para almacenar un valor que se usará más adelante.

Toda variable se define por tres características principales:

1.  **Nombre (Identificador):** nombre único que permite al programa acceder y manipular el valor almacenado en esa zona de memoria.
2.  **Tipo de dato:** especifica la clase de información que guarda la variable (por ejemplo, números enteros, caracteres, etc.).
3.  **Rango de valores:** conjunto de valores que la variable puede admitir, determinado por su tipo de dato (y por tanto, por el tamaño que ocupa en la memoria).

El **identificador** es el nombre específico que se le da a la variable y a otros elementos del programa.

Las variables se deben **declarar** antes de su uso. La sintaxis general es:

```
tipoVariable identificadorVariable;
```

#### 2.1.- Identificadores

Un **identificador** en Java es el nombre que se le da a una variable, función o clase. Debe ser una secuencia ilimitada **sin espacios** de letras y dígitos Unicode, comenzando obligatoriamente con una **letra**, un **símbolo de subrayado (`_`)** o el **símbolo dólar (`$`)**.

*Ejemplos válidos:* `x5`, `NUM_MAX`, `numCuenta`, o incluso caracteres de otros alfabetos como `ατη`.

**Código Unicode**

**Unicode** es un **sistema de codificación de caracteres** que recoge prácticamente todos los alfabetos importantes del mundo (Griego, Japonés, etc.).

- **Ventaja en Java:** Permite usar caracteres locales en los identificadores (como la `ñ`), haciendo el código más significativo y fácil de entender para los programadores locales.
- **Funcionamiento:**
    - Asigna un **número entero unívoco** a cada carácter. Por ejemplo, a la letra `ñ` le corresponde el entero 164.
    - Originalmente usaba 16 bits (65.536 caracteres), pero ahora utiliza formatos variables como **UTF-8, UTF-16 o UTF-32**.
    - Es **compatible con ASCII**: a los caracteres ASCII se les asignan los mismos 8 bits, precedidos por 8 bits a cero.

#### 2.2.- Convenios y reglas para nombrar variables

Aunque Java permite nombrar identificadores con gran libertad, existen normas de estilo que se usan de forma generalizada para escribir código claro y mantenible:

- **Sensibilidad a mayúsculas:** Java **distingue** entre mayúsculas y minúsculas. `Alumno` y `alumno` son dos variables diferentes.
- **Restricción de valores:** no se puede usar como identificador el valor booleano (`true` o `false`) ni el valor nulo (`null`).
- **Caracteres iniciales:** no se suelen usar identificadores que comiencen con **`$`** o **`_`**; por convenio, el símbolo dólar (`$`) **no se utiliza nunca**.
- **Descriptividad:** los identificadores deben ser **descriptivos** (ej., `FicheroClientes` en lugar de `Cl33`), lo cual mejora la legibilidad y ayuda a **autodocumentar** el código.

Existen convenciones de estilo que no son obligatorias, pero son la práctica estándar en la comunidad Java:

| Identificador | Convención | Ejemplo |
| :--- | :--- | :--- |
| Nombre de variable | Comienza por letra **minúscula**. Si tiene varias palabras, se escriben juntas y las palabras subsiguientes comienzan con mayúscula (formato *camelCase*) | `numAlumnos`, `sumaTotal` |
| Nombre de constante | En **letras mayúsculas**, separando las palabras con un **guion bajo** (`_`). El guion bajo no se utiliza en ningún otro sitio por convenio | `TAM_MAX`, `PI` |
| Nombre de una clase | Comienza por letra **mayúscula** | `String`, `MiTipo` |
|*Nombre de función (método) | Comienza con letra **minúscula** | `modificaValor`, `obtieneDato` |

#### 2.3. Palabras reservadas

Las **palabras reservadas** (*keywords* o palabras clave) son secuencias de caracteres, formadas con letras **ASCII**, cuyo uso está **exclusivamente reservado** para el lenguaje Java. Por esta razón, **no pueden utilizarse** para nombrar identificadores (variables, clases, funciones, etc.).

**Notas sobre palabras clave y literales**

* **Uso actual:** algunas palabras reservadas como **`const`** y **`goto`** están reservadas pero no se utilizan en la implementación actual del lenguaje Java.
* **Literales:** existen términos que, aunque no pueden ser usados como identificadores, **no son técnicamente palabras reservadas**, sino **literales**. Este es el caso de los valores booleanos (**`true`** y **`false`**) y el valor nulo (**`null`**).
* **Ayuda visual:** los editores y entornos de desarrollo integrado (**IDE**) utilizan **colores** para diferenciar automáticamente las palabras reservadas del resto del código, lo que facilita la lectura y la detección de errores de sintaxis.

**Palabras clave en Java**

| | | | | |
| :--- | :--- | :--- | :--- | :--- |
| `abstract` | `continue` | `for` | `new` | `switch` |
| `assert` | `default` | `goto` | `package` | `synchronized` |
| `boolean` | `do` | `if` | `private` | `this` |
| `break` | `double` | `implements` | `protected` | `throw` |
| `byte` | `else` | `import` | `public` | `throws` |
| `case` | `enum` | `instanceof` | `return` | `transient` |
| `catch` | `extends` | `int` | `short` | `try` |
| `char` | `final` | `interface` | `static` | `void` |
| `class` | `finally` | `long` | `strictfp` | `volatile` |
| `const` | `float` | `native` | `super` | `while` |

#### 2.4.- Tipos de variables

Java clasifica las variables basándose en varios factores, como el tipo de información que contienen, si su valor cambia, o el lugar donde se declaran en el código.

**Clasificación por tipo de información**

| Tipo de Variable | Descripción |
| :--- | :--- |
| **Variables de tipos primitivos** | Contienen valores simples (como números o caracteres). |
| **Variables referencia** | Almacenan la **dirección** o referencia a un objeto en memoria (no el objeto en sí). |

**Clasificación por cambio de valor**

| Tipo de Variable | Descripción |
| :--- | :--- |
| **Variables** | Su valor **puede cambiar** a lo largo de la ejecución del programa. |
| **Constantes (Variables finales)** | Su valor **no cambia** durante la ejecución del programa. Se definen para mantener un valor fijo. |

**Clasificación por ubicación**

| Tipo de Variable | Ubicación | Ciclo de Vida |
| :--- | :--- | :--- |
| **Variables miembro** | Se crean **dentro de una clase**, pero **fuera de cualquier método**. | Pertenecen a los objetos creados a partir de la clase y pueden ser primitivas o referencia, variables o constantes. |
| **Variables locales** | Se crean y usan **dentro de un método** o dentro de cualquier bloque de código. | **Dejan de existir** cuando la ejecución de ese método o bloque de código finaliza. Pueden ser primitivas o referencia. | 

### 3.- Los tipos de datos
