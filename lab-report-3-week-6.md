# Lab Report 3

## Streamlining ssh Configuration
### Show your .ssh/config file, and how you edited it (with VScode, another program, etc)
![image](https://user-images.githubusercontent.com/88159129/167331320-57555c95-37f8-4999-87c6-10a6b7f20a6d.png)
I added a file named "config", and pasted in the specified text. You can see the hostname and username I'm using to login to the remote server in this file, which is stored in my .ssh folder.  


### Show the ssh command logging you into your account using just the alias you chose.
![image](https://user-images.githubusercontent.com/88159129/167331442-601b0001-5472-44ba-9579-de41c9347d21.png)
In the image above, I'm logging in with just "ssh ieng6" (with ieng6 being my alias). Amazing!


### Show an scp command copying a file to your account using just the alias you chose.
Copying the file into my account:

![image](https://user-images.githubusercontent.com/88159129/167333555-0e9d7ef8-8a77-4521-9a4d-674173ef0283.png)

Here's its location in the remote server's directory:
![image](https://user-images.githubusercontent.com/88159129/167333680-eb15cd57-2d58-4c50-9e6f-74da01d7377e.png)




## Setup Github Access from ieng6
### Show where the public key you made is stored on Github and in your user account (screenshot).
Here is where my key is stored in github:
![image](https://user-images.githubusercontent.com/88159129/167342707-572caea5-8c19-4da1-be61-9008e7493959.png)


### Show where the private key you made is stored on your user account (but not its contents) as a screenshot.
Below, you can see where my private key is stored on my user account (ieng6).
![image](https://user-images.githubusercontent.com/88159129/167342587-beee8783-82f1-4d2b-b9b5-167a127e6bb4.png)


### Show running git commands to commit and push a change to Github while logged into your ieng6 account.
![image](https://user-images.githubusercontent.com/88159129/167342343-50e3295d-b091-45d1-83be-b296c6306cee.png)

The above image is me finally figuring out how to push a change to github in ieng6.

### Show a link for the resulting commit.
[Here is a link for this commit!](https://github.com/Kathegnosis/cse15l-lab-reports/commit/da9dab92e7e5d865f3e63fee95f34e0e2bd097f8)



## Copy whole directories with scp -r
### Show copying your whole markdown-parse directory to your ieng6 account.
![image](https://user-images.githubusercontent.com/88159129/167345794-673bc456-ba9a-4354-aff7-61fa63a142a0.png)
The above image depicts an entire copy of markdown parser to my ieng6 account.

### Show logging into your ieng6 account after doing this and compiling and running the tests for your repository.
Logging in:
![image](https://user-images.githubusercontent.com/88159129/167346561-5fa3ec94-2f39-400f-bc07-320f7b9e3e9e.png)



Running and compiling tests using a makefile:

![image](https://user-images.githubusercontent.com/88159129/167346460-2ecb672e-5b52-453f-a438-f15db4b22557.png)



### Show (like in the last step of the first lab) combining scp, ;, and ssh to copy the whole directory and run the tests in one line.
![image](https://user-images.githubusercontent.com/88159129/167348592-f3f4355f-4ade-4c8f-b741-8fb434bcf5a0.png)

See image above. Here, I am copying the entire directory and running the tests within it with the same makefile.


