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

¿Qué código de respuesta podría recibir si el servidor web no puede acceder a su base de datos y la aplicación falla?

    503

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

    THM{YOU'RE_IN_THE_ROOM}

Realice una solicitud GET a /blog y usando el icono de engranaje establezca el parámetro id en 1 en el campo URL

    THM{YOU_FOUND_THE_BLOG}

Hacer una solicitud DELETE a /usuario/1

    THM{USER_IS_DELETED}

Realice una solicitud PUT a /user/2 con el parámetro de nombre de usuario establecido en admin

    THM{USER_HAS_UPDATED}

PUBLIQUE el nombre de usuario de thm y una contraseña de letmein a /login

    THM{HTTP_REQUEST_MASTER}
