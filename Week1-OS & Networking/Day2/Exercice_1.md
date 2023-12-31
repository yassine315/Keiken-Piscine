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
## Q4 : Display localhost information from the /etc/hosts file, display the line number(s) matching the search string and count the number of occurrences of the string.
```bash
grep 'localhost' /etc/hosts
```
```bash
grep -n 'localhost' /etc/hosts
```
```bash
grep -o 'localhost' /etc/hosts | wc -l
```
## Q5 : Display a list of /usr/share/doc subdirectories containing information about shells.
```bash
find /usr/share/doc -type d -name "*shell*"
```
## Q6 : How many README files do these subdirectories contain? Don't count anything in the form of "README.a_string".
## Q7 : Make a list of files in your home directory that were changed less that 10 hours ago, using grep, but leave out directories.
```bash
find /Users/mac -type f -mmin -6 ! -type d
```
## Q8 : Can you find an alternative for wc -l, using grep?
```bash
grep -c 
```
## Q9 : Using the file system table (/etc/fstab for instance), list local disk devices.
```bash
awk '$3 ~ /^\/(mnt|media|mountpoint)$/ && $1 !~ /^#/ { print $1 }' /etc/fstab
```
## Q10 : Display configuration files in /etc that contain numbers in their names.
```bash
find /etc -type f -name '*[0-9]*'
```