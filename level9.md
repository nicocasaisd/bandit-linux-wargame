# OverTheWire Bandit Level 8 -> 9

## Login 

SSH: ```ssh bandit8@bandit.labs.overthewire.org -p 2220```

Password: ```TESKZC0XvTetK0S9xNwm25STk5iWrBvP```

## Code


``` 
grep -n millionth data.txt
```

## Piping and Redirecting

Piping and redirection is the means by which we may connect these streams between programs and files to direct data in interesting and useful ways.

* Redirecting to a File

The greater than operator ( > ) indicates to the command line that we wish the programs output (or whatever it sends to STDOUT) to be saved in a file instead of printed to the screen.

The way the mechanism works, the file is created first (if it does not exist already) and then the program is run and output saved into the file.

We can instead get the new data to be appended to an existing file by using the double greater than operator ( >> ).

* Redirecting from a File



``` 
grep [OPTION...] PATTERNS [FILE...]
```

* Usamos grep para encontrar la línea que contiene la palabra 'milliionth'


* Nos devuelve:


``````
