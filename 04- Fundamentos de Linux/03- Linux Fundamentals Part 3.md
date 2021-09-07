## Editores de texto de terminal

Crear un archivo usando Nano:

    root@ip-10-10-169-0:~# ls
    Desktop  Downloads  Instructions  Pictures  Postman  Rooms  Scripts  thinclient_drives  Tools
    root@ip-10-10-169-0:~# nano miarchivo
    root@ip-10-10-169-0:~# ls
    Desktop  Downloads  Instructions  miarchivo  Pictures  Postman  Rooms  Scripts  thinclient_drives  Tools
    root@ip-10-10-169-0:~# cat miarchivo
    Este es un archivo de prueba
     con las flechas me desplazo y con enter hago un salto de linea
    
    root@ip-10-10-169-0:~# 

Edite "task3" ubicado en el directorio de inicio de "tryhackme" usando Nano. ¿Qué es la bandera?


    root@ip-10-10-169-0:~/Desktop# ssh tryhackme@10.10.211.75
    The authenticity of host '10.10.211.75 (10.10.211.75)' can't be established.
    ECDSA key fingerprint is SHA256:IfInK36B8n+YDXXigyUhyCGtnieDKiuKLjs6b6hXQ7Q.
    Are you sure you want to continue connecting (yes/no)? yes
    Warning: Permanently added '10.10.211.75' (ECDSA) to the list of known hosts.
    tryhackme@10.10.211.75's password: 
    Welcome to Ubuntu 20.04.2 LTS (GNU/Linux 5.4.0-1047-aws x86_64)

    * Documentation:  https://help.ubuntu.com
    * Management:     https://landscape.canonical.com
    * Support:        https://ubuntu.com/advantage

      System information as of Thu Feb 10 13:54:02 UTC 2022
    
      System load:  0.0               Processes:             110
      Usage of /:   27.6% of 7.69GB   Users logged in:       0
      Memory usage: 47%               IPv4 address for eth0: 10.10.211.75
      Swap usage:   0%





    The list of available updates is more than a week old.
    To check for new updates run: sudo apt update


    The programs included with the Ubuntu system are free software;
    the exact distribution terms for each program are described in the
    individual files in /usr/share/doc/*/copyright.
    
    Ubuntu comes with ABSOLUTELY NO WARRANTY, to the extent permitted by
    applicable law.
    
    tryhackme@linux3:~$ ls
    task3
    tryhackme@linux3:~$ nano task3
    tryhackme@linux3:~$ cat task3
    THM{TEXT_EDITORS}


## Utilidades generales/útiles

Use el módulo "HTTPServer" de Python 3 para iniciar un servidor web en el directorio de inicio del usuario 
"tryhackme" en la instancia implementada.

    tryhackme@linux3:~$ python3 -m http.server
    Serving HTTP on 0.0.0.0 port 8000 (http://0.0.0.0:8000/) ...
    10.10.211.75 - - [04/May/2021/14:26:09] "GET /file HTTP/1.1" 200 -

Descargue el archivo  http://10.10.211.75:8000/.flag.txt en el TryHackMe AttackBox

    tryhackme@linux3:/tmp# wget http://10.10.211.75:8000/file
    
    2021-05-04 14:26:16  http://10.10.211.75:8000/file
    Connecting to http://10.10.211.75:8000... connected.
    HTTP request sent, awaiting response... 200 OK
    Length: 51095 (50K) [text]
    Saving to: ‘file’
    
    file                    100%[=================================================>]  49.90K  --.-KB/s    in 0.04s
    
    2021-05-04 14:26:16 (1.31 MB/s) - ‘.flag.txt’ saved [51095/51095]

¿Cuáles son los contenidos?

    THM{WGET_WEBSERVER}

Cree y descargue archivos para aplicar aún más su aprendizaje; vea cómo puede leer la documentación en el módulo 
"HTTPServer" de Python3.
Use Ctrl + C para detener el módulo Python3 HTTPServer una vez que haya terminado.

## Procesos 101

Si tuviéramos que lanzar un proceso donde el ID anterior era "300", ¿cuál sería el ID de este nuevo proceso?

    301

Si quisiéramos matar limpiamente un proceso, ¿qué señal le enviaríamos?

    SIGTERM

Localice el proceso que se está ejecutando en la instancia implementada 10.10.211.75. ¿Qué bandera se da?


    tryhackme@linux3:~$ ps aux | less
    
    USER         PID %CPU %MEM    VSZ   RSS TTY      STAT START   TIME COMMAND
    root         711  0.0  0.1   2356   584 ?        S    13:42   0:00 THM{PROCESSES}

    THM{PROCESSES}

¿Qué comando usaríamos para detener el servicio "myservice"?

    systemctl stop myservice

¿Qué comando usaríamos para iniciar el mismo servicio en el arranque del sistema?

    systemctl enable myservice

¿Qué comando usaríamos para traer un proceso previamente en segundo plano al primer plano?

    fg

## Mantenimiento de su sistema: automatización


Asegúrese de estar conectado a la instancia implementada y mire los crontabs en ejecución.

    tryhackme@linux3:~$ crontab -e


¿Cuándo se ejecutará crontab en la instancia implementada ?

      GNU nano 4.8                                        /tmp/crontab.Pkjy6b/crontab                                                  
    # Edit this file to introduce tasks to be run by cron.
    # 
    # Each task to run has to be defined through a single line
    # indicating with different fields when the task will be run
    # and what command to run for the task
    # 
    # To define the time you can provide concrete values for
    # minute (m), hour (h), day of month (dom), month (mon),
    # and day of week (dow) or use '*' in these fields (for 'any').
    # 
    # Notice that tasks will be started based on the cron's system
    # daemon's notion of time and timezones.
    # 
    # Output of the crontab jobs (including errors) is sent through
    # email to the user the crontab file belongs to (unless redirected).
    # 
    # For example, you can run a backup of all your user accounts
    # at 5 a.m every week with:
    # 0 5 * * 1 tar -zcf /var/backups/home.tgz /home/
    # 
    # For more information see the manual pages of crontab(5) and cron(8)
    # 
    # m h  dom mon dow   command
    @reboot /var/opt/processes.sh


    @reboot

## Mantenimiento de su sistema: registros


Busque los registros de apache2 en la máquina Linux implementable

    tryhackme@linux3:~$ cd /var/log/apache2
    tryhackme@linux3:/var/log/apache2$ ls
    access.log  access.log.1  error.log  error.log.1  other_vhosts_access.log
    tryhackme@linux3:/var/log/apache2$ ls -l
    total 12
    -rw-r----- 1 root adm    0 Feb 10 13:42 access.log
    -rwxrwxrwx 1 root adm  209 May  4  2021 access.log.1
    -rw-r----- 1 root adm  688 Feb 10 13:42 error.log
    -rwxrwxrwx 1 root adm 2001 May  5  2021 error.log.1
    -rw-r----- 1 root adm    0 May  4  2021 other_vhosts_access.log
    tryhackme@linux3:/var/log/apache2$ 


¿Cuál es la dirección IP del usuario que visitó el sitio?

    tryhackme@linux3:/var/log/apache2$ less access.log.1

    10.9.232.111 - - [04/May/2021:18:18:16 +0000] "GET /catsanddogs.jpg HTTP/1.1" 200 51395 "-" "Mozilla/5.0 
    (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/90.0.4430.93 Safari/537.36"

    10.9.232.111

¿A qué archivo accedieron?


    10.9.232.111 - - [04/May/2021:18:18:16 +0000] "GET /catsanddogs.jpg HTTP/1.1" 200 51395 "-" "Mozilla/5.0 
    (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/90.0.4430.93 Safari/537.36"

    catsanddogs.jpg
