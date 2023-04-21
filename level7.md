# OverTheWire Bandit Level 6 -> 7 - Walkthrough 

## Login 

SSH: ```ssh bandit6@bandit.labs.overthewire.org -p 2220```

Password: ```P4L4vucdmLnm8I7Vl7jG1ApGSfjYKqJU```

## Code


``` 
find / -type f -size 33c -user bandit7 -group bandit6 2>/dev/null
cat /var/lib/dpkg/info/bandit7.password
```
