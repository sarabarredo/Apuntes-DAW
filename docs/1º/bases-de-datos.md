---
id: bases-de-datos
sidebar_position: 3
title: Bases de Datos
toc_max_heading_level: 3
---

## **UD1.- Almacenamiento de la información**

![Esquema Unidad 1 Bases de Datos](../../static/img/bases-de-datos-unidad-1.jpg)

### 1.- Introducción

Casi todo lo que nos rodea, en alguna medida, está relacionado con los datos, su almacenamiento y su gestión. El gran volumen de datos que actualmente manejamos y sus innumerables posibilidades requieren de la existencia de técnicos perfectamente formados y capaces de trabajar con ellos.

En esta primera unidad comenzaremos conociendo los primeros sistemas basados en ficheros para el almacenamiento y gestión de la información. Seguidamente, se desarrollarán los conceptos y definiciones básicas relacionadas con las bases de datos, posteriormente analizaremos sus modelos y tipos, un poco más adelante, podremos conocer las características y capacidades de los sistemas gestores de bases de datos y finalmente, identificaremos las herramientas reales con las que llevar a cabo la gestión de dichas bases.

### 2.- Los ficheros de información

#### 2.1.- ¿Qué es un fichero?

Un **fichero o archivo** es conjunto de información relacionada, tratada como un todo y organizada de forma estructurada. Es una secuencia de dígitos binarios que organiza información relacionada con un mismo aspecto.

Los ficheros están formados por registros lógicos que contienen datos relativos a un mismo elemento u objeto (por ejemplo, los datos de usuarios de una plataforma educativa). A su vez, los registros están divididos en campos que contienen cada una de las informaciones elementales que forman un registro (por ejemplo, el nombre del usuario o su dirección de correo electrónico).

Los datos están almacenados de tal forma que se puedan añadir, suprimir, actualizar o consultar individualmente en cualquier momento.

Como los ficheros suelen ser muy voluminosos, solo se pueden llevar a la memoria principal partes de ellos para poder procesarlos. La cantidad de información que es transferida entre el soporte en el que se almacena el fichero, y la memoria principal del ordenador, en una sola operación de lectura/grabación, recibe el nombre de **registro físico** o **bloque**.

Normalmente en cada operación de lectura/grabación se transfieren varios registros del fichero, es decir, un bloque suele contener varios registros lógicos. Al número de registros que entran en un bloque se le conoce con el nombre de **factor de blocaje** o **factor de bloqueo**, y a esta operación de agrupar varios registros en un bloque se le llama **bloqueo de registros**.

#### 2.2.- Tipos de ficheros

Según la función que vayan a desempeñar los ficheros, éstos pueden ser clasificados de varias maneras.

a. **Ficheros permanentes**: contienen los datos necesarios para el funcionamiento de una aplicación. Se subdividen en:

    - **Ficheros maestros**: contienen el estado actual de los datos que pueden modificarse desde la aplicación. Es la parte central de la aplicación, su núcleo (ej. -> los datos de los usuarios de una plataforma).

    - **Ficheros constantes**: incluyen datos fijos para la aplicación. No suelen ser modificados y se accede a ellos para realización de consultas (ej. -> archivo con códigos postales). 

    - **Ficheros históricos**: contienen datos que fueron considerados como actuales en un periodo o situación anterior. Se utilizan para la reconstrucción de situaciones (ej. -> usuarios que han sido dados de baja en una plataforma). 

b. **Ficheros temporales**: almacenan información útil para una parte de la aplicación, pero no para toda ella. Son generados a partir de datos de ficheros permanentes y tienen un corto periodo de existencia. Se subdividen en:

    - **Ficheros intermedios**: almacenan resultados de una aplicación que serán utilizados por otra.

    - **Ficheros de maniobras**: almacenan datos de una aplicación que no pueden ser mantenidos en memoria principal por falta de espacio.

    - **Ficheros de resultados**: almacenan datos que van a ser transferidos a un dispositivo de salida.

#### 2.3.- Los soportes de información

Los ficheros se almacenan en soportes de información manejados por dispositivos periféricos del ordenador, que permiten leer y grabar datos en el soporte. Los soportes más utilizados para almacenar los ficheros son las **cintas magnéticas** y los **discos** (magnéticos, ópticos o magneto-ópticos).

Inicialmente, los primeros sistemas de almacenamiento físico eran tambores de cinta magnética. Tenían unas dimensiones parecidas a los discos de vinilo. Estos tambores funcionaban de manera similar a los antiguos casetes, pero sus mayores dimensiones les permitían almacenar gran cantidad de datos en formato digital, es decir en ceros y unos, en orden secuencial.

Posteriormente, los sistemas de almacenamiento de información comenzaron a cambiar de la mano de los avances en el hardware, en concreto con la aparición del disquete y del disco duro. Eran dispositivos de acceso aleatorio, no siendo necesario en ellos pasar por todos los datos desde el inicio hasta la zona donde se encontraba la información que nos interesaba.

Por tanto, se distinguen dos tipos de soportes para el almacenamiento de datos:

- **De acceso directo** (*ej. -> discos*): el acceso a los datos puede hacerse de forma directa, pudiendo colocarnos en la posición que nos interesa y leer a partir de ella. Son los más usados. 

- **De acceso secuencial** (*ej. -> cintas magnéticas*): si deseamos leer un dato que está en la mitad de la cinta, tendremos que leer todo lo que hay hasta llegar a esa posición. Se suelen usar en copias de seguridad.

#### 2.4.- Métodos de acceso

A medida que la tecnología ha ido evolucionando, el acceso a la información contenida en los diferentes tipos de ficheros ha variado mucho. Los objetivos fundamentales de estas modificaciones pueden resumirse en los siguientes puntos:

- Proporcionar un acceso rápido a los registros.  
- Economizar el almacenamiento.  
- Facilitar la actualización de los registros.  
- Permitir que la estructura refleje la organización real de la información.

Las distintas formas de organizar un fichero en un soporte de memoria (también conocido como "*métodos de acceso a los ficheros*"), son: 

```mermaid
graph TD
    A[Métodos de acceso a ficheros] --> B[Secuencial]
    A --> C[Secuencial Indexado]
    A --> D[Directo]
    
    B --> E[Encadenado]
    
    D --> F[Acceso Directo]
    D --> G[Acceso Indexado]
    D --> H["Acceso Calculado (Hash)"]

    style A fill:#FFB6C1,color:black,stroke:#FF69B4,stroke-width:2px
    style B fill:#87CEEB,color:black,stroke:#1E90FF
    style C fill:#87CEEB,color:black,stroke:#1E90FF
    style D fill:#87CEEB,color:black,stroke:#1E90FF
    style E fill:#FFFACD,color:black,stroke:#DAA520
    style F fill:#E8F5E8,color:black,stroke:#A5D6A7
    style G fill:#E8F5E8,color:black,stroke:#A5D6A7
    style H fill:#E8F5E8,color:black,stroke:#A5D6A7
```

A continuación, se detallarán las características de cada uno de estos métodos.

#### 2.5.- Fichero secuencial

Sus registros están almacenados de forma contigua de manera que, la única forma de acceder a él, es leyendo un registro tras otro desde el principio hasta el final. En los ficheros secuenciales suele haber una marca indicativa del fin del fichero, que suele denominarse EOF (End of File). Para detectar el final del fichero sólo es necesario encontrar la marca EOF.

Este tipo de ficheros pueden utilizar dispositivos o soportes no direccionables o de acceso secuencial, como son las cintas magnéticas de almacenamiento de datos. También se utiliza en los CD de audio y los DVD de vídeo, en los que la música o las imágenes se almacenan a lo largo de una espiral continua.

Los registros almacenados se identifican por medio de una información ubicada en uno de sus campos. A este campo se le denomina clave o llave. Si se ordena un archivo secuencial por su clave, es más rápido realizar cualquier operación de lectura o escritura.

Características de estos ficheros:

- La lectura siempre se realiza hacia delante.  
- Son monousuario.  
- Tienen una estructura rígida de campos, por lo que todos los registros deben aparecer en orden.  
- El modo de apertura del fichero condiciona la lectura o escritura.  
- Aprovechan al máximo el soporte de almacenamiento al no dejar huecos vacíos.  
- Se pueden grabar en cualquier tipo de soporte, tanto en secuenciales como direccionables.  
- Todos los lenguajes de programación disponen de instrucciones para trabajar con este tipo de ficheros.  
-  No se pueden insertar registros entre los que ya están grabados.

#### 2.6.- Fichero de acceso directo o aleatorio

En este tipo de ficheros se puede acceder a un registro indicando la posición relativa del mismo dentro del archivo, o a través de una clave que forma parte del registro como un campo más. Estos archivos deben almacenarse en dispositivos de memoria masiva de acceso directo.

- Campo clave: campo que permite identificar y localizar un registro de manera ágil y organizada.

Cada uno de los registros se guarda en una posición física, que dependerá del espacio disponible en memoria masiva, de ahí que la distribución de los registros sea aleatoria dentro del soporte de almacenamiento. Para acceder a la posición física de un registro se utiliza una dirección o índice, no siendo necesario recorrer todo el fichero para encontrar un determinado registro.

A través de una transformación específica aplicada a la clave, se obtendrá la dirección física en la que se encuentra el registro. Según la forma de realizar esta transformación, existen diferentes modos de acceso:

- **Acceso directo:** la clave lleva directamente a la dirección.
- **Acceso indexado:** la clave lleva a un índice y éste lleva a la dirección.
- **Acceso calculado:** la clave, combinada con una función matemática, nos da la dirección.

En el **acceso directo** la clave coincide con la dirección, debiendo ser numérica y comprendida dentro del rango de valores de las direcciones. Es el método más rápido.

La medida básica de posicionamiento del puntero en el fichero es el byte, dependiendo del tipo de codificación de caracteres que empleemos (Unicode, ANSI) se utilizarán 1 o 2 bytes por carácter respectivamente. Teniendo esto en cuenta, el puntero avanzará de uno en uno o de dos en dos bytes para poder leer o escribir cada carácter.

Características de estos ficheros:

- Posicionamiento inmediato.
- Registros de longitud fija.  
- Apertura del fichero en modo mixto, para lectura y escritura.  
- Son multiusuario.  
- Los registros se borran colocando un cero en la posición que ocupan.  
- Permiten la utilización de algoritmos de compactación de huecos.  
- Los archivos se crean con un tamaño definido (con un máximo de registros establecido durante la creación).  
- Esta organización sólo es posible en soportes direccionables.  
- Se usan cuando el acceso a los datos de un registro se hace siempre empleando la misma clave y la velocidad de acceso a un registro es lo que más nos importa.  
- Permiten la actualización de los registros en el mismo fichero, sin necesidad de copiar el fichero.  
- Permiten realizar procesos de actualización en tiempo real.

#### 2.7.- Ficheros indexados

Se basan en la utilización de índices en el almacenamiento de los registros, que permiten el acceso a un registro del fichero de forma directa sin tener que leer los anteriores. Estos índices son similares a los de los libros.

Existirá una zona de registros en la que se encuentran los datos del archivo y una zona de índices, que contiene una tabla con las claves de los registros y las posiciones donde se encuentran los mismos. La tabla de índices estará ordenada por el campo clave.

La tabla de índices será cargada en memoria principal para realizar en ella la búsqueda de la fila correspondiente a la clave del registro a encontrar, obteniéndose así la dirección donde se encuentra el registro. Una vez localizada la dirección, sólo hay que acceder a la zona de registros en el soporte de almacenamiento y posicionarnos en la dirección indicada. Puesto que la tabla debe prever la inclusión de todas las direcciones posibles del archivo, su principal inconveniente resulta determinar su tamaño y mantenerla ordenada por los valores de la clave.

Características de estos ficheros:

- El diseño del registro tiene que tener un campo, o combinación de campos, que permita identificar cada registro de forma única, es decir, que no pueda haber dos registros que tengan la misma información en él. A este campo se le llama campo clave y es el que va a servir de índice. Un mismo fichero puede tener mas de un campo clave, pero al menos uno de ellos no admitirá valores duplicados. Será la clave primaria. A las restantes se les llama claves alternativas.  
- Permiten utilizar el modo de acceso secuencial y el modo de acceso directo para leer la información guardada en sus registros.  
- Para acceder a este tipo de ficheros utilizando el modo de acceso directo se hace conociendo el contenido del campo clave del registro que queremos localizar. Con esa información el sistema operativo puede consultar el índice y conocer la posición del registro dentro del fichero.  
- Para acceder a este tipo de ficheros utilizando el modo de acceso secuencial los registros son leídos ordenados por el contenido del campo clave, independientemente del orden en que se fueron grabando (el orden lógico no es igual al orden físico), debido a que el acceso a los datos se hace a través del índice, que para hacer más fácil la búsqueda de los registros, permanece siempre ordenado por el campo clave.  
- Solamente se puede grabar en un soporte direccionable. Por ejemplo, un disco magnético. Si esto no fuera así, no podría emplear el acceso directo.

#### 2.8.- Otros (secuenciales indexados y hash)

**Ficheros secuenciales indexados**

Al igual que en los ficheros indexados, existe una zona de índices y otra zona de registros de datos, pero esta última se encuentra dividida en segmentos (bloques de registros) ordenados.

En la tabla de índices, cada fila hace referencia a cada uno de los segmentos. La clave corresponde al último registro y el índice apunta al registro inicial. Una vez que se accede al primer registro del segmento, dentro de él se localiza (de forma secuencial) el registro buscado.

Esta organización es muy utilizada, tanto para procesos en los que intervienen pocos registros como para aquellos en los que se maneja el fichero completo.

Características de estos ficheros:

- Permite el acceso secuencial. Esto es muy interesante cuando la tasa de actividad es alta. En el acceso secuencial, además, los registros se leen ordenados por el campo clave.  
- Permite el acceso directo a los registros. Realmente emula el acceso directo, empleando para ello las tablas de índices. Primero busca la clave en el área de índices y luego va a leer al área de datos en la dirección que le indica la tabla.  
- Se pueden actualizar los registros en el mismo fichero, sin necesidad de crear un fichero nuevo de copia en el proceso de actualización.  
- Ocupa más espacio en el disco que los ficheros secuenciales, debido al uso del área de índices.  
- Solo se pueden utilizar soportes direccionables.  
- Obliga a una inversión económica mayor, por la necesidad de programas y, a veces, hardware más sofisticado.

**Ficheros de acceso calculado o hash**

La técnica del acceso calculado o hash permite accesos más rápidos, ya que se utiliza una función matemática (*hashing*) que, a partir de la clave, genera la dirección de cada registro del archivo. Si la clave es alfanumérica, deberá previamente ser transformada en un número.

El mayor problema que presenta este tipo de ficheros es que, a partir de diferentes claves se obtenga la misma dirección al aplicar la función matemática o transformación. A este problema se le denomina colisión, y las claves que generan la misma dirección se conocen como sinónimos. Para resolver este problema se aplican diferentes métodos, como tener un bloque de excedentes o zona de sinónimos, o crear un archivo de sinónimos, etc.

Para llevar a cabo la transformación existen multitud de métodos, siendo algunos:

- **Módulo**: la dirección será igual al resto de la división entera entre la clave y el número de registros.  
- **Extracción**: la dirección será igual a una parte de las cifras que se extraen de la clave.

Una buena transformación o función de hash, será aquella que produzca el menor número de colisiones. En este caso hay que buscar una función, a ser posible biunívoca, que relacione los posibles valores de la clave con el conjunto de números correlativos de dirección. Esta función consistirá en realizar una serie de cálculos matemáticos con el valor de la clave hasta obtener un número entre 1 y n, siendo n el número de direcciones que tiene el fichero.

#### 2.9.- Parámetros de utilización.

En función del uso que se vaya a dar al fichero, serán adecuados unos tipos u otros de organización. Mediante la utilización de parámetros de referencia, podremos determinar el uso de un fichero. Estos parámetros son:

a. **Capacidad o volumen**: es el espacio, en caracteres, que ocupa el fichero. La capacidad podrá calcularse multiplicando el número previsto de registros por la longitud media de cada registro.

b. **Actividad**: permite conocer la cantidad de consultas y modificaciones que se realizan en el fichero. Para poder especificar la actividad se deben tener en cuenta:
    - **Tasa de consulta o modificación**: que es el porcentaje de registros consultados o modificados en cada tratamiento del fichero, respecto al número total de registros contenidos en él.
    - **Frecuencia de consulta o modificación**: número de veces que se accede al fichero para hacer una consulta o modificación en un periodo de tiempo fijo.

c. **Volatilidad**: mide la cantidad de inserciones y borrados que se efectúan en un fichero. Para determinar la volatilidad es necesario conocer:
    - **Tasa de renovación**: es el tanto por ciento de registros renovados en cada tratamiento del fichero, respecto al número total de registros contenidos en él.
    - **Frecuencia de renovación**: es el número de veces que se accede al fichero para renovarlo en un periodo de tiempo fijo.

d. **Crecimiento**: es la variación de la capacidad del fichero y se mide con la tasa de crecimiento, que es el porcentaje de registros en que aumenta el fichero en cada tratamiento.

### 3.- Bases de datos

Si las aplicaciones, al ser diseñadas, deben depender directamente de sus ficheros o archivos, se pierde independencia y surgen serios inconvenientes (información duplicada, incoherencia de datos, fallos de seguridad, etc). Para solucionarlo, aparecen las bases de datos. 

Una base de datos permitirá reunir toda la información relacionada en un único sistema de almacenamiento, pudiendo cualquier aplicación utilizarla de manera independiente y ofreciendo una mejora en el tratamiento de la información, así como una evolución para el desarrollo de aplicaciones.

#### 3.1.- Conceptos

**Base de datos**: colección de datos relacionados lógicamente entre sí, con una definición y descripción comunes y que están estructurados de una determinada manera. Es un conjunto estructurado de datos que representa entidades y sus interrelaciones, almacenados con la mínima redundancia y posibilitando el acceso a ellos eficientemente por parte de varias aplicaciones y usuarios.

La base de datos no sólo contiene los datos de la organización, también almacena una descripción de dichos datos. Esta descripción es lo que se denomina **metadatos**, se almacena en el **diccionario de datos** o **catálogo** y es lo que permite que exista **independencia de datos** lógica-física.

Una base de datos constará de:

- **Entidades**: objeto real o abstracto con características diferenciadoras de otros, del que se almacena información en la base de datos. (ej. -> perro).
- **Atributos**: datos que se almacenan de la entidad. Cualquier propiedad o característica de una entidad puede ser atributo. (ej. -> raza).
- **Registros**: donde se almacena la información de cada entidad. Es un conjunto de atributos que contienen los datos que pertenecen a una misma repetición de entidad (ej. -> labrador).
- **Campos**: donde se almacenan los atributos de cada registro (ej. -> valor "labrador").

Ventajas del uso de bases de datos:

- **Acceso múltiple**: diversos usuarios o aplicaciones podrán acceder a la base de datos.  
- **Utilización múltiple**: cada uno de los usuarios o aplicaciones podrán disponer de una visión particular de la estructura de la base de datos, de tal manera que cada uno de ellos accederá sólo a la parte que realmente le corresponde.  
- **Flexibilidad**: la forma de acceder a la información puede ser establecida de diferentes maneras, ofreciendo tiempos de respuesta muy reducidos.  
- **Confidencialidad y seguridad**: el control del acceso a los datos podrá ser establecido para que unos usuarios o aplicaciones puedan acceder a unos datos y a otros no, impidiendo a los usuarios no autorizados la utilización de la base de datos.  
- **Protección contra fallos**: en caso de errores en la información, existen mecanismos bien definidos que permiten la recuperación de los datos de forma fiable.  
- **Independencia física**: un cambio de soporte físico de los datos (por ejemplo: el tipo de discos), no afectaría a la base de datos o a las aplicaciones que acceden a ellos.  
- **Independencia lógica**: los cambios realizados en la base de datos no afectan a las aplicaciones que la usan.  
- **Redundancia**: los datos se almacenan, por lo general, una única vez. Aunque si es necesario, podríamos repetir información de manera controlada.  
- **Interfaz de alto nivel**: mediante la utilización de lenguajes de alto nivel puede utilizarse la base de datos de manera sencilla y cómoda.  
- **Consulta directa**: existe una herramienta para poder acceder a los datos interactivamente.

#### 3.2.- Usos

Existen cuatro tipos de personas que pueden hacer uso de una base de datos: 

- El administrador
- Los diseñadores de la base de datos
- Los programadores de aplicaciones
- Los usuarios finales

En la siguiente tabla se muestran las funciones y características de cada uno de estos usuarios:

| Usuario | Funciones y características |
|----------|----------|
| **Administrador** | Gestiona el funcionamiento físico, la seguridad y el acceso a la base de datos |
| **Diseñadores** | Crean la estructura lógica de la base de datos (datos, relaciones y restricciones) |
| **Programadores** | Desarrollan las aplicaciones que los usuarios finales emplean para interactuar con los datos |
| **Usuarios finales** | Son los clientes que utilizan la base de datos para gestionar su información |

Las bases de datos se utilizan para almacenar y gestionar información de forma organizada en prácticamente todos los ámbitos, como la banca, las telecomunicaciones, la educación, la medicina, el transporte, el comercio y los servicios públicos.

#### 3.3.- Ubicación de la información

Las bases de datos normalmente se almacenan y localizan en discos duros y otros dispositivos de almacenamiento, a los que se accede a través de un ordenador. Una gran base de datos puede necesitar servidores en lugares diferentes, y viceversa, pequeñas bases de datos pueden existir como archivos en el disco duro de un único equipo.

A continuación, se exponen los sistemas de almacenamiento de información más utilizados para el despliegue de bases de datos:

- **Discos SATA.** Discos de uso común, con buen balance entre capacidad y costo. Han evolucionado en velocidad (SATA I: 150 MB/s, SATA II: 300 MB/s, SATA III: 600 MB/s).

- **Discos SCSI.** Discos de alta velocidad y rendimiento, diseñados para servidores. Ofrecen distintas velocidades (de 5 a 20 MB/s en sus primeras versiones) y un controlador puede gestionar hasta 7 discos.

- **RAID.** Sistema que combina varios discos duros en una sola unidad para conseguir mayor capacidad, velocidad o seguridad (copias de datos).

- **Sistemas NAS.** Dispositivo de almacenamiento conectado en red, que permite a múltiples usuarios compartir archivos de forma centralizada. Son sistemas con capacidades muy grandes (varios Terabytes).

- **Sistemas SAN.** Red dedicada y de alta velocidad que interconecta servidores con sistemas de almacenamiento. Separa el almacenamiento de los servidores, permitiendo que varios servidores accedan a un mismo grupo de discos de forma optimizada.

### 4.- Modelos de bases de datos

La clasificación tradicional de las bases de datos establece tres modelos de bases de datos: jerárquico, en red y relacional. En la actualidad el modelo de bases de datos más extendido es el relacional. Aunque, hay que tener en cuenta que dos de sus variantes (modelo de bases de datos distribuidas y orientadas a objetos) son las que se más se están utilizando en los últimos tiempos.

#### 4.1.- Modelo jerárquico

También recibe el nombre de **modelo en árbol**, ya que utiliza una estructura en **árbol invertido** para la organización de los datos. Hoy en día está en **desuso**.

La información se organiza con una jerarquía, en la que la relación entre las entidades de este modelo siempre es del tipo **padre/hijo**. De tal manera que existen nodos que contienen atributos o campos y que se relacionarán con sus nodos hijos, pudiendo tener cada nodo **más de un hijo**, pero un nodo siempre tendrá **un sólo padre**.

Los datos de este modelo se almacenan en estructuras lógicas llamadas **segmentos**. Los segmentos se relacionan entre sí utilizando **arcos**. 

#### 4.2.- Modelo en red

Este modelo aparece como respuesta a limitaciones del modelo jerárquico.

El modelo en red organiza la información en **registros** (también llamados nodos) y **enlaces**. En los registros se almacenan los datos, mientras que los enlaces permiten relacionar estos datos. Las bases de datos en red son parecidas a las jerárquicas sólo que en ellas puede haber **más de un padre**.

En este modelo se pueden representar perfectamente cualquier tipo de relación entre los datos, pero hace muy complicado su manejo. Al no tener que duplicar la información se ahorra espacio de almacenamiento.

#### 4.3.- Modelo relacional

Las bases de datos relacionales son las más comunes en la actualidad.

En este modelo, la información se organiza en **tablas** que el usuario percibe como un conjunto de datos estructurados. Aunque visualmente parezcan simples tablas, internamente pueden estar almacenadas de diferentes maneras según el sistema que las gestione.

Cada **tabla** representa una **relación** y está compuesta por **filas** y **columnas**:

* Cada **fila** (también llamada *registro*, *entidad* o *tupla*) contiene los datos de un elemento concreto.
* Cada **columna** (también llamada *campo* o *atributo*) define un tipo de dato que describe una característica de los elementos.

El **dominio** es el conjunto de valores posibles que puede tener un atributo.

Una **clave** es uno o varios atributos que permiten identificar de manera única cada registro dentro de la tabla.

Para que una tabla sea válida en el modelo relacional, debe cumplir ciertas reglas:

* Todos los registros tienen la misma estructura.
* No hay columnas ni campos repetidos.
* No existen registros duplicados.
* El orden de los registros no influye.
* Cada registro se distingue mediante una clave única.

El lenguaje estándar para trabajar con bases de datos relacionales es **SQL (Structured Query Language)**, utilizado para crear, modificar y consultar los datos.

Durante el diseño de una base de datos relacional, se aplica un proceso llamado **normalización**, que busca optimizar su estructura y evitar redundancias en la información.

#### 4.4.- Modelo orientado a objetos

El modelo orientado a objetos define una base de datos en términos de objetos, sus propiedades y sus operaciones. Los objetos con la misma estructura y comportamiento pertenecen a una clase, y las clases se organizan en jerarquías. Las operaciones de cada clase se especifican en términos de procedimientos predefinidos denominados métodos. Algunos sistemas existentes en el mercado, basados en el modelo relacional, han sufrido evoluciones incorporando conceptos orientados a objetos. A estos modelos se les conoce como sistemas objeto-relacionales.

El objetivo del modelo orientado a objetos es cubrir las limitaciones del modelo relacional. Gracias a este modelo se incorporan mejoras como la herencia entre tablas, los tipos definidos por el usuario, soporte multimedia, etc.

Los conceptos más importantes del paradigma de objetos que el modelo orientado a objetos incorpora son:

- **Encapsulación:** propiedad que permite ocultar la información al resto de los objetos, impidiendo así accesos incorrectos o conflictos.
- **Herencia:** propiedad a través de la cual los objetos heredan comportamiento dentro de una jerarquía de clases.
- **Polimorfismo:** propiedad de una operación mediante la cual puede ser aplicada a distintos tipos de objetos.

#### 4.5.- Otros modelos

**Modelo Objeto-Relacional**

Combina elementos del modelo relacional con la orientación a objetos. Su objetivo es mantener las ventajas del modelo relacional incorporando conceptos como la **herencia** y los **tipos de datos definidos por el usuario**.
Se basa en el estándar **SQL99**, que añade funciones avanzadas como procedimientos almacenados, *triggers*, tipos de datos personalizados, consultas recursivas y soporte para grandes objetos (*LOB*).
También permite integrar funciones escritas en lenguajes como **SQL, Java o C**.
Ejemplos de sistemas que usan este modelo son **Oracle** y **SQL Server**.

**Modelo de Bases de Datos Deductivas**

Estas bases de datos no solo almacenan información, sino que también pueden **inferir nuevos datos** a partir de los existentes, utilizando principios de la **lógica matemática**.
Se crearon para superar las limitaciones del modelo relacional en consultas complejas o recursivas.
Su lenguaje estándar es **SQL3**, desarrollado en 1999.

**Bases de Datos Multidimensionales**

Diseñadas para el análisis de grandes volúmenes de información, especialmente en entornos empresariales.
Los datos se organizan en **múltiples dimensiones** y se representan en estructuras llamadas **cubos**, lo que permite realizar consultas complejas con gran rapidez.
Este tipo de bases se utiliza en sistemas **OLAP (OnLine Analytical Processing)**, orientados al análisis, a diferencia de **OLTP (OnLine Transaction Processing)**, más enfocado en operaciones transaccionales.

**Bases de Datos Transaccionales**

Su principal característica es la **velocidad y fiabilidad** en la ejecución de operaciones.
Se usan en sistemas donde la integridad de la información es crítica, como bancos o industrias.
Cada transacción se completa por completo o se cancela, garantizando consistencia en los datos.
Un ejemplo destacado es **Oracle**.

**Modelo de Bases de Datos Orientadas a Documentos**

El elemento principal es el **documento**, que contiene datos semiestructurados (por ejemplo, en formato **XML o JSON**).
Este tipo de bases es flexible y adecuado para aplicaciones web modernas.
Ejemplos: **MongoDB** y **CouchDB**.

### 5.- Tipos de bases de datos

**Según su contenido**

- Con información actual.
- Directorios.
- Documentales:
    - De texto completo.
    - Archivos electrónicos de imágenes.
    - Referenciales.

**Según su uso**

- Individual.
- Compartida.
- De acceso público.
- Propietarias o bancos de datos.

**Según la variabilidad de la información**

- Estáticas.
- Dinámicas.

**Según la localización de la información**

- Centralizadas:
    - Basada en anfitrión.
    - Basada en Cliente/Servidor.
- Distribuidas.

**Según el organismo productor**

- De organismos públicos y de la Administración:
    - De acceso público.
    - De uso interno.
- De instituciones sin ánimo de lucro.
- De entidades privadas o comerciales:
    - De uso interno.
    - De uso interno que ocasionalmente ofrecen servicio hacia el exterior.
    - Comerciales.
- Realizadas por cooperación en red.

**Según el modo de acceso**

- De acceso local.
- En CD-ROM.
- En línea:
    - Acceso vía telnet o mediante línea de Internet.
    - Acceso vía web.

**Según cobertura temática**

- Científico-tecnológicas: 
    - Multidisciplinares.
    - Especializadas.
- Económico-empresariales.
- De medios de comunicación.
- De ámbito político-administrativo y jurídico.
- De ámbito sanitario.
- Para el gran público.

### 6.- Sistemas gestores de base de datos

Un **Sistema Gestor de Bases de Datos (SGBD)**, o **DBMS (DataBase Management System)**, es un conjunto de programas que permite **crear, administrar y acceder** a la información contenida en una base de datos de forma **eficiente y segura**. Está diseñado para manejar grandes volúmenes de datos y garantizar su integridad y confidencialidad.

El SGBD proporciona a usuarios, analistas, programadores y administradores las herramientas necesarias para **definir, construir y manipular** los datos:

* **Definir** una base de datos implica establecer los tipos de datos, sus estructuras y las restricciones que deben cumplir.
* **Construir** la base consiste en almacenar físicamente la información bajo la supervisión del sistema gestor.
* **Manipular** los datos incluye realizar consultas, actualizaciones y generar informes a partir del contenido almacenado.

#### Ventajas de los SGBD

* Ofrecen una **visión abstracta** de los datos, ocultando la complejidad del almacenamiento físico.
* Garantizan **independencia física y lógica**, permitiendo modificar la estructura sin afectar las aplicaciones.
* Reducen la **redundancia e inconsistencia** de la información.
* Mantienen la **integridad, seguridad y privacidad** de los datos.
* Facilitan el **acceso rápido y fiable** a la información.
* Permiten el **uso compartido y concurrente** de los datos entre múltiples usuarios.
* Favorecen la **interoperabilidad** entre distintos sistemas.
* Incluyen mecanismos de **copia de seguridad y recuperación** ante fallos.

El SGBD se comunica directamente con el **sistema operativo**, utilizando sus funciones para gestionar el almacenamiento y el acceso a los datos. Además, actúa como intermediario entre las **aplicaciones** y la base de datos, proporcionando los medios necesarios para consultar y manipular la información de manera controlada.

#### 6.1.- Funciones

Un SGBD desarrolla **tres funciones** fundamentales: descripción, manipulación y control o utilización de los datos.

**Descripción o definición** 

Permite al diseñador de la base de datos crear las estructuras apropiadas para integrar adecuadamente los datos. Esta función es la que permite definir las tres estructuras de la base de datos: Estructura interna, Estructura conceptual y Estructura externa.

Esta función se realiza mediante el lenguaje de descripción de datos o DDL, con el cual definen las estructuras de datos, las relaciones entre los mismos y las reglas que han de cumplir. Se especificarán las características de los datos a cada uno de los tres niveles y el SGBD se ocupará de la transformación de las estructuras externas orientadas a los usuarios a las estructuras conceptuales y de la relación de ésta y la estructura física.

- **Estructura interna**. A nivel interno se ha de indicar el espacio de disco reservado para la base de datos, la longitud de los campos, su modo de representación (lenguaje para la definición de la estructura externa).
- **Estructura conceptual**. A nivel conceptual se proporcionan herramientas para la definición de las entidades y su identificación, atributos de las mismas, interrelaciones entre ellas, restricciones de integridad, etc.; es decir, el esquema de la base de datos (lenguaje para la definición de estructura lógico global).  
- **Estructura externa**. A nivel externo se deben definir las vistas de los distintos usuarios a través del lenguaje para la definición de estructuras externas.

**Manipulación**

Permite a los usuarios de la base buscar, añadir, suprimir o modificar los datos de la misma, siempre de acuerdo con las especificaciones y las normas de seguridad dictadas por el administrador. Se llevará a cabo por medio de un lenguaje de manipulación de datos (DML) que facilita los instrumentos necesarios para la realización de estas tareas.

También se encarga de definir la  vista externa de todos los usuarios de la base de datos o vistas parciales que cada usuario tiene de los datos definidos con el DDL.

Por manipulación de datos entenderemos:

- Recuperación de información almacenada.
- Inserción de información nueva.
- Borrado de información.
- Modificación de información almacenada.

**Función de control**

Permite al administrador establecer mecanismos de protección de las diferentes visiones de los datos asociadas a cada usuario, proporcionando elementos de creación y modificación de dichos usuarios. Adicionalmente, incorpora sistemas para la creación de copias de seguridad, carga de ficheros, auditoría, protección de ataques, configuración del sistema, etc. El lenguaje que implementa esta función es el lenguaje de control de datos o DCL.

#### 6.2.- Componentes

Un SGBD ha de proporcionar servicios relacionados con el almacenamiento y la explotación de los datos de forma eficiente. Para ello, cuenta con una serie de componentes:

- **Lenguajes de la base de datos**. Cualquier sistema gestor de base de datos ofrece la posibilidad de utilizar lenguajes e interfaces adecuadas para sus diferentes tipos de usuarios. A través de los lenguajes se pueden especificar los datos que componen la BD, su estructura, relaciones, reglas de integridad, control de acceso, características físicas y vistas externas de los usuarios. Los lenguajes del SGBD son: Lenguaje de Definición de los Datos (DDL), Lenguaje de Manejo de Datos (DML) y Lenguaje de Control de Datos (DCL).

- **Diccionario de datos**. Descripción de los datos almacenados. Se trata de información útil para los programadores de aplicaciones. Es el lugar donde se deposita la información sobre la totalidad de los datos que forman la base de datos. Contiene las características lógicas de las estructuras que almacenan los datos, su nombre, descripción, contenido y organización. En una base de datos relacional, el diccionario de datos aportará información sobre:
    - Estructura lógica y física de la BD.
    - Definición de tablas, vistas, indices, disparadores, procedimientos, funciones, etc.
    - Cantidad de espacio asignado y utilizado por los elementos de la BD.
    - Descripción de las restricciones de integridad.
    - Información sobre los permisos asociados a cada perfil de usuario.
    - Auditoría de acceso a los datos, utilización, etc.

- **Gestor de la base de datos**. Es la parte de software encargada de garantizar el correcto, seguro, íntegro y eficiente acceso y almacenamiento de los datos. Este componente es el encargado de proporcionar una interfaz entre los datos almacenados y los programas de aplicación que los manejan. Es un intermediario entre el usuario y los datos. Es el encargado de garantizar la privacidad, seguridad e integridad de los datos, controlando los accesos concurrentes e interactuando con el sistema operativo.

- **Usuarios de la base de datos**. En los SGBD existen diferentes perfiles de usuario:
    - El administrador, que será la persona encargada de la función de administración de la base de datos. Tiene el control centralizado de la base de datos y es el responsable de su buen funcionamiento. Es el encargado de autorizar el acceso a la base de datos, de coordinar y vigilar su utilización y de adquirir los recursos software y hardware que sean necesarios.
    - Los usuarios de la base de datos, que se pueden clasificar en:
        - Diseñadores.
        - Operadores y personal de mantenimiento.
        - Analistas y programadores de aplicaciones.
        - Usuarios finales.

- **Herramientas de la base de datos**. Son un conjunto de aplicaciones que permiten a los administradores la gestión de la base de datos, de los usuarios y permisos, generadores de formularios, informes, interfaces gráficas, generadores de aplicaciones, etc.

#### 6.3.- Arquitectura

Un SGBD cuenta con una arquitectura a través de la que se simplifica a los diferentes usuarios de la base de datos su labor. El objetivo fundamental es separar los programas de aplicación de la base de datos física.

Los tres estándares más importantes de las bases de datos son ANSI/SPARC/X3, CODASYL y ODMG (éste sólo para las bases de datos orientadas a objetos). Tanto ANSI (EEUU), como ISO (resto del mundo), son el referente en cuanto a estandarización de bases de datos, conformando un único modelo de bases de datos.

La arquitectura propuesta proporciona tres niveles de abstracción: nivel interno o físico, nivel lógico o conceptual y nivel externo o de visión del usuario:

- **Nivel interno o físico**. En este nivel se describe la estructura física de la base de datos a través de un esquema interno encargado de detallar el sistema de almacenamiento de la base de datos y sus métodos de acceso. Es el nivel más cercano al almacenamiento físico. A través del esquema físico se indican los archivos que contienen la información, su organización, los métodos de acceso a los registros, los tipos de registros, la longitud, los campos que los componen, las unidades de almacenamiento, etc.

- **Nivel lógico o conceptual**. En este nivel se describe la estructura completa de la base de datos a través de un esquema que detalla las entidades, atributos, relaciones, operaciones de los usuarios y restricciones. Los detalles relacionados con las estructuras de almacenamiento se ocultan, permitiendo realizar una abstracción a más alto nivel.

- **Nivel externo o de visión del usuario**. En este nivel se describen las diferentes vistas que los usuarios percibirán de la base de datos. Cada tipo de usuario o grupo de ellos verá sólo la parte de la base de datos que le interesa, ocultando el resto.

Para una base de datos, sólo existirá un único esquema interno, un único esquema conceptual y podrían existir varios esquemas externos definidos para uno o varios usuarios.

Gracias a esta arquitectura, se consigue la independencia de datos a dos niveles:

- **Independencia lógica**: podemos modificar el esquema conceptual sin alterar los esquemas externos ni los programas de aplicación.

- **Independencia física**: podemos modificar el esquema interno sin necesidad de modificar el conceptual o el externo. Es decir, se puede cambiar el sistema de almacenamiento, reorganizar los ficheros, añadir nuevos, etc., sin que esto afecte al resto de esquemas.

#### 6.4.- Tipos

**Según su modelo lógico**

- Modelo Jerárquico.
- Modelo de Red.
- Modelo Relacional.
- Modelo Orientado a Objetos.

**Según el número de usuarios**

- Monousuario.
- Multiusuario.

**Según el número de sitios en los que está distribuida la base de datos**

- Centralizados.
- Distribuidos (homogéneos o heterogéneos).

**Según el coste**

- Entre 0 y 3.000 euros.
- Entre 10.000 y 100.000 euros
- Más de 100.000 euros.

**Según el propósito o finalidad**

- Propósito general.
- Propósito específico.

### 7.- SGBD comerciales

| SGBD | Descripción |
|------|-------------|
| **ORACLE** | Reconocido como uno de los mejores a nivel mundial. Es multiplataforma, potente a nivel transaccional, confiable y seguro. Es Cliente/Servidor, basado en el modelo de datos Relacional. De gran potencia, aunque con un precio elevado que hace que sólo se vea en empresas muy grandes y multinacionales. Ofrece versiones gratuitas, como Oracle Database Express Edition (XE). |
| **MYSQL** | Sistema muy extendido que se ofrece bajo dos tipos de licencia: comercial o libre. Para empresas que deseen incorporarlo en productos privativos, deben comprar una licencia específica. Es relacional, multihilo, multiusuario y multiplataforma. Su gran velocidad lo hace ideal para consultas de bases de datos y plataformas web. |
| **DB2** | Multiplataforma, el motor de base de datos relacional integra XML de manera nativa, lo que IBM ha llamado pureXML, permitiendo almacenar documentos completos para realizar operaciones y búsquedas jerárquicas dentro de éste, e integrarlo con búsquedas relacionales. |
| **INFORMIX** | Otra opción de IBM para el mundo empresarial que necesita un DBMS sencillo y confiable. Es un gestor de base de datos relacional basado en SQL, multiplataforma. Consume menos recursos que Oracle, con utilidades avanzadas respecto a conectividad y funciones relacionadas con tecnologías de Internet/Intranet, XML, etc. |
| **Microsoft SQL SERVER**  | Sistema Gestor de Base de Datos producido por Microsoft. Es relacional, sólo funciona bajo Microsoft Windows y utiliza arquitectura Cliente/Servidor. Constituye la alternativa a otros potentes SGBD como Oracle, PostgreSQL o MySQL. |
| **SYBASE** | Un DBMS con bastantes años en el mercado, con tres versiones para ajustarse a las necesidades de cada empresa. Es un sistema relacional, altamente escalable, de alto rendimiento, con soporte a grandes volúmenes de datos, transacciones y usuarios, y de bajo costo. |

### 8.- SGBD libres

| SGBD | Descripción |
|------|-------------|
| **MySQL** | Relacional, multihilo y multiusuario con más de seis millones de instalaciones. Distribuido bajo dos tipos de licencias, comercial y libre. Multiplataforma, posee varios motores de almacenamiento, accesible a través de múltiples lenguajes de programación y muy ligado a aplicaciones web. |
| **PostgreSQL** | Relacional Orientado a Objetos. Considerado como la base de datos de código abierto más avanzada del mundo. Desarrollado por una comunidad de desarrolladores que trabajan de forma desinteresada, altruista, libre y/o apoyados por organizaciones comerciales. Es multiplataforma y accesible desde múltiples lenguajes de programación. |
| **Firebird** | Relacional, multiplataforma, con bajo consumo de recursos, excelente gestión de la concurrencia, alto rendimiento y potente soporte para diferentes lenguajes. |
| **Apache Derby** | Escrito en Java, de reducido tamaño, con soporte multilenguaje, multiplataforma, altamente portable, puede funcionar embebido o en modo cliente/servidor. |
| **SQLite**  | Relacional, basado en una biblioteca escrita en C que interactúa directamente con los programas, reduce los tiempos de acceso siendo más rápido que MySQL o PostGreSQL. Es multiplataforma y con soporte para varios lenguajes de programación. |

### 9.- Bases de datos centralizadas

La arquitectura centralizada es de las menos utilizadas. Es una estructura en la que el SGBD está implantado en una sola plataforma u ordenador desde donde se gestiona directamente la totalidad de los recursos. Es la arquitectura de los centros de proceso de datos tradicionales. Se basa en tecnologías sencillas, muy experimentadas y de gran robustez.

Las principales características de las bases de datos centralizadas son:

- Se almacena completamente en una ubicación central.
- No posee múltiples elementos de procesamiento ni mecanismos de intercomunicación como las bases de datos distribuidas.
- Sus componentes son: los datos, el software de gestión de bases de datos y los dispositivos de almacenamiento secundario asociados.
- Su seguridad puede verse comprometida más fácilmente.

| Ventajas | Inconvenientes |
|----------|----------------|
| Se evita la redundancia debido a la posibilidad de inconsistencias y al desperdicio de espacio | Un mainframe, en comparación con un sistema distribuido, no tiene mayor poder de cómputo |
| Se evita la inconsistencia, ya que si un hecho específico se representa por una sola entrada, la no-concordancia de datos no puede ocurrir | Si este sistema falla, se pierde toda disponibilidad de procesamiento y la información confiada |
| La seguridad se centraliza | En caso de un desastre o catástrofe, la recuperación es difícil de sincronizar |
| Puede conservarse la integridad | Las cargas de trabajo no se pueden difundir entre varias computadoras |
| El procesamiento de los datos ofrece un mejor rendimiento | Los departamentos de sistemas retienen el control de toda la organización |
| Ahorro en recursos, mantenimiento y recursos humanos | Requieren un mantenimiento central de datos |

### 10.- Bases de datos distribuidas

Una **base de datos distribuida (BDD)** es un conjunto de múltiples bases de datos lógicamente relacionadas las cuales se encuentran distribuidas entre diferentes nodos interconectados por una red de comunicaciones.

Un **sistema de bases de datos distribuida (SBDD)** es un sistema en el cual múltiples sitios de bases de datos están ligados por un sistema de comunicaciones, de tal forma que, un usuario en cualquier sitio puede acceder los datos en cualquier parte de la red exactamente como si los datos estuvieran almacenados en su sitio propio.

Un **sistema gestor de bases de datos distribuida (SGBDD)** es aquel que se encarga del manejo de la BDD y proporciona un mecanismo de acceso que hace que la distribución sea transparente a los usuarios. El término transparente significa que la aplicación trabajaría, desde un punto de vista lógico, como si un solo SGBD ejecutado en una sola máquina administrara esos datos.

Un SGBDD desarrollará su trabajo a través de un conjunto de sitios o nodos, que poseen un sistema de procesamiento de datos completo con una base de datos local, un sistema de gestor de bases de datos e interconectados entre sí. Si estos nodos están dispersos geográficamente se interconectarán a través de una red de área amplia o WAN, pero si se encuentran en edificios relativamente cercanos, pueden estar interconectados por una red de área local o LAN.

| Ventajas | Inconvenientes |
|----------|----------------|
| El acceso y procesamiento de los datos es más rápido ya que varios nodos comparten carga de trabajo | La probabilidad de violaciones de seguridad es creciente si no se toman las precauciones debidas |
| Desde una ubicación puede accederse a información alojada en diferentes lugares | Existe una complejidad añadida que es necesaria para garantizar la coordinación apropiada entre los nodos |
| Los costes son inferiores a los de las bases centralizadas | La inversión inicial es menor, pero el mantenimiento y control puede resultar costoso |
| Existe cierta tolerancia a fallos. Mediante la replicación, si un nodo deja de funcionar el sistema completo no deja de funcionar | Dado que los datos pueden estar replicados, el control de concurrencia y los mecanismos de recuperación son mucho más complejos que en un sistema centralizado. |
| Se adapta más naturalmente a la estructura de las organizaciones. Permiten la incorporación de nodos de forma flexible y fácil | El intercambio de mensajes y el cómputo adicional necesario para conseguir la coordinación entre los distintos nodos constituyen una forma de sobrecarga que no surge en los sistemas centralizados |
| Aunque los nodos están interconectados, tienen independencia local | Dada la complejidad del procesamiento entre nodos es difícil asegurar la corrección de los algoritmos, el funcionamiento correcto durante un fallo o la recuperación |

#### 10.1.- Fragmentación

La fragmentación es una técnica en bases de datos distribuidas que consiste en dividir una relación (tabla) en partes más pequeñas para distribuirla en distintos servidores. Su objetivo es optimizar el acceso a los datos, equilibrando el grado de fragmentación según las necesidades de las aplicaciones.

**Reglas fundamentales**

- **Completitud**. Todos los datos de la relación original deben estar presentes en al menos uno de los fragmentos.
- **Reconstrucción**. Debe ser posible reconstruir la relación original a partir de sus fragmentos, manteniendo las restricciones de los datos.
- **Disyunción**. En la fragmentación vertical, la clave primaria se repite en todos los fragmentos para permitir la reconstrucción.

**Tipos de fragmentación**

- **Horizontal**:
    - Divide la tabla por filas (tuplas).
    - Cada fragmento contiene un subconjunto de tuplas de la tabla original. 
    - Variantes: primaria (directa) y derivada (basada en otras tablas).

- **Vertical**:
    - Divide la tabla por columnas (atributos).  
    - Cada fragmento incluye un subconjunto de atributos, junto con la clave primaria.
    - Busca minimizar el tiempo de ejecución de las consultas.
    - Más compleja que la horizontal debido a la gran cantidad de alternativas.

- **Híbrida o mixta**:
    - Combina fragmentación horizontal y vertical.
    - Se representa mediante árboles para visualizar la estructura.

## **UD2.- Bases de datos relacionales**

![Esquema Unidad 2 Bases de Datos](../../static/img/bases-de-datos-unidad-2.jpg)

### 1.- Modelo de datos

Un **modelo** es un esquema teórico o una representación de una realidad compleja o sistema.

Un **modelo de datos** describe los elementos que intervienen en un problema y la forma en que se relacionan entre sí. En el contexto informático, es un conjunto de métodos y reglas que indican cómo almacenar y manipular la información.

En la implementación de una base de datos, el modelo de datos se utiliza para describir:
    - Estructuras de los datos
    - Restricciones de integridad (condiciones que los datos deben cumplir)
    - Operaciones de manipulación

Este lenguaje se divide en dos sublenguajes:
    - **Lenguaje de Definición de Datos (DDL):** describe las estructuras de datos y las restricciones de integridad de forma abstracta.
    - **Lenguaje de Manipulación de Datos (DML):** describe las operaciones de manipulación de los datos.

El diseño de una base de datos se realiza en tres fases basadas en su nivel de abstracción:

1.  **Modelo de datos conceptual:** se utiliza en el diseño conceptual. Es una representación (usualmente gráfica) de la realidad que **no está comprometida** con ningún entorno informático. Describe las estructuras y restricciones, estando orientado a representar los elementos y sus relaciones. Es una fase crítica, ya que los errores aquí se arrastran a las siguientes.
    * *Ejemplo:* **Modelo entidad-relación**
2.  **Modelo Lógico:** se utiliza en el diseño lógico. Determina los criterios de **almacenamiento** y las **operaciones de manipulación** de datos dentro de un tipo de entorno informático. Los Sistemas Gestores de Bases de Datos (SGBD) comerciales se basan en un modelo lógico específico.
    * *Ejemplo:* **Modelo relacional**
3.  **Modelo Físico:** se utiliza en el diseño físico. Es la **implementación física** del modelo lógico en estructuras de datos de bajo nivel, utilizando un SGBD comercial específico (ej., Oracle, MySQL).

### 2.- Terminología del modelo relacional

El **modelo relacional** fue propuesto por **Edgar Frank Codd** en los laboratorios de IBM. Se trata de un **modelo lógico** que permite representar la información del mundo real de una manera intuitiva y establece una estructura sobre los datos, independiente del modo en que se almacenarán físicamente. El nombre del modelo se debe a su estrecha relación con el concepto matemático de **relación**.

**Producto cartesiano**

Una relación entre dos conjuntos, *A* y *B*, es un subconjunto del **producto cartesiano** *A* x *B*.

El producto cartesiano da como resultado la relación de **todos los elementos de un conjunto con todos los elementos de los otros conjuntos** de ese producto. Al trabajar con conjuntos, no puede haber elementos repetidos.

> *Ejemplo:* si tienes un conjunto *Marcas* y un conjunto *Modelos*, el producto cartesiano es la combinación de todos los elementos de *Marcas* con todos los de *Modelos*. 

El diseño de las tablas en el modelo relacional es la segunda fase del diseño de la base de datos, que se realiza después de completar el diseño conceptual (análisis, identificación de tablas, atributos, restricciones y relaciones).

#### 2.1.- Relación o tabla. Tuplas. Dominios.

El modelo relacional, basado en la teoría de conjuntos y la lógica de predicados, utiliza una terminología específica para describir sus componentes, siendo los principales: **relaciones (tablas), tuplas (filas)** y **atributos (columnas)**.

En el modelo relacional, una **relación** se visualiza como una **tabla** compuesta por filas y columnas.

**Atributos (columnas)**
Un **atributo** es el nombre de cada dato que se almacena en la relación. En una tabla de *Alumnos*, los atributos serían *DNI*, *nombre* y *apellidos*.

* El nombre del atributo debe describir el significado de la información que representa.
* A veces se añade una descripción para aclarar el contenido (ej., si el sueldo es neto o bruto).

**Tuplas (filas)**
Una **tupla** se refiere a cada elemento de la relación o tabla. Una tupla se corresponde con la idea de **registro**.

* Cada tupla debe corresponderse con un elemento del mundo real.
* No puede haber dos tuplas iguales (con todos sus valores idénticos).

**Dominios**
Un **dominio** es un **conjunto de valores previamente establecidos** al que debe pertenecer un atributo. Esto evita errores (ej., guardar "250€" en un atributo *Población*).

* Un dominio se puede definir mediante la declaración de un **tipo de dato** (ej., número entero entre 1 y 16) o ser más complejo (ej., que el atributo *Sexo* solo admita "M" o "F").
* Una característica fundamental es que los dominios deben ser **atómicos**, es decir, los valores contenidos en los atributos no se pueden separar en valores de dominios más simples.
* Un dominio debe tener **Nombre**, **Definición lógica**, **Tipo de datos** y **Formato**.
    * *Ejemplo:* Para el atributo *Sueldo*: Nombre (*Sueldo*), Definición Lógica (*Sueldo neto del empleado*), Tipo de datos (*número entero*), y Formato (*9.999€*).

#### 2.2.- Grado. Cardinalidad.

El **grado** es el **tamaño de una tabla en base a su número de atributos (columnas)**. A mayor grado, mayor es la complejidad para trabajar con la tabla.

La **cardinalidad** es el **número de tuplas o filas** de una relación o tabla.

> Ejemplo (producto cartesiano):
>
> Dadas las relaciones `A={Carlos, María}, B={Matemáticas, Lengua, Inglés} y C={Aprobado, Suspenso}`.
> 
> El **producto cartesiano** A x B x C da como resultado una relación de **grado 3** (pues tiene 3 columnas o atributos).
>
> Si se toma un subconjunto de este producto cartesiano con 5 filas, se obtiene una relación de **cardinalidad 5**. 

#### 2.3.- Sinónimos

Los conceptos fundamentales del modelo relacional tienen distintas nomenclaturas dependiendo del contexto o de la perspectiva utilizada (matemática, informática o de programación de ficheros):

| Modelo relacional | Tablas | Ficheros |
| :--- | :--- | :--- |
| RELACIÓN | TABLA | FICHERO |
| TUPLA | FILA | REGISTRO |
| ATRIBUTO | COLUMNA | CAMPO |
| GRADO | Nº COLUMNAS | Nº CAMPOS |
| CARDINALIDAD | Nº FILAS | Nº REGISTROS |

### 3.- Relaciones. Características de una relación (tabla).

Para que una relación (tabla) sea válida dentro del modelo relacional, debe cumplir una serie de propiedades estrictas que aseguran la consistencia de los datos:

- Cada tabla dentro del modelo debe tener un **nombre distinto**.
- Cada atributo (columna) de la tabla debe tomar **un solo valor** en cada tupla (fila).
- Cada atributo (columna) debe tener un **nombre distinto** dentro de la misma tabla (aunque el mismo nombre puede usarse en tablas distintas).
- No puede haber dos tuplas (filas) **completamente iguales**; es decir, la combinación de todos los valores debe ser única para cada registro.
- El **orden de las tuplas (filas) no importa**.
- El **orden de los atributos (columnas) no importa**.
- Todos los datos de un atributo (columna) deben pertenecer al **mismo dominio** definido para ese atributo (ej. si el dominio del atributo *Nota* solo incluye *Aprobado* o *Suspenso*, el dato *NOTABLE* sería incorrecto).

#### 3.1.- Tipos de relaciones (tablas)

Las relaciones o tablas se pueden clasificar según su permanencia y la forma en que almacenan sus datos:

**Tablas persistentes**: solo pueden ser borradas por los usuarios. Se dividen en:
    - **Base:** son tablas **independientes** que se crean definiendo su estructura y el conjunto de tuplas (filas) que contienen.
    - **Vistas:** son tablas que solo almacenan una **definición de consulta**. Los datos que muestran provienen de otras tablas base, de otras vistas o de instantáneas. Si los datos de las tablas base cambian, los datos de la vista también cambiarán, ya que se obtienen dinámicamente a partir de la consulta que la define.
    - **Instantáneas:** son conceptualmente como vistas (se crean de la misma forma), pero a diferencia de ellas, sí **almacenan los datos** que muestran, además de la consulta que las creó. Solo modifican su resultado cuando el sistema se **refresca** cada cierto tiempo. Actúan como una "fotografía" de la relación que es válida solo durante un periodo de tiempo concreto. Dependiendo del SGBD (Sistema Gestor de Base de Datos) que se utilice, pueden ser de solo lectura.

**Tablas temporales**: son eliminadas automáticamente por el sistema (SGBD).

### 4.- Tipos de datos

En el modelado de datos, cada **atributo** (columna) debe tener asociado un **tipo de dato** para especificar formalmente su **dominio** (conjunto de valores posibles) y las operaciones que se pueden realizar con él.

Al crear una tabla, el proceso de asignación de tipos de datos a los atributos implica:
- Asignar un **nombre** al campo (relacionado con el dato que contiene).
- Asignar un **tipo de dato** (que restringe los valores que puede tomar y las operaciones que se pueden realizar).

En términos de bases de datos, el dominio se especifica indicando el **tipo de dato** (general) y el **conjunto de valores restringidos** (específico, indicado en la definición de la tabla si el SGBD lo permite).

La mayoría de los lenguajes y SGBD utilizan tipos de datos que caen en las siguientes categorías comunes, aunque su sintaxis y nombre varían:

* **Texto:** almacena cadenas de caracteres (letras, números o símbolos) con las que no se realizarán operaciones matemáticas.
* **Numérico:** almacena números. Se usa cuando se van a realizar **operaciones matemáticas** con el valor (ej., Sueldo).
* **Fecha/Hora:** almacena fechas y horas.
* **Sí/No (Booleano):** almacena datos con solo dos posibilidades (verdadero/falso).
* **Autonumérico:** subtipo de Numérico que almacena valores numéricos secuenciales que el SGBD incrementa automáticamente al añadir un registro (fila).
* **Memo:** almacena texto largo (mayor que un tipo Texto).
* **Moneda:** almacena valores numéricos con la característica especial de representar **cantidades de dinero**.
* **Objeto OLE:** almacena gráficos, imágenes o textos creados por otras aplicaciones.

Para determinar el tipo de dato y su tamaño, se deben considerar el conjunto de valores que puede tomar y las operaciones que se realizarán.

>**Ejemplo de criterio:** un código postal (`06800`) se define mejor como una cadena de 5 caracteres (texto) en lugar de numérico, porque no se usa para operaciones matemáticas y los ceros a la izquierda deben conservarse. El número de teléfono es un caso similar.
>
>Es fundamental que el tipo de dato y el tamaño/longitud se definan correctamente. Una mala definición podría no permitir almacenar la información o causar que se almacene incompleta (ej. si se define el DNI con longitud 8 y el valor tiene 9 caracteres, el sistema podría almacenar un valor truncado).

### 5.- Claves

Las **claves** son atributos o conjuntos de atributos que se utilizan para **identificar de modo único** las tuplas (filas) de una relación (tabla) y para establecer relaciones entre tablas.

* **Superclaves:** atributo o conjunto de atributos que identifica de modo único las tuplas de una relación. Puesto que no puede haber dos tuplas completamente iguales, la tupla completa es siempre una superclave.

En el modelo relacional, se trabaja con los siguientes tipos de claves:
    - Claves candidatas
    - Clave primaria
    - Claves alternativas
    - Claves ajenas (externas)

#### 5.1.- Clave candidata. Clave primaria. Clave alternativa.

**Clave candidata**: atributo o conjunto de atributos que identifica de manera **única** e **irreductible** cada tupla (fila) de la relación. Toda tabla debe tener al menos una clave candidata.
    - **Clave compuesta:** clave candidata formada por más de un atributo.
    - Requisitos de una clave candidata:
        1.  **Unicidad:** no puede haber dos tuplas con los mismos valores para esos atributos.
        2.  **Irreductibilidad:** si se elimina cualquiera de los atributos, el conjunto resultante deja de ser único.
    - La identificación de claves candidatas se basa en el **significado real** de los atributos y no en la observación de un estado temporal de los datos.

**Clave primaria (Primary Key - PK)**: clave candidata que se escoge para identificar de modo único sus tuplas dentro de una relación.
    - Una relación siempre tendrá una clave primaria. En el peor caso, estará formada por todos los atributos de la relación, pero generalmente es un subconjunto pequeño. A menudo, se utiliza un campo único artificial (ej. un código de usuario autonumérico).

**Clave alternativa**: clave candidata que no ha sido escogida como clave primaria.

#### 5.2.- Clave externa, ajena o secundaria (Foreign Key - FK)

Una **clave ajena** es un atributo o conjunto de atributos en una relación (tabla) cuyos valores **coinciden con los valores de la clave primaria de otra relación** (o de la misma). Su propósito es representar las **relaciones** o conexiones entre los datos de diferentes tablas.
    - Los valores de una clave ajena deben cumplir una de estas condiciones:
        1.  Estar presentes como un valor de la **clave primaria** en la tabla a la que hacen referencia.
        2.  Ser **valores nulos** (si se permite).
    - A diferencia de la clave primaria a la que referencian, las claves ajenas **sí pueden repetirse** en su tabla.
    - Si una clave ajena contiene un valor que no existe en la clave primaria de la tabla referenciada, la información se considera **inconsistente** (no fiable).

### 6.- Índices. Características.

Un **índice** es una estructura de datos que se define sobre uno o varios campos de una tabla para permitir un **acceso mucho más rápido a las filas**.

Al igual que un índice en un diccionario facilita la búsqueda de palabras, los índices en una base de datos agilizan las operaciones de búsqueda. 

- Son útiles cuando se realizan consultas frecuentes a un rango de filas o a una fila específica de una tabla, especialmente en bases de datos grandes.
- Los cambios en los datos de las tablas (agregar, actualizar o borrar filas) se incorporan automáticamente a los índices con total transparencia.
- Los índices son **independientes, lógica y físicamente, de los datos**. Por lo tanto, pueden ser creados y eliminados en cualquier momento sin afectar a las tablas ni a otros índices.
- **Impacto en el rendimiento:**
    * Crear índices agiliza las operaciones de **búsqueda**.
    * Crear índices **ralentiza** las operaciones de **modificar o agregar datos**, ya que es necesario actualizar tanto la tabla como el índice. Por ello, se debe pensar bien cuándo definirlos.
    * No conviene indexar columnas de **gran tamaño** porque puede ser contraproducente.
- **Relación con claves:** el SGBD utiliza índices para la gestión de las **claves ajenas** y de las **claves primarias**. En el caso de las claves primarias, se utilizan **índices únicos** (no admiten valores repetidos).

### 7.- El valor NULL. Operaciones con este valor.

El valor especial **NULO (NULL)** se utiliza para designar la **ausencia de dato** en un campo, independientemente del dominio al que pertenezca.

Se asigna NULO cuando:
* Se **desconoce** el valor de un campo (ej., desconocemos el teléfono de un usuario).
* El campo **carece de sentido** para esa tupla (ej., un usuario no tiene teléfono).
* En claves secundarias, indica que la tupla **no está relacionada** con ninguna otra tupla.

**Distinciones**
Es fundamental notar que:
* **NULO** no es lo mismo que **ESPACIO EN BLANCO**. Un espacio en blanco es un carácter que pertenece al dominio texto.
* **NULO** tampoco es lo mismo que el valor **CERO**.

**Lógica con el valor NULO**
El valor NULO no es ni **VERDADERO** ni **FALSO** en la lógica booleana. Esto afecta a las operaciones lógicas (`AND`, `OR`, `NOT`):

* VERDADERO Y (AND) NULO → **NULO**
* FALSO Y (AND) NULO → **FALSO**
* VERDADERO O (OR) NULO → **VERDADERO**
* FALSO O (OR) NULO → **NULO**
* NO (NOT) NULO → **NULO**

Para comparar un campo con este valor, las bases de datos relacionales utilizan el operador `IS NULL` (ES NULO), que devuelve **VERDADERO** si el valor comparado es NULO.

### 8.- Vistas

Una **vista** es una tabla **"virtual"** cuyas filas y columnas se obtienen a partir de una o varias tablas del modelo. Lo que se almacena no es la tabla en sí, sino su **definición de consulta**, razón por la que se considera "virtual". Una vista actúa como un filtro de las tablas a las que hace referencia.

- **Origen de datos:** la consulta que define una vista puede provenir de una o varias tablas, o de otras vistas de la base de datos actual o de otras bases de datos.
- **Restricciones:** aunque no existen restricciones para consultar vistas, sí hay restricciones para **modificar los datos** de estas, establecidas para mantener la integridad y consistencia de los datos. La posibilidad de actualizar datos a través de una vista depende de su complejidad y del gestor de base de datos (SGBD) (ej. Oracle no lo permite, mientras que SQL Server sí).
- **Propiedades:** las vistas no tienen una copia física de los datos; son sentencias de consultas a los datos existentes en las tablas. Si se actualizan los datos de una vista, se está actualizando realmente la tabla, y si se actualiza la tabla, los cambios son visibles desde la vista.

**Razones para crear vistas:**
* **Seguridad:** permite que los usuarios accedan solo a una **parte específica** de la información contenida en una tabla, sin acceso a la tabla completa.
* **Comodidad:** simplifica el uso de sentencias de consulta que podrían ser bastante complejas si se escribieran directamente en el lenguaje de base de datos.

### 9.- Usuarios. Roles. Privilegios

Para conectarse a una base de datos, se utiliza un modo de acceso que describe los permisos disponibles durante la conexión, definidos en función del nombre de usuario.

**Usuario**: es un conjunto de permisos que se aplican a una conexión de base de datos.
    - Es el **propietario** de ciertos objetos (tablas, vistas, etc.).
    - Realiza las **copias de seguridad**.
    - Tiene asignada una **cuota de almacenamiento**.
    - Tiene asignado un *tablespace* por defecto para los objetos (en Oracle).

**Privilegio**: es un permiso que se otorga a un usuario para que realice ciertas operaciones. Se clasifica en dos tipos:
    - **De sistema:** necesario para configurar parámetros del sistema.
    - **Sobre objeto:** necesario para realizar operaciones sobre un objeto específico (ej., permiso sobre una tabla para modificarla).

**Rol**: es una agrupación de permisos (de sistema y de objeto).
    - Permite asignar un grupo de permisos a un usuario.
    - Si se asigna un rol a varios usuarios y luego se necesita añadir un permiso nuevo, este se propaga automáticamente a todos los usuarios que tienen asignado ese rol, simplificando la administración.
    - Los roles son fundamentales en los CMS (Sistemas Gestores de Contenidos) para definir las interacciones de usuarios y gestores con el entorno.

### 10.- SQL

**SQL** es un lenguaje de **dominio específico** fundamental para los SGBD. Está diseñado para **administrar y recuperar información** de estas bases de datos.

* **Naturaleza:**eEs un lenguaje **declarativo**. Lo más importante es definir **qué se desea hacer**, y el SGBD se encarga de determinar **cómo hacerlo**.
* **Estándar:** es un lenguaje **normalizado** que permite trabajar en combinación con casi cualquier lenguaje de programación (ASP, PHP) y cualquier base de datos (Oracle, MySQL, SQL Server, etc.).
    * Aunque es estándar, determinadas bases de datos implementan **funciones específicas** que no necesariamente funcionan en otras. Siempre se recomienda revisar la documentación del SGBD para conocer su sintaxis concreta.
* **Características:** SQL es apreciado por su **potencia** y **versatilidad**, contrastando con su **facilidad de aprendizaje**, ya que utiliza un lenguaje bastante natural. Por esta última característica, se le considera un **Lenguaje de Cuarta Generación**.
* **Capacidades:** a pesar de ser llamado "lenguaje de consulta," SQL abarca mucho más que solo la consulta de datos:
    * Definición de la estructura de los datos (**DDL**).
    * Manipulación de datos (**DML**).
    * Especificación de conexiones seguras (**DCL**).

**Formas de trabajar con SQL:**
1.  **SQL embebido:** las sentencias se escriben **dentro de un programa** escrito en otro lenguaje (como Java o PHP).
2.  **SQL interpretado:** las sentencias se escriben y ejecutan en un **entorno gráfico** (como SQL Developer) o mediante un programa de **línea de comandos** (como SQLPlus para Oracle).

#### 10.1.- Elementos del lenguaje. Normas de escritura.

SQL se compone de comandos, cláusulas, operadores, funciones y literales, los cuales se combinan para formar instrucciones o sentencias que manipulan la base de datos.

| Elemento | Descripción |
| :--- | :--- |
| COMANDOS | Las instrucciones principales de SQL, que se distinguen en tres grupos: |
|| • **DDL:** permiten crear y definir nuevas bases de datos, tablas, campos, etc. |
|| • **DML:** permiten generar consultas para ordenar, filtrar y extraer datos |
|| • **DCL:** administran los derechos y restricciones de los usuarios |
| CLÁUSULAS | Palabras especiales que permiten modificar el funcionamiento de un comando |
| OPERADORES | Permiten crear expresiones complejas |
| FUNCIONES | Se utilizan para conseguir valores complejos |
| LITERALES | Valores concretos o constantes |

**Normas de escritura primordiales**
    - Todas las instrucciones deben terminar con `;`
    - No se distingue entre mayúsculas y minúsculas
    - Cualquier comando puede ser dividido con saltos de línea o espacios para facilitar su lectura
    - Los comentarios comienzan con `/*` y terminan con `*/`

### 11.- Lenguaje de descripción de datos (DDL)

El **DDL** es la primera fase del trabajo con cualquier base de datos y es imprescindible para crear, modificar y eliminar objetos de la base de datos (metadatos).

- Antes de almacenar y recuperar información, se deben definir las estructuras donde se guardarán los datos. Las estructuras básicas con las que trabaja SQL son las **tablas**.
- Aunque existen herramientas visuales que facilitan la labor, es imprescindible conocer el lenguaje SQL en profundidad para manipular los objetos sin depender de dichas herramientas.
- Las instrucciones DDL generan acciones que **no se pueden deshacer**, por lo que deben usarse con precaución y respaldadas por copias de seguridad.

En Oracle, cada usuario tiene un **esquema** con el mismo nombre que el usuario. Este esquema sirve para **almacenar los objetos** que posea ese usuario.

- Los objetos de los que hablamos pueden ser **tablas, vistas, índices** u otros objetos relacionados con la definición de la base de datos.
- En principio, solo el **usuario propietario** (quien los creó) y los **administradores** de la base de datos pueden crearlos y manipularlos. Estos privilegios pueden modificarse para permitir el acceso a otros usuarios.

#### 11.1.- Creación de bases de datos: objetos

La creación de una base de datos implica, en esencia, crear las tablas que la componen. Esto requiere primero definir un **espacio de nombres separado** para cada conjunto de tablas (esquemas o usuarios).

- La instrucción estándar para crear una base de datos es `CREATE DATABASE NombreBasedeDatos;`.
    * *Ejemplo:* `CREATE DATABASE RyMjuegos;`
- Según los estándares, una base de datos es un **conjunto de objetos** utilizados para gestionar los datos. Estos objetos están contenidos en **esquemas**, y los esquemas suelen estar asociados a un usuario.

> En Oracle, la sentencia `CREATE DATABASE` tiene un sentido distinto al de otros SGBD como MySQL. Nosotros trabajaremos creando las tablas **directamente en el esquema del usuario** creado previamente, por lo que **no utilizaremos la sentencia `CREATE DATABASE`**.

#### 11.2.- Creación de tablas

Antes de ejecutar la sentencia DDL para crear una tabla, es crucial tener clara la información obtenida en la fase de diseño lógico:
    - Nombre que se asignará a la tabla
    - Nombre que se asignará a cada columna (atributo)
    - Tipo y tamaño de datos que se almacenará en cada columna (dominio)
    - Restricciones que se aplicarán a los datos

Existen reglas estrictas para nombrar las tablas y otros objetos:
    - No puede haber nombres de tablas duplicados en el mismo esquema (usuario)
    - Deben comenzar por un carácter alfabético
    - La longitud máxima suele ser de **30 caracteres
    - Solo se permiten letras del alfabeto inglés, dígitos o el signo de guión bajo
    - No pueden coincidir con palabras reservadas de SQL
    - No se distingue entre mayúsculas y minúsculas por defecto
    - Si se utilizan comillas dobles alrededor del nombre, el nombre se vuelve sensible a mayúsculas*

```sql title="Instrucción DDL para crear una tabla"
CREATE TABLE [esquema.] nombredeTabla ( columna1 Tipo_Dato,columna2 Tipo_Dato, ...  columnaN Tipo_Dato );
```

```sql title="Ejemplo de creación de tabla básica"
CREATE TABLE USUARIOS (Nombre VARCHAR(25));
```

#### 11.3.- Restricciones

Una **restricción (Constraint)** es una **condición que una o varias columnas deben cumplir obligatoriamente** en una tabla. Las restricciones son fundamentales para asegurar la integridad y la consistencia de los datos.

Es una buena práctica asignar un nombre a cada restricción (si no se hace, el SGBD lo hará automáticamente). El nombre debe ser único para cada esquema (usuario) y ayudar a identificar la tabla, los campos involucrados y el tipo de restricción.

**Recomendación de Oracle para nombres de restricciones:**

1.  Tres letras para el nombre de la tabla.
2.  Carácter de subrayado (`_`).
3.  Tres letras con la columna afectada por la restricción.
4.  Carácter de subrayado (`_`).
5.  Dos letras con la abreviatura del tipo de restricción:
      * **PK** = Primary Key.
      * **FK** = Foreign Key.
      * **NN** = Not Null.
      * **UK** = Unique.
      * **CK** = Check (validación).

**Sintaxis de restricciones**

Las restricciones se definen durante la creación de la tabla (`CREATE TABLE`).

La sintaxis básica en SQL estándar (donde los corchetes `[]` indican opcionalidad) es:

```sql
CREATE TABLE NOMBRETABLA (
     Columna1 Tipo_Dato
          [CONSTRAINT nombredelarestricción]
          [NOT NULL]
          [UNIQUE]
          [PRIMARY KEY]
          [FOREIGN KEY]
          [DEFAULT valor]
          [REFERENCES nombreTabla [(columna [, columna ])]
          [ON DELETE CASCADE]]
          [CHECK condición],
     Columna2 Tipo_Dato
          [CONSTRAINT nombredelarestricción]
          [NOT NULL]
          [UNIQUE]
          [PRIMARY KEY]
          [FOREIGN KEY]
          [DEFAULT valor]
          [REFERENCES nombreTabla [(columna [, columna ])]
          [ON DELETE CASCADE]]
          [CHECK condición],...);
```

  * **`CONSTRAINT nombredelarestricción`**: asigna un nombre personalizado a la restricción
  * **`NOT NULL`**: asegura que el campo debe contener un valor
  * **`UNIQUE`**: garantiza que todos los valores en la columna o grupo de columnas sean diferentes
  * **`PRIMARY KEY`**: define la clave primaria
  * **`FOREIGN KEY` / `REFERENCES`**: define la clave ajena que hace referencia a una clave primaria en otra tabla
  * **`DEFAULT valor`**: especifica un valor por defecto si no se proporciona uno durante la inserción
  * **`CHECK condición`**: define una condición que debe ser verdadera para que los datos puedan ser insertados
  * **`ON DELETE CASCADE`**: (para `FOREIGN KEY`) especifica que si se elimina la fila padre, las filas hijas dependientes también se eliminan

```sql title="Ejemplo de restricciones en línea"
CREATE TABLE USUARIOS (
    Login VARCHAR(15) CONSTRAINT usu_log_PK PRIMARY KEY,
    Password VARCHAR (8) NOT NULL,
    Fecha_Ingreso DATE DEFAULT SYSDATE
);
```

##### 11.3.1.- Restricción NOT NULL

`NOT NULL` obliga a que una columna **tenga siempre un valor**, prohibiendo la asignación del valor nulo (`NULL`) a esa columna.

Se puede aplicar al crear o modificar el campo, añadiendo la cláusula `NOT NULL` después del tipo de dato.

```sql title="Sintaxis (con nombre de restricción)"
CREATE TABLE USUARIOS (
    F_Nacimiento DATE
    CONSTRAINT Usu_Fnac_NN NOT NULL
);
```

```sql title="Sintaxis (simplificada)"
CREATE TABLE USUARIOS (
    F_Nacimiento DATE NOT NULL
);
```

> **Cuidado:** se debe tener precaución con los valores nulos, ya que cualquier operación aritmética con `NULL` (ej., `1 * NULL`) resulta en `NULL`.

##### 11.3.2.- Restricción UNIQUE

`UNIQUE` asegura que **no se puedan repetir valores** en la columna o conjunto de columnas a la que se aplica.

    - **Índice automático:** Oracle (y otros SGBD) crea automáticamente un índice cuando se habilita esta restricción.

```sql title="Sintaxis (con nombre de restricción)"
CREATE TABLE USUARIOS (
    Login VARCHAR2 (25)
    CONSTRAINT Usu_Log_UK UNIQUE
);
```

```sql title="Sintaxis (simplificada)"
CREATE TABLE USUARIOS (
    Login VARCHAR2 (25) UNIQUE
);
```

**Clave compuesta (aplicación a múltiples campos):** se define la restricción después de la declaración de todas las columnas a las que afecta, referenciando los campos entre paréntesis:

```sql
CREATE TABLE USUARIOS (
    Login VARCHAR2 (25),
    Correo VARCHAR2 (25),
    CONSTRAINT Usuario_UK UNIQUE (Login, Correo)
);
```

##### 11.3.3.- Restricción PRIMARY KEY

`PRIMARY KEY` define la **clave primaria** de la tabla, que es el campo o conjunto de campos que identifica de modo único cada tupla.

  * **Regla:** solo puede haber **una clave primaria por tabla**.
  * **Propiedades implicadas:** la clave primaria automáticamente obliga a que los campos sean **`NOT NULL`** y **`UNIQUE`**.
  * **Referenciabilidad:** dicha clave puede ser referenciada como clave ajena en otras tablas.

```sql title="Sintaxis (clave simple)"
CREATE TABLE USUARIOS (
    Login VARCHAR2 (25) PRIMARY KEY
);
```

```sql title="Sintaxis (clave compuesta):"
/* Se debe utilizar este formato al final de la definición de los campos, antes del paréntesis de cierre */
CREATE TABLE USUARIOS (
    Nombre VARCHAR2 (25),
    Apellidos VARCHAR2 (30),
    F_Nacimiento DATE,
    CONSTRAINT Usu_PK PRIMARY KEY(Nombre, Apellidos, F_Nacimiento)
);
```

##### 11.3.4.- Restricción REFERENCES. FOREIGN KEY.

`FOREIGN KEY` establece que un campo o conjunto de campos hace **referencia** a la clave primaria (o clave candidata) de otra tabla.

```sql title="Sintaxis con REFERENCES (opción de columna)"
CREATE TABLE USUARIOS (
    Cod_Partida NUMBER(8)
        CONSTRAINT Cod_Part_FK
        REFERENCES PARTIDAS(Cod_Partida)
);
```

```sql title="Sintaxis simplificada (si se referencia la clave primaria de la otra tabla)"
CREATE TABLE USUARIOS (
    Cod_Partida NUMBER(8)
        CONSTRAINT Cod_Part_FK
        REFERENCES PARTIDAS
);
```

```sql title="Sintaxis con FOREIGN KEY (opción de tabla o clave compuesta)"
CREATE TABLE USUARIOS (
    Cod_Partida NUMBER(8),
    F_Partida DATE,
    CONSTRAINT Partida_Cod_F_FK FOREIGN KEY (Cod_Partida, F_Partida)
    REFERENCES PARTIDAS
);
```

**Orden de creación/borrado:**
    - **Creación:** siempre se deben crear las tablas que tienen claves ajenas **después** de aquellas donde esos campos son claves primarias o candidatas.
    - **Borrado:** se deben borrar las tablas que tienen claves ajenas **antes** que las tablas que contienen las claves primarias referenciadas.

**Acciones de Integridad Referencial (Junto a `REFERENCES`):**
Estas opciones definen qué debe hacer el SGBD cuando se borra o modifica la fila referenciada:
    - `ON DELETE CASCADE`: permite borrar todos los registros cuya clave ajena sea igual a la clave del registro borrado.
    - `ON DELETE SET NULL`: coloca el valor `NULL` en todas las claves ajenas relacionadas con la borrada.
    - `ON DELETE SET DEFAULT xxxx`: coloca el valor `xxxx` (valor por defecto) en todas las claves ajenas relacionadas.

> **Nota:** estas opciones también son válidas para la operación de modificación, especificando `ON UPDATE` en lugar de `ON DELETE`.

##### 11.3.5.- Restricción DEFAULT Y VALIDACIÓN

`DEFAULT` asigna un **valor por defecto** a una columna si no se proporciona uno durante la inserción de la tupla.

```sql title="Sintaxis (valor constante)"
CREATE TABLE USUARIOS (
    Pais VARCHAR2(20) DEFAULT 'España'
);
```

```sql title="Sintaxis (uso de funciones)"
CREATE TABLE USUARIOS (
    Fecha_ingreso DATE DEFAULT SYSDATE
);
```

`CHECK` comprueba que se cumpla una **condición determinada** al rellenar una columna. Dicha condición puede ser construida con otras columnas de la misma tabla.

```sql title="Sintaxis"
CREATE TABLE USUARIOS (
    Credito NUMBER(4) CHECK (Credito BETWEEN 0 AND 2000)
);
```

> **Múltiples CHECK:** una misma columna puede tener varios `CHECK` asociados, separando los `CONSTRAINT` por comas.

#### 11.4.- Eliminación de tablas

Cuando una tabla deja de ser útil, se puede eliminar para liberar espacio y permitir la reutilización de su nombre. El comando utilizado para esto es `DROP TABLE`.

```sql
DROP TABLE NombreTabla [CASCADE CONSTRAINTS];
```

- Esta instrucción elimina la tabla de la base de datos, incluyendo todos sus datos (filas) y toda la información de definición almacenada en el Diccionario de Datos.
- `CASCADE CONSTRAINTS`: esta opción es necesaria cuando la tabla a borrar tiene alguna columna que actúa como clave ajena en otras tablas (tablas secundarias). Al incluirla, se borran automáticamente las restricciones de clave ajena relacionadas **antes** de eliminar la tabla principal.

```sql title="Ejemplo de eliminación"
DROP TABLE USUARIOS;
```

> El comando `DROP TABLE` es **irreversible**, y el SGBD no pide confirmación antes de ejecutarse.

**Consecuencias del borrado:**
    - Desaparecen todos los datos de la tabla.
    - Cualquier vista asociada a esa tabla seguirá existiendo, pero **dejará de funcionar** al no encontrar la tabla base.

> **Alternativa:** la orden `TRUNCATE TABLE` elimina solo los datos (filas) de una tabla, **sin eliminar su estructura**.

#### 11.5.- Modificación de tablas (I)

Para modificar la estructura, las columnas o las restricciones de una tabla ya creada, se utiliza el comando `ALTER TABLE`, salvo para el cambio de nombre de la tabla.

```sql title="Renombrar una tabla"
RENAME NombreViejo TO NombreNuevo;
```

```sql title="Añadir columnas"
ALTER TABLE NombreTabla ADD
(
    ColumnaNueva1 Tipo_Datos [Propiedades],
    ColumnaNueva2 Tipo_Datos [Propiedades]
);
```

```sql title="Eliminar columnas"
ALTER TABLE NombreTabla DROP COLUMN (Columna1 [, Columna2, ...]);
```

```sql title="Modificar columnas"
ALTER TABLE NombreTabla MODIFY
(
    Columna1 TipoDatos [propiedades] [, columna2 TipoDatos [propiedades] ...]
);
```

Se pueden modificar el tipo de datos y las propiedades de una columna. Los cambios son posibles sin restricciones **si la tabla no contiene datos**.

Si la tabla **no está vacía**, se puede:
    - Aumentar la longitud de una columna
    - Aumentar o disminuir el número de posiciones decimales en tipos `NUMBER`
    - Reducir la anchura, siempre que los datos existentes no ocupen todo el espacio reservado

```sql title="Renombrar columnas"
ALTER TABLE NombreTabla RENAME COLUMN NombreAntiguo TO NombreNuevo;
```

```sql title="Ejemplo de renombrar columna"
ALTER TABLE USUARIO RENAME COLUMN User TO Login;
```

<details>
<summary>**Ejercicio resuelto**</summary>

> Tenemos creada la siguiente tabla:

```sql
CREATE TABLE EMPLEADOS (
    Cod_Cliente VARCHAR(5) PRIMARY KEY,
    Nombre VARCHAR(10),
    Apellidos VARCHAR(25),
    Sueldo NUMBER(2));
```

> Ahora queremos poner una restricción a sueldo para que tome valores entre 1000 y 1200, ¿cómo lo harías?

```sql
ALTER TABLE EMPLEADOS MODIFY (Sueldo NUMBER(2) CHECK (Sueldo BETWEEN 1000 AND 1200));
```
</details>

##### 11.5.1.- Modificación de tablas (II)

El comando `ALTER TABLE` no solo se utiliza para modificar columnas, sino también para manipular las **restricciones (constraints)** de una tabla.

| Operación | Sintaxis SQL | Notas |
| :--- | :--- | :--- |
| Borrar restricciones | `ALTER TABLE NombreTabla DROP CONSTRAINT NombreRestriccion;` | Elimina la restricción especificada de la tabla. |
| Renombrar restricciones | `ALTER TABLE NombreTabla RENAME CONSTRAINT NombreViejo TO NombreNuevo;` | Permite cambiar el nombre de una restricción existente. |
| Desactivar restricciones | `ALTER TABLE NombreTabla DISABLE CONSTRAINT NombreRestriccion [CASCADE];` | Desactiva temporalmente una restricción, lo que puede ser útil para pruebas o para insertar datos que temporalmente incumplen la regla. La opción `CASCADE` desactiva las restricciones que dependen de ella. |
| Activar restricciones | `ALTER TABLE NombreTabla ENABLE CONSTRAINT NombreRestriccion [CASCADE];` | Vuelve a activar una restricción previamente desactivada. |

#### 11.6.- Creación y eliminación de índices

Los índices son estructuras que mejoran la velocidad de acceso y localización de la información contenida en las tablas.

```sql title="Sintaxis para crear un índice"
CREATE INDEX NombreIndice ON NombreTabla (Columna1 [, Columna2 ...]);
```

  * Es aconsejable utilizar índices en campos de tablas grandes que se usen frecuentemente en consultas (`SELECT`) o en condiciones de búsqueda (`WHERE`).
  * Se deben evitar índices sobre:
      * Campos de tablas pequeñas
      * Campos que se actualicen con mucha frecuencia (ya que la actualización de la tabla también implica la actualización del índice)
      * Campos que no se usan en consultas o expresiones frecuentemente

> **Importancia:** el diseño de índices es crítico. Un diseño pobre causa ineficiencia, y un uso excesivo puede ralentizar gravemente las operaciones de inserción y modificación (`INSERT`/`UPDATE`), e incluso bloquear la Base de Datos.


```sql title="Sintaxis para eliminar un índice"
DROP INDEX NombreIndice;
```

> La mayoría de los índices se crean automáticamente (implícitamente) cuando se definen las restricciones `PRIMARY KEY`, `FOREIGN KEY` o `UNIQUE`.

<details>
<summary>**Ejercicio resuelto**</summary>

> Tenemos creada la siguiente tabla:

```sql
CREATE TABLE EMPLEADOS (
    Cod_Cliente VARCHAR(5) PRIMARY KEY,
    Nombre VARCHAR(10),
    Apellidos VARCHAR(25),
    Sueldo NUMBER(2));
```

> Crea un índice con el campo *Apellidos*, luego elimínalo. 

```sql
CREATE INDEX miIndice ON EMPLEADOS (Apellidos);
    DROP INDEX miIndice;
```
</details>

### 12.- Lenguaje de control de datos (DCL)

El **DCL** se utiliza para administrar los derechos y restricciones de los usuarios, gestionando el acceso y los permisos dentro de la base de datos.

Las claves de acceso de los usuarios se almacenan encriptadas en una tabla del diccionario de datos (ej., `DBA_USERS` en Oracle).

```sql title="Sintaxis de creación de usuarios"
CREATE USER NombreUsuario
IDENTIFIED BY ClaveAcceso
[DEFAULT TABLESPACE tablespace ]
[TEMPORARY TABLESPACE tablespace]
[QUOTA int {K | M} ON tablespace]
[QUOTA UNLIMITED ON tablespace]
[PROFILE perfil];
```

| Cláusula | Función | Notas |
| :--- | :--- | :--- |
| `CREATE USER` | Crea un nombre de usuario que será reconocido por el sistema. | |
| `IDENTIFIED BY` | Asigna la clave de acceso al usuario. | |
| `DEFAULT TABLESPACE` | Asigna el *Tablespace* por defecto para almacenar los objetos que cree el usuario. Si se omite, suele ser `SYSTEM`. | |
| `TEMPORARY TABLESPACE` | Especifica el *Tablespace* para trabajos temporales. Por defecto suele ser `SYSTEM`. | |
| `QUOTA` | Asigna un límite de espacio (`K` o `M`) en el *Tablespace* asignado. | Si no se especifica, el usuario no tendrá espacio y no podrá crear objetos. |
| `PROFILE` | Asigna un perfil al usuario. Si se omite, se asigna el perfil por defecto. | |

```sql title="Ejemplo de creación de usuario limitado"
CREATE USER UsuarioLimitado IDENTIFIED BY passworddemiusuariolimitado;
```

> Para ver los usuarios creados, se consultan las vistas `ALL_USERS` y `DBA_USERS`.

```sql title="Sintaxis de modificación de usuarios"
ALTER USER NombreUsuario
IDENTIFIED BY clave_acceso
[DEFAULT TABLESPACE tablespace ]
[TEMPORARY TABLESPACE tablespace]
[QUOTA int {K | M} ON tablespace]
[QUOTA UNLIMITED ON tablespace]
[PROFILE perfil];
```

> Un usuario sin privilegios de Administrador solo puede cambiar su propia clave de acceso. Al modificar una contraseña cifrada, su contenido debe insertarse ya cifrado en la base de datos.

```sql title="Sintaxis de eliminación de usuarios"
DROP USER NombreUsuario [CASCADE];
```

- `CASCADE` borra automáticamente **todos los objetos** (tablas, vistas, etc.) propiedad del usuario antes de eliminarlo. Sin esta opción, el comando fallará si el usuario tiene objetos creados.

#### 12.1.- Permisos (I)

Para poder llevar a cabo cualquier operación o acceder a objetos en la base de datos, un usuario debe haber sido **concedido el permiso (privilegio)** para realizar dicha acción.
    - Los privilegios se pueden agrupar en **roles**, lo que simplifica la administración. Un permiso puede ser asignado a un usuario o a un rol.
    - Los permisos se conceden utilizando el comando DCL `GRANT`.

```sql title="Concesión de privilegios sobre objetos"
GRANT {privilegio_objeto [, privilegio_objeto]...|ALL|[PRIVILEGES]}
ON [usuario.]objeto
TO {usuario1|rol1|PUBLIC} [,{usuario2|rol2|PUBLIC] ...
[WITH GRANT OPTION];
```

| Cláusula | Función |
| :--- | :--- |
| `ON [usuario.]objeto` | Especifica el **objeto** (tabla, vista, etc.) sobre el que se conceden los privilegios. |
| `TO {usuario1\|rol1\|PUBLIC}` | Señala a los **usuarios o roles** que reciben los privilegios. `PUBLIC` otorga el privilegio a todos los usuarios. |
| `ALL` | Concede **todos los privilegios** posibles sobre el objeto especificado. |
| `[WITH GRANT OPTION]` | Permite que el receptor del privilegio pueda, a su vez, **concederlo a otros**. |

```sql title="Ejemplos"
-- Permite a Ana insertar datos en la tabla Usuarios
GRANT INSERT ON Usuarios TO Ana;

-- Concede a Ana todos los privilegios sobre la tabla Partidas
GRANT ALL ON Partidas TO Ana;
```

```sql title="Concesión de privilegios de sistema"
GRANT {Privilegio1 | rol1 } [, privilegio2 | rol2}, ...]
TO {usuario1 | rol1| PUBLIC} [, usuario2 | rol2 | PUBLIC} ... ]
[WITH ADMIN OPTION];
```

| Cláusula | Función |
| :--- | :--- |
| `TO {usuario1\|rol1\|PUBLIC}` | Señala a los usuarios o roles a los que se conceden los privilegios de sistema. |
| `[WITH ADMIN OPTION]` | Permite que el receptor de los privilegios pueda **conceder esos mismos privilegios** a otros usuarios o roles (similar a `WITH GRANT OPTION` para objetos). |

```sql title="Ejemplos"
-- Concede a Ana el rol de CONNECT (con todos sus privilegios asociados)
GRANT CONNECT TO Ana;

-- Concede a Ana el privilegio de borrar usuarios y el derecho a conceder este mismo privilegio a otros
GRANT DROP USER TO Ana WITH ADMIN OPTION;
```

##### 12.1.1.- Permisos (II)

Para retirar los permisos o privilegios que han sido concedidos, se utiliza el comando DCL `REVOKE`.

```sql title="Revocación de privilegios sobre objetos"
REVOKE {privilegio_objeto [, privilegio_objeto]...|ALL|[PRIVILEGES]}
ON [usuario.]objeto
FROM {usuario|rol|PUBLIC} [,{usuario|rol|PUBLIC] ...;
```

```sql title="Ejemplo"
-- Juan retira el permiso de seleccionar y actualizar sobre la tabla Usuarios a Ana
REVOKE SELECT, UPDATE ON Usuarios FROM Ana;
```

```sql title="Revocación de privilegios de sistema o roles a usuarios"
REVOKE {privilegio_stma | rol} [, {privilegio_stma | rol}]...|ALL|[PRIVILEGES]}
FROM {usuario|rol|PUBLIC} [,{usuario|rol|PUBLIC] ...;
```

```sql title="Ejemplo"
-- Juan retira el permiso de eliminar usuarios a Ana
REVOKE DROP USER FROM Ana;
```

### Anexo - Elementos del lenguaje SQL

#### Comandos

##### DDL

| Comando | Descripción |
| :--- | :--- |
| **`CREATE`** | Crear nuevas tablas, campos e índices |
| **`DROP`** | Eliminar tablas e índices |
| **`ALTER`** | Modificar la estructura de las tablas |

##### DML

| Comando | Descripción |
| :--- | :--- |
| **`SELECT`** | Consultar filas que satisfagan un criterio determinado |
| **`INSERT`** | Cargar datos en la tabla en una única operación |
| **`UPDATE`** | Modificar valores de campos y filas específicos |
| **`DELETE`** | Eliminar filas de una tabla |

##### DCL

| Comando | Descripción |
| :--- | :--- |
| **`GRANT`** | Dar permisos a uno o varios usuarios o roles para realizar tareas determinadas |
| **`REVOKE`** | Eliminar permisos que previamente se han concedido con `GRANT` |

#### Cláusulas

| Cláusulas | Descripción |
| :--- | :--- |
| **`FROM`** | Especificar la tabla o tablas de la(s) que se van a seleccionar las filas |
| **`WHERE`** | Especificar las condiciones que deben reunir las filas que se van a seleccionar |
| **`GROUP BY`** | Separar las filas seleccionadas en grupos específicos |
| **`HAVING`** | Expresar la condición que debe satisfacer cada grupo (filtra grupos, a diferencia de `WHERE` que filtra filas) |
| **`ORDER BY`** | Ordenar las filas seleccionadas de acuerdo a un orden específico |

#### Operadores

##### Lógicos

| Operadores | Descripción |
| :--- | :--- |
| **`AND`** | Evalúa dos condiciones y devuelve un valor de verdad sólo si **ambas** son ciertas |
| **`OR`** | Evalúa dos condiciones y devuelve un valor de verdad si **alguna** de las dos es cierta |
| **`NOT`** | Devuelve el valor contrario de la expresión |

##### De comparación

| Operadores | Descripción |
| :--- | :--- |
| **`<`** | Menor que |
| **`>`** | Mayor que |
| **`< >`** | Distinto de |
| **`<=`** | Menor o igual |
| **`>=`** | Mayor o igual |
| **`=`** | Igual |
| **`BETWEEN`** |Especificar si un valor está dentro de un intervalo de valores |
| **`LIKE`** | Comparar una cadena de caracteres con un patrón |
| **`IN`** | Especificar si un valor coincide con alguno de una lista de valores |

#### Funciones

| Función | Descripción |
| :--- | :--- |
| **`AVG`** | Calcula el promedio (media) de los valores de un campo determinado |
| **`COUNT`** | Devuelve el número de filas de la selección |
| **`SUM`** | Devuelve la suma de todos los valores de un campo determinado |
| **`MAX`** | Devuelve el valor más alto de un campo determinado |
| **`MIN`** | Devuelve el valor mínimo de un campo determinado |

#### Literales

| Literales | Descripción |
| :--- | :--- |
| **`'23/03/97'`** | Literal fecha |
| **`'María'`** | Literal de caracteres (texto) |
| **`5`** | Literal número (entero o decimal) |

## **UD3.- Interpretación de diagramas entidad/relación**

![Esquema Unidad 3 Bases de Datos](../../static/img/bases-de-datos-unidad-3.jpg)

### 1.- Análisis y diseño de bases de datos

El desarrollo de bases de datos se divide en dos fases principales: **Análisis** y **Diseño**, orientadas a la creación del **Esquema Conceptual**, que representa la estructura de la información de manera **independiente del SGBD**. Saltarse la fase conceptual puede llevar a la pérdida de información del mundo real.

Fases de Trabajo| Fase de Análisis | Fase de Diseño |
| --- | --- |
| **Análisis de Entidades** (localizar y definir entidades y atributos). | **Diseño de Tablas** y **Normalización**. |
| **Análisis de Relaciones** (definir vínculos entre entidades). | **Diseño de Transacciones** y **Diseño de Sendas de Acceso**. |
| Obtención del **Esquema Conceptual** (usando el modelo E-R). | Aplicación de retrodiseño y enfoque relacional. |

**Modelos conceptuales clave** 
- **Modelo Entidad/Relación (E-R):** presentado por Peter Chen, es la base para el esquema conceptual.
- **Modelo Entidad/Relación Extendido (ERE)** es actualmente el más aceptado.

**Fases del Diseño de la Base de Datos**

El diseño progresa en tres niveles de abstracción:

1. **Diseño Conceptual:** Alto nivel de abstracción. Se usa el **Modelo E-R**.
2. **Diseño Lógico:** Nivel medio/lógico. Transformación a estructuras soportables por un SGBD (ej., **tablas**). Se usa el **Modelo Relacional**.
3. **Diseño Físico:** Implementación final. Se usa el lenguaje **DDL de SQL** en el SGBD específico (ej., Oracle).

**Diferencias entre Modelos**

| Modelo Conceptual (MC) | Modelo Lógico (ML) |
| --- | --- |
| **Independiente del SGBD** (no lleva estructuras de *hardware*). | **Dependiente del SGBD** (contiene estructuras soportadas por el ordenador, como tablas). |
| Nivel de abstracción **más alto**. | Nivel de abstracción **menor** (más concreto). |
| Mejor **capacidad semántica** (más significado conceptual). | Menor **capacidad semántica** (más enfocado en la relación física). |
| Interfaz entre el **usuario y la informática**. | Interfaz entre el **informático y el SGBD**. |

### 2.- ¿Qué es el Modelo E/R?

El **Modelo Entidad-Relación (E/R)** es una herramienta conceptual clave para representar problemas del mundo real y facilitar el diseño de bases de datos.

* **Objetivo:** especificar un **Esquema Conceptual** que represente la estructura lógica completa de una base de datos, partiendo de descripciones textuales de la realidad.
* **Naturaleza:** es un **modelo semántico**, lo que significa que representa el significado de los datos. Por ello, es independiente de cualquier sistema físico o ámbito informático puro; puede describir procesos de producción o estructuras empresariales.
* **Base:** el modelo, creado por Peter Chen en los años setenta, se basa en la percepción de **objetos básicos llamados entidades** y las **relaciones** entre estos objetos.

### 3.- Entidades

Una **Entidad** es un objeto (físico o abstracto), un concepto o cualquier elemento que tenga importancia para la organización y del cual se desee **guardar información**. Cada entidad debe poseer características que la hagan única frente al resto de objetos (ej., un ALUMNO distinguido por su Número de Identificación Escolar - NIE).

> **Entidad:** objeto real o abstracto, con características diferenciadoras capaces de distinguirse de otros objetos, acerca del cual se desea guardar información.

* **Ejemplos:** `camping`, `río`, `pico` (concretos), o `préstamo`, `reserva` (abstractos).
* **Conjunto de Entidades:** es un grupo de entidades que poseen las mismas características o propiedades (ej., el conjunto de entidades `CLIENTE` representa todas las personas que hacen reservas en un hotel). Generalmente, el término "entidad" se usa para identificar el "conjunto de entidades".
* **Ocurrencia de Entidad:** cada elemento individual dentro del conjunto de entidades.
* **Símil con POO:** el concepto de entidad es análogo al de **instancia de objeto**, y el conjunto de entidades es análogo al de **clase**.

**Representación Gráfica:** en el modelo E/R, la entidad se representa con el nombre encerrado en un **rectángulo**.

#### 3.1.- Tipos: fuertes y débiles

Las entidades se clasifican en:

- **Entidades fuertes o regulares**: tienen existencia por sí mismas, es decir, su existencia no depende de la existencia de otras entidades. (Ej., la existencia de un `DOCTOR` no depende de la existencia de un `PACIENTE`).
    - **Representación:** rectángulo simple.

- **Entidades débiles**: su existencia depende de la existencia de otra entidad fuerte con la que se relaciona.
    > **Entidad débil:** tipo de entidad cuyas propiedades o atributos no la identifican completamente, sino solo de forma parcial. Requiere participar en una relación que ayude a identificarla (ej., `AULA` necesita la clave de `EDIFICIO` para ser única).
    - **Representación:** el nombre de la entidad encerrado en un **rectángulo doble**.

Las entidades débiles presentan dos tipos de dependencia:
    1. **Dependencia en existencia:** si desaparece una instancia de la entidad fuerte, desaparecen las instancias de la entidad débil que dependen de ella.
    * *Representación:* Se incluye una **E** en el interior de la relación débil.
    2. **Dependencia en identificación:** requiere la dependencia en existencia y, además, la ocurrencia de la entidad débil no puede identificarse por sí misma, necesitando la clave de la entidad fuerte asociada.
    * *Representación:* Se incluye una **ID** en el interior de la relación débil.

> **Recomendación:** tanto las entidades fuertes como las débiles se nombran habitualmente con sustantivos en singular.

### 4.- Atributos

Los **atributos** son las propiedades o características que describen a una entidad o relación, y se utilizan para guardar información sobre ellas.

* Cada ocurrencia de entidad tendrá su propio valor para cada atributo (ej. cada paciente tendrá una fecha de nacimiento distinta).
* **Definición:** Cada una de las propiedades o características que tiene un tipo de entidad o un tipo de relación. Los atributos toman valores de uno o varios **dominios**.

**Representación gráfica:** en el modelo E/R, los atributos se representan mediante el nombre del atributo rodeado por una **elipse** y conectado a la entidad mediante una línea recta. El nombre debe ser único y en minúscula.

El **dominio** es el conjunto de valores permitidos para un atributo. Todos los posibles valores que puede tomar un atributo deben estar dentro de su dominio (ej. cadenas de caracteres de cierta longitud). Es recomendable establecer límites adecuados para que el SGBD pueda verificar los datos y garantizar la integridad.

#### 4.1.- Tipos de atributos

Los atributos se clasifican según varias características:

**Obligatorios y Opcionales**
- **Obligatorio:** aquel que siempre debe estar definido para una entidad o relación (ej., el DNI de un jugador). Una clave es siempre un atributo obligatorio.
- **Opcional:** aquel que **podría no estar definido** o no tener valor para algunas ocurrencias de entidad.

**Atómicos o Compuestos**
- **Simple o Atómico:** no puede dividirse en partes o atributos más pequeños que tengan significado propio (ej., el `dni` de un jugador).
- **Compuesto:** puede dividirse en subpartes que constituyen otros atributos con significado propio (ej., la `Dirección` se compone de `calle`, `número` y `localidad`).

**Monovaluados o Multivaluados**
- **Monovaluado:** tiene un **único valor** para cada ocurrencia de entidad (ej., `dni`).
- **Multivaluado:** puede tomar **diferentes valores** para cada ocurrencia de entidad (ej., un empleado puede tener varias direcciones de `e-mail`). Se representa con una elipse doble. En este tipo de atributos hay que tener en cuenta los siguientes conceptos:
        - **Cardinalidad de un Atributo:** indica el número **mínimo** y **máximo** de valores que puede tomar para cada ejemplar de la entidad a la que pertenece.
        - **Cardinalidad Mínima:** cantidad mínima de valores que debe existir (casi siempre 0 -opcional- o 1 -obligatorio-).
        - **Cardinalidad Máxima:** cantidad máxima de valores (generalmente 1 o *n* -múltiples-).

        *Ejemplo:* El atributo `E_mail` con cardinalidad **(0,n)** significa que es opcional (mínimo 0 valores) y puede almacenar múltiples cuentas (máximo *n* valores).

**Derivados, Calculados o Almacenados**  
El valor de este tipo de atributos se puede **obtener (calcular)** a partir del valor o valores de otros atributos relacionados.

*Ejemplo:* la **Edad** es un atributo derivado, ya que se calcula a partir de la **Fecha de Nacimiento** (atributo almacenado). Por lo tanto, no se debe almacenar la edad, sino la fecha de nacimiento. Se representa con una elipse discontinua o punteada.

#### 4.2.- Claves

Para identificar correctamente cada ocurrencia de entidad o relación, se utilizan las **claves**, que son un subconjunto de atributos cuyos valores permiten identificar a la entidad de forma unívoca.

* **Superclave (Superllave):** es cualquier conjunto de atributos que permite identificar de forma única a una ocurrencia de entidad. (La combinación de *todos* los atributos de una entidad es siempre una superclave).
* **Clave Candidata:** es una superclave que es **irreductible**; es decir, si se elimina cualquiera de sus atributos, el subconjunto restante ya no es una superclave.
* **Criterios de elección (basados en el dominio):** los valores deben ser conocidos (no nulos), la memoria que ocupen debe ser mínima, la codificación sencilla y el contenido de sus valores no debe variar.


* **Clave Primaria (Primary Key - PK):** es la clave candidata que el diseñador de la base de datos **escoge** para identificar unívocamente a cada ocurrencia de entidad.
* **Propiedades:** toma valores únicos y **no puede contener valores nulos**.
* **Criterios de elección (entre claves candidatas):**
    - Menor longitud
    - Simples sobre compuestas
    - Numéricas sobre no numéricas
    - Codificadas sobre no codificadas
    - Las de ámbito local sobre las de ámbito más general

* **Claves Alternativas o Secundarias:** las restantes claves candidatas que no fueron escogidas como clave primaria.

**Representación en el Modelo E/R:**
    - Si se usan elipses para atributos: se **subrayarán** aquellos que formen la clave primaria.
    - Si se usan círculos para atributos: se utilizará un **círculo negro** para aquellos que formen la clave primaria.

#### 4.3.- Atributos de una relación

Una **relación** también puede tener atributos que la describan. Estos atributos almacenan información específica sobre la asociación entre las entidades.

* **Ejemplo 1:** en la relación **CURSA** (entre ALUMNO y ASIGNATURA), el atributo `nota` se asocia a la relación para registrar la nota obtenida por un alumno en una asignatura determinada.
* **Ejemplo 2:** en relaciones que representan históricos (ej., CLIENTE y FACTURA), se puede crear un atributo `fecha_emision` asociado a la relación para registrar el momento de la acción.

**Representación en el Modelo E/R:**

La representación de atributos asociados a relaciones es **exactamente igual** a la que se utiliza para entidades (elipse con el nombre conectada a la relación).

### 5.- Relaciones

Las **relaciones** (o interrelaciones) son el elemento del modelo E/R que permite asociar datos entre sí, vinculando una ocurrencia de una entidad con otra de una entidad distinta.

* **Definición:** asociación entre diferentes entidades. En una relación, no pueden aparecer dos veces relacionadas las mismas ocurrencias de las entidades.
* **Representación gráfica:** se representan mediante un **rombo** que contiene un nombre (habitualmente un verbo en singular como "imparte", "posee" o "atiende"). El rombo se conecta a las entidades participantes mediante líneas rectas.

Para definir una relación, se deben considerar tres conceptos clave: el grado, la cardinalidad de la relación y la cardinalidad de las entidades.

#### 5.1.- Grado de una relación

El grado es el **número de entidades que participan** en una misma relación.

* **Relación Unaria (Grado 1):** participa una única entidad. También se denominan **reflexivas** o recursivas.
* **Relación Binaria (Grado 2):** participan dos entidades. Es el tipo de relación más común y el objetivo de la mayoría de los diseños lógicos.
* **Relación Ternaria (Grado 3):** participan tres entidades simultáneamente.
* **Relación N-aria (Grado n):** unvolucra *n* entidades. No son usuales y suelen simplificarse a relaciones de menor grado.
* **Relación Doble:** dos entidades están conectadas mediante dos relaciones distintas (ej. un empleado "dirige" un departamento y también "trabaja" en él).

#### 5.2.- Cardinalidad de relaciones

Indica el **número máximo** de ocurrencias de cada entidad que pueden intervenir en una ocurrencia de relación. Se expresa mediante etiquetas como **1:1, 1:N o M:N**.

| Tipo de relación | Descripción | Ejemplo |
| --- | --- | --- |
| **Uno a uno (1:1)** | Una instancia de A se relaciona con una de B, y viceversa. | Un `ALUMNO` tiene un único `EXPEDIENTE`. |
| **Uno a muchos (1:N)** | Una instancia de A se relaciona con muchas de B, pero una de B solo con una de A. | Un `DOCENTE` imparte varias `ASIGNATURAS`. |
| **Muchos a uno (N:1)** | Varias instancias de A se asocian con una única de B. | Muchos `JUGADORES` pertenecen a un `EQUIPO`. |
| **Muchos a muchos (M:N)** | Una instancia de A se relaciona con muchas de B, y viceversa. | Un `ALUMNO` puede cursar muchas `ASIGNATURAS`. |

#### 5.3.- Cardinalidad de entidades

A diferencia de la anterior, esta especifica el **número mínimo y máximo** de correspondencias en las que puede participar **cada ejemplar** de una entidad. Se representa con un paréntesis del tipo **(min, max)**.

* **Cardinalidad mínima:** indica el número mínimo de asociaciones (habitualmente **0** para participación opcional o **1** para participación obligatoria/total).
* **Cardinalidad máxima:** indica el número máximo de asociaciones (habitualmente **1** o **n** para representar "muchos").

**Ubicación en el diagrama:** los valores se colocan junto a la entidad con la que se relaciona (en el lado opuesto de la relación) para indicar su participación.

**Ejemplo Práctico:**
    - Un `JUGADOR` pertenece a **(0,1)** `EQUIPOS`: Puede no estar en ninguno o como máximo en uno.
    - Un `EQUIPO` tiene **(1,n)** `JUGADORES`: Debe tener al menos uno y puede tener muchos.

### 6.- Simbología del modelo E/R

![Simbología del modelo Entidad/Relación 1](../../static/img/bbdd-simbologia-1.jpg)
![Simbología del modelo Entidad/Relación 2](../../static/img/bbdd-simbologia-2.jpg)
![Simbología del modelo Entidad/Relación 3](../../static/img/bbdd-simbologia-3.jpg)

### 7.- El modelo E/R Extendido

El **Modelo Entidad/Relación Extendido (ERE)** incorpora elementos adicionales al modelo tradicional para mejorar su capacidad de representar circunstancias complejas y requisitos semánticos específicos.

Estas nuevas características incluyen restricciones avanzadas en las relaciones, así como conceptos de abstracción como la especialización, generalización, herencia y agregación.

#### 7.1.- Restricciones en las relaciones

El modelo extendido permite definir cómo deben comportarse las ocurrencias de entidades cuando participan en múltiples relaciones simultáneamente.

| Tipo de restricción | Descripción |
| --- | --- |
| **Exclusividad** | Una entidad participa en dos o más relaciones, pero cada ocurrencia solo puede pertenecer a **una de ellas** a la vez. Ej: Un músico dirige *o* toca en una orquesta, pero no ambas. |
| **Exclusión** | Las ocurrencias de las entidades solo pueden asociarse utilizando **una única relación específica** entre ellas. Ej: Si un monitor imparte un curso concreto, no puede estar recibiendo ese mismo curso. |
| **Inclusividad** | Para que una entidad participe en una relación, debe haber participado previamente en otra. Ej: Un monitor debe recibir al menos 2 cursos antes de poder impartir cualquiera. |
| **Inclusión** | Es una restricción más fuerte que la inclusividad. Una ocurrencia de entidad asociada a otra a través de una relación, debe estar unida a **esa misma ocurrencia** a través de la otra relación. |

Representación de restricción de exclusión:  
![Representación de restricción de exclusión](../../static/img/bbdd-restriccion-exclusion.jpg)

Representación restricción inclusividad:  
![Representación de restricción de inclusividad](../../static/img/bbdd-restriccion-inclusividad.jpg)

Representación restricción inclusión:  
![Representación de restricción de inclusión](../../static/img/bbdd-restriccion-inclusion.jpg)

#### 7.2.- Generalización y especialización

Esta extensión del modelo ERE permite modelar la realidad mediante **jerarquías** de entidades, utilizando los conceptos de refinamiento ascendente (**generalización**) y descendente (**especialización**).

* **Superclase (Supertipo):** Conjunto de entidades de nivel superior que engloba características comunes.
* **Subclase (Subtipo):** Conjunto de entidades de nivel inferior que poseen atributos específicos además de los comunes.

Identificamos una jerarquía cuando un grupo de entidades comparte ciertos atributos (**superclase**) pero se diferencian por otros atributos únicos (**subclase**).

La **herencia** es la característica fundamental de las jerarquías. Las **subclases heredan todos los atributos** de su superclase. Además, si una superclase participa en una relación, sus subclases también se consideran partícipes de dicha relación.

**Representación gráfica**

Se utiliza la notación **"ES UN" (IS A)** para indicar que una subclase "es un tipo de" superclase. En el diagrama se representa con un **triángulo invertido**:
    - La superclase se sitúa arriba, conectada al triángulo.
    - Las subclases se conectan a la base del triángulo mediante líneas rectas.

*Ejemplo:* `USUARIO` sería la superclase, mientras que `INVITADO`, `REGISTRADO` y `ADMINISTRADOR` serían sus subclases.

**Restricciones semánticas**

Las jerarquías pueden clasificarse según cómo se distribuyen los ejemplares de la superclase entre las subclases:

| Restricción | Descripción |
| --- | --- |
| **Totalidad** | Todo ejemplar de la superclase **debe** pertenecer obligatoriamente a alguna de las subclases. |
| **Parcialidad** | Existen ejemplares de la superclase que **no pertenecen** a ninguna de las subclases. |
| **Exclusividad** | Un ejemplar de la superclase pertenece **solo a una** de las subclases. |
| **Solapamiento** | Un mismo ejemplar de la superclase puede pertenecer a **varias subclases** simultáneamente. |

Las diferentes restricciones semánticas descritas tienen su representación gráfica:

![Representación de restricciones semánticas](../../static/img/bbdd-tipos-de-especializacion.jpg)

<details>
<summary>**Ejercicio resuelto: ejemplo de generalización y especialización**</summary>

> Supongamos la existencia de dos entidades: `TURISMO` y `CAMION`. Los atributos de la entidad `TURISMO` son: *Num_bastidor*, *Fecha_fab*, *precio* y *Num_puertas*. Los atributos de la entidad `CAMION` son: *Num_bastidor*, *Fecha_fab*, *precio*, *Num_ejes* y *Tonelaje*.
>
> Si analizamos ambas entidades existen algunos atributos comunes y otros que no. Por tanto, podremos establecer una jerarquía. Para ello, reuniremos los atributos comunes y los asociaremos a una nueva entidad superclase denominada `VEHICULO`. Las subclases `TURISMO` y `CAMI0N`, con sus atributos específicos, quedarán asociadas a la superclase `VEHICULO` mediante una jerarquía parcial con solapamiento.
>
> ¿Cómo lo representarías?
---
![Ejercicio de jerarquía resuelto](../../static/img/bbdd-ejercicio-jerarquia.jpg)

</details>

#### 7.3.- Agregación

La **agregación** es una abstracción que permite tratar una relación (junto con las entidades que asocia) como si fuera una **entidad de nivel más alto**. Esto soluciona la limitación del modelo E/R tradicional que no permite representar relaciones entre relaciones.

* **Propósito:** expresar relaciones entre una relación previa y otra entidad, o entre dos relaciones distintas.
* **Representación gráfica:** se engloban las entidades y la relación que se desea abstraer dentro de un **rectángulo**. Esta nueva "entidad agregada" puede entonces conectarse a otras relaciones.
* **Cardinalidad:** en esta estructura, la cardinalidad de la entidad agregada siempre es **(1,1)**, por lo que no suele indicarse en el esquema.

Existen dos formas de entender cómo se compone el "todo" a partir de sus partes:

1. **Compuesto/Componente:** el agregado se obtiene por la unión de partes que pueden ser **tipos de entidades distintos** y que desempeñan papeles diferentes en la unión.
2. **Miembro/Colección:** el agregado es una colección de miembros del **mismo tipo de entidad** y con el mismo rol.
* Esta clase puede incluir una **restricción de orden** para los miembros, utilizando un atributo de ordenación específico.

En la siguiente figura se muestran los tipos de agregación y su representación gráfica:

![Tipos de agregación](../../static/img/bbdd-tipos-de-agregacion.jpg)

### 8.- Elaboración de diagramas E/R

La creación de un diagrama Entidad/Relación es una tarea fundamental en el diseño conceptual. Funciona como un **plano** que permite comprender y solucionar el problema real de forma independiente al SGBD.

Saltarse esta fase conlleva una **pérdida de información**, por lo que es necesario realizar esquemas previos antes de realizar la conversión a tablas del modelo relacional. La destreza se adquiere con la práctica, retocando y rehaciendo esquemas según sea necesario.

#### 8.1.- Identificación de entidades y relaciones

El punto de partida es el **documento de especificación de requerimientos** (enunciado del problema). Las etapas principales son:

**Identificación de entidades:**
    - Se buscan **nombres o sustantivos** en el texto que representen objetos importantes con existencia propia.
    - **Reglas para ser entidad:** debe tener existencia propia, cada ejemplar debe ser diferenciable y todos deben compartir las mismas propiedades.
    - **Truco de descarte:** si solo existe una ocurrencia de algo (ej. el propio "Hospital" que se está modelando), no se representa como entidad.
    - *Nomenclatura:* sustantivos en mayúsculas y en singular.


**Identificación de relaciones:**
    - Se buscan **verbos o expresiones verbales** que conecten entidades.
    - Se debe definir el tipo de correspondencia (**1:1, 1:N, M:N**) y representar la cardinalidad mínima y máxima.
    - En relaciones recursivas (unarias), es esencial indicar los **roles** que desempeña la entidad.
    - *Nomenclatura:* verbos en minúsculas. Si se usan varias palabras, se recomienda usar guiones bajos (ej. `trabaja_para`).

#### 8.2.- Identificación de atributos, claves y jerarquías

Una vez establecida la estructura base, se procede a detallar los componentes:

**Identificación de atributos:**
    - Se buscan nombres relativos a características o cualidades de las entidades y relaciones.
    - **Simplificación:** los atributos compuestos deben descomponerse en simples. Los atributos **derivados o calculados** (como la edad) generalmente **no se incluyen** en esta etapa de diseño conceptual.
    - *Nomenclatura:* en minúsculas, representativos de su función.

**Identificación de claves:**
    - Se eligen las claves candidatas y se selecciona una como **clave primaria (PK)**, la cual identifica unívocamente cada ocurrencia.
    - Este proceso determina si una entidad es **fuerte** (tiene clave propia) o **débil** (depende de otra para su identificación).

**Determinación de jerarquías:**
    - Se analiza si existen entidades con atributos comunes que puedan agruparse en una **superclase** (generalización) o si una entidad debe dividirse en **subclases** con atributos específicos (especialización).
    - Es necesario definir si la jerarquía es **total/parcial** y **exclusiva/solapada**.

#### 8.3.- Metodologías

Para construir un diagrama E/R definitivo, se suele partir de una versión preliminar que se somete a sucesivos refinamientos. Las estrategias principales son:

* **Descendente (Top-Down):** se parte de conceptos generales y abstractos, descomponiéndolos en niveles con mayor detalle hasta llegar al esquema final.
* **Ascendente (Bottom-Up):** comienza desde los elementos más básicos (atributos), agrupándolos en entidades y estableciendo luego relaciones y jerarquías.
* **Dentro-fuera (Inside-Out):** se inicia el desarrollo en una parte central del problema y se va extendiendo hacia afuera, añadiendo entidades y relaciones a medida que se analizan los requerimientos.
* **Mixta:** ideal para problemas complejos. Divide los requerimientos en subconjuntos que se analizan de forma independiente (descendente para dividir, ascendente para construir cada parte) y luego se integran en una estructura común.

#### 8.4.- Redundancia en diagramas E/R

La **redundancia** es el almacenamiento de los mismos datos en diferentes lugares. Un buen diseño debe controlarla para evitar graves problemas.

**Consecuencias de la redundancia**
    - **Aumento de carga de trabajo:** los datos deben grabarse o actualizarse en múltiples sitios.
    - **Gasto de espacio:** se ocupa innecesariamente mayor capacidad de almacenamiento.
    - **Inconsistencia:** es el mayor riesgo; ocurre cuando datos repetidos tienen valores distintos, haciendo que la información no sea fiable.

**Indicios de redundancia en el esquema**
    1. **Atributos derivados:** valores que se calculan a partir de otros ya existentes (como la edad a partir de la fecha de nacimiento).
    2. **Ciclos:** varias entidades unidas circularmente a través de relaciones. Un ciclo es redundante si al eliminar una relación no se pierde significado ni información (incluyendo sus atributos).

> **Redundancia controlada:** a veces es conveniente introducir redundancia por motivos de **rendimiento**. Si un cálculo es muy complejo y ralentiza el sistema, el diseñador puede optar por almacenar el dato directamente.

#### 8.5.- Propiedades deseables de un diagrama E/R

Para garantizar la calidad de un esquema conceptual, se deben buscar las siguientes propiedades:

| Propiedad | Descripción |
| --- | --- |
| **Completitud** | Todos los requerimientos están en el diagrama y cada elemento del diagrama corresponde a un requerimiento. |
| **Corrección** | Uso adecuado de los elementos del modelo. Puede ser **sintáctica** (sin errores de dibujo/notación) o **semántica** (el significado es fiel a la realidad). |
| **Minimalidad** | El diagrama no contiene elementos innecesarios; eliminar cualquier concepto supondría pérdida de información. |
| **Sencillez** | Representación fácil de comprender, evitando estructuras artificialmente complejas. |
| **Legibilidad** | El diagrama es fácil de interpretar visualmente gracias a una buena disposición estética de sus elementos. |
| **Escalabilidad** | Capacidad del diseño para incorporar cambios o nuevos requerimientos en el futuro sin necesidad de rehacerlo todo. |

### 9.- Primeros pasos del diagrama E/R al modelo relacional

El diseño conceptual (diagrama E/R) es independiente del software o hardware. Una vez verificado, sirve de base para el **diseño lógico**, que adapta la información a un modelo de base de datos concreto (en este caso, el **modelo relacional**).

**Pasos para obtener el esquema lógico:**

1. **Simplificación:** preparar el diagrama E/R para facilitar la conversión.
2. **Transformación:** aplicar reglas para pasar del modelo E/R al relacional.
3. **Normalización:** validar la estructura lógica mediante técnicas específicas para asegurar que sea correcta.

Tras estos pasos, se obtiene el **paso a tablas**, que permite implementar físicamente la base de datos en cualquier SGBD relacional (como Oracle), fase que ya sí depende de las características del sistema elegido.

#### 9.1.- Simplificación previa de diagramas

Para que la transformación al modelo relacional sea automática y fiable, es necesario aplicar normas de simplificación sobre los elementos que el modelo relacional no soporta directamente:

* **Atributos compuestos:** deben descomponerse en sus **atributos simples**, ya que el modelo relacional no admite estructuras compuestas.
* **Atributos multivaluados:** se convierten en una **nueva entidad** relacionada con la original. Esta nueva entidad tendrá un único atributo (el antiguo multivaluado) y se deberán ajustar sus claves primarias, pudiendo resultar en una entidad débil.
* **Transformación a relaciones jerárquicas:** las relaciones **muchos a muchos (M:N)** se transforman en relaciones **uno a muchos (1:N)**. Esto suele implicar la creación de una entidad intermedia. Si la relación original tenía atributos, estos pasan a la nueva entidad.
* **Relaciones cíclicas:** se eliminan creando una nueva entidad cuya clave se forma con los atributos clave de las ocurrencias relacionadas, estableciendo dos relaciones entre la entidad original y la nueva.
* **Relaciones ternarias:** se tratan de forma similar a los atributos asociados a relaciones; se considera como una relación binaria a la que se asocia una tercera entidad mediante una nueva relación.
* **Entidades débiles en fuertes:** se transforman añadiendo a la entidad débil los atributos clave de la entidad fuerte de la que depende. La nueva clave primaria será la suma de los atributos originales de la débil más los heredados de la fuerte.

### 10.- Paso del diagrama E/R al Modelo Relacional

Si el diseño del modelo E/R es correcto, la transformación al **Modelo Relacional** es un proceso sistemático basado en las siguientes reglas fundamentales:

* **Entidades:** toda entidad se transforma en una **tabla**.
* **Atributos:** todo atributo se convierte en una **columna** de la tabla.
* **Clave Primaria:** el atributo clave de la entidad se convierte en la **clave primaria (PK)** de la tabla (se representa subrayado).

**Reglas de transformación específicas**

* **Entidades débiles:** generan una tabla con sus propios atributos más la clave primaria de la entidad fuerte relacionada. Esta última actúa como **clave foránea (FK)**. La clave primaria de la tabla resultante será la combinación de la clave de la fuerte y el discriminante de la débil.
* **Relaciones 1:1 y 1:N:** lo más habitual es la **propagación de clave** (la clave de una entidad pasa a la otra tabla como FK). En ocasiones, pueden generar una nueva tabla independiente.
* **Relaciones reflexivas:** pueden generar una o varias tablas según su cardinalidad.
* **Jerarquías:** se resuelven mediante la reunión, eliminación o creación de relaciones 1 a 1 entre las tablas de superclase y subclases.
* **Relaciones Muchos a Muchos (M:N):** siempre se transforman en una **nueva tabla**. Su clave primaria será la concatenación de las claves primarias de las entidades que relaciona.

**Relaciones N-arias (3 o más entidades)**

En estas relaciones, cada entidad se convierte en tabla y la relación genera una tabla adicional que incluye las claves de todas las entidades participantes como FK. La clave primaria de esta nueva tabla depende de las cardinalidades:

1. **Caso N:M:P (Todas cardinalidad máxima "muchos"):** la clave de la tabla resultante es la unión de las claves de todas las entidades relacionadas.
* *Ejemplo:* PROFESORES, CURSOS y ASIGNATURAS. La tabla `IMPARTE` tendrá como PK la combinación de `(CodProfesor, CodCurso, CodAsignatura)`.

2. **Caso 1:N:M (Una entidad con cardinalidad máxima 1):** la clave de la entidad con cardinalidad 1 **no forma parte de la clave primaria** de la tabla resultante, aunque sí se incluye como un atributo (FK) más.
* *Ejemplo:* Vventa de coches donde un coche es vendido por un solo empleado. La tabla `VENTA` tendrá como PK `(CodCoche, CodCliente)`, mientras que `CodEmpleado` será una FK pero no parte de la clave primaria.

<details>
<summary>**Ejercicio resuelto** </summary>

> Sea la siguiente representación a través del modelo E/R de una relación entre dos entidades, obtén el paso a tablas de dicho esquema:  
![Ejercicio de paso a tablas](../../static/img/bbdd-ejercicio-paso-a-tablas.jpg)
--- 
> El paso a tablas de dicho esquema sería el siguiente:
>
> EMPRESA (Codigo_empresa, razon_social, domicilio, N_Trabajadores) TRABAJADOR(DNI, Nombre, Apellido1, Apellido2, Num_SS)
>
> Para materializar la relación de uno a muchos LABORAL, se incluye una clave foránea en la entidad TRABAJADOR, que referencia a la entidad EMPRESA, quedando:
>
> EMPRESA (Codigo_empresa, razón_social, domicilio, N_Trabajadores)
>
> TRABAJADOR(DNI, Nombre, Apellido1, Apellido2, Num_SS, Codigo_empresa)
</details>

### 11.- Normalización de modelos relacionales

La **normalización** es un proceso de refinamiento que se aplica a las tablas del modelo relacional después de realizar el "paso a tablas". Su objetivo es imponer restricciones mediante transformaciones consecutivas para garantizar que el diseño sea fiable y eficiente.

Los objetivos de la normalización son:

* **Suprimir dependencias erróneas** entre atributos.
* **Optimizar operaciones DML:** evitar anomalías en la inserción, modificación y borrado de datos.
* **Eliminar redundancia innecesaria** y asegurar que cada atributo describa fielmente la entidad a la que pertenece.

**Fundamentos del proceso**

La normalización se basa en el análisis de las **dependencias entre atributos**. Para entenderlo, es necesario manejar tres conceptos clave:

1. **Dependencia funcional:** Cuando un atributo determina de forma única el valor de otro.
2. **Dependencia funcional completa:** Cuando un atributo depende de una clave compuesta entera, no solo de una parte de ella.
3. **Dependencia transitiva:** Cuando un atributo depende de otro que no es la clave primaria.

**Etapas: Las Formas Normales (FN)**

El proceso es **secuencial**: para alcanzar una forma normal, la tabla debe cumplir obligatoriamente los requisitos de todas las anteriores. A medida que se avanza, las restricciones son más estrictas y el esquema más robusto.

* **Escala de normalización:** primera (1FN), Segunda (2FN), Tercera (3FN), Boyce-Codd (FNBC), Cuarta (4FN), Quinta (5FN) y Dominio-Clave.
* **Recomendación práctica:** generalmente, un diseño se considera óptimo y libre de anomalías de actualización al alcanzar la **Tercera Forma Normal (3FN)** o la **Boyce-Codd (FNBC)**.

> **Nota importante:** si se ha realizado un diseño E/R riguroso (eliminando atributos compuestos y multivaluados, y eligiendo correctamente las claves), es muy probable que el esquema relacional resultante ya se encuentre en 3FN o FNBC.

#### 11.1.- Tipos de dependencias

Para aplicar las formas normales y analizar correctamente las tablas del modelo relacional, es imprescindible comprender el concepto de **dependencia funcional** y sus variantes. Estas dependencias definen cómo los atributos de una tabla se relacionan y se determinan entre sí.

**1. Dependencia Funcional (DF)**

Dados dos atributos (o conjuntos de ellos) **A** y **B**, existe una dependencia funcional si para cada valor de A le corresponde exactamente un único valor de B.

* **Notación:** A → B (se lee "A implica B" o "B depende funcionalmente de A").
* **Determinante:** El atributo A, ya que determina el valor de B.
* **Ejemplo:** DNI → NOMBRE. Si conocemos el DNI, sabemos con certeza el nombre asociado.

El estudio de las DF permite identificar las **claves candidatas** y, a partir de ellas, la **clave principal**, que es el conjunto mínimo de atributos que definen a todos los demás en una tupla.

**2. Dependencia Funcional Completa**

Existe cuando un atributo **B** depende de un conjunto de atributos (**A1, A2, ... Ak**), pero **no depende de ninguno de sus subconjuntos**.

* **Notación:** A1.A2...Ak → B
* **Dependencia Parcial:** ocurre cuando un atributo depende solo de una *parte* de una clave compuesta.
* **Ejemplo de DF Completa:** DNI.EMPRESA → SUELDO (suponiendo que un empleado trabaja en varias empresas con sueldos distintos). El sueldo no se sabe solo con el DNI ni solo con la empresa; se necesitan ambos.
* **Ejemplo de Dependencia Parcial:** DNI.EMPRESA → NOMBRE. Como el nombre se puede saber solo con el DNI, no es una dependencia completa respecto a la clave compuesta.

Las dependencias funcionales completas son el foco de la **2ª Forma Normal (2FN)**.

**3. Dependencia Transitiva**

Se produce cuando un atributo depende de la clave de forma indirecta, a través de otro atributo que no es clave. Dados A, B y C:

1. A → B
2. B → C
3. B *no implica* A

* **Ejemplo:** Num_matrícula → grupo_asig y grupo_asig → aula_grupo.
* **Conclusión:** el atributo `aula_grupo` tiene una dependencia transitiva respecto a `Num_matrícula` a través de `grupo_asig`.

Cuando existe una dependencia transitiva, la tabla no cumple con la **3ª Forma Normal (3FN)** y debe ser normalizada.

<details>
<summary>**Ejercicio resuelto** </summary>

> Dadas las siguientes tablas:
>
> `EMPLEADO` (DNI, Nombre, Dirección, Localidad, Cod_Localidad, Nombre_hijo, Edad_hijo)
>
> `LIBRO` (Título_libro, Num_ejemplar, Autor, Editorial, Precio)
>
>   - a) Indica qué atributos presentan una dependencia funcional de la clave primaria de la tabla `EMPLEADO`
>   - b) Indica qué atributos presentan una dependencia funcional completa en la tabla `LIBRO`
>   - c) Indica qué atributos presentan una dependencia transitiva en la tabla `EMPLEADO`

---

**Apartado a)**

Los atributos Nombre, y Dirección dependen funcionalmente de DNI, ya que para un DNI específico sólo podrá haber un nombre y una dirección. Pero los atributos Nombre_hijo y Edad_hijo no presentan esa dependencia funcional de DNI, ya que para un DNI específico podríamos tener varios valores diferentes en esos atributos. (Consideraremos para este ejemplo que todos los empleados registrados en esta base de datos tienen nombres distintos). Expresemos estas dependencias funcionales mediante su notación:

DNI → Nombre

DNI → Dirección

**Apartado b)**

Los atributos Editorial y Precio dependen funcionalmente del conjunto de atributos que forman la clave primaria de la tabla, pero no dependen de Título_libro o de Num_ejemplar por separado, por lo que presentan una dependencia funcional completa de la clave. El atributo Autor depende funcionalmente sólo y exclusivamente de Titulo_libro, por lo que no presenta una dependencia funcional completa de los atributos que forman la clave.

**Apartado c)**

Los atributos Cod_Localidad y Localidad dependen funcionalmente de DNI, pero entre Cod_Localidad y Localidad existe otra dependencia funcional. Por tanto, se establece que Localidad depende funcionalmente de Cod_Localidad, y a su vez, Cod_Localidad depende funcionalmente de DNI. Con lo que podemos afirmar que existe una dependencia transitiva entre Localidad y DNI. Si lo representamos con la notación asociada a las dependencias funcionales, quedaría: DNI → Cod_Localidad → Localidad.
</details>

#### 11.2.- Formas Normales

Tras analizar los tipos de dependencias, el proceso de normalización avanza a través de las distintas **Formas Normales**. Cada una impone restricciones más estrictas para eliminar redundancias y anomalías.

**1ª Forma Normal (1FN)**: una tabla está en **1FN** si todos sus atributos contienen **valores atómicos** (indivisibles) y no existen grupos repetitivos o atributos multivaluados.
    - **Requisito:** los atributos no clave deben depender funcionalmente de la clave.
    - **Normalización:**
        1.  Se crea una tabla con los atributos que dependen funcionalmente de la clave primaria original.
        2.  Con los atributos multivaluados restantes, se crea una nueva tabla con su propia clave primaria.
    - **Ejemplo de error:** una tabla `PERSONA (DNI, Nombre, Idiomas)` donde el campo "Idiomas" contiene "Inglés, Francés". Para normalizar, "Idiomas" debe ir a una tabla independiente.

**2ª Forma Normal (2FN)**: una tabla está en **2FN** si ya está en 1FN y todos los atributos que no son parte de la clave tienen **dependencia funcional completa** de ella.
    - **Requisito:** no pueden existir dependencias parciales (atributos que solo dependen de una parte de una clave compuesta). Si la clave es simple (un solo atributo), la tabla ya está en 2FN.
    - **Normalización:** se separan en tablas distintas aquellos atributos que solo dependen de una parte de la clave compuesta, asignándoles como clave ese subconjunto de atributos.

**3ª Forma Normal (3FN)**: una tabla está en **3FN** si está en 2FN y no existen **dependencias transitivas**. Es decir, ningún atributo no clave puede depender de otro atributo no clave.
    - **Requisito:** los atributos no clave deben depender de la clave primaria de forma directa, no "a través" de otro atributo.
    - **Normalización:** se extraen los atributos que forman la dependencia transitiva a una nueva tabla, donde el atributo determinante se convierte en la nueva clave primaria.

**Forma Normal de Boyce-Codd (FNBC)**: es una versión más estricta de la 3FN. Una tabla está en **FNBC** si todo **determinante** (atributo del que dependen otros) es una **clave candidata**.
    - **Detección:** si existe un atributo que determina a otro pero no puede ser clave de la tabla, no se cumple la FNBC. Esto suele ocurrir por una mala elección de la clave primaria original.
    - **Normalización:** descomponer la tabla en dos para asegurar que cada determinante sea una clave candidata.

**Otras Formas Normales**

Aunque llegar a **3FN o FNBC** suele ser suficiente para la mayoría de los diseños comerciales, existen niveles superiores para casos muy específicos:

* **4ª Forma Normal (4FN):** elimina dependencias multivaluadas independientes.
* **5ª Forma Normal (5FN):** basada en dependencias de unión o *join*.
* **Forma Normal de Dominio-Clave (DKFN):** el objetivo ideal donde todas las restricciones son consecuencia de las definiciones de dominios y claves.

![Mapa conceptual resumen de las formas normales](../../static/img/bbdd-mapa-conceptua-formas-normales.jpg)

<details>
<summary>**Ejercicio resuelto**</summary>

> Sea la siguiente tabla: `COMPRAS` (cod_compra, cod_prod, nomb_prod, fecha, cantidad, precio, fecha_rec, cod_prov, nomb_prov, tfno).
>
> Se pide normalizarla hasta FNBC.
---
**Comprobamos 1FN:**

La tabla `COMPRAS` está en 1FN ya que todos sus atributos son atómicos y todos los atributos no clave dependen funcionalmente de la clave.

**Comprobamos 2FN:**

Nos preguntaremos ¿Todo atributo depende de todo el conjunto de atributos que forman la clave primaria, o sólo de parte?. Como vemos, existen atributos que dependen sólo de una parte de la clave, por lo que esta tabla no está en 2FN.

Veamos las dependencias:

cod_prod → nomb_prod, y cod_prod es parte de la clave primaria.

Al no estar en 2FN, hemos de descomponer la tabla `COMPRAS` en:  

- `COMPRA1` (cod_compra, cod_prod, fecha, cantidad, precio, fecha_rec, cod_prov, nomb_prov, tfno)  
- `PRODUCTO` (cod_prod, nomb_prod)

Una vez hecha esta descomposición, ambas tablas están en 2FN. Todos los atributos no clave dependen de toda la clave primaria.

**Comprobamos 3FN:**

`PRODUCTO` está en 3FN, ya que por el número de atributos que tiene no puede tener dependencias transitivas. ¿`COMPRA1` está en 3FN? Hemos de preguntarnos si existen dependencias transitivas entre atributos no clave.

Veamos las dependencias:

cod_prov → nomb_prov cod_prov → tfno (siendo cod_prov el código del proveedor y nomb_prov el nombre del proveedor)

`COMPRA1` no está en 3FN porque existen dependencias transitivas entre atributos no clave, por tanto hemos de descomponer:

- `COMPRA2` (cod_compra, cod_prod, fecha, cantidad, precio, fecha_rec, cod_prov)
- `PROVEEDOR` (cod_prov, nomb_prov, tfno)

**Comprobamos FNBC:**

`PRODUCTO` está en FNBC, ya que está en 3FN y todo determinante es clave candidata. `COMPRA2` está en FNBC, ya que está en 3FN y todo determinante es clave candidata. `PROVEEDOR` está en FNBC, ya que está en 3FN y todo determinante es clave candidata.

La tabla inicial `COMPRAS` queda normalizada hasta FNBC del siguiente modo:

`PRODUCTO` (cod_prod, nomb_prod)

`COMPRA2` (cod_compra, cod_prod, fecha, cantidad, precio, fecha_rec, cod_prov)

`PROVEEDOR` (cod_prov, nomb_prov, tfno)
</details>

---

*Fin de la 1ª Evaluación*

---