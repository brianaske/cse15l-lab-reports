# Lab Report 4
## Tasks in competition
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
    
    find the bug and fix it. (in the last while loop: `index1+=1` should be `index2+=1`)
    
    <img width="222" alt="image" src="https://user-images.githubusercontent.com/57138953/221769285-f334c278-4e6e-4665-bf30-1e540de1ff6f.png">
    
6. Run the tests, demonstrating that they now succeed
    
    `$ javac -cp ".:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar" *.java` - compile files (use `<ctrl>+c and <ctrl>+v` to copy and paste from resource)
    
    `$ java -cp ".:lib/junit-4.13.2.jar:lib/hamcrest-core-1.3.jar" org.junit.runner.JUnitCore TestListExamples` - run tests (use `<ctrl>+c and <ctrl>+v` to copy and 
    
    <img width="757" alt="image" src="https://user-images.githubusercontent.com/57138953/221770345-58598007-3d4c-4fe6-89b0-fd542f291f8d.png">

7. Commit and push the resulting change to your Github account (you can pick any commit message!)
        
    `$ git add ListExamples.java`, `$ git add ListExamples.java`, `git push` - commit and push the change to online respository
    <img width="403" alt="image" src="https://user-images.githubusercontent.com/57138953/221771928-34b2df43-cda0-4786-a6e9-646cf91b2666.png">

