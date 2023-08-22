# OverTheWire Bandit Level 14 -> 15

## Login 

SSH: ```ssh bandit14@bandit.labs.overthewire.org -p 2220```

Password: ```fGrHPx402xGC7U7rXKDaxiWFTOiF0ENq```

## Tarea
The password for the next level can be retrieved by submitting the password of the current level to port 30000 on localhost.

## Teoría
Para establecer una conexión con el puerto 30000 utilizamos el comando  ```nc``` que nos permite realizar la conexión entre
redes utilizando un protocolo TCP o UDP.
La sintaxis básica del comando es:

```nc <host> <port>```


## Code


``` 
nc localhost 30000
fGrHPx402xGC7U7rXKDaxiWFTOiF0ENq
Correct!
jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt

```



Y así ingresamos obtenemos la contraseña del siguiente nivel. :)


