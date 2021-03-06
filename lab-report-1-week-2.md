 <p style="font-size:26px" align="center"> Remote Access Tutorial </p>

<p align="center">This tutorial will help you learn all of the basics of remote access!</p>

&nbsp;  

## 1. Installing Visual Studio Code
Make sure to install Visual Studio Code ([VSCode](https://code.visualstudio.com/)) and follow the installation steps. Once you open Visual Studio Code, it should look something like this: 
![Image](report_1_files/VSCodeSC.PNG)

&nbsp;  

## 2. Remotely Connecting 
Open a terminal on VS Code by clicking on **Terminal** at the top menu bar and then clicking **New Terminal**. To request access to your remote server at UCSD, take your server address and follow this command:
```
ssh cs15lwi22att@ieng6.ucsd.edu
```
Note that I will be using my server address throughout the tutorial -- make sure to substitute with your account. Enter the password you have for this account. Note that you will not be able to see any indication of the password you have typed out, but rest assured, your key strokes are going through. If it is successful, you will see an output similar to this:

![Image](report_1_files/login.PNG)

&nbsp;  

## 3. Trying Some Commands
Here are some commands you should be familiar with:
* `cd ~` -- changes directory to home directory   
* `pwd` -- prints working (current) 
directory
![Image](report_1_files/pwd.PNG)

* `ls` -- prints contents of current directory 
![Image](report_1_files/ls.PNG)

* `ls -a` -- prints all contents of current directory including hidden files
![Image](report_1_files/lsa.PNG)

* `cp sourcefile... targetdirectory` -- copies source file from a directory to target directory

&nbsp;  

## 4. Moving Files with `scp`
To copy a file from your current directory on the client (your computer) to the home directory of your server, follow this command:    
`scp fileName cs15lwi22att@ieng6.ucsd.edu:~/`

Enter your password. This is what your terminal should like:
![Image](report_1_files/scp.png)

&nbsp;  

## 5. Setting an SSH Key
To create a SSH key for easier access to the remote server (without having to type in your password every time), type
`ssh-keygen` on the client side. Save the key in the location given and create a passphrase to use instead of your password when logging in. This will create an SSH key and when you `ssh` from now on, the terminal should look like this:

![Image](report_1_files/sshkey.PNG)

Enter your passphrase to log into the server.

&nbsp;  

## 6. Optimizing Remote Running
Luckily, we can make running commands remotely more convenient. Let's say we want to run multiple commands on the same line. We can insert semicolons between commands on the same line.
For example, `ssh cs15wi22att@ieng6.ucsd.edu ls; javac Hello.java` will ssh into the server, list contents of the current directory, exit the server, and then compile Hello.java on the client side. This command only takes 51 keystrokes compared to over 55 keystrokes and more time waiting if you run them separately. Note that if we want to run both commands on the server, we can use put all the commands we want to run in quotes, separated by semicolons. For example, with the command `ssh cs15wi22att@ieng6.ucsd.edu "ls; javac Hello.java"` the server will be exited only after the closing double quotes. 

![Image](report_1_files/easierrunning.PNG)
*This will only take about 44 keystrokes (excluding entering password) compared to 48 keystrokes to `ssh`, `cd ..`, `pwd` and `logout` separately, plus extra time spent waiting for each command to run. This trick will definitely cause a noticeable difference and make the experience smoother.

