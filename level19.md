# OverTheWire Bandit Level 18 -> 19

## Login 

SSH: ```ssh bandit16@bandit.labs.overthewire.org -p 2220```

Password: ```hga5tuuCLF6fFzUpnagiMN8ssu9LFrdg```


## Tarea
The password for the next level is stored in a file readme in the homedirectory. Unfortunately, someone has modified .bashrc to log you out when you log in with SSH.

## Primera Aproximación

El archivo .bashrc se carga cada vez que un usuario ejecuta Bash. Cuando Bash inicia una Shell bash (Bourne-again shell), la Shell primero lee el archivo /etc/bashrc o /etc/bash.bashrc (según que distribución utilicemos) y luego el archivo ~/.bashrc del usuario que ejecuta Bash.
Es un archivo ubicado en el HOME de cada usuario de la computadora.
Para obtener el archivo utilizamos el comando scp de la siguiente manera:

``` 
scp -P 2220 bandit18@bandit.labs.overthewire.org:.bashrc .
``` 

Ejecutamos el comando diff para comparar con nuestro propio archivo .bashrc y obtenemos lo siguiente:
``` 
diff .bashrc ~/.bashrc 
118,119c118,133
< echo 'Byebye !'
< exit 0
---
``` 

Vemos que el archivo ha sido modificado para salirse al final de la ejecucion de la configuración de bash.

## A little bit of Theory

‘.bashrc’ is a file that is run every time a terminal is loaded. This means it is also run when logging in through SSH because this also loads a terminal.

In the walkthrough to Level 0 I have given a short introduction to SSH. Something I have not mentioned is that SSH does not just allows us to log into a machine remotely, but it also allows remote execution of commands by adding the commands after the common SSH expression.


## Code


``` 
ssh bandit18@bandit.labs.overthewire.org -p 2220 ls

ssh bandit18@bandit.labs.overthewire.org -p 2220 cat readme

bandit18@bandit.labs.overthewire.org's password: 
Authenticated to bandit.labs.overthewire.org ([16.16.8.216]:2220).
awhqfNnAbc1naukrpqDYcF95h7HoMTrC
Transferred: sent 2152, received 3100 bytes, in 0.8 seconds
Bytes per second: sent 2652.5, received 3821.0

```


Y así ingresamos obtenemos la contraseña del siguiente nivel. :)


