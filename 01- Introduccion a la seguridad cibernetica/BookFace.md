## BookFace


a) Eres un hacker ético y es tu trabajo probar las vulnerabilidades de seguridad en BookFace. ¡Veamos cómo hacerse 
cargo de una cuenta de usuario!


b) BookFace permite a los usuarios tener perfiles públicos. Si nota que la URL muestra el nombre de usuario de un 
perfil, copiémoslo y veamos si podemos restablecer la contraseña de Ben.

        bookface.com/Ben.Spring

c) Es común que los atacantes apunten a la funcionalidad de restablecimiento de contraseña para buscar problemas que 
les permitan obtener acceso a las cuentas de los usuarios.
Ingrese el nombre de usuario de Ben y haga clic en "Restablecer contraseña".

        Reset your password
    
        Ben.Spring      Reset Password
        
        Username not found?

d) Los restablecimientos de cuenta generalmente envían un código adicional al correo electrónico de los usuarios para 
verificar que realmente activaron el restablecimiento de contraseña.
Ben habrá recibido un correo electrónico con un código de 4 dígitos, pero no tenemos acceso a su correo electrónico. Me
pregunto si podemos adivinar el código.

        bookface.com/forgot-password
        
        Code Sent
        We have sent you an email with a 4 digit code!

e) Hay 10.000 combinaciones diferentes de códigos que podemos introducir. Podríamos intentar aumentarlos uno por uno, 
0001, luego 0002, luego 0003, pero eso llevará una eternidad.
Intente ingresar cualquier código de reinicio aleatorio.

        What is your code?
        4 Digit Reset Code     Submit

f) Cuando envió un código en el formulario, su navegador web realizó una solicitud web (que se muestra a continuación) 
a BookFace con los datos relevantes del formulario.

        Web Request
        POST /accounts/reset_password/ HTTP/1.1
        User-Agent: Mozilla/5.0 Chrome/74
        Host: bookface.com
        
        reset_code=0000&username=Ben.Spring

g) No será posible adivinar manualmente todos los códigos, así que repitamos la solicitud web de código que enviamos 
anteriormente y cada vez aumentemos el valor del código, automatizando el proceso usando el "Repetidor de solicitud" a 
continuación.
Este proceso de probar diferentes combinaciones hasta que una sea la correcta se llama fuerza bruta, un ataque común en 
la seguridad cibernética.
Use la herramienta BruteForce con un valor de código mínimo (1) y máximo (10,000).

    Web Request Repeater
    Min Code Value: 0001
     
    Max Code Value: 10000
     BruteForce             Web request data will appear here..

h) Felicidades, al usar fuerza bruta en todas las combinaciones de códigos, lograste obtener el valor del código para 
restablecer la contraseña de Ben.
Cada vez que solicite un restablecimiento de contraseña, el código de restablecimiento será diferente y deberá volver a 
aplicar fuerza bruta.
Restablezca la contraseña de Ben para continuar.

    Reset Password
    ••••     Reset Password
    Code 0187 is correct!
    
    Web Request
    POST /accounts/reset_password/ HTTP/1.1
    User-Agent: Mozilla/5.0 Chrome/74
    Host: bookface.com
    
    reset_code=0187&username=Ben.Spring

Este fue un ataque del mundo real, que (antes de que fuera parcheado) te permitía tomar el control de la cuenta de 
Instagram de cualquier persona. 

    Password has been reset
    The answer to the TryHackMe task is: THM{BRUTEFORCING}

i)  ¿Cuál es el nombre de usuario de la cuenta de BookFace de la que se hará cargo?

    Ben.Spring

j) ¡Hackea la cuenta de BookFace para revelar la respuesta de esta tarea!

    THM{BRUTEFORCING}