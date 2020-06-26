# RBP Paginador

Fácil, sencillo y para Bootstrap 4.

?> Este es un desarrollo para Bootstrap creado por: <strong>Rafael A. Blanco P.</strong>, Cartagena de Indias D. T. y C. / Sur América.

## ¿De qué se trata?

> Es un formulario organizado por páginas y algo más ...

<img src="_media/rbp-paginador-banner.png"/>

<code>RBP Paginador</code> es un método del plugin <code>RBPNetPlugins.js</code> creado para <code>Bootstrap 4</code> que permite la creación de un formulario organizado por páginas, de forma que se pueda controlar el número de campos, el envio y validación de los mismos y de igual forma la organización estructural del contenido del mismo por medio de slides los cuales pueden ser navegados en forma de páginas.

!> Para el uso de este plugin se hace necearia la instalación de <code>Bootstrap 4</code>.

!> Para instalar <code>Bootstrap 4</code> puedes utilizar el siguiente vinculo: [bootstrap.com](https://getbootstrap.com/docs/4.5/getting-started/introduction/)

```versión
(versión) RBP Paginador v.1.0 alpha
```

## ¿Cómo funciona?

Su funcionamiento es muy sencillo, es un formulario gestionado con Bootstrap, que permite listar por medeio de páginas partes agrupadas de un formulario, de forma que se pueda ofrecer rápidez y orden a la hora de gestionar formularios con grandes volumnes de informaicón.

!> Este plugin para su correcto funcionamiento, utiliza los métodos: <code>$.fn.alertar</code> y <code>$.fn.smallHelp</code>, los cuales vienen incluidos en el plugin <code>RBNetPlugins.js</code>.

## ¿Cómo agregarlo?

Para iniciar debes vincular el plugin a la cabecera de tu página HTML. Para esto, utiliza el siguiente código.

```html
<script src="tu_ruta_para_archivos_JS/RBNetPlugins.js"></script>
```

Eventualmente será necesario contar con iconografía, algunas tipografías y estilos vitales para garantizar la apariencia visual de los elementos gráficos del plugin (botones, ventanas, alertas, etc.), para esto, debes agregar en la cabecera de tu HTML los siguientes estilos css y tipografías.

```html
<link rel="stylesheet" href="_ruta_a_tus_estilos_css_/rbp_css/main.css" />
<link rel="stylesheet" href="_ruta_a_tus_estilos_css_/rbp_css/rbp-main.css" />

<link href="https://fonts.googleapis.com/icon?family=Material+Icons" rel="stylesheet"/>
<link href="https://fonts.googleapis.com/css2?family=PT+Sans:wght@400;700&family=Roboto&display=swap" rel="stylesheet"/>
```

> fuente: [fonts.google.com](https://fonts.google.com/).

Para continuar correctamente, vas a necesitar de una plantilla, la cual es una porción de código HTML (mostrada a continuación) que será utilizada como referencia para controlar e identificar, en tu HTML, al formulario.

```html
<form novalidate name="form-001" data-rbp-paginador-form-id="1" action="" class="needs-validation col-lg-12 px-0">
   <div class="row" data-slides-cont>
      <div class="col">
            <!-- coloca aquí tus slides (uno por cada página que desees en el formulario) --->
      </div>
   </div>

   <!-- posición del pie -->

   <div class="form-row" data-paginador-botones>
      <div class="col-2 col-sm-3 col-md-2 col-lg-2 col-xl-2 pr-0">
            <input type="button" value="Guardar" name="guardar-btn-001" class="btn btn-primary col" />
      </div>
      <div class="col-2 col-sm-3 col-md-2 col-lg-2 col-xl-2 pr-0">
            <input type="button" value="Enviar" name="btn-enviar" class="btn btn-secondary col" />
      </div>
   </div>
   <br />
</form>
```

> <strong>Nota:</strong> puede encerrar sus formularios con la siguiente etiqueta para podor controlar, por medio de <code>Bootstrap</code> en ancho del formulario con las clases de control para <ocde>grids</code>.

````html
<div class="container col-6">
   <!-- coloque aquí su plantilla de formulario -->
</div>
````

> <strong>Nota:</strong><br>Si solo va a utilizar una plantilla o formulario en su página HTML, puede conservar el valor de este atributo que viene por defecto.

## ¿Cómo lo ejecuto?

Luego de haber adjuntado el plugin y haber agregado la plantilla al cuerpo (body) de su página, el siguiente paso es la ejecución del script que se encargará de controlar todo el funcionamiento.

!> Tenga en cuenta que este código JS (jQuery) debe estar definido como una <code>sentencia</code>, del parámetro <code>function</code>, del método <code>ready</code>, de la declaración inicial de <cdoe>jQuery</code>, como se muestra a continuación.

```js
$(document).ready(function () {
   // en esta posición debe ejecutar el paginador
});
```

Teniendo esto en cuenta se ejecuta el paginador por medio del siguiente código.

```js
// ejecuación del paginador
$("[name='tu_nombre_de_formulario']").paginador();
```

Como el nombre del formulario de la plantilla es <ocde>form-001</code> nuestro código quedaría de la siguiente forma.

```js
// ejecuación del paginador para un formulario de nombre form-001
$("[name='form-001']").paginador();
```

!> Tenga en cuenta que se debe activar el <code>smallHelp</code> para los controles del formulario.

```js
// activación de smallHelp para los controles del formulario
$("[name='form-001']").smallHelp();
```

```js
// nuestra plantilla quedaría de la siguiente forma
$(document).ready(function () {
   $("[name='form-001']").smallHelp();
   $("[name='form-001']").paginador();
});
```

!> Tenga en cuenta que el paginador debe ser ejecutado con un selector <code>jQuery</code> que apunte a una plantilla (formulario) para que de esta forma, todo el control del método <code>paginador();</code>, recaiga sobre el formulario especificado.

## Aja! ¿Y cómo agrego páginas?

En el paginador a cada pagina se le llama <code>slide</code>, agregar páginas (slides) es muy sencillo, para esto se necesita de una plantilla que le permitirá agregar campos y grupos de campos como lo desees.

> Agregando una página

```html
<!-- plantilla de slides -->
<div class="rbp-slide form-row" data-slide-titulo="Información inicial">
   <!-- Aquí debe agregar la plantilla de cada elemento de formulario que necesite -->
</div>
```

> Tenga en cueta que usted puede agregar elementos de formulario tales como:
>
> -  Inputs
> -  Selects
> -  y Textareas.

# Agregando INPUTs

> Agregando un <code>input tipo="text"</code>

```html
<div class="form-group col-12 col-sm-12 col-md-12 col-lg-12 col-xl-12">
   <label for=""></label>
   <input required type="text" class="form-control" />
   <small class="form-text text-muted" data-rbp-small-help="[__SMALL_HELP_ID__]">__SMALL_HELP__MANUAL__</small>
</div>
```

# Agregando SELECTs

> Agregando un <code>select</code>

```html
<div class="form-group col-12 col-sm-12 col-md-12 col-lg-12 col-xl-12">
   <label for=""></label>
   <select required class="custom-select">
      <option value="">(No hay selección)</option>
      <option value="">__OPCION__</option>
   </select>
   <small class="form-text text-muted" data-rbp-small-help="__SMALL_HELP_ID__">__SMALL_HELP_MANUAL__</small>
</div>
```

<br>

# Agregando TEXTAREAs

> Agregando un <code>textarea</code>

```html
<div class="form-group col-lg-12">
   <label for="">Etiqueta del control de formulario</label>
   <textarea required maxlength="250" class="form-control" cols="30" rows="5"></textarea>
   <small class="form-text text-muted" data-rbp-small-help="t1">Tip relacionado con lo que sugiere la etiqueta del control de formulario.</small>
</div>
```

<br>

# Activando Small Help

> Para activar <code>smallHelp</code> se debe agregar un archivo en formato <code>json</code> que contenga todos los tips a utilizar en el formulario.

<img src="_media/small-help-banner.png"/>

<code>SmallHelp</code> activa la posibilidad de indicar a quien diligencia el formulario, instrucciones para que la tarea sea llevada a cabo correctamente y el campo cumpla con la recepción de la información que este solicita. De esta forma se puede acceder a este mensaje con solo hacer clic en un botón de ayuda ubicado a la derecha de la etiqueta de cada uno de los campos de formularios.

!> Para activarlo se debe agregar un documento en formato JSON en algun lugar del su proyecto web. Utilice el formato sugerido a continuación.

```json
// Documento guardado como ./rbp-small-help-f1.json

{
   "tips": {
      "t1": "Detalle el nombre de la entidad tal y como aparece en el documento de constitución ante la Cámara de comercio de Barranquilla.",
      "t2": "",
      "t3": "",
      "t4": "",
      "t5": "",
      "t6": "",
      "t7": "",
      "t8": "",
      "t9": "",
      "t10": ""
   }
}
```

> <strong>Nota:</strong> puede agregar tandos mensajes como sea posible, esta forma de agregar los tips se creó para facilitar los procesos de correción ortografica y actualización de sugerencias en campos de formularios.

Para activar <code>SmallHelps</code> solo debe ejecutar el siguiente código <code>jQuery</code> que se muestra a continuación.

```js
$("[name='____NOMBRE_DE_SU_FORMULARIO____']").smallHelp({
   titulo: "Tenga en cuenta",
   ruta_json:
      "___TU_RUTA_A_CARPETA_DE_JAVASCRIPTS___/RBNet/rbp-bootstrap-small-help/rbp-small-help-f1.json",
   ver_que_tip: true,
});
```

?> Puedes utilizar el código anterior de una forma corta, con solo especificar la ruta del archivo.

```js
$("[name='____NOMBRE_DE_SU_FORMULARIO____']").smallHelp({
   ruta_json:
      "___TU_RUTA_A_CARPETA_DE_JAVASCRIPTS___/RBNet/rbp-bootstrap-small-help/rbp-small-help-f1.json",
});
```

?> De igual forma, en una línea adicional, puedes especificar ajustes que puedes manejar de forma global como una ruta única para el archivo <code>json</code> contenedor de todos los tips, un título global o por defecto para todos los tips y el modo de verificación activado (<code>ver_que_tip</code>) para cuando lo necesites. Esto se puede lograr de la siguiente forma.

```js
$.fn.smallHelp.defaults.titulo = "Tenga en cuenta";
$.fn.smallHelp.defaults.ruta_json =
   "___TU_RUTA_A_CARPETA_DE_JAVASCRIPTS___/RBNet/rbp-bootstrap-small-help/rbp-small-help-f1.json";
$.fn.smallHelp.defaults.ver_que_tip = true;
```

?> Y el código de activación del <code>smallHelp</code> se reduciría a esta pocas líneas.

```js
$("[name='____NOMBRE_DE_SU_FORMULARIO____']").smallHelp();
```

> En el código anterior, cada uno de sus propiedades permiten respectivamente:
>
> -  <b>Titulo:</b> Agregar un titulo al inicio del tip (El cual aparece después de hacer clic en el correspondiente <code>botón de ayuda</code> que luego de la activación.).
> -  <b>ruta_json:</b> Referenciar un archivo <code>json</code> contenedor de todos los tips relacionados a uno o varios formularios.
> -  <b>ver_que_tip:</b> Ayuda visual tipo <code>Ayuda:t35</code> que aparece a la derecha de cada botón de ayuda, y permite identificar el tip de un campo de formulario, cara al archivo json especificado. Esta propiedad, debe estar definida como false al lanzar el sitio y publicar.

> Luego de haber creado el documento en formato <code>json</code> y haber ejecutado el codigo anterior, solo resta especficar el correspondiente código <code>t1, t2, ..., tn</code> del <code>json</code> en la etiqueta <code>small</code> de cada uno de los elementos de formulario agregados con las plantillas mostradas anateriormenten en los partes: <code>agregando inputs</code>, <code>agregando textareas</code> y <code>agregando selects</code> y que están especificados con el texto <code>**SMALL_HELP_ID**</code>

<img src="_media/small-help-ejemplo.png"/>
