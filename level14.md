# OverTheWire Bandit Level 13 -> 14

## Login 

SSH: ```ssh bandit13@bandit.labs.overthewire.org -p 2220```

Password: ```wbWdlBxEir4CaE8LaPhauuOo6pwRmrDw```

## Code


``` 
ver abajo

```

## Miramos los permisos de los archivos

```
ls -l /etc/bandit_pass/

cat ~/sshkey.private 
```


## Login por ssh usando identity-file

Until now, we have only logged into the remote machine using ssh with a password. An alternative to a password is using public-key cryptography. The public key is placed on the computers that should allow access (the remote host) to the user that owns the private key. Like with the password, it is important that only the user knows/owns the private key. The -i flag allows login with the private key.

## Obtener la key usando scp

* Sintaxis del comando scp

``` 
scp -P <port> <user>@<IP>:<remotefilepath> <localfilepath>
```
Desde nuestro ordenador ejecutamos el comando:

``` 
scp -P 2220 bandit13@bandit.labs.overthewire.org:sshkey.private .
```

Y así obtenemos el archivo ```sshkey.private```.

Además, debemos cambiar los permisos del archivo porque sino nos tira un error por estar demasiado abierto.

```
chmod 700 sshkey.private
```

## Login usando ssh -i

Nos logueamos usando el identity file. Para eso debemos ejecutar la bandera -i que nos habilita a usar un archivo de identidad.
```
ssh -i sshkey.private bandit14@bandit.labs.overthewire.org -p 2220
```

Y así ingresamos al servidor. :)
