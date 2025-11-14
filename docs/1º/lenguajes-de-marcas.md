---
id: lenguajes-de-marcas
sidebar_position: 4
title: Lenguajes de marcas y sistemas de gestión de información
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
Las partes importantes del texto pueden resaltarse usando la <negrita>negrita</negrita>, o el <subrayar>subrayado</subrayar></times 10></color>
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
| Trabaja con documentos bien formados, no exige que estén validados | Solo trabaja con documentos válidos |
| Facilita el desarrollo de aplicaciones de bajo coste | Su complejidad hace que las aplicaciones informáticas para procesar SGML sean muy costosas |
| Es muy utilizado en informática y en más áreas de aplicación  | Solo se utiliza en sectores muy específicos |
| Compatibilidad e integración con HTML | No hay una compatibilidad con HTML definida |
|Formato y estilos fáciles de aplicar  | Formateo y estilos relativamente complejos |   
|No usa etiquetas opcionales | |

#### 2.7.- Etiquetas

Los lenguajes de marcas utilizan una serie de etiquetas especiales intercaladas en un documento de texto sin formato. Dichas etiquetas serán posteriormente interpretadas por los intérpretes del lenguaje y ayudan al procesado del documento.

Las etiquetas se escriben encerradas entre `<` y `>`. Normalmente se utilizan dos etiquetas: una de inicio y otra de fin para indicar que ha terminado el efecto que queríamos presentar (la única diferencia es que la de cierre lleva una `/` antes del `>`). Es necesario que estas etiquetas se escriban siempre en minúsculas para considerar que el documento está correctamente creado.

```xml
<etiqueta>texto que sufrirá las consecuencias de la etiqueta</etiqueta>
```

#### 2.8.- Herramientas de edición

Para trabajar con XML se necesitan dos tipos principales de herramientas:

1. **Editores XML**

Los documentos XML son **ficheros de texto plano**, por lo que se puede usar un procesador de texto normal. Para documentos más complejos, se recomienda un **editor XML** especializado, ya que ayuda a crear **estructuras y etiquetas**. 
Algunos editores también facilitan la creación de elementos relacionados como **DTD**, **CSS** u **XSL**. Un ejemplo es **Amaya**, un editor gratuito desarrollado por el W3C que soporta XML. 

2. **Procesadores XML**

Permiten **leer los documentos XML** y acceder a su contenido. Incluyen un **parser o analizador** que verifica que el documento cumple con las normas (que esté **"bien formado"**). Se pueden clasificar en:
- **Validadores**: Exigen que el documento sea de tipo **válido** (que cumpla con un DTD o esquema).
- **No validadores**: Solo exigen que el documento esté **bien formado**.

Los procesadores **XSLT** se usan para **publicar XML en Internet**, transformándolo en archivos **HTML**. **Cualquier navegador** puede interpretar y mostrar código XML. Para el **intercambio de datos entre aplicaciones**, se usan **motores independientes** (ej. **JAXP** de Oracle), que actúan sin intervención directa del usuario.

### 3.- XML: estructura y sintaxis

**XML (Lenguaje de Etiquetas Extendido)** es un lenguaje de marcado diseñado para **estructurar y guardar información** de forma ordenada. El programador crea las etiquetas, y XML se encarga de organizar la estructura, no de representar los datos por sí mismo.

Características de XML:

- **Formato universal:** Ha sido adoptado por diversos sistemas operativos y dispositivos.
- **Compatibilidad web:** Es compatible con protocolos web como **HTTP** y **URL**.
- **Base en texto:** Un documento XML es un archivo de texto con extensión **`.xml`**, compuesto por parejas de etiquetas.
- **Estructura jerárquica:** Las etiquetas están organizadas en una **estructura de árbol**.
- **Facilidad de uso:** Las tareas sencillas no requieren conocimientos de programación.
- **Legibilidad humana:** El marcado de XML es **legible** para las personas.
- **Extensible y adaptable:** Es **extensible** (las etiquetas las crea el usuario), adaptable y orientado a objetos.
- **Composición:** Se compone exclusivamente de **datos de marcado** y **datos carácter** (la información real).

Componentes de un documento XML:

1. **Datos de marcado**
    - Son las etiquetas que se añaden al texto para **estructurar el contenido**.
    - Permiten a los ordenadores "interpretar" el texto.
    - Todo lo que se sitúa entre los caracteres **`<`** y **`>`** o **`&`** y **`;`**.

2. **Datos carácter**
    - Son la **verdadera información** o contenido del documento.

3. **Comentarios**
    - No son interpretados por el procesador XML.
    - Se incluyen entre las cadenas **``**.
    - No pueden ir antes del prólogo o dentro de una etiqueta.

4. **Estructura global**
    - **Prólogo (opcional):** parte inicial del documento.
    - **Ejemplar (obligatorio):** contiene la estructura y los datos principales. 

Etapas de creación de un documento XML:

1. Especificación de requisitos
2. Diseño de etiqueta
3. Marcado de los documentos

#### 3.1.- El prólogo

El **prólogo**, si se incluye, debe **preceder obligatoriamente al ejemplar** del documento. Su función principal es **facilitar el procesamiento** de la información del ejemplar.

El prólogo se divide en dos partes:

1. **Declaración XML**

Debe ser la **primera línea** del documento. Es opcional, lo que permite que documentos HTML y SGML sean procesados como XML sin requerir una declaración de versión. Esta declaración puede tener tres funciones:

- **Declaración de la versión de XML:**
    - Indica la versión de XML utilizada.
    - Sintaxis: `<?xml versión= “1.0” ?>`

- **Declaración de la codificación de caracteres:**
    - Determina el conjunto de caracteres empleado en el documento (ej. para permitir el uso de acentos).
    - Sintaxis: `<?xml versión= “1.0” encoding=”iso-8859-1” ?>` (usando Latin-1).

- **Declaración de la autonomía del documento:**
    - Informa si el documento es **independiente** o necesita otro archivo para su interpretación.
    - Sintaxis: `<?xml versión= “1.0” encoding=”iso-8859-1” standalone=”yes” ?>`
    - El valor puede ser `"yes"` (documento independiente) o `"no"`.

2. **Declaración del tipo de documento**

Define el **tipo de documento** que se está creando para asegurar su correcto procesamiento. Toda declaración de este tipo comienza con la cadena: `<!DOCTYPE Nombre_tipo ...>`.

Aquí tienes el resumen sobre el ejemplar, los elementos y los atributos de un documento XML, utilizando el formato solicitado:

#### 3.2.- El ejemplar. Los elementos.

El **ejemplar** es la parte más importante de un documento XML, ya que contiene los **datos reales**. Está formado por **elementos anidados** y es, en realidad, el **elemento raíz (*root*)** del documento. Todos los datos deben pertenecer a un elemento.

Los **elementos** son los bloques de información que definen la estructura. Están delimitados por una etiqueta de apertura y una etiqueta de cierre, y pueden contener otros elementos y/o atributos.

**Reglas de formación de elementos**

* Debe existir **uno y solo un elemento raíz** en todo el documento.
* Todos los elementos deben tener una **etiqueta de inicio y una de cierre**.
* **Elementos vacíos** (sin contenido) pueden sustituir ambas etiquetas por una sola etiqueta de elemento vacío: `<elemento/>` en lugar de `<elemento></elemento>`.
* La **anidación** debe ser correcta: no se puede cerrar un elemento si contiene otro que aún no se ha cerrado.
* Los nombres de las etiquetas de inicio y cierre deben ser **idénticos**, respetando mayúsculas y minúsculas (*case-sensitive*).
* Los nombres de las etiquetas no pueden contener espacios, ni empezar por `:` o por la cadena `xml` (en cualquiera de sus combinaciones de mayúsculas/minúsculas).
* El contenido no puede incluir la cadena `]]>`.

**Caracteres especiales**

Ciertos caracteres deben ser sustituidos por entidades para evitar conflictos con la sintaxis de XML:
    
| Carácter | Entidad |
| :---: | :---: |
| `>` | `&gt;` |
| `<` | `&lt;` |
| `&` | `&amp;` |
| `"` | `&quot;` |
| `'` | `&apos;` |

Para caracteres especiales como `£` o `©`, se usan las expresiones `&#D;` o `&#H;`, donde **D** y **H** son los números decimal o hexadecimal del código **UNICODE** del carácter.

##### 3.2.1. Atributos

Los **atributos** permiten añadir **propiedades** a los elementos. Se usan para información no susceptible de ser dividida, ya que:

- No pueden organizarse jerárquicamente.
- No pueden contener otros elementos o atributos.
- No reflejan una estructura lógica.

**Definición de atributos**

- Se definen y se les da valor **dentro de la etiqueta de inicio** o de elemento vacío.
- Van separados del nombre del elemento (y de otros atributos) por un espacio.
- El valor del atributo va precedido de un igual y debe definirse entre **comillas simples o dobles**.
    - Ejemplo: `<ejemplar tipo_ejem="libro" titulo="XML práctico">`

- Los nombres de los atributos deben cumplir las mismas reglas que los nombres de los elementos y, adicionalmente, **no pueden contener el carácter menor que (`<`)**. 

### 4.- Documentos XML bien formados

Todos los documentos XML deben **verificar las reglas sintácticas** que define la recomendación del W3C para el estándar XML. Esas normas son:

1. El documento **ha de tener definido un prólogo** con la declaración xml completa.
2. Existe un **único elemento raíz** para cada documento: es un solo elemento en el que todos los demás elementos y contenidos se encuentran anidados.
3. Hay que **cumplir las reglas sintácticas** del lenguaje XML para definir los distintos elementos y atributos del documento.

### 5.- Utilización de espacios de nombres en XML

Los **espacios de nombres** (*namespaces*) resuelven las **ambigüedades** que surgen cuando dos documentos XML de diferentes orígenes usan el **mismo nombre de etiqueta** para representar cosas distintas.

- Permiten definir la **pertenencia** de elementos y atributos a un **vocabulario XML** específico.
- Asignan un nombre único a cada elemento, asociándolo a un **URI** que lo identifica de forma global.

Para distinguir entre elementos con el mismo nombre, se utiliza un **prefijo** en las etiquetas:

- La etiqueta se convierte en un **nombre cualificado**:
    `**<prefijo:nombre_etiqueta></prefijo:nombre_etiqueta>**`

El prefijo indica el contexto al que pertenece la etiqueta, seguido de dos puntos (`:`), y no debe contener espacios o caracteres especiales ni puede empezar con un dígito.

Antes de usar un prefijo, el espacio de nombres debe ser **declarado**. Esto asocia el prefijo con su URI único.

- Se realiza mediante el atributo especial **`xmlns`** (XML Name Space), y la declaración se hace habitualmente entre el prólogo y el ejemplar del documento, o en el elemento raíz.
    - El URI asociado tiene la forma: `**<conexion>://<direccionservidor>/<apartado1>/...**` 

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

## UD2.- Utilización de lenguajes de marcas en entornos web