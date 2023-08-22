# OverTheWire Bandit Level 15 -> 16

## Login 

SSH: ```ssh bandit15@bandit.labs.overthewire.org -p 2220```

Password: ```jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt```

## Tarea
The password for the next level can be retrieved by submitting the password of the current level to port 30001 on localhost using SSL encryption.

## Teoría
The SSL protocol operates between the application layer and the TCP/IP layer. This allows it to encrypt the data stream itself, which can then be transmitted securely, using any of the application layer protocols. 

OpenSSL is a library for secure communication over networks. It implements the Transport Layer Security (TLS) and Secure Sockets Layer (SSL) cryptographic protocols that are, for example, used in HTTPS to secure the web traffic.

openssl s_client is the implementation of a simple client that connects to a server using SSL/TLS.

Para establecer una conexión con el puerto 30000 utilizamos el comando  ```nc``` que nos permite realizar la conexión entre
redes utilizando un protocolo TCP o UDP.
La sintaxis básica del comando es:


## Code


``` 
openssl s_client -connect localhost:30001
...
jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt
Correct!
JQttfApK4SeyHwDlI9SXGR50qclOAil1


```


Y así ingresamos obtenemos la contraseña del siguiente nivel. :)


