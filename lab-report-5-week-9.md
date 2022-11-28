Below is the grade.sh script.
``` 
# Create your grading script here


rm -rf student-submission
git clone $1 student-submission

echo "Sucessfully Cloned"

if [ -f ./student-submission/ListExamples.java ]
then
    echo "File Found."
else
    echo "Wrong File Submitted."
    exit 1
fi

cd student-submission/


javac -cp .:../lib/hamcrest-core-1.3.jar:../lib/junit-4.13.2.jar *.java 2

if [[ $? -eq 0 ]]
then
  echo "Compiled."
else
  echo "Compile Error."
  exit 1
fi

rm -rf out.txt
java -cp .:../lib/hamcrest-core-1.3.jar:../lib/junit-4.13.2.jar org.junit.runner.JUnitCore TestListExamples > out.txt

JunitExitCode=$?

if [[ $JunitExitCode -eq 0 ]]
then
  echo "Tests PASSED."
else
  a=`cat out.txt`
  echo "Some test FAILED: " $a
  exit 1
fi
```

![Image](/lab5/corrected.png)
![Image](/lab5/compile-error.png)
![Image](/lab5/unedited.png)

Trace error for compile error example which is the second screeshot:
First, remove student submission folder and git clone the repository. If cloned successfully, we print the message "Sucessfully Cloned" and the exit code is 0 and the  output is the standard output. If not sucessful, the exit code is nonzero and the error message goes into standard error. Then, check the if condition whether ListExamples.java file exists. If it exists, we print “File Found.”; If not, we print “Wrong File Submitted” to give the student hints about what they have done wrong, and then we exit the grade.sh. After that, we change directory as we go into student-submission. Then, we javac to compile the file. If the exit code of the last executed command is 0 meaning that the file successfully compile. If the exit code is non-zero, then the file fails to compile and we will print “compile error”, then we exit the program by setting the exit code to be 1, so it wouldn’t continue latter lines in grade.sh. In this example, the file doesn’t successfully compile. 