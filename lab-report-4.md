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

## less commman-line options
less *-N*
```
[cs15lfa22qq@ieng6-201]:biomed:426$ less -N cc2190.txt
      1
      2
      3
      4
      5         Introduction
      6         Enteral nutrition is increasingly being recognized as an
      7         integral component in the management of critically ill
      8         patients, having a major effect on morbidity and outcome.
      9         Early enteral nutrition has been demonstrated to improve
     10         nitrogen balance, wound healing and host immune function,
     11         and to augment cellular antioxidant systems, decrease the
     12         hypermetabolic response to tissue injury and preserve
     13         intestinal mucosal integrity [ 1 2 3 4 5 6 7 ] . In a
     14         previous study [ 8 ] , we reported that initiation of
     15         enteral nutrition within 36 hours of surgery or admission
     16         to hospital reduces infectious complications and hospital
     17         length of stay (LOS).
     18         These data suggest that enteral nutrition should be
     19         initiated as soon as possible after admission to the
     20         intensive care unit (ICU). Although the gastric route of
     21         enteral feeding is easier to achieve and cheaper than
     22         post-pyloric nutrient administration, many clinicians worry
cc2190.txt
```

* This commmand option will display the line number while reading the text.

less *-X*
```
[cs15lfa22qq@ieng6-201]:biomed:429$ less -X cc2190.txt




        Introduction
        Enteral nutrition is increasingly being recognized as an
        integral component in the management of critically ill
        patients, having a major effect on morbidity and outcome.
        Early enteral nutrition has been demonstrated to improve
        nitrogen balance, wound healing and host immune function,
        and to augment cellular antioxidant systems, decrease the
        hypermetabolic response to tissue injury and preserve
        intestinal mucosal integrity [ 1 2 3 4 5 6 7 ] . In a
        previous study [ 8 ] , we reported that initiation of
        enteral nutrition within 36 hours of surgery or admission
        to hospital reduces infectious complications and hospital
        length of stay (LOS).
        These data suggest that enteral nutrition should be
        initiated as soon as possible after admission to the
        intensive care unit (ICU). Although the gastric route of
        enteral feeding is easier to achieve and cheaper than
        post-pyloric nutrient administration, many clinicians worry
[cs15lfa22qq@ieng6-201]:biomed:430$
```
* This command option will keep the less content on terminal after exiting.

less *-p*
```
[cs15lfa22qq@ieng6-201]:biomed:444$ less -p "and" -X -N cc1856.txt
      8         oxygen delivery and countercurrent microcirculation of the
      9         villi [ 1]. There is increasing evidence that
     10         gastrointestinal hypoperfusion plays an important role in
     11         development of systemic inflammatory response and multiple
     12         organ failure [ 1, 2]. Decreased splanchnic perfusion
     13         precedes the appearance of the usual indicators of
     14         hypovolemic shock, such as hypotension and lactic acidosis
     15         [ 3, 4, 5]. Gastric intramucosal acidosis and hypercapnia
     16         are observed during inadequate organ perfusion [ 6, 7, 8]
     17         and are predictive of poor clinical outcome [ 9, 10, 11].
     18         Therefore, early detection of gastrointestinal
     19         hypoperfusion and effective treatment may improve clinical
     20         outcome. Because gastric intubation is done in most
     21         critically ill patients, gastric tonometry has
     22         traditionally been used to evaluate intramucosal pH or
     23         partial carbon dioxide tension (P CO
     24         2 ) indirectly during the management of
     25         critically ill patients [ 9, 10, 11, 12, 13, 14, 15].
     26         However, gastric tonometers have some limitations. For
     27         example, air and saline tonometers may require 10-90 min
     28         for equilibration [ 16, 17, 18, 19]. Reliable gastric
     29         tonome-try requires suppression of gastric acid [ 20],
cc1856.txt
```

* This command will display the text starting with the pattern given after -p