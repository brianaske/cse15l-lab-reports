# Lab Report 5
## Tasks in competition (Lab Report 4 content)
1. Log into ieng6

    `$ ssh cs15lwi23apu@ieng6.ucsd.edu`
    
    <img width="403" alt="image" src="https://user-images.githubusercontent.com/57138953/221766706-110b128d-a692-4837-aaee-ab297cc8dce7.png">

2. Clone your fork of the repository from your Github account
    
    `$ git clone git@github.com:brianaske/lab7.git`
    
    <img width="422" alt="image" src="https://user-images.githubusercontent.com/57138953/221767232-23264852-4371-4ff7-8945-5bc17a656255.png">

3. Run the tests, demonstrating that they fail

    `$ cd lab7/`: type l and press `<tab>` . Terminal will show `lab7/`
    
    `$ javac -cp ".:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar" *.java` - compile files (use `<ctrl>+c and <ctrl>+v` to copy and paste from resource)
    
    `$ java -cp ".:lib/junit-4.13.2.jar:lib/hamcrest-core-1.3.jar" org.junit.runner.JUnitCore TestListExamples` - run tests (use `<ctrl>+c and <ctrl>+v` to copy and paste from resource)
    
    <img width="787" alt="image" src="https://user-images.githubusercontent.com/57138953/221768470-c75978a5-cf8d-4049-a816-515e3ad92281.png">
    
4. Edit the code file to fix the failing test
    
    `$ nano ListExamples.java` - open and ready to edit the file`
    
    find the bug press,by pressing < down > for 42 times and < right > to locate the bug, and fix it. (in the last while loop: `index1+=1` should be `index2+=1`)
    Press <ctrl>+O to write out, <enter> to save, < ctrl >+x to exit.
    
    <img width="222" alt="image" src="https://user-images.githubusercontent.com/57138953/221769285-f334c278-4e6e-4665-bf30-1e540de1ff6f.png">
    
6. Run the tests, demonstrating that they now succeed
    
    `$ javac -cp ".:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar" *.java` - compile files (use `<ctrl>+c and <ctrl>+v` to copy and paste from resource or press < up > for three times.)
    
    `$ java -cp ".:lib/junit-4.13.2.jar:lib/hamcrest-core-1.3.jar" org.junit.runner.JUnitCore ListExamplesTests` - run tests (use `<ctrl>+c and <ctrl>+v` to copy and paste from resource or press < up > for three times.) 
    
    <img width="757" alt="image" src="https://user-images.githubusercontent.com/57138953/221770345-58598007-3d4c-4fe6-89b0-fd542f291f8d.png">

7. Commit and push the resulting change to your Github account (you can pick any commit message!)
        
    `$ git add ListExamples.java`, `$ git commit -m "Updated"`, `git push` - commit and push the change to online respository
    <img width="456" alt="image" src="https://user-images.githubusercontent.com/57138953/224529368-381326d9-84dd-49d5-96ec-d06a49f006d8.png">

## Put all the thing into one file

1. create a bash file named command.sh as follows:
    ````
    ```
    git clone git@github.com:brianaske/lab7.git && cd lab7/ && sed -i '43s/index1 += 1/index2 += 1/' ListExamples.java 
    && javac -cp ".:lib/hamcrest-core-       1.3.jar:lib/junit-4.13.2.jar" *.java 
    && java -cp ".:lib/junit-4.13.2.jar:lib/hamcrest-core-1.3.jar" org.junit.runner.JUnitCore ListExamplesTests 
    && git add ListExamples.java && git commit -m "Updated" && git push && cd.. && rm -rf lab7/
    ```
    ````
2. type `bash command.sh` in terminal
    
    <img width="455" alt="image" src="https://user-images.githubusercontent.com/57138953/224614108-34e51e0e-8eca-4dbc-a521-ee1ce531cc1a.png">


