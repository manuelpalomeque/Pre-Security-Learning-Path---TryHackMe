## Un poco de historia sobre Linux:

Investigación: ¿En qué año fue el primer lanzamiento de un sistema operativo Linux?

    1991

## Ejecutando sus primeros comandos:


Si quisiéramos generar el texto " TryHackMe ", ¿cuál sería nuestro comando?

    tryhackme@linux1:~$ echo "TryHackMe"

¿Cuál es el nombre de usuario con el que inició sesión en su máquina Linux implementada?

    tryhackme@linux1:~$ whoami
    tryhackme

## ¡Interactuando con el sistema de archivos!

En la máquina Linux que implementa, ¿cuántas carpetas hay?

<img src="">
    4

¿Qué directorio contiene un archivo? 

<img src="">
    folder4

¿Cuál es el contenido de este archivo?

<img src="">
    Hello World

Use el comando cd para navegar a este archivo y encontrar el nuevo directorio de trabajo actual. ¿Cuál es el camino?

    /home/tryhackme/folder4

## Búsqueda de archivos

Use grep en "access.log" para encontrar el indicador que tiene el prefijo "THM". ¿Qué es la bandera?

THM{ACCESS}

## Una introducción a los operadores de Shell

Si quisiéramos ejecutar un comando en segundo plano, ¿qué operador querríamos usar?

    &

Si quisiera reemplazar el contenido de un archivo llamado "contraseñas" con la palabra "contraseña123", ¿cuál sería mi comando?

    echo password123 > passwords

Ahora, si quisiera agregar "tryhackme" a este archivo llamado "contraseñas" pero también conservar "contraseñas123", ¿cuál sería mi comando?

    echo tryhackme >> passwords
