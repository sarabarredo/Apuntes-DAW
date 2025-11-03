---
id: programacion
sidebar_position: 2
title: Programación
---

# UD1.- Introducción a la programación

## 1.- Introducción

En esta primera unidad realizaremos un recorrido por los conceptos fundamentales de la programación de aplicaciones. Iniciaremos nuestro camino conociendo con qué vamos a trabajar, qué técnicas podemos emplear y qué es lo que pretendemos conseguir. Continuaremos con el análisis de las diferentes formas de programación existentes, identificaremos qué fases conforman el desarrollo de una aplicación software y avanzaremos detallando las características relevantes de cada uno de los lenguajes de programación disponibles, para posteriormente, realizar una visión general del lenguaje de programación Java. Finalmente, tendremos la oportunidad de conocer con qué herramientas podríamos desarrollar nuestros programas, escogiendo entre una de ellas para ponernos manos a la obra utilizando el lenguaje Java.

## 2.- Programas y programación
### 2.1.- Buscando una solución

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

### 2.2.- Algoritmos y programas

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

## 3.- Paradigmas de la programación

Un **Paradigma de programación** es un modelo básico para el diseño y la implementación de programas. Este modelo determinará como será el proceso de diseño y la estructura final del programa. Algunos de ellos son:

- **Programación declarativa:** se basa en el desarrollo de algoritmos aplicando una especificación de un conjunto de condiciones, proposiciones, afirmaciones y restricciones que describen el problema. Las sentencias utilizadas describen el problema que se quiere solucionar, pero no la instrucciones necesarias para llegar a la solución (ej. SQL). Dentro de este paradigma, se encuentran la **programación funcional** y la **programación lógica**. 
- **Programación imperativa:** se basa en el desarrollo de algoritmos detallando de forma clara y específica los comandos a ejecutar para, a través del paso por diferentes estados,  llegar a la solución. Se basa en el uso de variables, tipos de datos, expresiones y estructuras de control del flujo de ejecución (ej. Python, Java...). Dentro de este paradigma se encuentran la **programación no estructurada**, la **programación estructurada**, la **programación orientada a objetos**, la **programación orientada a eventos**...

Puede haber lenguajes de programación que no se clasifiquen únicamente dentro de uno de ellos.

El objetivo que se busca con la aplicación de diferentes enfoques, es el de reducir la dificultad para el desarrollo y mantenimiento de las aplicaciones, mejorar el rendimiento del programador y mejorar la productividad y calidad de los programas.

## 4.- Fases de la programación

Sea cual sea el estilo que escojamos a la hora de automatizar una determinada tarea, debemos realizar el proceso aplicando un método a nuestro trabajo.

El proceso de creación de software puede dividirse en diferentes fases:

1. Resolución del problema.
2. Implementación.
3. Explotación y mantenimiento.

### 4.1.- Resolución del problema

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

### 4.2.- Implementación

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

### 4.3.- Explotación

Cuando el programa ya está instalado en el sistema y está siendo de utilidad para los usuarios, decimos que se encuentra en fase de explotación.

Periódicamente será necesario realizar evaluaciones y, si es necesario, llevar a cabo modificaciones para que el programa se adapte o actualice a nuevas necesidades, pudiendo también corregirse errores no detectados anteriormente. Este proceso recibe el nombre de mantenimiento del software.

Será imprescindible añadir una documentación adecuada que facilite al programador la comprensión, uso y modificación de dichos programas.

## 5.- Ciclo de vida del software

Sean cuales sean las fases en las que realicemos el proceso de desarrollo de software, y casi independientemente de él, siempre se debe aplicar un modelo de ciclo de vida.

El Ciclo de vida del software es una sucesión de estados o fases por las cuales pasa un software a lo largo de su "vida".

El proceso de desarrollo puede involucrar siempre las siguientes etapas mínimas:

    Especificación y Análisis de requisitos.
    Diseño.
    Codificación.
    Pruebas.
    Instalación y paso a Producción.
    Mantenimiento.

Aprenderás mucho más sobre el ciclo de vida del software en el Módulo Profesional "Entornos de Desarrollo".
6.- Lenguajes de programación.
