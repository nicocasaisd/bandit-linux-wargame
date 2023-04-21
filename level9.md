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

```
ls > myoutput
```

The way the mechanism works, the file is created first (if it does not exist already) and then the program is run and output saved into the file.

We can instead get the new data to be appended to an existing file by using the double greater than operator ( >> ).

```
ls >> myoutput
```

* Redirecting from a File

If we use the less than operator ( < ) then we can send data the other way. We will read data from the file and feed it into the program via it's STDIN stream.

```
wc -l < myoutput
```

* Redirecting STDERR

STDERR is stream number 2 and we may use these numbers to identify the streams. If we place a number before the > operator then it will redirect that stream (if we don't use a number, like we have been doing so far, then it defaults to stream 1).

```
ls -l video.mpg blah.foo 2> errors.txt
```

* Piping
Piping is a mechanism for sending data from one program to another. The operator we use is ( | ).
What this operator does is feed the output from the program on the left as input to the program on the right.

``` 
grep [OPTION...] PATTERNS [FILE...]
```

* Usamos grep para encontrar la línea que contiene la palabra 'milliionth'


* Nos devuelve:

```

```

``````
