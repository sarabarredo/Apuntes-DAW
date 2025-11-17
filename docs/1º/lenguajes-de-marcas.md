---
id: lenguajes-de-marcas
sidebar_position: 4
title: Lenguajes de marcas y sistemas de gestión de información
toc_max_heading_level: 3
---

## UD1.- Reconocimiento de las características de lenguajes de marcas

![Esquema Unidad 1 Lenguajes de Marcas](../../static/img/lenguajes-de-marcas-unidad-1.jpg)

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

![Esquema Unidad 2 Lenguajes de Marcas](../../static/img/lenguajes-de-marcas-unidad-2.jpg)

### 1.- Introducción
#### 1.1.- HTML: evolución y versiones

**HTML** es el lenguaje estándar utilizado para la mayoría de las páginas web. Es reconocido por todos los navegadores, lo que garantiza una visualización similar del contenido, independientemente del sistema operativo.

**Evolución de HTML**

| Versión | Año (Estándar) | Entidad | Características clave |
| :--- | :--- | :--- | :--- |
| **Origen** | 1990 | | Nace como un sistema de hipertexto para compartir documentos. |
| **HTML 2.0** | Sep. 1995 | IETF | **Primera versión oficial** reconocida como estándar. |
| **HTML 3.2** | Ene. 1997 | W3C | Incorpora **applets de Java** y la capacidad de rodear imágenes con texto. |
| **HTML 4.0** | Abr. 1998 | W3C | Introduce las **Hojas de Estilo CSS** y la posibilidad de incluir pequeños programas. |
| **HTML 4.01** | Dic. 1999 | W3C | Actualización final de la serie 4.0. El W3C detuvo la estandarización hasta 2007. |
| **HTML 5.x** | Desde 2007 | WHATWG / W3C | Es la **versión más avanzada** y el estándar actual (la última especificación es HTML 5.3, de 2018). |

El cambio más significativo en **HTML 5** es la **separación de responsabilidades**:

- **HTML:** se encarga únicamente de la **información**, la **estructura** y la **semántica** del documento.
- **CSS (Hojas de Estilo):** asume la **presentación** del documento.

Esta separación hizo que muchos elementos y atributos de HTML 4 relacionados con la presentación (como `<font>`, `<center>`, `align`) queden **obsoletos**. 

#### 1.2.- HTML y XHTML

**XHTML** (*eXtensible HyperText Markup Language*) es una adaptación del lenguaje **HTML** al estándar **XML**. Esto significa que los documentos XHTML deben cumplir con las reglas de **XML bien formado**.

| Característica | HTML (Sintaxis permisiva) | XHTML (Sintaxis estricta, basada en XML) |
| :--- | :--- | :--- |
| **Flexibilidad** | Muy flexible: permite etiquetas en mayúsculas/minúsculas y valores de atributos sin comillas. | **No flexible:** impone normas de escritura obligatorias (bien formado). |
| **Mantenimiento** | Puede generar código desordenado y difícil de mantener. | Código **más regular**, sencillo de editar, mantener y procesar automáticamente. |
| **Procesamiento** | Los navegadores intentan mostrar el contenido aunque haya errores. | Si se sirve como XML, cualquier **error de sintaxis causa que el documento no se muestre**. |

Para que el código HTML se considere XHTML (XML bien formado), debe cumplir las siguientes normas:

* **Elemento Raíz:** toda la página debe estar contenida en el elemento raíz `<html>`.
* **Minúsculas:** los nombres de las **etiquetas** y **atributos** deben escribirse **siempre en minúsculas**.
* **Comillas:** el valor de **todos los atributos**, incluidos los numéricos, debe ir **siempre entre comillas**.
* **Cierre de Etiquetas:** **Todas las etiquetas deben cerrarse**. Las etiquetas vacías se cierran con una sintaxis especial: `<br/>` en lugar de `<br><br/>`.
* **Atributos no comprimibles:** no se puede omitir el valor en atributos donde el nombre y el valor coinciden (aunque son poco habituales).

Aunque los diseñadores web suelen preferir HTML, los tres primeros puntos de las reglas sintácticas se consideran **buenas prácticas** que se aplican universalmente para mejorar la calidad del código. 

#### 1.3.- Estructura de un documento HTML

Un documento HTML mantiene la estructura de un documento XML, dividiéndose en un **prólogo** y un **ejemplar**.

El **prólogo** es la declaración inicial que informa al navegador sobre el tipo de documento y la versión de HTML utilizada, lo que permite su correcta interpretación.

```html title="Declaración en HTML 5"
<!DOCTYPE html>
```

En **HTML 4.0** existen tres tipos de documentos definidos por su DTD:
1.  **Strict:** No permite el uso de elementos obsoletos (*deprecated*).
2.  **Transitional:** Permite tanto los elementos Strict como los obsoletos.
3.  **Frameset:** Variante de Transitional para documentos que utilizan *frames* (reemplaza la etiqueta `<body>`).

El **ejemplar** está delimitado por las etiquetas `<html>` y `</html>` y se divide en dos secciones principales:

1.  **Cabecera (`<head>...</head>`):**
    - Contiene **metadatos** sobre la página (autor, palabras clave, etc.).
    - Es obligatorio incluir el **título** del documento con la etiqueta `<title>...</title>`.
    - Esta información **no se muestra** en la ventana del navegador, excepto el título, que aparece en la barra superior.

2.  **Cuerpo (`<body>...</body>`):**
    - Contiene toda la **información que se presentará** en la pantalla del navegador (textos, imágenes, enlaces, etc.).
    - En documentos *Frameset*, el `<body>` se sustituye por la etiqueta `<frameset>`.
    
#### 1.4.- Identificación de etiquetas y atributos HTML

Un documento HTML se construye a partir de **etiquetas** y **atributos**.

**Etiquetas**

Las etiquetas son las marcas que estructuran el contenido (ej., `<etiqueta>` de apertura y `</etiqueta>` de cierre). A diferencia de XML (donde se crean etiquetas personalizadas), el número de etiquetas en HTML está **limitado** a aquellas que están **predefinidas** por el lenguaje (el estándar HTML).

**Atributos**

Los atributos se utilizan para añadir **información adicional o complementaria** a una etiqueta, lo que permite crear elementos complejos (como definir la fuente de una imagen o el destino de un enlace).  La combinación de la etiqueta y sus atributos forma el **elemento** completo. Cada atributo tiene un conjunto definido de valores que se le pueden asignar. Si se proporciona un valor no válido, el navegador simplemente lo **ignora**. Cada etiqueta define qué atributos específicos puede utilizar, aunque algunos son **comunes** a muchas etiquetas. 

#### 1.5.- Clasificación de los atributos comunes según su funcionalidad

Los atributos permiten añadir información adicional a las etiquetas HTML. Aunque existen atributos específicos para cada etiqueta, los siguientes se pueden clasificar según su propósito general:

**Atributos básicos o globales**

Estos atributos se pueden usar en casi **todas las etiquetas** de HTML y son fundamentales para la identificación y el estilo:

| Atributo | Descripción |
| :--- | :--- |
| **`name`** | Asigna un **nombre** al elemento, útil para scripts o formularios. |
| **`title`** | Asigna un **título descriptivo** al elemento. El navegador lo muestra cuando el usuario pasa el ratón por encima, mejorando la **accesibilidad** (especialmente útil en enlaces e imágenes). |
| **`id`** | Proporciona un **identificador único** al elemento. Es esencial para trabajar con CSS y JavaScript. (Restricción: no puede empezar por números). |
| **`style`** | Permite aplicar **estilos CSS directamente** al elemento de forma *inline*. |
| **`class`** | Aplica un **estilo definido en las hojas CSS** al elemento, permitiendo aplicar el mismo estilo a múltiples elementos. (Restricción: no puede empezar por números). | 

**Atributos para internacionalización**

Se utilizan para indicar el **idioma** y la **dirección** del texto, especialmente en páginas multilingües:

| Atributo | Descripción | Valores |
| :--- | :--- | :--- |
| **`dir`** | Indica la **dirección del texto** | **`ltr`** (left to right, por defecto) o **`rtl`** (right to left) |
| **`lang`** | Especifica el **idioma del elemento** mediante un código predefinido | `en` (Inglés), `es` (Español), etc. |
| **`xml:lang`** | Especifica el idioma en documentos **XHTML** | En XHTML, este atributo es **obligatorio** si se incluye `lang` y tiene mayor prioridad |

**Atributos de eventos**

Esta categoría incluye atributos específicos que solo se utilizan en páginas **dinámicas** (como *eventos* para JavaScript), por lo que no se detallan en este contexto.

### 2.- Elementos HTML

Un **elemento HTML** es la unidad fundamental de un documento y está compuesto por cuatro partes principales:

1.  Una **etiqueta de apertura** (`<etiqueta>`).
2.  **Cero o más atributos**.
3.  Opcionalmente, un **texto** encerrado por la etiqueta (no todas las etiquetas lo permiten).
4.  Una **etiqueta de cierre** (`</etiqueta>`), la cual es opcional o inexistente para ciertos elementos.

Según el modo en que ocupan el espacio en la página, los elementos se dividen en dos tipos de visualización:

1.  **Elementos en línea (*Inline*)**
    * **Espacio:** Solo ocupan el **espacio estrictamente necesario** para mostrar su contenido.
    * **Contenido:** Pueden contener texto u otros elementos en línea.
    * **Ejemplos:** Los **enlaces** (`<a>`) y el **texto resaltado** (`<strong>`).

2.  **Elementos de bloque (*Block*)**
    * **Espacio:** Siempre comienzan en una **nueva línea** y ocupan **todo el ancho disponible** hasta el final de la línea.
    * **Contenido:** Pueden contener texto, elementos en línea u otros elementos de bloque.
    * **Ejemplos:** Los **encabezados** (`<h1>`) y los **párrafos** (`<p>`).

#### 2.1.- Elementos de la estructura básica de un documento

La estructura de un documento HTML está definida por:

- **`<html>`**: El elemento **raíz** que delimita el inicio y el fin de todo el documento.
- **`<head>`**: Define la **cabecera**. Contiene metadatos, enlaces a estilos y el título (`<title>`). **No se muestra** en la ventana principal.
- **`<body>`**: Define el **cuerpo visible** del documento. Contiene toda la información que se presenta en la pantalla y permite aplicar **formatos globales** (como color de fondo). 

#### 2.2.- Elementos de la sección de cabecera

Los elementos de la cabecera (`<head>`) contienen metadatos e información de soporte para el documento y se clasifican en dos tipos:

- **Elementos contenedores**: encierran su contenido y requieren etiquetas de apertura y cierre:
    - **`<title>`**: define el **título del documento** que aparece en la barra del navegador. Es un elemento **obligatorio**.
    - **`<script>`**: se utiliza para incrustar **código *script*** (como JavaScript) en la página. (Tradicionalmente se recomendaba envolver el contenido en comentarios para evitar su interpretación por navegadores antiguos, pero esto ya no es una práctica común).
    - **`<style>`**: define las **reglas de estilo CSS** que se aplicarán al documento. (Al igual que con `<script>`, su contenido solía ir entre comentarios).

- **Elementos no contenedores**: no encierran contenido y se cierran a sí mismos (o no tienen etiqueta de cierre):
    - **`<base>`**: establece la **URI base** para todas las URL relativas que aparecen en el documento.
    - **`<link>`**: se utiliza para **enlazar documentos externos**, siendo el uso más común la vinculación a hojas de estilo **CSS**.
    - **`<meta>`**: define **metadatos** sobre la página, como la codificación de caracteres, la descripción del contenido o la información del autor.
    - **`<isindex>`**: se utilizaba como *prompt* de entrada de datos, pero ha sido **eliminado de los estándares** web actuales. 

#### 2.3.- Encabezados y párrafos

HTML utiliza elementos específicos para agrupar texto y definir títulos jerárquicos:

- **Párrafos**: se utiliza para agrupar el texto en párrafos utilizando la etiqueta `<p>`. Es un **elemento de bloque**, lo que significa que siempre empieza en una nueva línea y ocupa todo el ancho disponible.

- **Encabezados**: sirven para organizar el contenido de la página de forma **jerárquica**, donde `<h1>` es el título principal de la sección o página. Se definen seis niveles de encabezado, desde `<h1>` hasta `<h6>`. Cuanto menor es el número, mayor es la importancia del encabezado.    

##### 2.3.1.- Saltos de línea y espacios en blanco

Al procesar HTML, los navegadores **ignoran** los saltos de línea introducidos en el código fuente y **colapsan** múltiples espacios consecutivos en uno solo.

Para forzar un salto de línea visible, se usa el elemento `<br>`, y para forzar múltiples espacios, se usa la entidad `&nbsp;`. 

##### 2.3.2.- Comentarios

Los comentarios en HTML no son procesados por los navegadores, solo sirven para documentar el código. Pueden ser de dos tipos:

```html title="De una sola línea"
<!-- comentario -->
```

```html title="Multilínea"
<!-- comentario
  de varias
  líneas -->
```

#### 2.4.- Semántica a nivel de texto

Los siguientes elementos HTML se utilizan para dar significado (*semántica*) a porciones de texto:

| Elemento | Función |
| :--- | :--- |
| `<a>` | Define **hipervínculos** |
| `<strong>` | Representa que el texto marcado es de **gran importancia** (negrita) |
| `<em>` | Indica **énfasis** en el texto (cursiva) |
| `<br>` | Introduce un **salto de línea** |
| `<small>` | Utilizado para **comentarios accesorios** (letra pequeña) |

El elemento `<a>` transforma el texto que encierra en un enlace navegable.

* **Atributo clave: `href`**
    * Especifica la **URL de destino** del vínculo.
    * Usar **`href="#" `** se refiere a la misma página.

* **Atributo `target`**
    * Define **dónde se abrirá** el vínculo.
    * `target="_self"`: abre el enlace en la **misma ventana/pestaña**.
    * `target="_blank"`: abre el enlace en una **ventana o pestaña nueva**. 

#### 2.5. Elementos de listas en HTML

HTML define tres tipos de listas:

| Elemento | Tipo de lista | Descripción | Función interna |
| :--- | :--- | :--- | :--- |
| `<ul>` | **Desordenada** | Delimita la lista completa | Contiene elementos `<li>` |
| `<ol>` | **Ordenada** | Delimita la lista completa (los ítems se numeran) | Contiene elementos `<li>` |
| `<dl>` | **De Definición** | Delimita la lista completa de términos y descripciones | Contiene elementos `<dt>` y `<dd>` |
| `<li>` | Ítem de lista | Define cada **elemento individual** de una lista ordenada o desordenada | |
| `<dt>` | Término | Define cada **término** que va a ser definido en una lista de definición | |
| `<dd>` | Definición | Define la **descripción** o definición del término anterior en una lista de definición | | 


#### 2.6.- Elementos de tablas

Las tablas son una forma común de presentar información de manera compacta. El elemento principal es `<table>`, que agrupa al resto de los elementos.

Una tabla se construye principalmente con filas (`<tr>`) que contienen celdas de datos (`<td>`) o celdas de cabecera (`<th>`).

| Elemento | Descripción | Función |
| :--- | :--- | :--- |
| `<table>` | Delimita el contenido completo de la tabla | Contenedor principal |
| `<tr>` | Delimita cada una de las **filas** de la tabla | Contiene celdas (`<td>` o `<th>`) |
| `<th>` | Delimita una **celda de cabecera** | Usualmente se usa en la primera fila para encabezar las columnas |
| `<td>` | Delimita el contenido de una **celda de datos** estándar | Usualmente se usa en el cuerpo de la tabla |

Hay elementos opcionales de **agrupación y leyenda**, que permiten estructurar la tabla semánticamente:

| Elemento | Descripción |
| :--- | :--- |
| `<caption>` | Añade una **leyenda** o título a la tabla |
| `<thead>` | Define la sección de la **cabecera** de la tabla (las filas iniciales) |
| `<tbody>` | Permite agrupar las **filas del cuerpo** principal de la tabla |
| `<tfoot>` | Define la sección del **pie** de la tabla (las filas finales) |
| `<colgroup>` | Permite **agrupar columnas** para aplicar estilos o lógica | 

***NOTA IMPORTANTE***: aunque era habitual hace años, no es correcto usar tablas para la maquetación de la página.

#### 2.7.- Elementos de formularios

Los **formularios** permiten al navegador **recoger información** introducida por el usuario. Es fundamental **validar** estos datos en el equipo local (cliente), generalmente combinando formularios con código **JavaScript**, para evitar enviar datos erróneos que sobrecarguen la red y el servidor.

##### 2.7.1.- Declaración de formulario

Un formulario se delimita usando el elemento `<form>`, que puede tener varios atributos:

- `name`: asigna un **nombre** al formulario.
- `action`: especifica la **URL** de la página o *script* que se ejecutará al enviar el formulario.
- `enctype`: define el **formato** en que se enviarán los datos del formulario.
- `method`: define el **método de envío** de los datos al servidor. Se puede elegir entre dos métodos: **GET** y **POST**.

| Característica | GET | POST |
| :--- | :--- | :--- |
| Visibilidad | Los valores se ven en la **URL** (concatenados con `&`) | Los valores **no son visibles** en la URL |
| Longitud | Tienen un **límite de longitud** | **Carece de restricciones** de longitud |
| Contenido | Pasa valores en ASCII | Pasa valores y otros elementos como **archivos** adjuntos | 

##### 2.7.2.- Campos de formulario: `<input>`

El elemento `<input>` es el control más versátil dentro de un formulario y **no tiene etiqueta de cierre**. Su función cambia drásticamente según el valor de su atributo **`type`** (p. ej., `type="text"` por defecto, o `type="radio"` para un botón de radio).

| Atributo | Función |
| :--- | :--- |
| `name` | **Nombre** del campo; es la clave con la que se identifica el valor enviado al servidor |
| `size` | Número de **caracteres visibles** en el campo (por defecto, 20) |
| `maxlength` | **Número máximo** de caracteres que el usuario puede introducir |
| `value` | **Valor por defecto** inicial del campo |
| `placeholder` | **Valor sugerido** (en color gris) que desaparece cuando el usuario enfoca el campo |
| `readonly` | El valor del campo **no puede ser modificado** por el usuario (solo lectura) |
| `autofocus` | Sitúa el **cursor del ratón** automáticamente en este campo al cargar la página |
| `required` | Indica que el campo es **obligatorio**; el formulario no se puede enviar si no está rellenado | 


##### 2.7.3.- Campos de formulario: `<textarea>`

El elemento **`<textarea>`** se utiliza para **recoger información abierta** del usuario, permitiendo un **mayor número de caracteres** que un campo de texto simple. A diferencia de `<input>`, el valor por defecto debe escribirse **entre las etiquetas** de apertura y cierre.

| Atributo | Función | Notas |
| :--- | :--- | :--- |
| `name` | **Nombre** del campo, usado para identificar el dato al enviarlo | |
| `rows` | Número de **filas** (altura visible) del área de texto | Reemplazable por la propiedad CSS `height` |
| `cols` | Número de **columnas** (ancho visible) del área de texto | Reemplazable por la propiedad CSS `width` |

El elemento `<textarea>` también acepta otros atributos comunes a `<input>`, como `placeholder`, `readonly`, `autofocus`, `maxlength`, y `required`. 

##### 2.7.4.- Campos de formularios: `<select>`

Una **lista desplegable** permite al usuario seleccionar una o varias opciones de un conjunto predefinido de valores. Utiliza dos etiquetas:

- `<select>`: etiqueta contenedora que **define la lista** desplegable completa.
- `<option>`: define **cada una de las opciones** disponibles dentro de la lista.

| Etiqueta | Atributo | Función |
| :--- | :--- | :--- |
| `<select>` | `name` | **Nombre** del elemento, utilizado para identificar el valor enviado |
| `<select>` | `size` | Número de **elementos visibles** de la lista |
| `<select>` | `multiple` | Permite al usuario seleccionar **varias opciones** a la vez |
| `<option>` | `value` | **Valor que se transmite** al servidor cuando se envía el formulario |
| `<option>` | `selected` | Indica que esa opción aparece **seleccionada por defecto** al cargar el formulario |

##### 2.7.5.- Campos de formulario: `checkbox`

La **casilla de verificación** (*checkbox*) se usa para permitir al usuario seleccionar **una o varias opciones** dentro de un grupo, indicando su conformidad o elección.

| Etiqueta | **`<input type="checkbox">`** |
| :--- | :--- |
| `name` | **Obligatorio**. Nombre del campo, clave para identificar la opción enviada |
| `checked` | Si está presente, la casilla aparecerá **marcada por defecto** al cargar el formulario |
| `value` | **Valor que se transmite** al servidor si la casilla está marcada | 

##### 2.7.6.- Botones de formulario

**Botón de envío (`submit`)**: 
    - Envía los datos del formulario al destino especificado en el atributo `action` del elemento `<form>`
    - Su etiqueta es `<input type="submit">`
    - El atributo `value` define el **texto** que se muestra dentro del botón

**Botón de anulación (`reset`)**:
    - Borra o **restaura el contenido** de todos los campos del formulario a sus valores por defecto
    - Su etiqueta es `<input type="reset">`
    - El atributo `value` define el **texto** que se muestra dentro del botón
    
##### 2.7.7.- Otros campos de formulario

Existen múltiples tipos de campos `<input>` que se utilizan para recoger información específica, muchos de los cuales ofrecen **validación automática** y controles de entrada mejorados en HTML5:

| Campo | Etiqueta | Notas y atributos clave |
| :--- | :--- | :--- |
| Oculto | `<input type="hidden">` | El campo es **invisible** para el usuario |
| Contraseña | `<input type="password">` | Los caracteres introducidos se ocultan |
| Envío de ficheros | `<input type="file">` | Permite al usuario seleccionar un archivo para subirlo. **Requiere** que el formulario use `method="post"` y `enctype="multipart/form-data"`. |
| Correo electrónico | `<input type="email">` | Valida que el texto tenga el formato de un correo electrónico |
| URL | `<input type="url">` | Valida que el texto tenga el formato de una URL válida |
| Números en un rango | `<input type="number">` | Permite recoger solo números enteros o decimales. Atributos para control: **`max`**, **`min`**, **`step`** | 


##### 2.7.8.- Campos de formulario con formato de fecha y hora

HTML5 introdujo varios tipos de campos **`<input>`** especializados para recoger fechas y horas, que proporcionan una interfaz de usuario estandarizada y validación automática.

| Tipo de campo | Etiqueta | Información que recoge |
| :--- | :--- | :--- |
| Fecha y hora local | `<input type="datetime-local">` | Permite seleccionar día, mes, año y hora |
| Fecha | `<input type="date">` | Permite seleccionar día, mes y año |
| Mes | `<input type="month">` | Permite seleccionar mes y año |
| Semana | `<input type="week">` | Permite seleccionar una semana específica |
| Hora | `<input type="time">` | Permite seleccionar solo la hora |

Existen atributos que controlan los valores válidos y los incrementos permitidos:

- `min`: define el valor de tiempo o fecha más temprano que puede ser seleccionado.
- `max`: define el valor de tiempo o fecha más tardío que puede ser seleccionado.
- `step`: Define el **incremento** del contador del campo, medido en segundos (p. ej., para limitar la selección de horas a intervalos de 30 minutos). 

##### 2.7.9.- Campos de formulario: Rangos

El campo de **rango** (`<input type="range">`) permite seleccionar un valor mediante un **control deslizante** (*slider*).

| Atributo | Función |
| :--- | :--- |
| `value` | Valor inicial | 
| `min` | Valor mínimo |
| `max` | Valor máximo |
| `step` | Valor del incremento |

##### 2.7.10. Organización de formularios

Para mejorar la **usabilidad** y la **accesibilidad** de los formularios, HTML proporciona elementos para agrupar y etiquetar los campos:

| Elemento | Función | Uso clave |
| :--- | :--- | :--- |
| `<label>` | Asocia una etiqueta a un campo de formulario | Mejora la **accesibilidad** para lectores de pantalla. Se vincula al campo usando el atributo **`for`**, cuyo valor debe ser el **`id`** del campo de destino |
| `<fieldset>` | **Agrupa** campos relacionados del formulario | Rodea los campos con un **borde visible** para la organización visual |
| `<legend>` | Define un **título o leyenda** para el grupo de campos | Debe colocarse inmediatamente después de la etiqueta de apertura `<fieldset>` |


<details>
  <summary>Ejemplo de formulario HTML completo</summary>

    ```jsx live
    <form action="/procesar-matricula" method="post">
            
        <fieldset>
            <legend>Datos Personales</legend>
            <div>
                <label htmlFor="nombre">Nombre:</label>
                <input type="text" id="nombre" name="nombre" required />
            </div>
            <br />
            <div>
                <label htmlFor="apellidos">Apellidos:</label>
                <input type="text" id="apellidos" name="apellidos" required />
            </div>
            <br />
            <div>
                <label htmlFor="fechaNacimiento">Fecha de nacimiento:</label>
                <input type="date" id="fechaNacimiento" name="fechaNacimiento" required />
            </div>
            <br />
            <div role="group" aria-labelledby="sexo-label">
                <span id="sexo-label">Sexo:</span>
                <input type="radio" id="sexoM" name="sexo" value="M" required />
                <label htmlFor="sexoM">Masculino</label>
                
                <input type="radio" id="sexoH" name="sexo" value="H" />
                <label htmlFor="sexoH">Femenino</label>
            </div>
        </fieldset>
        
        <br />
        
        <fieldset>
            <legend>Módulos de Matrícula</legend>
            <p>Escoge los módulos en los que te matriculas:</p>

            <input type="checkbox" id="mod1" name="modulos[]" value="HW" />
            <label htmlFor="mod1">Fundamentos de Hardware</label> 
            <br />
            
            <input type="checkbox" id="mod2" name="modulos[]" value="BBDD" />
            <label htmlFor="mod2">Gestión de Bases de Datos</label>
            <br />
            
            <input type="checkbox" id="mod3" name="modulos[]" value="SO" />
            <label htmlFor="mod3">Implantación de Sistemas Operativos</label>
            <br /> 
            
            <input type="checkbox" id="mod4" name="modulos[]" value="Redes" />
            <label htmlFor="mod4">Planificación y Administración de Redes</label>
            <br />
            
            <input type="checkbox" id="mod5" name="modulos[]" value="LM" />
            <label htmlFor="mod5">Lenguajes de Marcas y Sistemas de Gestión de Información</label>
            <br />
            
            <input type="checkbox" id="mod6" name="modulos[]" value="FOL" />
            <label htmlFor="mod6">Formación y Orientación Laboral</label> 
            <br />
            
            <input type="checkbox" id="mod7" name="modulos[]" value="Proyecto" />
            <label htmlFor="mod7">Proyecto de Administración de Sistemas Informáticos en Red</label>
            <br />
            
            <input type="checkbox" id="mod8" name="modulos[]" value="Servicios" />
            <label htmlFor="mod8">Servicios de Red e Internet</label> 
            <br />
            
            <input type="checkbox" id="mod9" name="modulos[]" value="AdminSO" />
            <label htmlFor="mod9">Administración de Sistemas Operativos</label> 
            <br />
            
            <input type="checkbox" id="mod10" name="modulos[]" value="AppWeb" />
            <label htmlFor="mod10">Implantación de Aplicaciones Web</label> 
            <br />
            
            <input type="checkbox" id="mod11" name="modulos[]" value="AdminBBDD" />
            <label htmlFor="mod11">Administración de Sistemas Gestores de Bases de Datos</label> 
            <br />
            
            <input type="checkbox" id="mod12" name="modulos[]" value="Seguridad" />
            <label htmlFor="mod12">Seguridad y Alta Disponibilidad</label> 
            <br />
            
            <input type="checkbox" id="mod13" name="modulos[]" value="Empresa" />
            <label htmlFor="mod13">Empresa e Iniciativa Emprendedora</label>
            <br />
            
            <input type="checkbox" id="mod14" name="modulos[]" value="FCT" />
            <label htmlFor="mod14">Formación en Centros de Trabajo</label>
        </fieldset>
        
        <br />

        <fieldset>
            <legend>Estudios Previos</legend>
            <br />
            <label htmlFor="estudiosPrevios">Detalle brevemente sus estudios previos:</label>
            <br />
            <textarea id="estudiosPrevios" name="estudiosPrevios" rows="5" cols="50"></textarea>
        </fieldset>

        <br />
        
        <input type="submit" value="Enviar" />
        <input type="reset" value="Restablecer" />
        
        <p>Pulsa el botón de "Enviar" para formalizar la matrícula o el botón de "Restablecer" para limpiar el formulario.</p>

    </form>
    ```
</details>

#### 2.8.- Multimedia

Los siguientes elementos son los más habituales para incrustar contenido multimedia en una página web:

| Elemento | Descripción |
| :--- | :--- |
| `<img>` | Inserta una **imagen** |
| `<audio>` | Inserta un **audio** |
| `<video>` | Inserta un **vídeo** |
| `<object>` | Elemento genérico para incrustar **contenido multimedia** externo (vídeo, audio, PDFs, *applets*) |

El elemento `<img>` se usa para insertar imágenes y **no tiene etiqueta de cierre**. Sus atributos clave son:
    - `src`: ruta de la imagen. Los formatos comunes soportados incluyen **JPG, PNG y GIF**.
    - `alt`: texto alternativo. Es **obligatorio** y se muestra si la imagen no carga, o es leído por los *lectores de pantalla* (accesibilidad).
    - `height` y `width`: definen la **altura** y la **anchura** de la imagen. Si se especifican, la imagen se escala; si no, se usa el tamaño original.

#### 2.9.- Secciones y etiquetas semánticas

El elemento `<div>` se usa para agrupar y organizar contenido. Sin embargo, en **HTML5** surgieron **etiquetas semánticas** con propósitos específicos, por lo que **solo se debe usar `<div>` cuando no exista una etiqueta más apropiada**.

Estas etiquetas añaden significado estructural al contenido:

| Etiqueta | Función semántica | Contenido típico |
| :--- | :--- | :--- |
| `<header>` | Contenido **introductorio** para una sección o página | Títulos (`<h1>` a `<h6>`), logotipos. |
| `<nav>` | Contiene **vínculos** de navegación principales (menús) | Enlaces internos o externos |
| `<section>` | Representa una **sección genérica** dentro de un documento | Grupos de contenido temáticamente relacionados |
| `<article>` | Representa un elemento que es **independiente** y **reutilizable** (ej. Una entrada de blog, un comentario) | Contenido autónomo que podría distribuirse por separado |
| `<aside>` | Contenido **parcialmente relacionado** con el contenido principal | Notas al margen, *sidebars*, publicidad (no necesariamente tiene que estar en un lateral) |
| `<footer>` | Contiene información de cierre o metadatos de su sección correspondiente | Información de autor, enlaces relacionados (no tiene que estar necesariamente al final de la página) | 

#### 2.10.- Elemento iframe

El elemento `<iframe>` permite **integrar una página web completa dentro de otra**. Este elemento sustituye en ciertos aspectos a la especificación obsoleta de marcos (`frameset`) de HTML 4.

| Atributo | Función | Notas |
| :--- | :--- | :--- |
| `src` | Especifica la **ruta** al contenido web inicial que se cargará dentro del *iframe* | Puede ser una URL local o externa |
| `height` | Define la **altura** del *iframe* | Si el contenido es mayor, se usa una barra de desplazamiento. Se puede fijar con CSS |
| `width` | Define la **anchura** del *iframe* | Se puede fijar con CSS |
| `name` | Asigna un **nombre** al *iframe* | Es crucial para que los enlaces externos se dirijan a él |

Para que un **vínculo** (`<a>`) cargue su contenido dentro de un *iframe* específico en lugar de la ventana principal, se debe hacer lo siguiente:

1.  El *iframe* debe tener el atributo `name` con un valor definido.
2.  El vínculo (`<a>`) debe tener el atributo **`target`** con el **mismo valor** que el `name` del *iframe*.

### 3.- Hojas de estilo o CSS

**CSS** permite a los desarrolladores controlar el **estilo y formato** de múltiples páginas web simultáneamente. Su objetivo principal es **separar los contenidos (HTML/XHTML) de su aspecto**.

Antes de CSS, el estilo se definía dentro de las etiquetas HTML, lo que hacía que las páginas fueran difíciles de actualizar y mantener.

**Funcionalidad y estructura**

- **Separación:** primero se usa **HTML/XHTML** para marcar la **estructura y semántica** del contenido (párrafo, cabecera). Luego se usa **CSS** para definir el **formato** de esos elementos.
- **Mantenimiento:** cualquier cambio en una regla de estilo CSS afecta a **todas las páginas** vinculadas a esa hoja de estilo.
- **Ventajas:** CSS obliga a crear documentos **semánticos**, mejora la **accesibilidad**, reduce la complejidad de **mantenimiento** y permite una visualización consistente en **diferentes dispositivos**.

**Evolución y versiones de CSS**

La necesidad de un mecanismo de estilo surgió alrededor de 1970 con el lenguaje SGML. El W3C asumió la estandarización en 1995.

| Versión | Publicación | Características |
| :--- | :--- | :--- |
| CSS 1 | 1996 | Primera recomendación oficial |
| CSS 2 | 1998 | Segunda recomendación oficial |
| CSS 3 | Desde 1998 | La especificación se divide en **múltiples documentos separados** llamados **módulos**. Permite que los módulos evolucionen de forma independiente |
| CSS 4 | En desarrollo | Continúa con la división modular de CSS 3, donde cada módulo evoluciona a su propio ritmo | 

#### 3.1.- Cómo incluir CSS en un documento HTML o XHTML

Hay tres métodos para aplicar estilos CSS a los elementos de una página web, ofreciendo diferentes niveles de control y separación de contenido y formato:

1. **Declaración en línea (inline)**
    - El estilo se declara **directamente dentro de la etiqueta HTML** utilizando el atributo `style`.
    - Esta opción está **desaconsejada** porque viola el principio de separación de contenido y estilo.

2. **Declaración interna**
    - Los estilos se definen en la **cabecera** del documento, dentro de las etiquetas `<style>...</style>`.
    - Su ventaja es que centraliza el estilo para esa página específica.

3. **Declaración en archivo externo**
    - Se define un archivo con extensión `.css` que contiene todas las reglas de estilo y se **vincula** a la página desde la cabecera mediante la etiqueta `<link>`.
    - Su ventaja es que permite controlar el estilo de **múltiples páginas** desde un solo archivo, facilitando el mantenimiento.
    - Tiene dos sintaxis:
        - `<link>`: es la más recomendada.
        - `@import`: se importa un archivo CSS desde dentro de otra etiqueta `<style>` o desde otro archivo CSS.

##### 3.1.1.- Elemento `span`

Es un contenedor genérico en línea que se usa para aplicar estilos o lógica a una pequeña porción de texto o contenido. 

#### 3.2.- Sintaxis de las reglas de estilo

Cada estilo definido en una hoja CSS se llama **regla**. Una regla CSS se compone de tres partes principales que definen qué elementos se modifican y cómo:

1.  **Selector:** indica el elemento o elementos HTML a los que se aplicará el estilo (ej., `p` para párrafos).
2.  **Llave de apertura:** `{`
3.  **Declaración:** especifica los estilos a aplicar y se forma por:
      * **Propiedad:** el aspecto del elemento que se va a modificar (ej., `color`).
      * **Valor:** el nuevo valor asignado a esa propiedad (ej., `blue`).
4.  **Llave de cierre:** `}`

Una hoja CSS puede contener múltiples reglas. A su vez, una sola regla puede tener varios selectores (separados por comas) y varias declaraciones (separadas por punto y coma).

#### 3.3.- Cascada y herencia de estilos

La **cascada** y la *herencia** determinan qué estilos de CSS se aplican a un elemento.

1. **Cascada**: define qué estilo gana cuando hay conflictos, siguiendo este orden de prioridad (de mayor a menor):
    1.  **En línea** (`style` en la etiqueta HTML)
    2.  **Interna** (`<style>` en el `<head>`)
    3.  **Externa** (`<link>` a archivo `.css`)
    4.  **Por defecto del navegador**

2. **Herencia**: los elementos internos (hijos) **heredan** las propiedades de estilo de sus elementos contenedores (padres), **a menos que** el elemento hijo defina su propio estilo para esa propiedad. 

#### 3.4.- Selectores

Los **selectores** son mecanismos que permiten **identificar qué elementos** de tu código HTML recibirán los estilos definidos en una regla.

1. **Selector Universal (`*`)**: selecciona **todos los elementos** de la página web. Se usa a menudo para aplicar estilos o reseteos básicos que afectan globalmente al diseño (ej., márgenes y rellenos).
  * **Ejemplo:**
    ```css
    * { 
        margin: 10px; 
        padding: 5px;
    }
    ```

2. **Selectores de etiqueta**: los estilos se aplican a **todos los elementos** que utilizan una etiqueta HTML específica. Se pueden aplicar los mismos estilos a varias etiquetas diferentes **separándolas por comas**.
  * **Ejemplo:**
    ```css
    p, h1, h2 { 
        text-align: center;
    }
    ```

##### 3.4.1.- Selectores de clase

Los **selectores de clase** permiten aplicar estilos específicos solo a un **subconjunto de etiquetas** sin afectar a todas las de su mismo tipo. Los elementos HTML se asocian a una clase mediante el atributo **`class`**.

**Sintaxis y uso**

1.  **En HTML:** La etiqueta recibe el atributo `class`.

    ```html
    <p class="parrafoCentrado"> ... </p>
    ```

2.  **En CSS (específico por etiqueta):** el estilo se aplica solo a un tipo de etiqueta con esa clase.

      * **Sintaxis:** `etiqueta.nombreClase`
      * **Ejemplo:** `p.parrafoCentrado { text-align: center; }` (Solo centrará los párrafos con esa clase).

3.  **En CSS (genérico):** el estilo se aplica a **cualquier elemento** que tenga esa clase, independientemente de su etiqueta.

      * **Sintaxis:** `.nombreClase`
      * **Ejemplo:** `.parrafoCentrado { text-align: center; }` (centrará cualquier `<p>`, `<h1>`, `<div>`, etc., con esa clase).

##### 3.4.2.- Selectores de ID

El **selector de ID** se usa para seleccionar un **único elemento** de la página mediante su atributo `id`.
    - **Uso:** Debe aplicarse de manera excepcional, ya que el valor de `id` **no debe repetirse** en la misma página.
    - **Sintaxis:** Se referencia usando el símbolo de almohadilla (`#`).

##### 3.4.3.- Selectores descendentes

Permiten seleccionar elementos que se encuentran **dentro de otros elementos**, utilizando un espacio para separar los selectores.
    - El estilo se aplica a los elementos más internos, siempre que sean descendientes del selector más externo. La anidación **no tiene por qué ser directa** y puede tener múltiples niveles.
    -  Es fundamental no confundir el selector descendente (separado por espacios, `p a b i`) con la **agrupación de selectores** (separados por comas, `p, a, b, i`), que aplica el mismo estilo a todos esos elementos a la vez.
    - Se puede usar el selector universal (`*`). Por ejemplo, `p * b` selecciona cualquier etiqueta `<b>` que esté anidada dentro de *cualquier otra etiqueta* (`*`), que a su vez esté dentro de un `<p>`.

##### 3.4.4.- Selector hijo

El selector **hijo** (`>`) es similar al descendente, pero **solo afecta al primer nivel de anidamiento**; es decir, solo selecciona a los descendientes **directos**.
    - Se utiliza el símbolo **mayor que** (`>`) entre los selectores: `padre > hijo`.

    
#### 3.5.- Propiedades principales

##### 3.5.1.- Propiedades de color y fondo

Controlan el color del texto y el fondo de los elementos. Se recomienda usar valores **RGB**.

| Propiedad | Función |
| :--- | :--- |
| `color` | Color del **texto** |
| `background-color` | Color de **fondo** |
| `background-image` | Inserta una **imagen** en el fondo |
| `background-repeat` | Define si la imagen se repite (`repeat-x`, `repeat-y`, `no-repeat`) |
| `background-attachment` | Fija la imagen o permite el desplazamiento (`fixed`, `scroll`) |
| `background-position` | Ubica la imagen de fondo |
| `background` | Propiedad **abreviada** para definir todas las anteriores a la vez |

##### 3.5.2.- Propiedades de fuente
 
Controlan la tipografía de los elementos de texto.

| Propiedad | Descripción |
| :--- | :--- |
| `font-size` | Indica el **tamaño** de la fuente |
| `font-family` | Establece la **familia tipográfica** de la fuente |
| `font-weight` | Define el **grosor** de los caracteres |
| `font-style` | Determina si la fuente es normal o **cursiva** |
| `font-variant` | Define si la fuente es normal o **mayúsculas pequeñas** (*small-caps*) |
| `line-height` | Define el **alto de la línea** (el espaciado vertical entre líneas) |
| `font` | Propiedad **abreviada** para establecer todas las anteriores en un solo paso |

##### 3.5.3.- Propiedades de texto

Controlan el formato, la alineación y el espaciado dentro de un elemento.

| Propiedad | Descripción |
| :--- | :--- |
| `text-decoration` | Establece el estilo de la línea sobre o a través del texto |
| `text-align` | Indica la **alineación horizontal** del contenido |
| `text-indent` | Determina la **tabulación** o sangría inicial del texto |
| `text-transform` | Permite **transformar la caja** del texto |
| `word-spacing` | Determina el **espaciado entre palabras** |
| `letter-spacing` | Determina el **espaciado entre letras** (kerning) |
| `vertical-align` | Establece la **alineación vertical** del texto (útil en elementos en línea) |
| `line-height` | Establece la **altura de la línea** (espaciado vertical entre líneas) | 

##### 3.5.4.- Propiedades de lista