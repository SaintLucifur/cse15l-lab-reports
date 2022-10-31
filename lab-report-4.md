## find commman-line options
* find *-type f*
```
[cs15lfa22qq@ieng6-201]:biomed:337$ find -type f -name "*.txt"
./1468-6708-3-1.txt
./1468-6708-3-10.txt
./1468-6708-3-3.txt
./1468-6708-3-4.txt
./1468-6708-3-7.txt
./1471-2091-2-10.txt
./1471-2091-2-11.txt
./1471-2091-2-12.txt
./1471-2091-2-13.txt
// more output ...
```
* This command option will only list files but not directories. That's why the biomed directory or "." is not shown here. This would be useful if the output needs to be piped into grep and grep won't have to deal with directories