# Capítulo 1. Introducción

## ¿Qué es CSS?

CSS es un lenguaje de hojas de estilos creado para controlar el  aspecto o presentación de los documentos electrónicos definidos con HTML y XHTML. CSS es la mejor forma de separar los contenidos y su  presentación y es imprescindible para crear páginas web complejas.

Separar la definición de los contenidos y la definición de su aspecto presenta numerosas ventajas, ya que obliga a crear documentos  HTML/XHTML bien definidos y con significado completo (también llamados *"documentos semánticos"*). Además, mejora la accesibilidad del documento, reduce la complejidad de su mantenimiento y permite visualizar el mismo documento en infinidad  de dispositivos diferentes.

Al crear una página web, se utiliza en primer lugar el lenguaje HTML/XHTML para *marcar* los contenidos, es decir, para designar la función de cada elemento  dentro de la página: párrafo, titular, texto destacado, tabla, lista de  elementos, etc.

Una vez creados los contenidos, se utiliza el lenguaje CSS para  definir el aspecto de cada elemento: color, tamaño y tipo de letra del  texto, separación horizontal y vertical entre elementos, posición de  cada elemento dentro de la página, etc.



### Funcionamiento básico de CSS

Antes de que se generalizara el uso de CSS, los diseñadores de  páginas web utilizaban etiquetas HTML especiales para modificar el  aspecto de los elementos de la página. El siguiente ejemplo muestra una  página HTML con estilos definidos sin utilizar CSS:

```
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN"
  "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">
<html xmlns="http://www.w3.org/1999/xhtml">
<head>
  <meta http-equiv="Content-Type" content="text/html; charset=iso-8859-1" />
  <title>Ejemplo de estilos sin CSS</title>
</head>

<body>
  <h1><font color="red" face="Arial" size="5">Titular de la página</font></h1>
  <p><font color="gray" face="Verdana" size="2">Un párrafo de texto no muy largo.</font></p>
</body>
</html>
```

```
!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN"
  "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">
<html xmlns="http://www.w3.org/1999/xhtml">
<head>
<meta http-equiv="Content-Type" content="text/html; charset=iso-8859-1" />
<title>Ejemplo de estilos con CSS</title>
<style type="text/css">
  h1 { color: red;  font-family: Arial;   font-size: large;  }
  p  { color: gray; font-family: Verdana; font-size: medium; }
</style>
</head>

<body>
  <h1>Titular de la página</h1>
  <p>Un párrafo de texto no muy largo.</p>
</body>
</html>
```

CSS permite separar los contenidos de la página y la información  sobre su aspecto. En el ejemplo anterior, dentro de la propia página  HTML se crea una zona especial en la que se incluye toda la información  relacionada con los estilos de la página.



### Incluir CSS en el mismo documento HTML

Los estilos se definen en una zona específica del propio documento HTML. Se emplea la etiqueta `<style>` de HTML y solamente se pueden incluir en la cabecera del documento (sólo dentro de la sección `<head>`).

Ejemplo:

```
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN"
  "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">
<html xmlns="http://www.w3.org/1999/xhtml">
<head>
<meta http-equiv="Content-Type" content="text/html; charset=iso-8859-1" />
<title>Ejemplo de estilos CSS en el propio documento</title>
<style type="text/css">
  p { color: black; font-family: Verdana; }
</style>
</head>

<body>
<p>Un párrafo de texto.</p>
</body>
</html>
```

Este método se emplea cuando se define un número pequeño de estilos o cuando se quieren incluir estilos específicos en una determinada página HTML que completen los estilos que se incluyen por defecto en todas las páginas del sitio web.



### Glosario básico

CSS define una serie de términos que permiten describir cada una de  las partes que componen los estilos CSS. El siguiente esquema muestra  las partes que forman un estilo CSS muy básico:

![Componentes de un estilo CSS básico](https://uniwebsidad.com/static/libros/imagenes/css/f0101.gif)

**Figura 1.1** Componentes de un estilo CSS básico

Los diferentes términos se definen a continuación:

- Regla: cada uno de los estilos que componen una hoja de estilos CSS. Cada regla está compuesta de una parte de *"selectores"*, un símbolo de *"llave de apertura"* (`{`), otra parte denominada *"declaración"* y por último, un símbolo de *"llave de cierre"* (`}`).
- Selector: indica el elemento o elementos HTML a los que se aplica la regla CSS.
- Declaración: especifica los estilos que se aplican a los elementos. Está compuesta por una o más propiedades CSS.
- Propiedad: característica que se modifica en el elemento  seleccionado, como por ejemplo su tamaño de letra, su color de fondo,  etc.
- Valor: establece el nuevo valor de la característica modificada en el elemento.

Un archivo CSS puede contener un número ilimitado de reglas CSS, cada regla se puede aplicar a varios selectores diferentes y cada  declaración puede incluir tantos pares propiedad/valor como se desee.

El estándar CSS 2.1 define 115 propiedades, cada una con su propia  lista de valores permitidos. Por su parte, los últimos borradores del  estándar CSS 3 ya incluyen 239 propiedades.



# Capítulo 2. Selectores

Para crear diseños web profesionales, es imprescindible conocer y  dominar los selectores de CSS. Como se vio en el capítulo anterior, una  regla de CSS está formada por una parte llamada "selector" y otra parte  llamada "declaración".

La declaración indica *"qué hay que hacer"* y el selector indica *"a quién hay que hacérselo"*. Por lo tanto, los selectores son imprescindibles para aplicar de forma correcta los estilos CSS en una página.

A un mismo elemento HTML se le pueden aplicar varias reglas CSS y  cada regla CSS puede aplicarse a un número ilimitado de elementos. En  otras palabras, una misma regla puede aplicarse sobre varios selectores y un mismo selector se puede utilizar en varias reglas.

El estándar de CSS 2.1 incluye una docena de tipos diferentes de  selectores, que permiten seleccionar de forma muy precisa elementos  individuales o conjuntos de elementos dentro de una página web.

No obstante, la mayoría de páginas de los sitios web se pueden diseñar utilizando solamente los cinco selectores básicos.



# Capítulo 3. Modelo de cajas

El modelo de cajas o *"box model"* es seguramente la  característica más importante del lenguaje de hojas de estilos CSS, ya  que condiciona el diseño de todas las páginas web. El modelo de cajas es el comportamiento de CSS que hace que todos los elementos de las  páginas se representen mediante cajas rectangulares.

Las cajas de una página se crean automáticamente. Cada vez que se  inserta una etiqueta HTML, se crea una nueva caja rectangular que  encierra los contenidos de ese elemento. La siguiente imagen muestra las tres cajas rectangulares que crean las tres etiquetas HTML que incluye  la página:

![Las cajas se crean automáticamente al definir cada elemento HTML](https://uniwebsidad.com/static/libros/imagenes/css/f0402.gif)

**Figura 4.1** Las cajas se crean automáticamente al definir cada elemento HTML

Las cajas de las páginas no son visibles a simple vista porque  inicialmente no muestran ningún color de fondo ni ningún borde. La  siguiente imagen muestra las cajas que forman la página web de  http://www.alistapart.com/ después de forzar a que todas las cajas  muestren su borde:

![Cajas que forman la página alistapart.com](https://uniwebsidad.com/static/libros/imagenes/css/f0401.gif)

**Figura 4.2** Cajas que forman la página alistapart.com





# Capítulo 4. Posicionamiento y visualización

Cuando los navegadores descargan el contenido HTML y CSS de las  páginas web, aplican un procesamiento muy complejo antes de mostrar las  páginas en la pantalla del usuario.

Para cumplir con el modelo de cajas presentado en el capítulo  anterior, los navegadores crean una caja para representar a cada  elemento de la página HTML. Los factores que se tienen en cuenta para  generar cada caja son:

- Las propiedades `width` y `height` de la caja (si están establecidas).
- El tipo de cada elemento HTML (elemento de bloque o elemento en línea).
- Posicionamiento de la caja (normal, relativo, absoluto, fijo o flotante).
- Las relaciones entre elementos (dónde se encuentra cada elemento, elementos descendientes, etc.)
- Otro tipo de información, como por ejemplo el tamaño de las imágenes y el tamaño de la ventana del navegador.

En este capítulo se muestran los cinco tipos de posicionamientos  definidos para las cajas y se presentan otras propiedades que afectan a  la forma en la que se visualizan las cajas.





# Capítulo 5. Imágenes

###### Establecer la anchura y altura de las imágenes

Utilizando las propiedades `width` y `height`, es posible mostrar las imágenes con cualquier altura/anchura, independientemente de su altura/anchura real:

```
#destacada {
  width: 120px;
  height: 250px;
}

<img id="destacada" src="imagen.png" />
```

No obstante, si se utilizan alturas/anchuras diferentes de las  reales, el navegador deforma las imágenes y el resultado estético es muy desagradable.





# Capítulo 6. Tablas

######  Estilos básicos

Cuando se aplican bordes a las celdas de una tabla, el aspecto por  defecto con el que se muestra en un navegador es el siguiente:

![Aspecto por defecto de los bordes de una tabla](https://uniwebsidad.com/static/libros/imagenes/css/f1001.gif)

**Figura 10.1** Aspecto por defecto de los bordes de una tabla

El código HTML y CSS del ejemplo anterior se muestra a continuación:

```
.normal {
  width: 250px;
  border: 1px solid #000;
}
.normal th, .normal td {
  border: 1px solid #000;
}

<table class="normal" summary="Tabla genérica">
  <tr>
    <th scope="col">A</th>
    <th scope="col">B</th>
    <th scope="col">C</th>
    <th scope="col">D</th>
    <th scope="col">E</th>
  </tr>
  ...
</table>
```

------

# Capítulo 7. Layout

El diseño de las páginas web habituales se divide en bloques:  cabecera, menú, contenidos y pie de página. Visualmente, los bloques se  disponen en varias filas y columnas. Por este motivo, hace varios años  la estructura de las páginas HTML se definía mediante tablas.

El desarrollo de CSS ha permitido que se puedan realizar los mismos  diseños sin utilizar tablas HTML. Las principales ventajas de diseñar la estructura de las páginas web con CSS en vez de con tablas HTML son las siguientes:

- **Mantenimiento**: una página diseñada exclusivamente  con CSS es mucho más fácil de mantener que una página diseñada con  tablas. Cambiar el aspecto de una página creada con CSS es tan fácil  como modificar unas pocas reglas en las hojas de estilos. Sin embargo,  realizar la misma modificación en una página creada con tablas supone un esfuerzo muy superior y es más probable cometer errores.
- **Accesibilidad**: las páginas creadas con CSS son más  accesibles que las páginas diseñadas con tablas. De hecho, los  navegadores que utilizan las personas discapacitadas (en especial las  personas invidentes) pueden tener dificultades con la estructura de las  páginas complejas creadas con tablas HTML. No obstante, diseñar una  página web exclusivamente con CSS no garantiza que la página sea  accesible.
- **Velocidad de carga**: el código HTML de una página  diseñada con tablas es mucho mayor que el código de la misma página  diseñada exclusivamente con CSS, por lo que tarda más tiempo en  descargarse. En cualquier caso, si el usuario accede al sitio con una  conexión de banda ancha y la página es de un tamaño medio o reducido,  las diferencias son casi imperceptibles.
- **Semántica**: aunque resulta obvio, las tablas HTML  sólo se deben utilizar para mostrar datos cuya información sólo se  entiende en forma de filas y columnas. Utilizar tablas para crear la  estructura completa de una página es tan absurdo como utilizar por  ejemplo la etiqueta `<ul>` para crear párrafos de texto.

Por estos motivos, la estructura basada en tablas ha dado paso a la  estructura basada exclusivamente en CSS. Aunque crear la estructura de  las páginas sólo con CSS presenta en ocasiones retos importantes, en  general es más sencilla y flexible.

En este capítulo se muestra cómo crear algunas de las estructuras o *layouts* más habituales de los diseños web utilizando exclusivamente CSS.