
# Introducción al WAI-ARIA y landmark roles

## Principios generales

ARIA significa "Accessible Rich Internet Applications" y su implementación ayuda a que nuestros sites sean más accesibles.
Una de las formas de utilizar ARIA es aplicándolo a nustro código html, además de utilizar las etiquetas semánticas que nos proporciona HTML5.

### ¿Cómo se aplica?

WAI-ARIA asigna **"roles"** a los elementos, y a esos roles les añade **propiedades** o **estados**

*Ejemplo*

```html
  <li role="menuitemcheckbox" aria-checked="true">Sort by Date</li>
```

#### Landmark roles 

* A la estructura lógica de nuestro site, a cada área, le asignamos un landmark "role", que ya están definidos en el la especificacion [WAI-ARIA](https://www.w3.org/TR/wai-aria/). 
* Cada "role" transmite información de la estructura de la página y su información semántica.
* `banner`, `main`, `complementary` y `contentinfo` Deben ser puntos de referencia o "landkmarks" de nivel superior.
* Los roles de referencia o "landmark roles" pueden anidarse para identificar las relaciones padre / hijo de la información que se está presentando.

Algunos de los elementos de sección de html5, crean automaticamente regiones de referencia ARIA, sin necesidad de añadirle "role"

Elemento HTML5 | Landmark Role "por defecto" 
---------------| ------------------------------
aside	| complementary
footer |	contentinfo **en el contexto del elemento `<body>`**
header |	banner **en el contexto del elemento `<body>`**
main |	main
nav |	navigation
section |	region **cuando tiene un nombre accesible usando `aria-labelledby` o `aria-label`**


*Ejemplos*

```html
<div role="contentinfo">
    Este site está realizado por S. Fernández
</div>
```

```html
<div role="alert">
   Por favor actualice su navegador para una mejor experiencia de navegación
</div>
```


####  Añadir etiquetas o `label` a las áreas.

- Si se utiliza más de una vez un "landmark role" específico en nuestro site, debería tener asociado un "label" único.

- El atributo `aria-label` se utiliza para definir una cadena que etiqueta el elemento actual. 

```html
 <button aria-label="Close" onclick="myDialog.close()">X</button>
```

- El atributo `aria-labelledby` contiene los ID de elemento de etiquetas en objetos como inputs, widgets. El atributo establece relaciones entre los objetos y sus etiquetas.

*Ejemplo radio group*

```html
<div id="radio_label">My radio label</div>
<ul role="radiogroup" aria-labelledby="radio_label">
    <li role="radio">Item #1</li>
    <li role="radio">Item #2</li>
    <li role="radio">Item #3</li>
</ul>
```
####  Añadir propiedades y estados para una mejor interacción.

W3C - Listado completo y carácterísticas [Supported States and Properties](https://www.w3.org/TR/wai-aria/states_and_properties)

*Algunos ejemplos de estructuras del W3C con role, propiedades y estado*

* [Sendero de migas](https://www.w3.org/TR/wai-aria-practices/examples/breadcrumb/index.html)
* [Tabs](https://www.w3.org/TR/wai-aria-practices/examples/tabs/tabs.html)















