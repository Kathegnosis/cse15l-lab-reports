
# Logging in on ieng6
You want to know how to log into a course-specific account on ieng6? Well, you've come to the right place! 
<br>
<br>
However, let's make sure you have the prerequisites to do this first.
<br>
## Installing VScode
Having Visual Studio Code (VScode) will likely make it more comfortable to work with remote servers as the course goes on. You'll have to install it eventually. So, let's do it now.
<br>
Go to VScode's [website](https://code.visualstudio.com/), and scroll down until you see the image below:
![Image](https://github.com/Kathegnosis/cse15l-lab-reports/blob/main/report1_screenshot1_VScode.PNG)
Choose the one you download based on your operating system. (Windows, Mac, Linux) 
<br>
<br>
Once it has finished downloading, run the installer. You can modify the settings as you like, but I suggest using the defaults if you're unsure.
<br>
<br>
When you're done with that, you should have an image that looks like this when you launch the application (but perhaps with a different GUI or main color based on your operating system):
![image](https://user-images.githubusercontent.com/88159129/162631870-759a0cb5-cad7-41b1-ab44-cdeec8762783.png)
<br>
## Remotely Connecting
Now that you have VScode up and running, let's make sure your computer and account are well prepared to connect to a remote server.
<br>
<br>
Firstly, you need to have access to your course-specific account for CSE15L. Go to this [website, which will allow you to lookup your cse15l account](https://sdacs.ucsd.edu/~icc/index.php), and enter your username and student ID.
![image](https://user-images.githubusercontent.com/88159129/162633178-724bfc69-a733-4897-a587-0d581ec4f38d.png)
<br>
<br>
Once you're in, you should see this page:
<br>
![image](https://user-images.githubusercontent.com/88159129/162633254-bf0c0b76-e9e3-4089-b73c-81158adfe245.png)
<br>
You see the "cs15lsp22aki" account? That's my course-specific account for cs15l, and how I connect to the remote server. 
<br>
Yours should be the same except for the last three letters ("aki"), which will be replaced by your three letters, and perhaps "sp22" as well if you're reading this in a different quarter.
<br>
<br>
Make sure to change your password for this account if you haven't already, because you will not be able to log in otherwise. [Here's a tutorial for that](https://urldefense.proofpoint.com/v2/url?u=https-3A__piazza.com_redirect_s3-3Fbucket-3Duploads-26prefix-3Dpaste-252Fktv2gnof3sx5bf-252F181c3cb053df5cf1ccaf0457f56f12a2e5aa90b139aef8c2ea8fcc590f02fadf-252FHow-2Dto-2DReset-2Dyour-2DPassword.pdf&d=DwMFAw&c=-35OiAkTchMrZOngvJPOeA&r=378Yq_2ArBhLwPIcKm07svPfOjA-UlFx-llIi1s6w34&m=a3RNYWClHHTw3hF9KyJlmBPmwRQo8UufiIVF8W1ij4hBJwdWPwVEKOw9qpRJ07EV&s=mhiZJFG9uhDgZs9sAMpw6bdgP-sIhqdABp6d7mf4CBk&e=).
<br>
<br>
Windows User note: if you're on Windows, you'll need to [install OpenSSH](https://docs.microsoft.com/en-us/windows-server/administration/openssh/openssh_install_firstuse) to connect to remote servers. 
<br>
<br>
Now that your account is ready, it's time to actually connect to a remote host. 
<br>
Open VScode and get a new terminal:
<br>
![image](https://user-images.githubusercontent.com/88159129/162635426-5bfa5281-228c-4611-9eba-24f47851b332.png)
<br>
Within this terminal, enter the command below. Make sure to replace 'aki' with your account-specific three letters!
<br>
```ssh cs15lsp22aki@ieng6.ucsd.edu```
<br>
If this is your first time logging in, you'll likely see a message like this:
<br>
```
The authenticity of host 'ieng6.ucsd.edu (128.54.70.238)' can't be established.
RSA key fingerprint is SHA256:ksruYwhnYH+sySHnHAtLUHngrPEyZTDl/1x99wUQcec.     
Are you sure you want to continue connecting (yes/no/fingerprint)?
```

In this case, since it's your first time logging in, it's expected. Just type out "yes" and press enter.
<br>
If it wasn't your first time  (and you're not connecting to cs15l) then the server may have been reconfigured, or someone messing with the server and there is a possibility for a man-in-the-middle attack... but luckily that's not the case!
<br>
...
<br>
The server has now been added to the list of hosts your computer knows. Hooray! 
<br>
Now you need to type in your password when prompted (or re-enter the command if the connection was closed).
<br>
<br>
Don't worry if you're typing in your password and words aren't appearing in the terminal. They're actually being put in, but the characters are invisible because the terminal is ultra secure! You may have to do this multiple times, because it's so secure that it erases your memory of how to type your password correctly.
<br>
<br>
The whole interaction looks something like this:
<br>
![image](https://user-images.githubusercontent.com/88159129/162642954-651df26e-0241-49c2-9b3f-406e6b8f3d42.png)
<br>
<br>
Now you're connected to some random computer in the CS basement! Any commands you run in the connected terminal will be run by that computer! You can also access the files stored in the remote server.

## Trying Some Commands
Since you're finally here, why not try some commands? I recommend the following:
<br>
<br>
`cd ~`
<br>
This command, cd, means "change directory." The ~ means "home directory," but you can get the same result by just writing cd. You're just going to the home directory.
<br>
<br>


```
ls
ls -lat
ls -a
```
The command ls prints out everything in your current directory. The addition of -lat or -a just specifies how you want it printed out. For example, `ls -lat` simply prints out the current directory laterally.
![image](https://user-images.githubusercontent.com/88159129/162638709-897e2061-1847-4008-b2d2-18c16639bab1.png)
<br>
<br>

`ls <directory>`
<br>
Take the directory `/home/linux/ieng6/cs15lsp22/cs15lsp22aki` as an example. Using that, this command will print out the contents of the file named after my username. You can change the username and/or directory as you wish if you want to print the results of other directories.
..
<br>
<br>

`cp /home/linux/ieng6/cs15lsp22/public/hello.txt ~/`
<br>
This will copy a file the directory you specify.
..
<br>
<br>

`cat /home/linux/ieng6/cs15lsp22/public/hello.txt`
<br>
This will print the contents of hello.txt
..
<br>
<br>

`exit`
<br>
Exits the remote server.
..
<br>
<br>
## Moving Files with scp
You've established some commands, great. However, I wouldn't be happy if my abilities only consisted of those few commands, so neither will you be.
<br>
It's time to learn how to move files from your computer to the remote server.
<br>
<br>
Take a file. In this case, it's a file called "WhereAmI2.java." Now, go to the directory where you made it in the terminal, and type the following command (make sure to change aki to your 3 letters):
<br>
`scp WhereAmI2.java cs15lsp22aki@ieng6.ucsd.edu:~/`
<br>
<br>
Enter your password when prompted, as usual.
![image](https://user-images.githubusercontent.com/88159129/162639905-2c8cabe9-0011-402d-bf26-90d94fe0f8c9.png)

<br>
<br>
Then, if you type ls on the server, you'll see "WhereAmI.java" there! You can run this file on the remote server!
<br>
What you did is copy your file to the server. In fact, scp means "Secure CoPy."
![image](https://user-images.githubusercontent.com/88159129/162639931-af623c7a-1848-43b8-8142-0c8c159c7a50.png)

## Setting an SSH Key
Great. You've gotten an arsenal of commands. Don't you think this whole process is slow and time consuming, though?
<br>
<br>
Well, luckily for me/you, Lab 1 offered this solution: ssh keys.
<br>
To start, enter this command (if you're not on Windows):
<br>
`ssh-keygen`
<br>
<br>
If you're on windows, enter this:
`ssh-keygen -t ed25519`
<br>
This is where you will save the file:
<br>
`/Users/<user-name>/.ssh/id_rsa`
<br>
Make sure the passphrase is empty.
<br>
<br>
The following image should show up:
<br>
![image](https://user-images.githubusercontent.com/88159129/162641742-2226039f-b437-4b6e-b1c4-d6620f066ff0.png)
<br>
<br>
Great, you made the key. Now copy it to the server. First, log in with ssh, and use this command to mkdir:
<br>
`mkdir .ssh`
<br>
Then exit the server, and when you're back on client, use this command:
<br>
`scp /Users/<user-name>/.ssh/id_rsa.pub cs15lsp22zz@ieng6.ucsd.edu:~/.ssh/authorized_keys`
<br>
Now you should be able to ssh and scp without needing to enter your pass every time.
<br>
![image](https://user-images.githubusercontent.com/88159129/162642030-1f4ec394-89a4-45ba-ae67-41a9ae627ed0.png)
<br>

## Optimizing Remote Running
It's almost over. One last thing I want to show you. You can run multiple commands on the same line!
<br>
![image](https://user-images.githubusercontent.com/88159129/162642116-fe7ec24e-3930-46a7-bbd7-bbd01baf0348.png)
<br>
For example, log in with ssh, and put "ls" in quotation marks next to it (as in the image above). By doing this, you can log in, and immediately run the "ls" command. This prints out everything in the home directory.
<br>
<br>
Another example is running programs on the same line:
<br>
![image](https://user-images.githubusercontent.com/88159129/162642230-8e9cdfbd-07ef-4fdd-b58d-dfe8a774aca6.png)
<br>
In the image above, I copied WhereAmI.java to another file, compiled a file, and also ran a program. All on the same line!
<br>
<br>
We're done here. Have fun!

