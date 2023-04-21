# OverTheWire Bandit Level 6 -> 7

## Login 

SSH: ```ssh bandit6@bandit.labs.overthewire.org -p 2220```

Password: ```P4L4vucdmLnm8I7Vl7jG1ApGSfjYKqJU```

## Code


``` 
find / -type f -size 33c -user bandit7 -group bandit6 2>/dev/null
```
### Usamos find pasandole varios argumentos:
```-type f``` : Archivos (file)

```-size 33c``` : Tamaño 33 bytes

```-user bandit``` : Propiedad del usuario bandit7

```-group bandit6``` :  Propiedad del grupo bandit7

El comando 
```2>/dev/null``` 
nos exceptua los mensajes de error por permiso denegado.

### Usamos cat para mostrar la password:

```
cat /var/lib/dpkg/info/bandit7.password
```

Nos devuelve:


```z7WtoNQU2XfjmMtWA8u5rN4vzqu4v99S```
