# Week 2 Lab Report

1. First Instal [Visual Studio Code](https://code.visualstudio.com/)

![VSCode](https://user-images.githubusercontent.com/97692709/149589685-3cb3fc3c-7a62-458f-9253-8060420b9aa9.png)

Then instal a program called [OpenSSH](https://docs.microsoft.com/en-us/windows-server/administration/openssh/openssh_install_firstuse), look up your CSE15L account email [here](https://sdacs.ucsd.edu/~icc/index.php) and reset your password.

2. Open the terminal in VS Code and type the following, but replace the aeg with your course specific username:

> ssh cs15lwi22aeg@ieng6.ucsd.edu

You will get the message below. Type yes.

> The authenticity of host 'ieng6.ucsd.edu (128.54.70.227)' can't be established.\
RSA key fingerprint is SHA256:ksruYwhnYH+sySHnHAtLUHngrPEyZTDl/1x99wUQcec.\
Are you sure you want to continue connecting (yes/no/[fingerprint])? 

After entering your password you should see a window similar to the one below
![Remotely Connecting](https://user-images.githubusercontent.com/97692709/149595378-8d3c91f8-4733-46fe-9be8-31fdce6012d3.png)

3. Try running the commands cd, ls, pwd, mkdir, and cp

![Trying Some Commands](https://user-images.githubusercontent.com/97692709/149592012-952885e8-66f7-4c0c-b6e2-e8529a0fbe33.png)

4. We will now copy files over ssh wich scp. Create a file on your computer called WhereAmI.java and put the following contents into it: 

![Code](https://user-images.githubusercontent.com/97692709/149596611-58099bbe-a757-4567-8fa6-41af3f5aaebd.png)

Then, in the terminal from the directory where you made this file, run this command, using your username:

> scp WhereAmI.java cs15lwi22aeg@ieng6.ucsd.edu:~/

You should see something similar to the image below

![Moving Files with scp](https://user-images.githubusercontent.com/97692709/149596724-1e6fd93d-c726-4682-9099-11b98d2a9a22.png)

5. Using ssh keys we will not have to repeately input our password. The following command will create a public key and a private key which will be used to log in instead of a password

Type the following

> ssh-keygen

You can leave the prompts empty and then your terminal should look similar to the image below

![Screenshot 2022-01-15 021342](https://user-images.githubusercontent.com/97692709/149597070-c353d1a5-1d7b-4b74-b1dd-35b4cfcf4b06.png)

Now run the following command

![Screenshot 2022-01-15 022225](https://user-images.githubusercontent.com/97692709/149597637-a709070d-d41f-4bdf-8272-05a51a9264cd.png)

Run the following command put replace the destination of the key with the one provided in your terminal above (destination of the key)

![Screenshot 2022-01-15 021908](https://user-images.githubusercontent.com/97692709/149597642-e3a8b743-a29c-49fc-aa03-aef7adbdec76.png)

As you can see below, I was logged into my account without inputting my password

![Screenshot 2022-01-15 021949](https://user-images.githubusercontent.com/97692709/149597645-9260728c-c284-4613-acc3-2642761c29c5.png)

6. You can now use all the command you have learned and more for smooth running of programs, such as writing a command in quotes at the end of an ssh command. 

![Screenshot 2022-01-15 022902](https://user-images.githubusercontent.com/97692709/149598014-25fff4f4-8cb6-4a3e-8580-7c359f0235f7.png)
