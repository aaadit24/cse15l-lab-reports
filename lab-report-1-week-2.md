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

4. <code>
  class WhereAmI {
  public static void main(String[] args) {
    System.out.println(System.getProperty("os.name"));
    System.out.println(System.getProperty("user.name"));
    System.out.println(System.getProperty("user.home"));
    System.out.println(System.getProperty("user.dir"));
  }
}
  </code>
