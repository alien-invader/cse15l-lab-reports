## Lab Vim
### Part 1
#### Changing the name of the start parameter and its uses to base

Our method has 23 keystrokes:
```:12,26s/start/base g<Enter>:w<Enter>```

At first, we decided to use `:%s/start/base/g` where we can find each occurrence of ‘start’ (in all lines), and replace it with ‘base’. Then we realized that we would also changed Server.start to Server.base which we don’t want it to happen because we only want to change the name of the start parameter of getFiles, and all of its uses. We then decided to specify the range of lines that we want to change the parameter name. 

Looking at it step by step:

```:12,26s/start/base g``` takes us to our first instance of start in the code between line 12 and line 26 as we specified in the command. It would substitue "start" by "base". The command follows the pattern :[range]s/{pattern}/{string}/[flags] [count]

1. ```:12,26s```
This character indicates a range from the 12th line to the 26th line of the file. The range is inclusive, which means that the first and last lines are included in the range. If I want to search and replace the pattern in the entire file, use the percentage character % as a range. When no range is specified the substitute command operates only in the current line.

2. ```/start/base```
This part searches for the occurrences of the string 'start' and replace it with 'base'. The substitute command looks for the pattern as a string, not a whole word. By default, the search operation is case sensitive.

3. ```g```
To replace all occurrences of the search pattern of desired lines, add the g flag

![Image](/lab4/sub.png)

By pressing ```<Enter>```, it make the changes without further confirmations by the users.  
![Image](/lab4/sub-enter.png)

```:w``` saves the changes we have made to the file. 
![Image](/lab4/save.png)
By pressing ```<Enter>```, it shows that "DocSearchServer.java" is saved. 
![Image](/lab4/save-enter.png)

## Part 2

1. It took me 1min43sec to start in Visual Studio Code and make the edit there, then scp the file to the remote server and run it there to confirm it works (you can just run bash test.sh on the remote to test it out).
2. It took me 1min30sec to start already logged into a ssh session. Then, make the edit for the task you chose in Vim, then exit Vim and run bash test.sh.

Personally, I prefer I prefer the second way as it takes less time and I have got some sort of practice using vim. I don’t need to login and scp which means less command to input. In addition, without having the file locally saves space on the client machine. 

Visual Studio Code can be more intuitive when it comes making editions. When using vim, it is very easy to accidentally done something that I don’t want it to do. If the local computer already have the file and I am more comfortable with directly editing, the first way is a good choice. 
