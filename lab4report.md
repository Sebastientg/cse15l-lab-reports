# Lab 4 Report


**STEPS:** 

## Log into ieng6 -

I began by opening the terminal with my mouse pad. I then typed in `ssh` followed by my login `cs15lfa23fa@ieng6.ucsd.edu`. I then pressed `<enter>`. I then entered my password then pressed `<enter>` again. 
![Image](Step4.png)


## Clone your fork of the repository from your Github account (using the SSH URL)- 

With my mouspad I went over to the fork of the repository to copy and paste the ssh link for the terminal. I highlighted the link with my mouse and pressed `<Cmd-c>` to copy the link. I then went back over to VSCode and used the command `git clone` followed by `<Cmd-v>` to paste the ssh url. I then pressed `<enter>` to run the command. This overall terminal command was used to clone a repository onto my ieng6 account, considering my account was already a recognized host. 
![Image](ssh.png)

## Run the tests, demonstrating that they fail- 

I first typed out the command `ls` then `<enter>` to check if the correct repository was on my account. The then typed `cd` followed by `lab7` then pressed `<enter>`. This command put me in the correct directory to run tests. To run tests, I typed `bash test.sh` in the terminal followed by the key `<enter>`. The command ran the proper tests and displayed the failures.  
![Image](failtest.png)

## Edit the code file to fix the failing test-

I started off editing the ListExamples.java file. To edit the file, I used the terminal to run the command `vim ListExamples.java`. This opened the text editor. Then, I typed `/index1` to search for the first occurrence of index1 in the file and then pressed `<enter>`. After, I typed `<n>` until I reached the last while occurrence of index1. I then typed `<i>` to enter insert mode in vim. I pressed the `<right>` arrow key six times so that I can `<backspace>` the number 1. Then I pressed the number key `<2>` on my keyboard to create the change. I then pressed `<esc>` followed by `:wq` and `<enter>` to save the edits made and exit out of vim. 
![Image](vim.png)
![Image](edits.png)
![Image](quit.png)

## Run the tests, demonstrating that they now succeed-

To run the tests, I typed the command `bash test.sh`. I then pressed `<enter>`. This command was a bash command that would run JUnit tests from the bash file. The tests now show that they pass.  
![Image](pass.png)


## Commit and push the resulting change to your Github account (you can pick any commit message!)- 

I first typed in the command `git add ListExamples.java` then pressed `<enter>`. 
![Image](add.png)

I then typed in the command `git commit ListExamples.java` then pressed `<enter>`. This would prepare the changes to be sent off to GitHub. I was then prompted to vim to add a message. 
![Image](commit.png)

Once I was in vim, I typed the key `<i>` to enter instert mode. I then typed the message "ListExamples files has been changed." Afterwards, I hit the `<esc>` key to exit insert mode. I then, typed `:wq` followed by `<enter>` to save and quit vim. I was then prompted back to the terminal with a new mesage. 
![Image](message.png)
![Image](after.png)

I then typed the command `git push` and pressed `<enter>` to send off my edits to be changed in GitHub. This would therefore update my Lab7 repository that was forked. 
![Image](push.png)
