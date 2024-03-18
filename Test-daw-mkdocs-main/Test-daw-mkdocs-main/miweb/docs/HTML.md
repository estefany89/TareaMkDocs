# Capítulo 1. Introducción



## ¿Qué es HTML?

Definiéndolo de forma sencilla, "HTML es lo que se utiliza para crear todas las páginas web de Internet". Más concretamente, HTML es el lenguaje con el que se "escriben" la mayoría de páginas web.

Los diseñadores utilizan el lenguaje HTML para crear sus páginas web, los programas que utilizan los diseñadores generan páginas escritas en HTML y los navegadores que utilizamos los usuarios muestran las páginas web después de leer su contenido HTML.

Aunque HTML es un lenguaje que utilizan los ordenadores y los programas de diseño, es muy fácil de aprender y escribir por parte de las personas. En realidad, HTML son las siglas de HyperText Markup Language y más adelante se verá el significado de cada una de estas palabras.

- ## HTML y XHTML

El lenguaje XHTML es muy similar al lenguaje HTML. De hecho, XHTML no es más que una adaptación de HTML al lenguaje XML. Técnicamente, HTML  es descendiente directo del lenguaje SGML, mientras que XHTML lo es del  XML (que a su vez, también es descendiente de SGML).

![Esquema de la evolución de HTML y XHTML](https://uniwebsidad.com/static/libros/imagenes/xhtml/esquema_evolucion_html_xhtml.gif)

**Figura 1.1** Esquema de la evolución de HTML y XHTML

Las páginas y documentos creados con XHTML son muy similares a las  páginas y documentos HTML. Las discusiones sobre si HTML es mejor que  XHTML o viceversa son recurrentes en el ámbito de la creación de  contenidos web, aunque no existe una conclusión ampliamente aceptada.

Actualmente, entre HTML 4.01 y XHTML 1.0, la mayoría de diseñadores  escogen XHTML. En un futuro cercano, si los diseñadores deben elegir  entre HTML 5 y XHTML 1.1 o XHTML 2.0, quizás la elección sea diferente.

------

- ## HTML y CSS

Originalmente, las páginas HTML sólo incluían información sobre sus  contenidos de texto e imagenes. Con el desarrollo del estándar HTML, las páginas empezaron a incluir también información sobre el aspecto de sus contenidos: tipos de letra, colores y márgenes.

La posterior aparición de tecnologías como JavaScript, provocaron que las páginas HTML también incluyeran el código de las aplicaciones  (llamadas *scripts*) que se utilizan para crear páginas web dinámicas.

Incluir en una misma página HTML los contenidos, el diseño y la  programación complica en exceso su mantenimiento. Normalmente, los  contenidos y el diseño de la página web son responsabilidad de  diferentes personas, por lo que es conveniente separarlos.

CSS es el mecanismo que permite separar los contenidos definidos  mediante XHTML y el aspecto que deben presentar esos contenidos:

![Esquema de la separación de los contenidos y su presentación](https://uniwebsidad.com/static/libros/imagenes/xhtml/separacion_contenidos_presentacion.gif)

**Figura 1.2** Esquema de la separación de los contenidos y su presentación

Una ventaja añadida de la separación de los contenidos y su  presentación es que los documentos XHTML creados son más flexibles, ya  que se adaptan mejor a las diferentes plataformas: pantallas de  ordenador, pantallas de dispositivos móviles, impresoras y dispositivos  utilizados por personas discapacitadas.

De esta forma, utilizando exclusivamente XHTML se crean páginas web *"feas"* pero correctas. Aplicando CSS, se pueden crear páginas *"bonitas"* a partir de las páginas XHTML correctas.





# Capítulo 2. Texto

La mayor parte del contenido de las páginas HTML habituales está  formado por texto, llegando a ser más del 90% del código de la página.  Por este motivo, es muy importante conocer los elementos y etiquetas que define HTML para el manejo del texto.

El lenguaje HTML incorpora al tratamiento del texto muchas de las  ideas y normas establecidas en otros entornos de publicación de  contenidos. De esta forma, HTML define etiquetas para **estructurar** el contenido en secciones y párrafos y define otras etiquetas para **marcar** elementos importantes dentro del texto.

La tarea inicial del editor de contenidos HTML consiste en  estructurar el texto original definiendo sus párrafos, titulares y  títulos de sección, como se muestra en la siguiente imagen:

![Resultado de estructurar un texto sencillo](https://uniwebsidad.com/static/libros/imagenes/xhtml/f0301.gif)

**Figura 3.1** Resultado de estructurar un texto sencillo



# Capítulo 3. Enlaces

El lenguaje de marcado HTML se definió teniendo en cuenta algunas de  las características que existían en ese momento para la publicación  digital de contenidos. Entre los conceptos utilizados en su creación, se encuentra el mecanismo de *"hipertexto"*.

De hecho, las letras "HT" de la sigla HTML significan *"hipertexto"* (*hypertext* en inglés), por lo que el significado completo de HTML podría traducirse como "lenguaje de marcado para hipertexto".

La incorporación del *hipertexto* fue una de las claves del  éxito del lenguaje HTML, ya que permitió crear documentos interactivos  que proporcionan información adicional cuando se solicita. El elemento  principal del hipertexto es el *"hiperenlace"*, también llamado "enlace web" o simplemente "enlace".

Los enlaces se utilizan para establecer relaciones entre dos  recursos. Aunque la mayoría de enlaces relacionan páginas web, también  es posible enlazar otros recursos como imágenes, documentos y archivos.

Una característica que no se suele tener en cuenta en los enlaces es  que están formados por dos extremos y un sentido. En otras palabras, el  enlace comienza en un recurso y apunta hacia otro recurso. Cada uno de  los dos extremos se llaman *"anchors"* en inglés, que se puede traducir literalmente como "anclas".



# Capítulo 4. Listas

En ocasiones, es posible agrupar determinadas palabras o frases en un conjunto de elementos que tienen más significado de forma conjunta. El  menú de navegación de un sitio web por ejemplo está formado por un grupo de palabras. Aunque cada palabra por separado tiene sentido, de forma  conjunta constituyen el menú de navegación de la página, por lo que su  significado conjunto es mayor que por separado.

El lenguaje HTML define tres tipos diferentes de listas para agrupar  los elementos: listas no ordenadas (se trata de una colección simple de  elementos en la que no importa su orden), listas ordenadas (similar a la anterior, pero los elementos están numerados y por tanto, importa su  orden) y listas de definición (un conjunto de términos y definiciones  similar a un diccionario).





# Capítulo 5. Imágenes 

Las imágenes son uno de los elementos más importantes de las páginas  web. De hecho, prácticamente todas las páginas web contienen alguna  imagen y la mayoría incluyen decenas de imágenes. Dentro de las imágenes que se pueden incluir en una página HTML se deben distinguir dos tipos: las imágenes de contenido y las imágenes *de adorno*.

Las imágenes de contenido son las que proporcionan información y complementan la información textual. Las imágenes *de adorno* son las que se utilizan para hacer bordes redondeados, para mostrar  pequeños iconos en las listas de elementos, para mostrar fondos de  página, etc. Las imágenes de contenido se incluyen directamente en el  código HTML mediante la etiqueta `<img>` y las imágenes de adorno no se deberían incluir en el código HTML, sino que deberían  emplearse hojas de estilos CSS para mostrarlas.

A continuación se muestra la definición de la etiqueta `<img>`, utilizada para incluir las imágenes en las páginas HTML:

| Etiqueta          | **<img>**                                                    |
| ----------------- | ------------------------------------------------------------ |
| Atributos comunes | [básicos](https://uniwebsidad.com/libros/xhtml/capitulo-2/etiquetas_y_atributos#atributos_basicos), [internacionalización](https://uniwebsidad.com/libros/xhtml/capitulo-2/etiquetas-y-atributos#atributos-para-internacionalizacion) y [eventos](https://uniwebsidad.com/libros/xhtml/capitulo-2/etiquetas-y-atributos#atributos-de-eventos) |
| Atributos propios | `src = "url"` - Indica la URL de la imagen que se muestra`alt = "texto"` - Descripción corta de la imagen`longdesc = "url"` - Indica una URL en la que puede encontrarse una descripción más detallada de la imagen`name = "texto"` - Nombre del elemento imagen`height = "unidad_de_medida"` - Indica la altura con la que se debe mostrar la imagen (no es obligatorio que coincida con la altura original de la imagen)`width = "unidad_de_medida"` - Indica la anchura con la que se debe mostrar la imagen (no es obligatorio que coincida con la anchura original de la imagen) |
| Tipo de elemento  | En línea y etiqueta vacía                                    |
| Descripción       | Se emplea para incluir imágenes en los documentos            |

Los dos atributos requeridos son `src` y `alt`. El atributo `src` es similar al atributo `href` de los enlaces, ya que establece la URL de la imagen que se va a  mostrar en la página. Las URL indicadas pueden ser absolutas o  relativas. El atributo `alt` permite describir el contenido  de la imagen mediante un texto breve. Las descripciones deben tener una  longitud inferior a 1024 caracteres y son útiles para las personas y  dispositivos discapacitados que no pueden acceder a las imágenes.

Ejemplo sencillo para incluir una imagen:

```
<img src="logotipo.gif" alt="Logotipo de Mi Sitio" />
```

Como `<img>` es una etiqueta vacía, no tiene  etiqueta de cierre. No obstante, para que la página XHTML sea válida,  todas las etiquetas deben estar cerradas. Como ya se explicó  anteriormente, para cerrar una etiqueta vacía se incluyen los caracteres `/>` al final de la etiqueta.



# Capítulo 6. Tablas

Desde sus primeras versiones, HTML incluyó el soporte para crear  tablas de datos en las páginas web. Además de ser sencillo, el modelo  definido por HTML es muy flexible y bastante completo.

Las tablas en HTML utilizan los mismos conceptos de filas, columnas,  cabeceras y títulos que los que se utilizan en cualquier otro entorno de publicación de documentos:

![Partes que componen una tabla compleja](https://uniwebsidad.com/static/libros/imagenes/xhtml/f0701.gif)

**Figura 7.1** Partes que componen una tabla compleja

Las tablas de HTML puede contener elementos simples, agrupaciones de  filas y de columnas, cabeceras y pies de tabla, subdivisiones, cabeceras múltiples y otros elementos complejos.

A pesar de que las tablas HTML son fáciles de comprender y utilizar,  son uno de los elementos más polémicos de HTML. El problema de las  tablas es que no siempre se utilizan adecuadamente. Aunque parezca  obvio, las tablas se deben utilizar para mostrar información tabular.



Hasta hace unos años, las tablas también se utilizaban para definir  la estructura de las páginas web. La cabecera de la página era una fila  de una gran tabla, el pie de página era otra fila de esta tabla y la  zona de contenidos estaba formada por varias columnas dentro de esa gran tabla.

Aunque algunos malos diseñadores siguen utilizando hoy en día las  tablas para definir la estructura completa de las páginas web, se trata  de una técnica obsoleta y nada recomendable. El motivo es que se  complica en exceso el código HTML y su mantenimiento es muy complejo. La solución correcta para definir la estructura de las páginas consiste en la utilización de hojas de estilos CSS.

------