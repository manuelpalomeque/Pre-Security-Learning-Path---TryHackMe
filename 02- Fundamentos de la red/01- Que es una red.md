## Identificación de dispositivos en una red:

¿Qué significa el término "IP"?

    Internet Protocol

¿Cómo se llama cada sección de una dirección IP?

    Octeto

¿Cuántas secciones tiene una dirección IP? 

    4

¿Qué significa el término "MAC"?

    Media Access Control


Implemente el laboratorio interactivo con el botón "Ver sitio" y falsifique su dirección MAC para acceder al sitio. 
¿Qué es la bandera?

    Mediante la suplantacion de direcciones MAC, utilice una MAC que si tiene acceso, para lograr enviar paquetes
    
    THM{YOU_GOT_ON_TRYHACKME}

## Hacer ping (ICMP):
Hacer ping a la dirección de " 8.8.8.8 " en el sitio web desplegable en esta tarea. Hacer ping a la dirección correcta 
revelará una bandera para responder a la siguiente pregunta a continuación.

    user@thm:~$ ping -c 4 8.8.8.8
    PING 8.8.8.8 (8.8.8.8) 56(84) bytes of data
    64 bytes from 8.8.8.8: icmp_seq=1 ttl=56 time=9.15 ms
    64 bytes from 8.8.8.8: icmp_seq=1 ttl=56 time=9.69 ms
    64 bytes from 8.8.8.8: icmp_seq=1 ttl=56 time=8.55 ms
    64 bytes from 8.8.8.8: icmp_seq=1 ttl=56 time=7.36 ms
    --- 8.8.8.8 ping statistics ---
    4 packets transmitted, 4 received, 0% packet loss, time 4006ms
    rtt min/avg/max/mdev = 8.132/9.428/10.957/1.057 ms
    Flag: THM{I_PINGED_THE_SERVER}

-c 4: determina la cantidad de paquetes enviados

¿Qué protocolo utiliza ping?

    ICMP (Internet Control Message Protocol)

¿Cuál es la sintaxis para hacer ping 10.10.10.10?

    ping 10.10.10.10

¿Qué bandera obtienes cuando haces ping a 8.8.8.8?

    THM{I_PINGED_THE_SERVER}