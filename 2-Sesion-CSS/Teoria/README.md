
# Introducción al CSS

Vamos a realizar un pequeño repaso importante para entender la base del CSS

Documentos de referencia

1. W3C Cascading Style Sheets home page [CSS Overview](https://www.w3.org/Style/CSS/Overview.en.html).
2. W3C Cascading Style Sheets articles and tutorials [CSS Learn & Use](https://www.w3.org/Style/CSS/learning).
3. [MDN Referencia CSS](https://developer.mozilla.org/es/docs/Web/CSS/Referencia_CSS).
4. [w3schools Referencia CSS](https://www.w3schools.com/cssref/default.asp).


## Sintaxis

Regla de estilo: selector { propiedad: valor;}

* Selectores CSS [MDN CSS Selectors](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Selectors)
* Propiedades CSS [w3schools CSS Properties](http://htmlreference.io/semantic/)

Hay dos mecanismos que intervienen en el aspecto final de un elemento, la **herencia** y la **cascada**. 

## Herencia

Todos los elementos de un documento HTML heredan todas las propiedades heredables de su padre excepto el elemento raíz `html` (que no tiene progenitor)

La importancia de este hecho es que cada elemento hereda las propiedades del elemento que lo contiene (llamado el elemento padre). Quiere decir que si especificamos la propiedad `color: red` para `<body>`, todos los elementos de la página heredarán esta característica y no será necesario especificar nuevamente la propiedad color en cada uno de ellos.


## Cascada

¿Qué ocurre si dos reglas diferentes asignan la misma propiedad al mismo elemento?  
La cascada responde a esa pregunta, con los siguientes conceptos que controlan el orden en el que se aplican las declaraciones de CSS.

El algoritmo en cascada determina cómo encontrar el valor a aplicar para cada propiedad para cada elemento de documento.

### 1 - Orden de las fuentes
Primero filtra todas las reglas de las diferentes fuentes para mantener sólo las reglas que se aplican a un elemento dado. Esto significa reglas cuyo selector coincide con el elemento dado y que forman parte de una regla apropiada de medios.


### 2 - Importancia 
Luego ordena estas reglas de acuerdo con su importancia, es decir, si son o no seguidas por `!important` y por su origen. La cascada está en orden ascendente, lo que significa que los valores `!important` de una hoja de estilo definida por el usuario tienen precedencia sobre los valores normales originados de una hoja de estilos de agente de usuario:

 Orden | Origen | Importancia
-------| -------| -------------
1 | user agent (navegador) | normal
2 | user (usuario) | normal
3 | author  | normal
4 | author | !important 
5 | user | !important 
6 | user agent | !important

### 3 - Especificidad
En caso de igualdad, se considera que la especificidad de un valor elige uno u otro.

#### Selectores y especificidad

Especificidad es el medio por el que el navegador decide qué valores de una propiedad de CSS es más relevante para un elemento y, por lo tanto, será aplicado. Se basa en en las reglas de concordancia que siguen los diferentes tipos de Selectores CSS.

La siguiente lista de selectores se incrementa en función de la especificidad.

0.  Selectores de título (p.e., h1) y pseudo-elementos (p.e., :before).
1.  Selectores de clase (p.e., .user), selectores de atributos (p.e., [type="radio"]) y pseudo-clases (p.e., :hover).
2.  Selectores de ID (p.e., #user).

El selector Universal (*), combinadores (+, >, ~, ' ') y la pseudo-clase negación (`:not()`) no tienen efectos sobre la especificidad. (Sin embargo, los selectores declarados dentro de :not() si lo tienen.)

Los estilos inline añadidos a un elemento (p.e., `style="font-weight:bold"`) siempre sustituyen a cualquier estilo escrito en hojas de estilo externas, por lo que se puede pensar que tienen la mayor especificidad.

Sobre el uso del `!important` [Guía MDN](https://developer.mozilla.org/es/docs/Web/CSS/Especificidad#La_excepción_!important)

*  Cuando aplicamos la regla `!important` rompemos la "cascada" natural de las hojas de estilo.
*  Cuando se aplican dos declaraciones en conflicto con la regla `!important` al mismo elemento, se aplicará la declaración con mayor especificidad.
*  Busca siempre una manera de emplear la especificidad antes de considerar el uso de !important.




# Evolución del CSS

Frameworks y arquitectura CSS, Convenciones de nombrado "naming", Preprocesadores, Pattern libraries, Design systems, Performance, Legacy, Hacks... y mucho más.


# Grid Systems 

Para una mejor estructura responsive de los sites, se utiliza un grid system.
El grid o retícula, es una herramienta que se he utiliza en diseño gráfico y que se ha heredado en el diseño digital. Consiste en líneas horizontales y verticales que dividen el espacio y forman un grid o retícula. Esta retícula o grid, es una herramienta que facilita el diseño del layout. El layout o la composición, es la disposicion de lo elementos en ese espacio.

Lo interesante es crear tu propio grid system para tus proyectos y reutilizarlo a través tus proyectos.

## Cómo aplicamos un grid a nuestro site

Como hemos comentado antes y aplicando el grid a nuestro site, podemos resumir que el grid consiste en una serie de filas y columnas. 
¿Cúantas filas y columnas necesito para mi site? El número de filas es más claro, tantas como sea necesario para encajar por ejemplo: cabecera, menú, contenido y pie de página. 

¿Y las columnas? Hay diferentes opiniones respecto a las columnas pero normalmente todas se basan en un número par, porque esto hace más sencillo dividir la página. Los números divisibles por tres son los más usados, [artículo que explica el por qúe](https://en.wikipedia.org/wiki/Golden_ratio). Los valores de columan más populares son 12, 16, 24.
A su vez, el 12-column grid system es el más popular porque se puede dividir en una variedad de tamaños de uso cómún como la mitad, un tercio y un cuarto. 

El grid lo creamos en nuestro css, definiendo el número de columnas que queramos que nuestros elementos abarquen.

Las soluciones CSS más actuales para crear estos tipos layout son Flexbox y CSS Grid Layout.

Flexbox o [The CSS Flexible Box Layout Module](https://www.w3.org/TR/css-flexbox-1/), Es una parte reciente de la especificación CSS y ya goza de buen soporte de navegador. 
Fue diseñado para proporcionar una solución más moderna para este tipo de layouts basados en grid, ofreciéndo funcionalidades específicas para la tarea.
Utilizar Flexbox para nuestros componentes de página simplificará drásticamente nuestra estructura HTML y clases de CSS.


Complementario a flexbox es el [CSS Grid Layout Module](https://www.w3.org/TR/css3-grid-layout/), que ayuda a definir y establecer las regiones de una página. 
En el pasado, la principal solución para crear estructuras de sites "flexibles" era utilizar tablas para definir áreas de página con filas y columnas, pero éstas resultaban ser terribles para la accesibilidad. El "diseño de la retícula" o Grid Layout es algo así como una interpretación moderna de ese concepto.


También podemos encontrar soluciones ya hechas, creadas por otros diseñadores y desarrolladores en Frameworks como **Bootstrap** y **Foundation** entre otros.
La valoración de uso entre uno u otro es saber cual ofrece mejore soluciones para el tipo de proyecto que se quiera realizar, ya que este tipo de frameworks no solo ofrecen soluciones de "responsive grid", sino que mucho vienen con elementos como fuentes, iconos y widgets reutilizables.

Vamos a ver el grid de Bootstrap 3 con ejemplos.



