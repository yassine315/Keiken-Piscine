# Hands on Awk & Sed / POSIX
## Q1 : Give the AWK script that displays the word frequency of a text.
create a file script1.awk with this centent : 
```bash
{
    for (i=1; i<=NF; i++) {
        word = $i
        gsub(/[[:punct:]]/, "", word)  
        if (word != "") {
            words[word]++
        }
    }
}

END {
    for (word in words) {
        print word, words[word]
    }
}
```
and run this command : 
```bash
awk -f script1.awk /etc/passwd
```
## Q2 : Create an AWK script that show the number of repetition of a specific string in a list of strings
create a script script2.awk
```bash
BEGIN {
    target = ARGV[1]
    delete ARGV[1]
    count = 0
}

{
    for (i=1; i<=NF; i++) {
        if ($i == target) {
            count++
        }
    }
}

END {
    print "The string \"" target "\" appears " count " times."
}
```
## Q3 : Given a list of telephone numbers of the form 123456789 use sed to rewrite them as (123)456-789.
using this regex
```bash
's/\([0-9]\{3\}\)\([0-9]\{3\}\)\([0-9]\{3\}\)/(\1)\2-\3/'
```
## Q4 : Use sed to extract full user names from /etc/passwd

```bash
sed -n 's/^[^:]*:[^:]*:[^:]*:[^:]*:[^:]*:\([^:]*\).*/\1/p' /etc/passwd
```