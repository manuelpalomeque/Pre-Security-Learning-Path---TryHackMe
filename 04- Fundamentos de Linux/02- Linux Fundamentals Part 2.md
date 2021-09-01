## Acceder a su máquina Linux usando SSH (Implementar)

iniciaremos sesión como "tryhackme", cuya contraseña es "tryhackme" sin las comillas (""). Usemos la dirección IP de la 
máquina que se muestra en la tarjeta en la parte superior de la sala como la dirección IP y este usuario, para 
construir un comando para iniciar sesión en la máquina remota usando SSH. El comando para hacerlo es ssh y luego el
nombre de usuario de la cuenta, @la dirección IP de la máquina.

    root@ip-10-10-8-100:~# ssh tryhackme@10.10.233.95
    The authenticity of host '10.10.233.95 (10.10.233.95)' can't be established.
    ECDSA key fingerprint is SHA256:Ew+GTVunrsaIPXvQRz33138D0Ywrg77LNGIYdRqBrzE.
    Are you sure you want to continue connecting (yes/no)? yes
    Warning: Permanently added '10.10.233.95' (ECDSA) to the list of known hosts.
    tryhackme@10.10.233.95's password: 
    Welcome to Ubuntu 20.04.2 LTS (GNU/Linux 5.4.0-1047-aws x86_64)

    * Documentation:  https://help.ubuntu.com
    * Management:     https://landscape.canonical.com
    * Support:        https://ubuntu.com/advantage

    System information disabled due to load higher than 1.0
    
    
    
    
    
    The list of available updates is more than a week old.
    To check for new updates run: sudo apt update
    
    
    The programs included with the Ubuntu system are free software;
    the exact distribution terms for each program are described in the
    individual files in /usr/share/doc/*/copyright.
    
    Ubuntu comes with ABSOLUTELY NO WARRANTY, to the extent permitted by
    applicable law.
    
    tryhackme@linux2:~$ 



## Introducción a banderas e interruptores


¿Qué tecla de flecha direccional usaríamos para navegar hacia abajo en la página del manual?

    down

¿Qué bandera usaríamos para mostrar la salida de una manera "legible por humanos"?

    tryhackme@linux2:~$ man ls

    -h, --human-readable
                  with -l and -s, print sizes like 1K 234M 2G etc.

    -h

## Continuación de la interacción del sistema de archivos


¿Cómo crearías el archivo llamado "newnote"?

    tryhackme@linux2:~$ touch newnote
    tryhackme@linux2:~$ ls
    important  myfile  myfolder  newnote  unknown1
    tryhackme@linux2:~$

En la máquina implementable, ¿cuál es el tipo de archivo "unknown1" en el directorio de inicio de "tryhackme"?

    tryhackme@linux2:~$ file unknown1
    unknown1: ASCII text

¿Cómo moveríamos el archivo "myfile" al directorio "myfolder"? 

    tryhackme@linux2:~$ ls
    important  myfile  myfolder  newnote  unknown1
    tryhackme@linux2:~$ mv myfile myfolder
    tryhackme@linux2:~$ ls
    important  myfolder  newnote  unknown1
    tryhackme@linux2:~$ 

¿Cuáles son los contenidos de este archivo?

    tryhackme@linux2:~$ cd myfolder
    tryhackme@linux2:~/myfolder$ cat myfile
    THM{FILESYSTEM}
    tryhackme@linux2:~/myfolder$ 

## Permisos 101

En la máquina desplegable, ¿quién es el propietario de "importante"?

    user2

¿Cuál sería el comando para cambiar al usuario "usuario2"?

    su user2

Muestra el contenido de "importante", ¿cuál es la bandera?

    THM{SU_USER2}

## Directorios comunes

¿Cuál es la ruta del directorio en el que esperaríamos que se almacenen los registros?

    /var/log

¿Qué directorio raíz es similar a cómo funciona la memoria RAM en una computadora?

    /tmp

Asigne un nombre al directorio de inicio del usuario raíz 

    /root



