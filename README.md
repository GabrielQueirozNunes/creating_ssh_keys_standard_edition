![alt text](./assets/SSH-KEY.png)

# The easiest way to set your ssh key. 

## Go to your user home

~~~Bash
$ cd ~
~~~

## Create a ".ssh" folder

~~~Bash
$ mkdir ~/.ssh
~~~

## Run "ssh-keygen" to generate the keys

~~~Bash
$ ssh-keygen
~~~

* Press enter for the next requests.

## Create the "authorized_keys" and "known_hosts" files

~~~Bash
$ touch ~/.ssh/authorized_keys && touch ~/.ssh/known_hosts
~~~

## Add your public key in your authorized keys file

~~~Bash
$ cat ~/.ssh/id_rsa.pub >> ~/.ssh/authorized_keys
~~~

## Active the ssh agent

~~~Bash
$ ssh-add ~/.ssh/id_rsa
~~~

## Configure the follow access rights to your files

~~~Bash
$ chmod 700 ~
$ chmod 700 ~/.ssh
$ chmod 600 ~/.ssh/id_rsa
$ chmod 644 ~/.ssh/id_rsa.pub
$ chmod 644 ~/.ssh/known_hosts
$ chmod 644 ~/.ssh/authorized_keys
~~~

## Congratulations! You ssh key is ready to be used. 

## To access the host, use the follow command

~~~Bash
$ ssh -i /path/to/privateKeyFile -o StrictHostKeyChecking=no userThatPrivateKeyIsConfigured@host.address
~~~

* You need to copy the **id_rsa** content to a file in the computer you'll make the SSH connection. That will be the **privateKeyFile**.

* You only can access the user that configured the SSH key.

