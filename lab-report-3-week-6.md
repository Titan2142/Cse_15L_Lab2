# Week 6 Lab Report 3

## Streamlining ssh Configuration

Using `ssh cs15lsp22zzz@ieng6.ucsd.edu` everytime to login to the remote server is a lot to remember. We can speed this up by streamlining 
the ssh config file to automaticaly log us into the server.

![config](https://user-images.githubusercontent.com/102689054/167331739-05efd4e7-a84c-4e48-9bed-0521aad9b503.PNG)

creating a config to log into the remote server

![ssh ieng6](https://user-images.githubusercontent.com/102689054/167332165-ec1e86f2-f6a0-4214-bc05-32a4a4f37b5e.PNG)
using the host name `ieng6` to login, much faster!

![scp file2 txt ieng6](https://user-images.githubusercontent.com/102689054/167332221-db7e53cd-3f54-409b-aad6-118d3bec4831.PNG)
Using the streamlined ssh command to quickly transfer a file to the remote server.

## Setup Github Access from ieng6

Commiting and pulling fromthe ieng6 server to github is necessary. setting up ssk keys is necessary

![local keys](https://user-images.githubusercontent.com/102689054/167345368-3aa6e7f6-51a8-492b-99f3-caddc5ab38e7.PNG)

local keys

![github key](https://user-images.githubusercontent.com/102689054/167345416-f6e5c020-01fa-4c2a-a0ad-484cfe66d325.PNG)
the github key

![git push](https://user-images.githubusercontent.com/102689054/167345485-048587d7-9d95-4a61-b83a-9bd5a3cbbd76.PNG)
pushing a change to git hub

![commit log](https://user-images.githubusercontent.com/102689054/167345508-9bb3b781-c528-409f-8b2f-07a3ca7666b7.PNG)
github commit log

## Copy whole directories with ``scp -r``

We can copy an entire direstory using ``scp -r`` 
![scp -r 1](https://user-images.githubusercontent.com/102689054/167348867-a82613d4-f03c-4fc0-af44-b36035d68368.PNG)
![scp -r 2](https://user-images.githubusercontent.com/102689054/167348886-b18b19ae-79cd-4a0d-915b-2d3673cc85eb.PNG)

this copys all files, we can select certain files to copy, and complete other commands
![scp file2 txt ieng6](https://user-images.githubusercontent.com/102689054/167349009-0f77d49d-7f30-4c46-9594-839352b18868.PNG)
![test complete](https://user-images.githubusercontent.com/102689054/167349026-310da1aa-b0c2-4ca9-a6c2-11829e034b2c.PNG)
aftercopying the directory, the tester ran sucessfully
