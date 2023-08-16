# FS Discovery
Using the find command, find and list the names of:
## all files under the /etc directory whose names begin with rc 
```bash
find /etc/ -type f -name 'rc*'
```
## all regular files belonging to you; put the result in the file /tmp/findme and errors in/dev/null
```bash
find /etc/ -type f -user $(whoami) > /tmp/findme 2>/dev/null
``` 
## all subdirectories of /etc
```bash
find /etc/ -type d
```
## all regular files under your home directory that have not been modified in the last 10 days
```bash
find ~/ -type f -mtime +10
```
## The 10 largest file in your computer
```bash
find / -type f -exec du -h {} + | sort -rh | head -n 10
``````
