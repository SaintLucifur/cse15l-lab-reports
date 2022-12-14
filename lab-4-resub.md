## find commman-line options
find *-type f*
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
* This command option will only list files but not directories. That's why the biomed directory or "." is not shown here. This would be useful if the output needs to be piped into grep and grep won't have to deal with directories.

find *-type d*
```
[cs15lfa22qq@ieng6-201]:technical:358$ find -type d
.
./911report
./biomed
./government
./government/About_LSC
./government/Alcohol_Problems
./government/Env_Prot_Agen
./government/Gen_Account_Office
./government/Media
./government/Post_Rate_Comm
./plos
```

* This command option will only list directories but not files. That's why no .txt files are shown here.

find *-prune*
```
[cs15lfa22qq@ieng6-201]:technical:409$ find * -prune
911report
biomed
government
notInDirFile.txt
plos
```

* This command option will not descend into any directories as opposed to what find normally does.