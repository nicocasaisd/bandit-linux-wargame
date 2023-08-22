# OverTheWire Bandit Level 16 -> 17

## Login 

SSH: ```ssh bandit16@bandit.labs.overthewire.org -p 2220```

Password: ```JQttfApK4SeyHwDlI9SXGR50qclOAil1```

## Tarea
The credentials for the next level can be retrieved by submitting the password of the current level to a port on localhost in the range 31000 to 32000. First find out which of these ports have a server listening on them. Then find out which of those speak SSL and which don’t. There is only 1 server that will give the next credentials, the others will simply send back to you whatever you send to it.

## Teoría
Port scanning is a method to find open ports on a host. A port can be seen as an address for a specific service. Every computer has ports with the numbers 0 to 65535. Some services have standard ports, like HTTP/80 or SSH/22. An open port means that the host offers a service to the network on this port.

Nmap is a network scanner. It can do Host Discovery, Port Scanning, Version Detection (Service Detection) and a lot more. For this task, the -p flag is important. This flag lets us choose which ports to scan. By default, Nmap scans the top 1000 ports (not the first 1000 ports). Use -p- to scan all 65535 ports. The -sV flag lets us do a service/version detection scan. It is possible to make Nmap perform all possible scans with the -A flag this will take a while though. A full scan would have the following command: nmap -p- -A <host>, where <host> could be either an IP address or the name.

This level also uses SSL again, which was described in Level 16.


## Code


``` 
nmap -sV localhost -p 31000-32000

openssl s_client -connect localhost:31790

```


Lo que nos devuelve el puerto 31790 es el contenido de un archivo de identidad que debemos guardar en nuestra máquina local.
Creamos el archivo sshkey17.private, le copiamos el contenido que obtuvimos y cambiamos los permisos del archivo para que sea una identidad válida.


