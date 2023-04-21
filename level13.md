# OverTheWire Bandit Level 12 -> 13

## Login 

SSH: ```ssh bandit12@bandit.labs.overthewire.org -p 2220```

Password: ```JVNBBFSmZwKKOP0XbFXOoW8chDz5yVRv```

## Code


``` 
ver abajo

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
Podemos buscar a qué tipo de archivo corresponde en una lista como [esta].(https://en.wikipedia.org/wiki/List_of_file_signatures)

```
1f 8b
```
Encontramos que esto pertenece a un archivo comprimido con GZIP.

Lo descomprimimos usando 
```
gzip -d compressed_data.gz
```

Como sigue siendo ilegible, asumimos que se encuentra comprimido otra vez.
Hacemos un Hexadump para ver nuevamente de qué tipo de archivo se trata.
```
xxd compressed_data 
```
Y vemos que los caracteres ``` 42 5A 68 ``` coinciden con el tipo de archivo Bzip2, otro compresor.

# Empieza una ronda de descompresiones de muchos formatos

```
bzip2 -d compressed_data
xxd compressed_data.out
mv compressed_data.out compressed_data.gz
gzip -d compressed_data.gz 
mv compressed_data compressed_data.tar
tar -xf compressed_data.tar
tar -xf data5.bin 
bzip2 -d data6.bin
tar -xf data6.bin.out
cp data8.bin data8.gz
gzip -d data8.gz
cat data8

```



# Output Password

```
wbWdlBxEir4CaE8LaPhauuOo6pwRmrDw
```

``````
