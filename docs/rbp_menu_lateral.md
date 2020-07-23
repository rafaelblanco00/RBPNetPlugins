# RBP - MenuLateral v.1.0

Nuestro Menú lateral desarrollado con HTML, CSS, jQuery y GSAP es una forma práctica y útil de generar una barra de opciones al lado derecho de una página web. Se presenta de forma superpuesta, como una ventana modal para que puedas disponer de una forma organizada y usable, de un grupo de opciones o vínculos a diferentes partes un sitio web. Permite muchas opciones entre las que se encuentran: el cambio de color para la personalización del mismo; la adición de tantas opciones como llegues a necesitar con sus respectivas funciones de respuesta (callbacks); la adición de un título, un antetítulo y hasta un pié que te permitirá visualizar información relevante como el nombre de dominio de tu sitio web o proyecto. De antemano, te invito a utilizarlo y a que me apoyes para seguir desarrollando este tipo de recursos. 

<img src="_media/menu-lateral/rbp-menu-lateral-banner.png"/>

## ¿Cómo funciona?

Su utilidad es muy práctica, tienes una página web en la que te encuentras trabajando, necesitas agrupar vínculos y opciones para controlar la interacción y la navegación del mismo y usas nuestro menú, de forma que al hacer un simple clic, puedas ofrecer alternativas de navegación para tus usuarios de una manera atractiva, rápida y usable. 

## ¿Por donde inicio?

No te preocupes, primero necesitas utilizar nuestra plantilla de inicio como se explica en el aparte de <b>Primeros pasos / Instalación inicial / Pantilla inicial</b>. Si deseas revisar este aparte [haz clic aquí](primeros_pasos?id=plantilla-inicial).

Luego de esto, solo debes dirigirte a la parte inferior y agregar el siguiente código en una etiqueta <code>SCRIPT</code>

```` js
// ejecución del MenuLateral con jQuery
$(function(){
    $.fn.menuLateral();
});
````
> Ten en cuenta que este simple código te permitirá visualizar nuestro Menú Lateral de forma automática, debes ejecutar esta porción de código como resultado de un evento de ratón sobre un botón programado con <code>javascript</code> o <code>jQuery</code> o como lo desees.

Para personalizar nuestro Menú Lateral, utiliza objeto <code>defaults</code>del mismo, al cual puedes acceder con la siguiente línea de código

````javascript
$.fn.menuLateral.defaults = {
    caption: "Opciones",
    titulo: "¿Qué desea hacer?",
    pie: "www.rafaelblanco.net",
    botones: ["Botón No.1", "Botón No.2", "Botón No.3"],
    botonesFunciones: [
        function () {
            alert("Acciones para el botón No.1");
        },
        function () {
            alert("Acciones para el botón No.2");
        },
        function () {
            alert("Acciones para el botón No.3");
        },
    ],
    colorFondo: "#121232",
    colorTextos: "#ffffff",
    colorBloqueo:"rgba(0,0,0,0.25)"
}
````

Como se puede apreciar, el objeto <code>defaults</code> te permite modificar la apariencia física de nuestro <code>Manú Lateral</code> y está compuesto por 8 opciones que puedes modificar y especificar a tu gusto.

A continuación se discriminan cada una de estas 8 opciones y sus respectivas funciones.

- <b><code>caption</code></b>: hace referencia a un pequeño texto ubicado como antetítulo, se utiliza para ofrecer contexto como parte informativa del menú.

- <b><code>titulo</code></b>: Es el titulo del menú, y está pensado para preguntarle que opción desea seleccionar de las que se ofrecen en la lista.

- <b><code>pie</code></b>: El pié está pensado para que se presente como un texto corto, de forma que se coloque el nombre de dominio del sitio web, esto es útil ya que cuando el menú se presenta en dispositivos móviles, por lo general ocupa toda la pantallar esta es una forma de decirle al usuario en que sitio web se encuentra.

- <b><code>botones</code></b>: es un arreglo de textos (array de cadenas de textos) que representa las diferentes opciones con las que contará el <code>Menú Lateral</code>. Ten en cuenta que el ejemplo solo muestra 3 botones, sin embargo, por ser este un arreglo, puedes colocar todos los que desees.

- <b><code>botonesFunciones</code></b>: es un arreglo de funciones definidas por el usuario que debe tener la misma longitud de la cadena de botones, y representan las diferentes acciones que cumpliran cada uno de los botones al hacer clic sobre estos.

- <b><code>colorFondo</code></b>: es el color general del <code>Menú Lateral</code>. Se recomienda utilizar un color puro (con alta saturación) y oscuro, para lograr contraste con todos los textos que hacen parte del mismo.

- <b><code>colorTextos</code></b>: es el color de todos los textos presentes en el <code>Menú Lateral</code>.

- <b><code>colorBloqueo</code></b>: este color hace referencia al color del fondo del menu que permite bloquear toda la página y que por lo general se utiliza de color negro. Se recomienda especificarlo con la notación <code>rgba(RR,GG,BB,ALPHA)</code>.

> Ten en cuenta que este Plugin está creado para trabajar con <code>Bootstrap</code> asi que debes considerar revisar el aparte de primeros pasos, para que procedas con la instalación del mismo y este pueda funcionar correctamente.

¡Listo! hasta este punto, el plugin debe funcionar correctamente. Espero te sirva de mucha ayuda y puedas utilizarlo entus proyectos. ¡Gracias de ante mano!.


> <b>¡Tu apoyo es muy importante para mi!</b><br>
> * Utiliza el siguiente botón si deseas apoyar mi trabajo y asi porder seguir construyendo este tipo de recursos. 
> * Recuerda que estos desarrollos son grátis y están disponibles para que puedan se utilizados en proyectos web basados en Bootstrap. 

<a target="_blank" href="https://www.buymeacoffee.com/rafaelblanco">![Buy me a Coffe!](_media/BuyMeACoffe-02.png)</a>

!> Si aún no haz descargado nuestro plugin, te invitamos a descargarlo haciendo clic [aquí](https://github.com/rafaelblanco00/RBPNetPlugins) y para más información de descarga e instalación te invitamos a revisar el aparte de [instalación inicial](primeros_pasos.md)