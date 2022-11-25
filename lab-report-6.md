# grade.sh run on web
* [My Grading Script](https://saintlucifur.github.io/cse15l-lab-reports/gradingscript.html)

student-submission: `*https://github.com/ucsd-cse15l-f22/list-methods-corrected*`

![Image](corrected.png)

```
rm -rf student-submission
git clone $1 student-submission
cd student-submission
```

`rm -f` is used to recursively remove the old student-submission directory without confirmation
`git clone` is used to clone the student directory taking an URL as a parameter
`cd` is used to go into the new student-submission directory we just cloned