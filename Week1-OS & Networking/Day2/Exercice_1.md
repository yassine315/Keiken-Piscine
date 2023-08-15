# Hands on regular expressions
## Q1 : Display a list of all the users on your system who log in with the Bash shell as a default.
```bash
grep -E '.*:.*:/bin/bash' /etc/passwd
```
## Q2 : From the /etc/group directory, display all lines starting with the string "daemon".
```bash
grep -E '^daemon' /etc/group
```
## Q3 : Print all the lines from the same file that don't contain the string.
```bash
grep -vE '^daemon' /etc/group
```

