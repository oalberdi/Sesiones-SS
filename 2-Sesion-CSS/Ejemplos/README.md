# Grid system de Bootstrap 3

El grid de Bootstrap consta de 3 elementos:
1. Un contenedor principal `container`
2. Filas `rows`
3. Columnas `columns`


## 1 - Cómo creamos el contenedor o "container"

El Grid system de Bootstrap necesita un contenedor para mantener filas y columnas. Un contenedor es un simple elemento `<div>` con una clase de `.container`. El contenedor se utiliza para proporcionar una anchura adecuada para el diseño, actuando como un envoltorio para el contenido. El código es el siguiente:

**Fixed layout**
El elemento contenedor envuelve el contenido y establece los márgenes izquierdo y derecho. Tiene anchos fijos en dispositivos de diferentes tamaños, que se muestran en la siguiente tabla:

 Ancho dispositivo | Ancho del container | Media query
-------------------| ------------------- | -----------
Menor que 768px | auto | No tiene, es el "default" de bootstrap
Entre 768px y 991px | 750px | @media (min-width: 768px) and (max-width: 991px) { ... }
Entre 992px y 1199px | 970px | @media (min-width: 992px) and (max-width: 1199px) { ... }
1200px o superior | 1170px | @media (min-width: 1200px) { ... }


*HTML de ejemplo de un contenedor de ancho fijo*

```
<div class="container">
nuestro contenido 
</div>
```

*CSS del `.container`*

```
.container {
padding-right: 15px; /* para impedir que el contenido dentro del elemento toque el borde del navegador */
padding-left: 15px;  /* para impedir que el contenido dentro del elemento toque el borde del navegador */ 
margin-right: auto;  /* para centrar el contenido */
margin-left: auto;   /* para centrar el contenido */
}
```


**Fluid layout**
El elemento contenedor es fluido, no tiene ancho fijo, su ancho será siempre el ancho del dispositivo. 

*Código de ejemplo de un contenedor fluido*

```
<div class="container-fluid">
nuestro contenido 
</div>
```

*CSS del `.container-fluid`*

```
.container-fluid {
padding-right: 15px; /* para impedir que el contenido dentro del elemento toque el borde del navegador */
padding-left: 15px;  /* para impedir que el contenido dentro del elemento toque el borde del navegador */ 
margin-right: auto;  /* para centrar el contenido */
margin-left: auto;   /* para centrar el contenido */
}
```


## 2 - Cómo creamos las filas o "rows"

Una fila actúa como una envoltura alrededor de las columnas. La fila anula el relleno establecido por el contenedor (padding) ,usando un valor de margen negativo de -15px en los lados izquierdo y derecho.

Una fila se extiende desde el borde izquierdo hasta el borde derecho del elemento del contenedor. Se crea agregando la clase `.row` a un elemento de nivel de bloque dentro del contenedor. no hay límites en el número de filas que se pueden crear.

*Código de ejemplo de una fila*

```
<div class="container-fluid">
	<div class="row">
		Nuestro contenido
	</div>
</div>
```

*CSS del `.row`* 

```
.row {
margin-right: -15px; /* Para permitir que la fila toque el borde de su elemento contenedor */
margin-left: -15px; /* Para permitir que la fila toque el borde de su elemento contenedor */
}

/* El margen negativo actúa como una envoltura para mantener las columnas, que pueden sumar hasta 12 en número */
```



## 3 - Cómo creamos las columnas o "columns"

Bootstrap utiliza porcentajes (%) como unidad para definir los anchos de las columnas. Como hemos visto antes, hay 4 categorías diferentes de puntos de interrupción o breakpoints basados en dispositivos. Cada categoría establece clases para columnas de diferentes tamaños.


Prefijo class | Ancho del dispostivo | Denominación
--------------| ---------------------| ---------------
.col-xs-* | Menor que 768px | Extra small (xs)
.col-sm-* | Entre 768px y 991px | Small devices (sm)
.col-md-* | Entre 992px y 1199px | Medium devices (md)
.col-lg-* | 1200px o superior | Large devices (lg)

**Por defecto, todas las columnas no tienen un ancho definido, el valor por defecto es `width: auto`.
Con las media queries, Bootstrap añade el valor de ancho a cada class de columna.**

*CSS de Bootstrap para las clases de columna con asteriscos que reemplazan los tamaños (xs, sm, md y lg):*

```
	.col-*-12 { width: 100%; }
	.col-*-11 { width: 91.66666667%; }
	.col-*-10 { width: 83.33333333%; }
	.col-*-9 { width: 75%; }
	.col-*-8 { width: 66.66666667%; }
	.col-*-7 { width: 58.33333333%; }
	.col-*-6 { width: 50%; }
	.col-*-5 { width: 41.66666667%; }
	.col-*-4 { width: 33.33333333%; }
	.col-*-3 { width: 25%; }
	.col-*-2 { width: 16.66666667%; }
	.col-*-1 { width: 8.33333333%; }

```

Por ejemplo: `.col-lg-6` tendrá un ancho de 50% en dispositivos de 1200px o superior (Large devices), pero cuando se vea en dispositivos "Medium", "Small" o "Extra small" el ancho por defecto es `width:auto` esto hace que las columnas se vean alineadas verticalmente.


## Creando layout más complejos con el Grid System

El anidamiento es una de las maneras de crear diseños o layouts más complejos utilizando el grid system de Bootstrap. 
Hemos comentado antes que para utilizar el grid system de Bootstrap, necesitamos 3 cosas: un contenedor, filas y columnas. 

Asi que Para anidar un sistema de cuadrícula dentro de una columna necesitaremos las mismas tres cosas. Pero la única diferencia es que el contenedor ya está definido. 
En este caso, las columnas se comportarán como los contenedores para el anidado del grid system.

*Funcionamiento:* Los contenedores o `.container` y `.container-fluid` proporcionan 15px de relleno (padding), que se anula por la fila o `.row`. Luego definimos columnas que de nuevo tienen 15px de relleno (padding) en el lado izquierdo y derecho. Entonces, para anidar un grid system dentro de un columna, simplemente necesitamos filas y columnas. 
No hace falta declarar o crear ningún container.

*Código de ejemplo de un grid system anidado*

```
<div class="container">
  <div class="row">
    <div class="col-sm-6">
      <h1>Boostrap Grids Demo</h1>
        <!-- declaramos un row dentro de un col -->
	      <div class="row">
	          <!-- volvemos a declarar columnas -->
		        <div class="col-sm-6">
		          <h2>Nested</h2>
		        </div>
		        <div class="col-sm-6">
		          <h2>Columns</h2>
		        </div>
	      </div>
    </div>
    <div class="col-sm-6">
      <h1>Column 2</h1>
    </div>
  </div><!--/ row principal -->
</div>

```

### ¿Qué pasa si tengo más de 12 columnas?

Un cálculo incorrecto al decifir el número de columnas virtuales, es una de las causas principales que rompen el layout de Bootstrap.

En tal caso, se creará una fila virtual y las columnas no adaptadas se desplazarán a la fila siguiente. Por ejemplo, si se han definido 2 columnas con las clases `.col-md-8` y `.col-md-5`, la segunda columna cambiará a una nueva fila porque requiere 5 columnas virtuales Bootstrap mientras que sólo quedan 4.

### Helper classes

Para ayudarnos en layout complejos o ante ciertas situaciones a la hora de crear el grid,  bootstrap viene con unas classes denominadas "helpers"  que son:

* `.clearfix` : Normalmente utilizado para "limpiar" la propiedad `float`, si añadimos esta clase a cualquier columna hará que se cambie automaticamente a una
nueva fila, para ayudar a corregir los problemas que se producen con alturas de columna irregulares.

* **Offsetting columns** o desplazamiento de columnas : No hay que ocupar las 12 columnas obligatoriamente. Se pueden usar clases de "desplazamiento" como `.col-xs-offset-*` o `.col-md-offset-*` para ocupar un número determinado de columnas "vacías" a la izquierda de cualquier columna.

* Reordenar columnas: Para desplazar columnas a la derecha `push`, para desplazar a la izquierda `pull`.



# Ejemplos del Grid sytem de Bootstrap 3

[Grid de Bootstrap](http://getbootstrap.com/examples/grid/)
