# INTRODUCCION

He integrado el formulario en mi página web, para acceder al mismo, habrá que simplemente clickar en el icono de usuario arriba a la derecha.

**IMPORTANTE**: Se deberá usar de navegador Firefox (ya que con Chrome no se guardan las cookies en local). 

1. Primero habrá que registrarse con unas credenciales validas, si lo hemos realizado correctamente, nos saldrá un mensaje de &quot;_Te has registrado correctamente_&quot;.
2. Segundo tendremos que irnos al apartado de Login e iniciar sesión con nuestro correo y nuestra contraseña. Si todo está OK nos saldrá un mensaje de &quot;_Sesión iniciada, bienvenido_&quot;. En cambio, si cometemos algún error al introducir nuestras credenciales, el mensaje será de &quot;_Correo no registrado, pruebe de nuevo_&quot;.

# VALIDACIÓN DEL FORMULARIO:

En primer lugar, para recoger los datos del HTML, he usado _document.forms._

Para validar los datos he usado los eventos **addEventListener** (&quot;keyup&quot;)(keyup significa que saltará el evento al levantar la tecla de nuestro teclado). Para cambiar el tipTool usaremos **setCustomValidity(**&quot;_mensaje que queramos mostrar_&quot;**).**

Para validar el email he utilizado una expresión regular donde haya que introducir una _@_ y posteriormente un punto seguido de 2, 3 o 4 caracteres por el contrario, nos mostrará el siguiente mensaje &quot;_Formato inválido de correo&quot;_.

Para la contraseña he seguido el mismo procedimiento cambiando la expresión regular y comprobando que tenga una minúscula, una mayúscula, un número y un carácter especial.

# IMPLEMENTACIÓN DE COOKIES

Para implementar las cookies, en primer lugar he comprobado que el usuario haya pulsado el botón de Registrarse después de haber introducido todos los datos correctamente. Tras esto, he creado una cookie guardando su correo y su contraseña hasheada con sha256.

En segundo lugar, cuando el usuario quiera iniciar sesión con su cuenta ya creada, comprobaré que el correo y la contraseña (hasheada) que introduzca son iguales a la cookie anteriormente creada. Si es así, crearé otra cookie de sesión la cual expirará cuando el usuario cierre su sesión (todavía no he podido implementar lo del _Logout_).
