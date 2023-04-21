# OverTheWire Bandit Level 12 -> 13

## Login 

SSH: ```ssh bandit12@bandit.labs.overthewire.org -p 2220```

Password: ```JVNBBFSmZwKKOP0XbFXOoW8chDz5yVRv```

## Code


``` 


```

## Archivos Hexdumps

Hexdumps are often used when we want to look at data that cannot be represented in strings and therefore is not readable, so it is easier to look at the hex values. A hexdump has three main columns. The first shows the address, the second the hex representation of the data on that address and the last shows the actual data as strings (with ‘.’ being hex values that cannot be represented as a string).

## Crear directorio, mover y renombrar

``` 
mkdir /tmp/nico
cp -v data.txt /tmp/nico/data.txt
cd /tmp/nico
mv data.txt hexdump_data
```

* Mostramos la data hexadecimal

``` 
cat hexdump_data
```

Los primeros caracteres corresponden a la firma del archivo.
Podemos buscar a qué tipo de archivo corresponde en una lista como [esta](https://en.wikipedia.org/wiki/List_of_file_signatures)

```
1f 8b
```



# Output Password

```
JVNBBFSmZwKKOP0XbFXOoW8chDz5yVRv
```

``````
