---
id: entornos-de-desarrollo
sidebar_position: 2
title: Entornos de Desarrollo
toc_max_heading_level: 3
---

## UD1.- Reconocimiento de las características de lenguajes de marcas

### 1.- Lenguajes de Marcas

Un **lenguaje de marcas** es un modo de codificar un documento donde, junto con el texto, se incorporan etiquetas, marcas o anotaciones con información adicional relativa a la estructura del texto o su formato de presentación. Permiten hacer explícita la estructura de un documento, su contenido semántico o cualquier otra información lingüística o extralingüística que se quiera hacer patente.

Todo lenguaje de marcas está definido en un documento denominado **DTD** (Document Type Definition). En él se establecen las marcas, los elementos utilizados por dicho lenguaje y sus correspondientes etiquetas y atributos, su sintaxis y normas de uso.

```xml title="Ejemplo"
<carta>
	<fecha>22/11/2006</fecha>
	<presentacion>Estimado cliente:</presentacion>
	<contenido>bla bla bla bla …</contenido>
	<firma>Don José Gutiérrez González</firma>
</carta>
```

En un mismo documento pueden combinarse varios tipos diferentes de lenguajes de marcas.

Un lenguaje de marcas puede ser:

- **De presentación**: define el formato del texto.
- **De procedimientos**: orientado también a la presentación pero, en este caso, el programa que representa el documento debe interpretar el código en el mismo orden en que aparece.
- **Descriptivo o semántico**: describe las diferentes partes en las que se estructura el documento pero sin especificar cómo deben representarse.

Algunos ejemplos de lenguajes de marcado agrupados por su ámbito de utilización son:

1. **Documentación electrónica**
    - **RTF (Rich Text Format)**. Intercambio de documentos de texto entre distintos procesadores de texto.
    - **TeX**. Creación de ecuaciones matemáticas complejas.
    - **Wikitexto**. Creación de páginas wiki.
    - **DocBook**. Generar documentos separando la estructura lógica del documento de su formato.

2. **Tecnologías de Internet**
    - **HTML, XHTML**. Creación de páginas web.
    - **RSS**. Difusión de contenidos web.

3. **Otros lenguajes**
    - **MathML**. Expresar el formalismo matemático de tal modo que pueda ser entendido por distintos sistemas y aplicaciones.
    - **VoiceXML**. Intercambio de información entre un usuario y una aplicación con capacidad de reconocimiento de habla.
    - **MusicXML**. Intercambio de partituras entre distintos editores de partituras.

### 2.- Evolución de los lenguajes de marcas.

Los lenguajes de marcas nacieron en los años 70. Al principio, eran simples códigos de formato y presentación introducidos por los procesadores de texto. Su principal limitación era que este formato estaba ligado a una máquina o programa concreto, impidiendo a los desarrolladores expresar la estructura lógica de un documento de forma independiente al software de creación.

```xml title="Código de marcas anterior a GML (etiquetas de invención propia)"
<times 14><color verde><centrado> Este texto es un ejemplo para mostrar la utilización primitiva de las marcas</centrado></color></times 14>
<color granate><times 10><cursiva>Para realiza este ejemplo se utilizan etiquetas de nuestra invención. </cursiva> 
Las partes importantes del texto pueden resaltarse usando la 
<negrita>negrita</negrita>, o el <subrayar>subrayado</subrayar></times 10></color>
```

Después de la era de los códigos de formato manual y específico, el proceso de marcado se automatizó con la introducción de botones o atajos de teclado. Sin embargo, este sistema seguía centrado únicamente en la presentación de la información. Eventualmente, al reconocerse el amplio potencial del marcado para resolver necesidades más allá del simple formato, esta limitación fue superada, dando origen al concepto de formato generalizado.

#### 2.1.- GML (Generalized Markup Language)

El GML nació en los años sesenta, por encargo de IBM, como una solución a la falta de estandarización en los formatos de información entre distintos programas. Su objetivo principal era crear un formato estándar, flexible y válido para todo tipo de documentos legales, logrando que el documento fuera gestionable en cualquier departamento y con cualquier aplicación, sin importar dónde ni con qué se había generado. El resultado fue un sistema que permitía describir los documentos de tal modo que el resultado final fuese independiente de la plataforma y la aplicación utilizada.

#### 2.2.- SGML (Standard Generalized Markup Language)

El formato GML evolucionó hasta convertirse en SGML, el estándar ISO 8879, publicado en 1986. Sin embargo, SGML resultó ser un lenguaje de marcas muy complejo, lo que conllevó la necesidad de utilizar herramientas de software caras. Debido a esta complejidad y coste, su uso se limitó estrictamente a grandes aplicaciones industriales.

```xml title="Ejemplo de documento SGML sencillo"
<email>
	<remitente>
		<persona>
		<nombre> Pepito </nombre>
		<apellido> Grillo </apellido>
		</persona>
	</remitente>
	<destinatario>
		<direccion> pinocho@hotmail.com </direccion>
	</destinatario>
	<asunto>¿quedamos?</asunto>
	<mensaje> Hola, he visto que ponen esta noche la película que querías ver. ¿Te apetece ir?</mensaje>
</email>
```

#### 2.3.- HTML (HyperText Markup Language)

**HTML** surgió en 1989/90, creado por **Tim Berners-Lee**  para el **World Wide Web**. Su objetivo era organizar, enlazar y compatibilizar información procedente de diversos sistemas. HTML combina dos estándares existentes:
    - **ASCII:** Permite el reconocimiento por procesadores de texto sencillos y facilita la transferencia de datos.
    - **SGML:** Aporta la capacidad de estructurar el texto y aplicar formatos.

Es una **versión simplificada de SGML** que utiliza solo las instrucciones imprescindibles, lo que le dio una rápida y gran aceptación, y rápido se convirtió en el **estándar general** para la creación de páginas web, impulsando la mejora continua de navegadores y herramientas de *software*.

Aunque fue revolucionario, HTML presenta limitaciones:

- Las etiquetas son **limitadas**, haciendo el lenguaje poco flexible.
- No soporta contenido dinámico.
- La estructura lógica y el diseño (formato) están **mezclados** en el mismo documento.
- Presenta dificultades con tareas complejas de impresión y diseño.

```html title="Ejemplo de documento HTML"
<html>
	<head>
		<title> Ejemplo de código HTML</title>
	</head>
	<body>
		<p></p>
		<p>
			<b>23 de julio de 2020</b>
		</p>
		<p><b> Bienvenido al modulo de “Lenguajes de Marcas y Sistemas de Gestión de Información” </b></p>
		<p> En este curso aprender&aacute;s, entre otras cosas:<br/>
		<ul>
			<li>Las ventajas que ofrece XML </li>
			<li>La creaci&oacute;n de documentos bien formados </li>
			<li>La creaci&oacute;n de DTD</li>
		</ul>
		</p>
	</body>
</html>
```

#### 2.4.- XML (eXtensible Markup Language).

Para resolver los problemas de HTML, el **W3C** establece en 1998, el estándar internacional **XML**, un lenguaje de marcas puramente estructural que no incluye ninguna información relativa al diseño. A diferencia de HTML, las etiquetas indican el significado de los datos en lugar del formato con el que se van a visualizar los datos.

- Permite definir etiquetas propias.
- Permite asignar atributos a las etiquetas.
- Utiliza un esquema para definir de forma exacta las etiquetas y los atributos.
- La estructura y el diseño son independientes.

XML es un conjunto de estándares relacionados entre sí y que son:

- **XSL, eXtensible Style Language**. Permite definir hojas de estilo para los documentos XML e incluye capacidad para la transformación de documentos.
- **XML Linking Language**. Determina aspectos sobre los enlaces entre documentos XML.
- **XML Namespaces**. Provee un contexto al que se aplican las marcas de un documento de XML y que sirve para diferenciarlas de otras con idéntico nombre válidas en otros contextos.
- **XML Schemas**. Permite definir restricciones que se aplicarán a un documento XML. Actualmente los más usados son las DTD.

```xml title="Ejemplo de documento XML"
<?xml version="1.0" encoding="iso-8859-1"?>
<!DOCTYPE biblioteca">
<biblioteca>
    	<ejemplar tipo_ejem="libro" titulo="XML practico" editorial="Ediciones Eni">
        <tipo> <libro isbn="978-2-7460-4958-1" edicion="1" paginas="347"></libro> </tipo>
        <autor nombre="Sebastien Lecomte"></autor>
        <autor nombre="Thierry Boulanger"></autor>
        <autor nombre="Ángel Belinchon Calleja" funcion="traductor"></autor>
        <prestado lector="Pepito Grillo">
            <fecha_pres dia="13" mes="mar" año="2009"></fecha_pres>
            <fecha_devol dia="21" mes="jun" año="2009"></fecha_devol>
        </prestado> 
    </ejemplar>
    <ejemplar tipo_ejem="revista" titulo="Todo Linux 101. Virtualización en GNU/Linux" editorial="Studio Press">
        <tipo>
            <revista>
                <fecha_publicacion mes="abr" año="2009"></fecha_publicacion> 
            </revista> 
        </tipo>
        <autor nombre="Varios"></autor>
        <prestado lector="Pedro Picapiedra">
            <fecha_pres dia="12" mes="ene" año="2010"></fecha_pres>
        </prestado> 
    </ejemplar>
</biblioteca>
```

#### 2.5.- XML vs HTML

| XML |	HTML |
| --- | ---- |
|Es un perfil de SGML| Es una aplicación de SGML|
|Especifica cómo deben definirse conjuntos de etiquetas aplicables a un tipo de documento | Aplica un conjunto limitado de etiquetas sobre un único tipo de documento |
| Modelo de hiperenlaces complejo | Modelo de hiperenlaces simple |
| El navegador es una plataforma para el desarrollo de aplicaciones | El navegador es un visor de páginas |
| Fin de la guerra de los navegadores y etiquetas propietarias | El problema de la 'no compatibilidad' y las diferencias entre navegadores ha alcanzado un punto en el que la solución es difícil |


``` xml title="Ejemplo fichero con código XML"
<?xml version="1.0" encoding="iso-8859-1"?>
<!DOCTYPE libro>
<libro>
    <titulo>XML practico </titulo>
    <autor>SebastienLecomte</autor>
    <autor>Thierry Boulanger</autor>
    <editorial>Ediciones Eni</editorial>
    <isbn>978-2-7460-4958-1</isbn>
    <edicion>1</edicion> 
    <paginas>347</paginas> 
</libro>
```

``` xml title="Ejemplo fichero con código HTML"
<html>
    <head>
        <title>Libro</title> 
    </head>
    <body>
        <h3>XML practico</h3><br>
        <p>autores: Sebastien Lecomte,
        Thierry Boulanger</p>
        <ul>
            <li>editorial: Ediciones Eni</li>
            <li>isbn:978-2-7460-4958-1</li>
            <li>edicion: 1 </li>
            <li>paginas: 347</li> 
        </ul>
    </body> 
</html> 
```

#### 2.6.- XML cvs SGML

| XML |	SGML |
| --- | ---- |
| Uso sencillo | Uso complejo |
| Trabaja con documentos bien formados. No exige que estén validados | Solo trabaja con documentos válidos |
| Facilita el desarrollo de aplicaciones de bajo coste | Su complejidad hace que las aplicaciones informáticas para procesar SGML sean muy costosas |
| Es muy utilizado en informática y en más áreas de aplicación  | Solo se utiliza en sectores muy específicos |
| Compatibilidad e integración con HTML | No hay una compatibilidad con HTML definida |
|Formato y estilos fáciles de aplicar  | Formateo y estilos relativamente complejos |   
|No usa etiquetas opcionales | |

Es aquel documento XML que verifica las reglas establecidas por la recomendación de W3C.

Es aquel documento XML que, además de estar bien formado, verifica las restricciones de otro elemento del que depende para su interpretación.

#### 2.7.- Etiquetas

Los lenguajes de marcas utilizan una serie de etiquetas especiales intercaladas en un documento de texto sin formato. Dichas etiquetas serán posteriormente interpretadas por los intérpretes del lenguaje y ayudan al procesado del documento.

Las etiquetas se escriben encerradas entre ángulos, es decir < y >. Normalmente, se utilizan dos etiquetas: una de inicio y otra de fin para indicar que ha terminado el efecto que queríamos presentar. La única diferencia entre ambas es que la de cierre lleva una barra inclinada "/" antes del código.

```xml
<etiqueta>texto que sufrirá las consecuencias de la etiqueta</etiqueta>
```

Ejemplo de etiqueta HTML de subrayado (Underline):

```html
<u>Esto está subrayado</u>
```

Las últimas especificaciones emitidas por el W3C indican la necesidad de que vayan escritas siempre en minúsculas para considerar que el documento está correctamente creado.

#### 2.8.- Herramientas de edición

Para trabajar en XML es necesario editar los documentos y luego procesarlos, por tanto tenemos dos tipos de herramientas:

Editores XML

Una característica de los lenguajes de marcas es que se basan en la utilización de ficheros de texto plano por lo que basta utilizar un procesador de texto normal y corriente para construir un documento XML.

Para crear documentos XML complejos e ir añadiendo datos es conveniente usar algún editor XML. Estos nos ayudan a crear estructuras y etiquetas de los elementos usados en los documentos, además algunos incluyen ayuda para la creación de otros elementos como DTD, hojas de estilo CSS o XSL, ... El W3C ha desarrollado un editor de HTML, XHTML, CSS y XML gratuito cuyo nombre es Amaya.

Procesadores XML 

Los procesadores XML permiten leer los documentos XML y acceder a su contenido y estructura. Un procesador es un conjunto de módulos de software, entre los que se encuentra un parser o analizador de XML, que comprueba que el documento cumple las normas establecidas para que pueda abrirse.

Los procesadores XML pueden obliguen a trabajar sólo con documentos de tipo válido (entonces se denominan "validadores") o pueden sólo exigir que el documento esté bien formado ("no validadores").

El modo en que los procesadores deben leer los datos XML está descrito en la recomendación de XML establecida por  W3C.

Para publicar un documento XML en Internet se utilizan los procesadores XSLT, que permiten generar archivos HTML a partir de documentos XML.

Para interpretar el código XML se puede utilizar cualquier navegador.

XML también se puede utilizar para el intercambio de datos entre aplicaciones. En este caso, hay que recurrir a motores independientes, que se ejecutan sin que nos demos cuenta. Por ejemplo JAXP de Oracle.

### 3.- XML, estructura y sintaxis

El XML, o Lenguaje de Etiquetas Extendido, es lenguaje de etiquetas, creadas por el programador, que estructuran y guardan de forma ordenada la información. No representa datos por sí mismo, solamente organiza la estructura.

El XML ahorra tiempos de desarrollo y proporciona ventajas, dotando a webs y a aplicaciones de una forma realmente potente de guardar la información. Además, se ha convertido en un formato universal que ha sido asimilado por todo tipo de sistemas operativos y dispositivos móviles.

Al igual que en HTML un documento XML es un documento de texto, en este caso con extensión ".xml", compuesto de parejas de etiquetas, estructuradas en árbol, que describen una función en la organización del documento, que puede editarse con cualquier editor de texto y que es interpretado por los navegadores Web.

Las características básicas de XML son:

    Dado que XML se concibió para trabajar en la Web, es directamente compatible con protocolos que ya funcionan, como HTTP y los URL.
    Todo documento que verifique las reglas de XML está conforme con SGML.
    No se requieren conocimientos de programación para realizar tareas sencillas en XML.
    Los documentos XML son fáciles de crear.
    La difusión de los documentos XML está asegurada ya que cualquier procesador de XML puede leer un documento de XML.
    El marcado de XML es legible para los humanos.
    El diseño XML es formal y conciso.
    XML es extensible, adaptable y aplicable a una gran variedad de situaciones.
    XML es orientado a objetos.
    Todo documento XML se compone exclusivamente de datos de marcado y datos carácter entremezclados.

El proceso de creación de un documento XML pasa por varias etapas en las que el éxito de cada una de ellas se basa en la calidad de la anterior. Estas etapas son:

    Especificación de requisitos.
    Diseño de etiquetas.
    Marcado de los documentos.

El marcado en XML son etiquetas que se añaden a un texto para estructurar el contenido del documento. Esta información extra permite a los ordenadores "interpretar" los textos. El marcado es todo lo que se sitúa entre los caracteres `<` y `>` o `&` y `;`.

Los datos carácter son los que forman la verdadera información del documento XML.

El marcado puede ser tan rico como se quiera. Puede ser interesante detectar necesidades futuras y crear documentos con una estructura fácilmente actualizables.

Los documentos XML pueden tener comentarios, que no son interpretados por el interprete XML. Estos se incluyen entre las cadenas `<!-` y `-->`, pueden estar en cualquier posición en el documento salvo:

    Antes del prólogo.
    Dentro de una etiqueta.

Los documentos XML pueden estar formados por una parte opcional llamada prólogo y otra parte obligatoria llamada ejemplar.

#### 3.1.- El prólogo

Si se incluye, el prólogo debe preceder al ejemplar del documento. Su inclusión facilita el procesado de la información del ejemplar. El prólogo está dividido en dos partes:

        La declaración XML: En el caso de incluirse ha de ser la primera línea del documento, de no ser así se genera un error que impide que el documento sea procesado.

        El hecho de que sea opcional permite el procesamiento de documentos HTML y SGML como si fueran XML, si fuera obligatoria éstos deberían incluir una declaración de versión XML que no tienen.

        El prólogo puede tener tres funciones:
            Declaración la versión de XML usada para elaborar el documento.

            Para ello se utiliza la etiqueta:

            ```xml
            <?xml versión= “1.0” ?>
            ```

            En este caso indica que el documento fue creado para la versión 1.0 de XML.
        Declaración de la codificación empleada para representar los caracteres.

Determina el conjunto de caracteres que se utiliza en el documento. Para ello se escribe:

```xml
<?xml versión= “1.0” encoding=”iso-8859-1” ?>
```

En este caso se usa el código iso-8859-1 (Latin-1) que permite el uso de acentos o caracteres como la ñ.

Los códigos más importantes son:
Estándar ISO 	Código de país
UTF-8 (Unicode) 	Conjunto de caracteres universal
ISO-8859-1 (Latin-1) 	Europa occidental, Latinoamérica
ISO-8859-2 (Latin-2) 	Europa central y oriental
ISO-8859-3 (Latin-3) 	Sudoeste de Europa
ISO-8859-4 (Latin-4) 	Países Escandinavos, Bálticos
ISO-8859-5 	Cirílico
ISO-8859-6 	Árabe
ISO-8859-7 	Griego
ISO-8859-8 	Hebreo
ISO-8859-9 	Turco
ISO-8859-10 	Lapón. Nórdico, esquimal
EUC-JP oder Shitf_JIS 	Japonés

 
    Declaración de la autonomía del documento.

    Informa de si el documento necesita de otro para su interpretación. Para declararlo hay que definir el prólogo completo:

    ```xml
    <?xml versión= “1.0” encoding=”iso-8859-1” standalone=”yes” ?>
    ```

    En este caso, el documento es independiente, de no ser así el atributo standalone hubiese tomado el valor "no".

La declaración del tipo de documento, define qué tipo de documento estamos creando para ser procesado correctamente. Toda declaración de tipo de documento comienza por la cadena:

```xml
<!DOCTYPE Nombre_tipo ...>
```

#### 3.2.- El ejemplar. Los elementos.

Es la parte más importante de un documento XML, ya que contiene los datos reales del documento. Está formado por elementos anidados.

Los elementos son los distintos bloques de información que permiten definir la estructura de un documento XML. Están delimitados por una etiqueta de apertura y una etiqueta de cierre. A su vez, los elementos pueden estar formados por otros elementos y/o por atributos.

```xml title="Dado el siguiente código XML..."
<?xml version="1.0" encoding="iso-8859-1"?>
<!DOCTYPE libro>
<libro>
    <titulo>XML practico </titulo>
    <autor>Sebastien Lecomte</autor>
    <autor>Thierry Boulanger</autor>
    <editorial>Ediciones Eni</editorial>
    <isbn>978-2-7460-4958-1</isbn>
    <edicion>1</edicion>
    <paginas>347</paginas> 
<libro>
```

El ejemplar es el elemento `<libro>`, que a su vez está compuesto de los elementos `<autor>`, `<editorial>`, `<isbn>`, `<edicion>` y `<paginas>`.

En realidad, el ejemplar es el elemento raíz (root) de un documento XML. Todos los datos de un documento XML han de pertenecer a un elemento del mismo.

Los nombres de las etiquetas han de ser autodescriptivos, lo que facilita el trabajo que se hace con ellas.

La formación de elementos ha de cumplir ciertas normas para que queden perfectamente definidos y que el documento XML al que pertenecen pueda ser interpretado por los procesadores XML sin generar ningún error fatal. Dichas reglas son:

    En todo documento XML debe existir un elemento raíz, y sólo uno.

    Todos los elementos tienen una etiqueta de inicio y otra de cierre. En el caso de que en el documento existan elementos vacíos, se pueden sustituir las etiquetas de inicio y cierre por una de elemento vacío. Ésta se construye como la etiqueta de inicio, pero sustituyendo el carácter `>` por `/>`. Es decir, `<elemento></elemento>` puede sustituirse por: `<elemento/>`.

    Al anidar elementos hay que tener en cuenta que no puede cerrarse un elemento que contenga algún otro elemento que aún no se haya cerrado.

    Los nombres de las etiquetas de inicio y de cierre de un mismo elemento han de ser idénticos, respetando las mayúsculas y minúsculas. Pueden ser cualquier cadena alfanumérica que no contenga espacios y no comience ni por el carácter dos puntos, ":", ni por la cadena "xml" ni ninguna de sus versiones en que se cambien mayúsculas y minúsculas ("XML", "XmL", "xML",...).

    El contenido de los elementos no puede contener la cadena `]]>` por compatibilidad con SGML. Además no se pueden utilizar directamente los caracteres mayor que, `>`, menor que, `<`, `ampersand`, `&`, `dobles comillas`, `"`, y apostrofe, `‘`. En el caso de tener que utilizar estos caracteres se sustituyen por las siguientes cadenas:
    
    ```
    Carácter 	Cadena
    > 	 &gt;
    < 	&lt;
    & 	&amp;
    " 	&quot;
    ' 	&apos;
    ```


Para utilizar caracteres especiales, como `£`, `©` y `®`, hay que usar las expresiones `&#D;` o `&#H;` donde `D` y `H` se corresponden respectivamente con el número decimal o hexadecimal correspondiente al carácter que se quiere representar en el código UNICODE.

##### 3.2.1.- Atributos

Permiten añadir propiedades a los elementos de un documento. Los atributos no pueden organizarse en ninguna jerarquía, no pueden contener ningún otro elemento o atributo y no reflejan ninguna estructura lógica.

No se debe utilizar un atributo para contener información susceptible de ser dividida.

```xml title="Dado el siguiente código XML..."
<?xml version="1.0" encoding="UTF-8" standalone="yes" ?>
<!DOCTYPE biblioteca >
<biblioteca>
    <ejemplar tipo_ejem="libro" titulo="XML práctico" editorial="Ediciones Eni">
        <tipo> <libro isbn="978-2-7460-4958-1" edicion="1" paginas="347"></libro> </tipo>
        <autor nombre="Sebastien Lecomte"></autor>
        <autor nombre="Thierry Boulanger"></autor>
        <autor nombre="Angel Belinchon Calleja" funcion="traductor"></autor>
        <prestado lector="Pepito Grillo">
            <fecha_pres dia="13" mes="mar" año="2009"></fecha_pres>
            <fecha_devol dia="21" mes="jun" año="2009"></fecha_devol> 
        </prestado>
    </ejemplar> 
</biblioteca>
```

Como se observa en el ejemplo, los atributos se definen y dan valor dentro de una etiqueta de inicio o de elemento vacio, a continuación del nombre del elemento o de la definición de otro atributo, siempre separado de ellos por un espacio. Los valores del atributo van precedidos de un igual que sigue al nombre del mismo y tienen que definirse entre comillas simples o dobles.

Los nombres de los atributos han de cumplir las mismas reglas que los de los elementos, y no pueden contener el carácter menor que, `<`.

### 4.- Documentos XML bien formados

Todos los documentos XML deben verificar las reglas sintácticas que define la recomendación del W3C para el estándar XML. Esas normas básicas son:

    El documento ha de tener definido un prólogo con la declaración xml completa.
    Existe un único elemento raíz para cada documento: es un solo elemento en el que todos los demás elementos y contenidos se encuentran anidados.
    Hay que cumplir las reglas sintácticas del lenguaje XML para definir los distintos elementos y atributos del documento.

### 5.- Utilización de espacios de nombres en XML

Permiten definir la pertenencia de los elementos y los atributos de un documento XML al contexto de un vocabulario XML. De este modo se resuelven las ambigüedades que se pueden producir al juntar dos documentos distintos, de dos autores diferentes, que han utilizado el mismo nombre de etiqueta para representar cosas distintas.

Los espacios de nombres, también conocidos como "name spaces", permiten dar un nombre único a cada elemento, indexándolos según el nombre del vocabulario adecuado. Además están asociados a un URI que los identifica de forma única.

En el documento, las etiquetas ambiguas se sustituyen por otras en las que el nombre del elemento está precedido de un prefijo, que determina el contexto al que pertenece la etiqueta, seguido de dos puntos, `:`. Esto es:

`<prefijo:nombre_etiqueta></prefijo:nombre_etiqueta>`

Esta etiqueta se denomina "nombre cualificado". Al definir el prefijo hay que tener en cuenta que no se pueden utilizar espacios ni caracteres especiales y que no puede comenzar por un dígito.

Antes de poder utilizar un prefijo de un espacio de nombres, para resolver la ambigüedad de dos o más etiquetas, es necesario declarar el espacio de nombres, es decir, asociar un índice con el URI asignado al espacio de nombres, mediante un atributo especial xmlns. Esto se hace entre el prólogo y el ejemplar de un documento XML y su sintaxis es la siguiente:

`<conexion>://<direccionservidor>/<apartado1>/<apartado2>/...`

#### 5.1.- Ejemplo: Utilización de espacios de nombres

Supongamos dos documentos que organizan la información sobre profesores y alumnos:

```xml title="XML de alumnos"
<?xml version="1.0" encoding="iso-8859-1" standalone="yes"
<!DOCTYPE alumnos>
<alumnos>
    <nombre>Fernando Fernández González</nombre>
    <nombre>Isabel González Fernández</nombre>
    <nombre>Ricardo Martínez López</nombre>
</alumnos>
```

```xml title="XML de profesores"
<?xml version="1.0" encoding="iso-8859-1" standalone="yes" ?>
<!DOCTYPE profesores>
<profesores>
    <nombre>Pilar Ruiz Pérez</nombre>
    <nombre>Tomás Rodríguez Hernández</nombre>
</profesores> 
```

Si uniéramos los dos documentos en uno único, sin usar espacios de nombres, no se distinguirían los profesores de los alumnos ya que en los dos casos la etiqueta `<nombre>` se llama igual.

Para resolverlo necesitamos definir un espacio de nombres para cada contexto.