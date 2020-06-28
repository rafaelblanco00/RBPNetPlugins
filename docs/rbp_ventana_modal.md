# RBP - Ventana Modal v.1.0 

Nuestra ventana es un hermoso y sencillo cuadro flotante que te permitirá ofrecer información con una ventana superpuesta sobre toda la interfaz de tu sitio web y a la que puedes agregarle los botones, títulos, mensajes y acciones necesarias para que esta cumpla con el proposito que le destines en tu proyecto personal.

?> <b>Nota:</b> Para poder utilizar nuestra <code>ventanaModal</code> es necesario que te remitas al aparte [instalación inicial](primeros_pasos.md), de esta forma podrás contar con todos los requerimientos iniciales para el uso correcto de la misma.

<img src="_media/rbp-ventana-modal-banner.png"/>

## ¿Cómo funciona?

La idea es muy sencilla, estas en tu proyecto y necesitas informar algo y utilizas nuestra ventana modal. Puedes hacer muchas como por ejemplo:

- Puedes especificar un mensaje como contenido de la ventana.
- Puedes agregarle un título a la ventana de forma que puedas ofrecer un contexto.
- Puedes acompañar la información con una pregunta, que te permitirá detonar una actitud de interacción.
- Paralelo a esto puedes agregar tantos botones como creas necesario y defirenciarlos de tres formas diferente.
- Por último, puedes asignar una función de respuesta - <b>o callback</b> - para cada botón que especifiques, de forma que puedas controlar las acciones del usuario al hacer clic en cada uno de ellos.

## Plantilla

Para utilizar nuestra ventana modal, no es necesaria plantilla html algúna, sin enbargo puedes editar su apariencia haciendo una cuidadosa revisión de las hojas de estilo <ocde>scss</code> que vienen incluidas en la ruta <code>RBPNet/sass/scss/_rbp_ventana_modal.scss</code>

## ¿Cómo se ejecuta?

!> Para ejecutar nuestra ventana modal, debes contar con la respectiva declaración del método <code>ready</code> (de jQuery), lo que te permitirá ejecutar los cógidos de nuestro plugin, en este sentido debes ejecutar nuestra ventana modal dentro de la siguiente función.

````js
$( document ).ready(function() {
    // aquí debes ejecutar tu ventana modal
});
````

- Por todo lo anterior y para lograr ejecutar y utilizar nuestra ventana modal, solo necesitas el siguiente código <code>javascript</code>.

!> Te recomendamos probar ejecutanto solo la ventana modal sin propiedades, y luego ir modificandolas una a una para que logres evidenciar cómo se hace y que controlan cada una de estas propiedades.

- Ejecución básica y con propiedades predeterminadas

````js
$.fn.ventanaModal();
````

- Ejecución predeterminada con título propio

````js
$.fn.ventanaModal({
    titulo:"Este sería tu nuevo titulo!"
});
````

- Ejecución predeterminada con título y contenido propio

````js
$.fn.ventanaModal({
    titulo:"Este sería tu nuevo titulo!",
    contenido:"Ahora este contenido te permitirá informar con largos bloques de texto."
});
````

- Ejecución predeterminada con título, contenido y pregunta propia

````js
$.fn.ventanaModal({
    titulo:"Este sería tu nuevo titulo!",
    contenido:"Ahora este contenido te permitirá informar con largos bloques de texto.",
    pregunta:"¿Que botón crees que necesitas?, esta sería una pregunta interesante e invita a tus usuarios a identificar el botón que deben presionar."
});
````

- Ejecución predeterminada con título, contenido, pregunta y 3 botones propios

````js
$.fn.ventanaModal({
    titulo:"Este sería tu nuevo titulo!",
    contenido:"Ahora este contenido te permitirá informar con largos bloques de texto.",
    pregunta:"¿Que botón crees que necesitas?, esta sería una pregunta interesante e invita a tus usuarios a identificar el botón que deben presionar.",
    botones:["Continuar","Volver","Cancelar"],
    botonesTipo:["btn-primary","btn-secondary","btn-terciary"]
});
````

- Ejecución predeterminada con título, contenido, pregunta y 3 botones con sus respectivas funciones de respuesta o CallBacks

````js
$.fn.ventanaModal({
    titulo:"Este sería tu nuevo titulo!",
    contenido:"Ahora este contenido te permitirá informar con largos bloques de texto.",
    pregunta:"¿Que botón crees que necesitas?, esta sería una pregunta interesante e invita a tus usuarios a identificar el botón que deben presionar.",
    botones:["Continuar","Volver","Cancelar"],
    botonesTipo:["btn-primary","btn-secondary","btn-terciary"],
    botonesCallbacks:[
        function(){
            alert("Acciones para botón -Continuar-!");
        },
        function(){
            alert("Acciones para botón -Volver-!");
        },
        function(){
            alert("Acciones para botón -Cancelar-!");
        }
    ]
});
````

Como puedes ver, nuestra ventana modal es de fácil uso y recuerda que para que puedas extender su uso debes agregar su ejecuación a la acción de un botón o como respuesta a algún proceso que desees informar. Si deseas conocer más de nuestro plugin haz clic [aquí](README.md).