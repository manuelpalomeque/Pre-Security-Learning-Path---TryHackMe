## ¿Qué es HTTP(S)?

¿Qué significa HTTP?

    HyperText Transfer Protocol

¿Qué significa la S en HTTPS?

    secure

En la página web simulada a la derecha hay un problema, una vez que lo haya encontrado, haga clic en él. ¿Qué es la bandera de desafío?

    THM{INVALID_HTTP_CERT}

## Solicitudes y respuestas


¿Qué protocolo HTTP se está utilizando en el ejemplo anterior?
    
    HTTP/1.1

¿Qué encabezado de respuesta le dice al navegador cuántos datos esperar?

    Content-Length

## Métodos HTTP

¿Qué método se utilizaría para crear una nueva cuenta de usuario?

    POST

¿Qué método se usaría para actualizar su dirección de correo electrónico?

    PUT

¿Qué método se usaría para eliminar una imagen que hayas subido a tu cuenta?

    DELETE

¿Qué método se usaría para ver un artículo de noticias?

    GET

## Códigos de estado HTTP

¿Qué código de respuesta podría recibir si ha creado un nuevo usuario o artículo de publicación de blog?

    201

¿Qué código de respuesta podría recibir si ha intentado acceder a una página que no existe?

    404

    -----------------------------------------------------------------

    Not Found
    The requested URL /missing.html was not found on this server.
    
    Apache/2.0.54 Server at www.test.thm Port 80

¿Qué código de respuesta podría recibir si el servidor web no puede acceder a su base de datos y la aplicación falla?

    503

    ------------------------------------------------------

    Service Unavailable
    The server is temporarily unable to service your request due to maintenance downtime or capacity problems. Please try again later
    
    Apache/2.0.54 Server at www.test.thm Port 80

¿Qué código de respuesta podría recibir si intenta editar su perfil sin iniciar sesión primero?

    401

## Encabezados

¿Qué encabezado le dice al servidor web qué navegador se está utilizando?

    User-Agent

¿Qué encabezado le dice al navegador qué tipo de datos se devuelven?

    Content-Type

¿Qué encabezado le dice al servidor web qué sitio web se está solicitando?

    Host

## Cookies

¿Qué encabezado se usa para guardar cookies en su computadora?
    
    Set-Cookie

## Haciendo peticiones

Haz una solicitud GET a /room

    http://tryhackme.com/room
    
    -----------------------------------------

    GET /room HTTP/1.1
    Host: tryhackme.com
    User-Agent: Mozilla/5.0 Firefox/87.0
    Content-Length: 8
    
    ------------------------------------------
    
    Response
    HTTP/1.1 200 Ok
    Server: nginx/1.15.8
    Mon, 7 Feb 2022 11:9:24 GMT
    Content-Type: text/html; charset=utf-8
    Content-Length: 233
    Last-Modified: Mon, 7 Feb 2022 11:9:24 GMT
    
    <html>
    <head>
        <title>TryHackMe</title>
    </head>
    <body>
        Welcome to the Room page THM{YOU'RE_IN_THE_ROOM}
    </body>
    </html>



Realice una solicitud GET a /blog y usando el icono de engranaje establezca el parámetro id en 1 en el campo URL

    http://tryhackme.com/blog
    
    -------------------------
    
    GET /blog?id=1 HTTP/1.1
    Host: tryhackme.com
    User-Agent: Mozilla/5.0 Firefox/87.0
    Content-Length: 8
    
    -------------------------
    
    Response
    HTTP/1.1 200 Ok
    Server: nginx/1.15.8
    Mon, 7 Feb 2022 11:11:6 GMT
    Content-Type: text/html; charset=utf-8
    Content-Length: 231
    Last-Modified: Mon, 7 Feb 2022 11:11:6 GMT
    
    <html>
    <head>
        <title>TryHackMe</title>
    </head>
    <body>
        Viewing Blog article 1 THM{YOU_FOUND_THE_BLOG}
    </body>
    </html>


Hacer una solicitud DELETE a /usuario/1

    http://tryhackme.com/user/1
    
    ------------------------------
    
    DELETE /user/1 HTTP/1.1
    Host: tryhackme.com
    User-Agent: Mozilla/5.0 Firefox/87.0
    Content-Length: 0
    
    --------------------------------
    
    Response
    HTTP/1.1 200 Ok
    Server: nginx/1.15.8
    Mon, 7 Feb 2022 11:14:25 GMT
    Content-Type: text/html; charset=utf-8
    Content-Length: 231
    Last-Modified: Mon, 7 Feb 2022 11:14:25 GMT
    
    <html>
    <head>
        <title>TryHackMe</title>
    </head>
    <body>
        The user has been deleted THM{USER_IS_DELETED}
    </body>
    </html>


Realice una solicitud PUT a /user/2 con el parámetro de nombre de usuario establecido en admin

    http://tryhackme.com/user/2
    
    -----------------------------
    
    PUT /user/2 HTTP/1.1
    Host: tryhackme.com
    User-Agent: Mozilla/5.0 Firefox/87.0
    Content-Length: 14
    
    username=admin
    
    ----------------------------
    
    HTTP/1.1 200 Ok
    Server: nginx/1.15.8
    Mon, 7 Feb 2022 11:16:25 GMT
    Content-Type: text/html; charset=utf-8
    Content-Length: 232
    Last-Modified: Mon, 7 Feb 2022 11:16:25 GMT
    
    <html>
    <head>
        <title>TryHackMe</title>
    </head>
    <body>
        Username changed to admin THM{USER_HAS_UPDATED}
    </body>
    </html>


PUBLIQUE el nombre de usuario de thm y una contraseña de letmein a /login

    http://tryhackme.com/login

    -----------------------------

    POST /login HTTP/1.1
    Host: tryhackme.com
    User-Agent: Mozilla/5.0 Firefox/87.0
    Content-Length: 33
    
    username=thm&password=letmein
    
    ---------------------------------
    
    Response
    HTTP/1.1 200 Ok
    Server: nginx/1.15.8
    Mon, 7 Feb 2022 11:22:9 GMT
    Content-Type: text/html; charset=utf-8
    Content-Length: 237
    Last-Modified: Mon, 7 Feb 2022 11:22:9 GMT
    
    <html>
    <head>
        <title>TryHackMe</title>
    </head>
    <body>
        You logged in! Welcome Back THM{HTTP_REQUEST_MASTER}
    </body>
    </html>
