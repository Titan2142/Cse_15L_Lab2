## Lab Report 1: Setting up remote access 

By John Carrion

The purpose of this report is to give a step by step guide to logging into the course specific account on  `` ieng6``.

Here are the steps I took in order to login and setup remote access on my laptop.

* Install Open ssh

  [Follow these steps](https://docs.microsoft.com/en-us/windows-server/administration/openssh/openssh_install_firstuse) if you are using a Windows computer.
  
* change your password  

  ![Follow This guide](How-to-Reset-your-Password.pdf) to reset your remote access password.
  
  It's important to do this step first, because it takes about 15-20 min for the UCSD server to update your password
  
* download Vs Code

    [Go to this link](https://code.visualstudio.com/download) to download Visual Studio code.
    Any IDE can be used, but this guide uses VS Code as the example.
    
    ![VSC capture](https://user-images.githubusercontent.com/102689054/162342170-81d27c7d-66a4-43f5-9f0a-7d1fd46b07a7.PNG)

    
* Remotly connect to `` ieng6``

  Use the command `` ssh cs15lsp22***@ieng6.ucsd.edu `` with the *** being your specific account login name.
  you can find your login name from the [account lookup](https://sdacs.ucsd.edu/~icc/index.php) page you used to update your password.
  
  ![remote connect capture](https://user-images.githubusercontent.com/102689054/162341886-ec49dd9a-215d-43a4-9864-38eb6d9f760a.PNG)

  
* Try some commands
   try some commands, like ``ls``, to show your directory. make a new directory, change directories to the new directory, create a file called ``file1``
   and move it between directories. when you feel comfortable, logout with the ``exit`` command.
   
   ![adding and deleting a file](https://user-images.githubusercontent.com/102689054/162341769-f92d09d5-bd0e-4319-bebb-37cb451af116.PNG)

   
* move a file with ``SCP``

  After logging out, on the client terminal, create a text file with ``touch newText`` to make a new text file.
  
  use ``scp newText.txt cs15lsp22***@ieng6.ucsd.edu `` where ** is your specific account login, to move `` newText`` to ypur remote server.
  
  It will ask for your password, enter it in to complete the transfer.
  
  try logging back in to the remote server and use ``ls`` to see if the `` newText`` sucessfully transferd over
  
  you can logout, you are now ready to remote access the UCSD server form your local client computer.
  
  ![Scp1](https://user-images.githubusercontent.com/102689054/162342004-7cd24ecf-b5d4-4f79-b4fa-d5942a38696c.PNG)

  
### Making it easier to login to your remote server

  You may have noticed, but it can be tedious logging in and moving files to your remote server, because it asks for a password every time.
  
  We can generate a priviate and public pair og ssh keys to speed up this process.
  
* create an ssh key
  
  on your personal computer (client) run:
  
  ``ssh-keygen``
  
  you should see:
  
 ``` 
  Generating public/private rsa key pair.
  
  Enter file in which to save the key (/Users/<user-name>/.ssh/id_rsa): /Users/<user-name>/.ssh/id_rsa
  
  Enter passphrase (empty for no passphrase):
 ```
 **Note: Make sure that you do not add a paraphrase for this step.**
 
 ```
 Enter same passphrase again:
Your identification has been saved in
/Users/<user-name>/.ssh/id_rsa.
Your public key has been saved in
/Users/<user-name>/.ssh/id_rsa.pub.
The key fingerprint is:
SHA256:jZaZH6fI8E2I1D35hnvGeBePQ4ELOf2Ge+G0XknoXp0
<user-name>@<system>.local
The key's randomart image is:
+---[RSA 3072]----+
|                 |
|       . . + .   |
|      . . B o .  |
|     . . B * +.. |
|      o S = *.B. |
|       = = O.*.*+|
|        + * *.BE+|
|           +.+.o |
|             ..  |
+----[SHA256]-----+
If you’re on Windows, follow the extra ssh-add steps here:
https://docs.microsoft.com/en-us/windows-server/administration/openssh/openss
h_keymanagement#user-key-generation
This created two new files on your system; the private key (in a file id_rsa) and the
public key (in a file id_rsa.pub), stored in the .ssh directory on your computer.
Now we need to copy the public (not the private) key to the .ssh directory of your user
account on the server.
$ ssh cs15lsp22zz@ieng6.ucsd.edu
<Enter Password>
# now on server
$ mkdir .ssh
```

if on windows, use ```ssh-add``` command

you now have a pair of keys, a priviate and public one.
  
* optimize remote login 

  Now we need to copy the _public_ (not the private) key to a ``.ssh`` directory of your user
  account on the server. 
  
  log back into the remote server with `` ssh cs15lsp22***@ieng6.ucsd.edu ``
  
  make a new directory:
  
  ``mkdir .ssh``
  
  log out with ``exit``
  
  on your personal computer(client), type:
  
```
  scp /Users/<user-name>/.ssh/id_rsa.pub cs15lsp22zz@ieng6.ucsd.edu:~/.ssh/authorized_keys
```

![ssh key](https://user-images.githubusercontent.com/102689054/162342120-f4295ee6-dfd3-4993-a52e-50d8e9d1b943.PNG)

with <user-name> your user name for your pathway to your .ssh file
  
  you should now be able to login without having to enter a password.

![remote connect capture](https://user-images.githubusercontent.com/102689054/162286392-d2a25752-a560-4154-bb0c-85fcb747f4ca.PNG)

