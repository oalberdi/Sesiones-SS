
# Introducción al CSS

Vamos a realizar un pequeño repaso importante para entender la base del CSS

## CSS
Documentos de referencia para:

1. W3C Cascading Style Sheets home page [CSS Overview](https://www.w3.org/Style/CSS/Overview.en.html).
2. W3C Cascading Style Sheets articles and tutorials [CSS Learn & Use](https://www.w3.org/Style/CSS/learning).
3. [MDN Referencia CSS](https://developer.mozilla.org/es/docs/Web/CSS/Referencia_CSS).
4. [w3schools Referencia CSS](https://www.w3schools.com/cssref/default.asp).


### Sintaxis

Regla de estilo: selector { propiedad: valor;}

* Selectores CSS [MDN CSS Selectors](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Selectors)
* Propiedades CSS [w3schools CSS Properties](http://htmlreference.io/semantic/)

### Herencia y Cascada
Hay dos mecanismos que intervienen en el aspecto final de un elemento, la herencia y la cascada. 



#### Herencia
Todos los elementos de un documento HTML heredan todas las propiedades heredables de su padre excepto el elemento raíz 'html' (que no tiene progenitor)

La importancia de este hecho es que cada elemento hereda las propiedades del elemento que lo contiene (llamado el elemento padre). Quiere decir que si especificamos la propiedad color: red para `<body>`, todos los elementos de la página heredarán esta característica y no será necesario especificar nuevamente la propiedad color en cada uno de ellos.


#### Cascada

¿qué ocurre si dos reglas diferentes asignan la misma propiedad al mismo elemento?  
La cascada responde a esa pregunta, con los siguientes conceptos que controlan el orden en el que se aplican las declaraciones de CSS:

El algoritmo en cascada determina cómo encontrar el valor a aplicar para cada propiedad para cada elemento de documento.

1.- Primero filtra todas las reglas de las diferentes fuentes para mantener sólo las reglas que se aplican a un elemento dado. Esto significa reglas cuyo selector coincide con el elemento dado y que forman parte de una regla apropiada de medios.

2.-Luego ordena estas reglas de acuerdo con su importancia, es decir, si son o no seguidas por `!important` y por su origen. La cascada está en orden ascendente, lo que significa que los valores `!important` de una hoja de estilo definida por el usuario tienen precedencia sobre los valores normales originados de una hoja de estilos de agente de usuario:

 Orden | Origen | Importancia
-------| -------| -------------
1 | user agent (navegador) | normal
2 | user (usuario) | normal
3 | author  | normal
4 | author | !important 
5 | user | !important 
6 | user agent | !important

3. - En caso de igualdad, se considera que la especificidad de un valor elige uno u otro.

### Selectores y especificidad

Especificidad es el medio por el que el navegador decide qué valores de una propiedad de CSS es más relevante para un elemento y, por lo tanto, será aplicado. Se basa en en las reglas de concordancia que siguen los diferentes tipos de Selectores CSS.

La siguiente lista de selectores se incrementa en función de la especificidad.

0. - Selectores de título (p.e., h1) y pseudo-elementos (p.e., :before).
1. - Selectores de clase (p.e., .user), selectores de atributos (p.e., [type="radio"]) y pseudo-clases (p.e., :hover).
2. - Selectores de ID (p.e., #user).

El selectore Universal (*), combinadores (+, >, ~, ' ') y la pseudo-clase negación (`:not()`) no tienen efectos sobre la especificidad. (Sin embargo, los selectores declarados dentro de :not() si lo tienen.)

Los estilos inline añadidos a un elemento (p.e., `style="font-weight:bold"`) siempre sustituyen a cualquier estilo escrito en hojas de estilo externas, por lo que se puede pensar que tienen la mayor especificidad.

Sobre el uso del !important

1.- Cuando aplicamos la regla `!important` rompemos la "cascada" natural de las hojas de estilo.
2.- Cuando se aplican dos declaraciones en conflicto con la regla `!important` al mismo elemento, se aplicará la declaración con mayor especificidad.







