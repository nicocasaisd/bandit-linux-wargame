# OverTheWire Bandit Level 17 -> 18

## Login 

Ingresamos usando un Identity File que obtuvimos en el nivel anterior

SSH: ```ssh -i sshkey17.private bandit17@bandit.labs.overthewire.org -p 2220```


## Tarea
There are 2 files in the homedirectory: passwords.old and passwords.new. The password for the next level is in passwords.new and is the only line that has been changed between passwords.old and passwords.new

## Teoría


## Code


``` 
diff passwords.old passwords.new
42c42
< glZreTEH1V3cGKL6g4conYqZqaEj0mte
---
> hga5tuuCLF6fFzUpnagiMN8ssu9LFrdg
```


Y así ingresamos obtenemos la contraseña del siguiente nivel. :)


