Links
Freecodecamp.org
https://stackoverflow.com/questions/5068951/what-do-lt-and-gt-stand-for
https://www.w3schools.com/HTML/html_entities.asp

En los anchor <a>
El atributo "target" tienelas siguientes opciones:
1. _self = se abre en la misma ventana, viene por defecto
2. _blank = nueva pestaña
3. _parent = en otra ventana fuera el elementao embebido.
4. _top = en otra ventana y full size 

Path
Absolutos: 
    empieza desde la raiz hacia la direccion exacta del archivo.
    Incluye el protocolo (http, https, file, etc)
    Se usa para linkear recursos externos o cuando necesitas mantener un contorl exacto de donde nace ese archivo.
    
Relativos:
    da la dirección desde la ubicación del archivo que se esta ejecutando.
    se usa mientras estas dentro del mismo web, par amantener el codigo limpio, y para mantener código seguro durante el testing.


Maneras de llamar los recursos (FIle Paths)

Ruta Absoluta (/public/logo.png):
    Comienza con una barra /, lo que indica que la ruta es absoluta desde la raíz del servidor.
    Se utiliza para acceder a archivos que están en una ubicación fija dentro del servidor.
    Ejemplo: /public/logo.png buscará el archivo logo.png en la carpeta public ubicada en la raíz del servidor.
    
Ruta Relativa (./script.js y ../styles.css):
  Se interpreta en relación con la ubicación del archivo que está haciendo la llamada.
  Programacion indica que el archivo está en el mismo directorio que el archivo actual.
  Ejemplo: ./script.js buscará el archivo script.js en el mismo directorio.
  "../" indica que el archivo está en el directorio padre del archivo actual.
  Ejemplo: ../styles.css buscará el archivo styles.css en el directorio inmediatamente superior al actual.

Estados de los anchor 

a:link:
Representa un enlace que aún no ha sido visitado por el usuario.
Es el estado predeterminado de un enlace.

a:visited:
Representa un enlace que ya ha sido visitado por el usuario.
El navegador determina esto basándose en el historial del usuario.

a:hover:
Representa un enlace cuando el usuario pasa el cursor sobre él (sin hacer clic).

a:active:
Representa un enlace en el momento en que se hace clic en él (mientras se mantiene presionado el botón del mouse).

a:focus:
Representa un enlace que ha recibido el foco, por ejemplo, al navegar con el teclado (usando la tecla Tab).

En CSS se tiene que estilar en el siguiente orden:
link, visited, hover, focus, then active