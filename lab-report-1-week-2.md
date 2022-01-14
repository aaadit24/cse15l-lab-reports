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

![Remotely Connecting](https://user-images.githubusercontent.com/97692709/149591637-c5e14c17-defb-4be0-b033-c67b2dc01a02.png)

3. Try running the commands cd, ls, pwd, mkdir, and cp