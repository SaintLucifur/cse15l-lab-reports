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

## grep commman-line options
grep *-n*
```
[cs15lfa22qq@ieng6-201]:technical:414$ grep -n "why" ./plos/*
./plos/journal.pbio.0020001.txt:107:        important question, however, is why the number of publications per dollar invested in   
./plos/journal.pbio.0020012.txt:118:        saying that it's not possible in people because I don't see why it wouldn't be…. I'm    
./plos/journal.pbio.0020013.txt:96:        family, a fundamental question can be raised: why does a proteolytic enzyme like the     
./plos/journal.pbio.0020028.txt:195:        people are surprised at how complicated it is, but why should it be any other way? It's an
// more output ...
```
* This command option will print out which line in the text matches the argument.

grep *-c*
```
[cs15lfa22qq@ieng6-201]:technical:416$ grep -c "why" ./plos/*
./plos/journal.pbio.0020001.txt:1
./plos/journal.pbio.0020010.txt:0
./plos/journal.pbio.0020012.txt:1
./plos/journal.pbio.0020013.txt:1
./plos/journal.pbio.0020019.txt:0
./plos/journal.pbio.0020028.txt:1
./plos/journal.pbio.0020035.txt:0
./plos/journal.pbio.0020040.txt:0
./plos/journal.pbio.0020042.txt:1
./plos/journal.pbio.0020043.txt:6
// more output ...
```

* This command option will count how many matches there are in each text.

grep *-i*
```
[cs15lfa22qq@ieng6-201]:technical:420$ grep -i "why" ./plos/*
./plos/journal.pbio.0020001.txt:            Why has the number of publications per dollar invested in research and
./plos/journal.pbio.0020001.txt:        important question, however, is why the number of publications per dollar invested in       
./plos/journal.pbio.0020001.txt:        they are the exception. Why, in general, do Latin American scientists often fail to reach   
./plos/journal.pbio.0020012.txt:        saying that it's not possible in people because I don't see why it wouldn't be…. I'm        
./plos/journal.pbio.0020013.txt:        family, a fundamental question can be raised: why does a proteolytic enzyme like the        
./plos/journal.pbio.0020028.txt:        people are surprised at how complicated it is, but why should it be any other way? It's an  
./plos/journal.pbio.0020042.txt:        would generate a short document highlighting why its expertise might be suitable for a      
./plos/journal.pbio.0020043.txt:        What could possibly be going on here? Why should scale insects, of all creatures, have      
./plos/journal.pbio.0020043.txt:        explain why obligate sibling chimerism never evolves (except perhaps in the very limited  
// more output ...
```

* This command option will ignore uppercase and lowercase, and output them all. That's why when I search for "why", both "Why" and "why" show up.