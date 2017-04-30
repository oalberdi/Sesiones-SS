
# Introducción al HTML

Vamos a realizar un pequeño repaso importante para un buen marcado semántico y estructural a la hora de realizar un documento html.

## HTML
Documentos de referencia para:

1. Sintaxis html en detalle [HTML syntax](http://w3c.github.io/html-reference/syntax.html).
2. índice de elementos HTML organizados en grupos de acuerdo con la función [HTML elements organized by function](http://w3c.github.io/html-reference/elements-by-function.html).
3. Elementos agrupados por "Modelos de contenido" comunes [Common content models](http://w3c.github.io/html-reference/common-models.html).
4. Atributos comunes a todos los elementos HTML [Global attributes](http://w3c.github.io/html-reference/global-attributes.html).

## MAQUETACIÓN
Para una correcta maquetación de un website cumpliendo los estándares, es necesario asociar a cada tipo de contenido su correspondiente etiqueta html.

1. Comprender el significado semántico de las etiquetas.
2. Seleccionar el tipo de elemento que va a categorizar nuestro contenido.

### 1. Comprender el significado semántico de las etiquetas

Referencia principal del W3C [The elements of HTML](http://w3c.github.io/html/semantics.html#semantics).

Listado completo de elementos HTML5 [MDN](https://developer.mozilla.org/es/docs/HTML/HTML5/HTML5_lista_elementos)

Sitio online con ejemplos de consulta básicos [htmlreference.io](http://htmlreference.io/):
* Elementos básicos de estructura html [Base Elements](http://htmlreference.io/base/)
* Elementos semánticos dentro del `<body>` [Semantic Elements](http://htmlreference.io/semantic/)



### 2. Seleccionar el tipo de elemento que va a categorizar nuestro contenido

La distinción entre los elementos en bloque y los elementos en línea se utiliza en las especificaciones HTML hasta 4.01. 

#### Elementos en línea (inline) y en bloque (block-level) del HTML

##### Inline 
* Un elemento en línea ocupa sólo el espacio limitado por las etiquetas que definen el elemento en línea.
* Generalmente, los elementos en línea pueden contener sólo datos y otros elementos en línea.
* De forma predeterminada, los elementos en línea no comienzan con nueva línea.


##### block-level

* Un elemento de nivel de bloque ocupa todo el espacio de su elemento padre (contenedor), creando así un "bloque".
* Se usan dentro de un elemento <body>.
* Generalmente, los elementos de nivel de bloque pueden contener elementos en línea y otros elementos de nivel de bloque. Inherente a esta distinción estructural está la idea de que los elementos de bloque crean estructuras "más grandes" que los elementos en línea.


#### Nuevas categorías de contenido en HTML5

En HTML5, esta distinción binaria se sustituye por un conjunto más complejo de categorías de contenido. 
La categoría "nivel de bloque" corresponde aproximadamente a la "categoría de contenido de flujo" en HTML5, mientras que "en línea" corresponde al contenido de texto, pero hay categorías adicionales.

Cada elemento HTML debe respetar las reglas que definen qué tipo de contenido puede tener. Estas reglas se agrupan en modelos de contenido comunes a varios elementos. 
Cada elemento HTML pertenece a cero, uno o varios modelos de contenido, cada uno establece reglas que el contenido del elemento debe seguir en un documento compatible con HTML.

Tipos de contenido "Content Model - Kind of content"
* [Referencia del W3C](http://w3c.github.io/html/dom.html#kinds-of-content)
* [Referencia del WHATWG](https://html.spec.whatwg.org/multipage/dom.html#kinds-of-content)





