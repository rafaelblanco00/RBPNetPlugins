# RBP Small Help

<code>SmallHelp</code> es un plugin que te permitirá mostrar, de una forma diferente, los textos de ayuda que pueden ser asociados a controles de formularios en <code>Bootstrap</code>. En el siguiente aparte podrás ver como lucen los textos de ayuda ([help texts](https://getbootstrap.com/docs/4.5/components/forms/?#help-text)) agregados por defecto en <code>Bootstrap</code> y su contraste con respecto al resultado despues de aplicar nuestro plugin.

## ¿Como funciona?

?> <b>Nota:</b> Para poder utilizar nuestro <code>smallHelp</code> es necesario que te remitas al aparte [instalación inicial](primeros_pasos.md), de esta forma podrás contar con todos los requerimientos iniciales para el uso correcto del mismo.

<img src="_media/small-help/small-help-comparacion.png"/>

Como se puede notar, <code>SmallHelp</code> oculta el texto de ayuda para evitar generar ruido visual cuando estos son utilizados en controles de formulario, de esta forma, <code>SmallHelp</code> agrega un botón de ayuda inmediatamente después de la etiqueta del control de formulario y le permite al usuario visualizar estos <code> textos de ayuda </code> cuando lo deseé. Su comportamiento de este es el mismo ofrecido por <code>Bootstraps Help Texts</code>, sin embargo, al activar el plugin se puede agregar un título que permite contextualizar a quienes interactúen con estos controles de formularios.

## ¿Cómo utilizarlo?

Para utilizar nuestro <code>SmallHelp</code> necesitas de una plantilla, que utiliza la misma metodología propuesta por <code>Bootstrap</code>, como se muestra a continuación.

````html
<label for="inputPassword5">Password</label>
<input type="password" id="inputPassword5" class="form-control" aria-describedby="passwordHelpBlock">
<small id="passwordHelpBlock" class="form-text text-muted">
  Your password must be 8-20 characters long, contain letters and numbers, and must not contain spaces, special characters, or emoji.
</small>
````

?> Para que funcione correctamente, la plantilla debe estar envuelta en un formulario al que debes nombrar con el atributo <code>name</code> como se muestra continuación.

````html
<form name="formulario-1">
    <label for="inputPassword5">Password</label>
    <input type="password" id="inputPassword5" class="form-control" aria-describedby="passwordHelpBlock">
    <small id="passwordHelpBlock" class="form-text text-muted">
        Your password must be 8-20 characters long, contain letters and numbers, and must not contain spaces, special characters, or emoji.
    </small>
</form>
````

?> Para finalizar y no menos importante, debes agregar el atributo de control <code>data-rbp-small-help</code> a la etiqueta <code>small</code> de la plantilla.

````html
<form name="formulario-1">
    <label for="inputPassword5">Password</label>
    <input type="password" id="inputPassword5" class="form-control" aria-describedby="passwordHelpBlock">
    <small id="passwordHelpBlock" class="form-text text-muted" data-rbp-small-help="__SMALL_HELP_INDICE__">
        Your password must be 8-20 characters long, contain letters and numbers, and must not contain spaces, special characters, or emoji.
    </small>
</form>
````

!> Tenga en cuenta que <code>data-rbp-small-help</code> hace referencia a un indice que representa, en un archivo <code>json</code> externo, a un texto de ayuda específico. Estos textos de ayuda viene nombrados secuenciamente de la siguiente forma: <code>t1</code>, <code>t2</code>,<code>(...)</code>, <code>tn</code>. Y te permitirán de una forma práctica agregar todos los textos de ayuda que requieras, desde un solo archivo y con la posibilidad de escribir en formato <code>html</code>.

De esta forma le especificarás al control de formulario que permita ser controlado por nuestro <code>SmallHelp</code> y que de igual forma permita visualizar el texto de ayuda <code>t1</code>, en un archivo externo, que contendrá todos los textos de ayuda.

### Plantilla

Por todo lo anterior, la plantilla quedaría de la siguiente forma:

````html
<!-- RBPNetPlugin > SmallHelp para Bootstrap 4 - Plantilla Final -->

<form name="formulario-1">
    <label for="inputPassword5">Password</label>
    <input type="password" id="inputPassword5" class="form-control" aria-describedby="passwordHelpBlock">
    <small id="passwordHelpBlock" class="form-text text-muted" data-rbp-small-help="t1">
        Your password must be 8-20 characters long, contain letters and numbers, and must not contain spaces, special characters, or emoji.
    </small>
</form>
````

La cual, hace referencia a un formulario nombrado <code>formulario-1</code> que mostrará por medio de nuestro <codoe>SmallHelp</code> el tip con el indice <code>t1</code>.

!> Debes tener en cuenta que nuestro <code>SmallHelp</code> necesitar de <code>jQuery</code> para que pueda funcionar correctamente.

Para activar nuestro <code>SmallHelp</code> debes declarar dentro del método <code>ready</code> de <code>jQuery</code> nuestro plugin como se muestra e continuación.

````js
// declaración de método ready para jQuery
$(document).ready(function () {
   // <AQUÍ SE DECLARA SMALLHELP>
});
````

Para ejecutar el smallHelp, utilizando el nombre de formuario <code>formulario-1</code>, utiliza el siguiente código.

````js
// Ejecución de smallHelp para los controles de formulario de nombre formulario-1
$("[name='formulario-1']").smallHelp();
````

### ¿Como se ejecuta?

Teniendo en cuenta lo anterior y las indicaciones expuestas generarían el siguiente resultado.

````js
// ejecutando smallHelp para formulario-1
$(document).ready(function () {
   $("[name='formulario-1']").smallHelp();
});
````

!> Pro defecto, nuestro <code>SmallHelp</code> viene solo con el tip de indice <code>t1</code> definido. Debes manipualar tu archivo contenedor de textos de ayuda, para agregar todos los indices que desees con los textos -o tips- que consideres necesarios. En este sentido, debes dirigirte a la ruta <code>./RBPNet/plugins/small-help-tips</code> y proceder con la edición de los archivos <code>.json</code> que son los que se encargarán de proveer de forma organizada y práctica los textos de ayuda que necesites para tus controles de formularios.