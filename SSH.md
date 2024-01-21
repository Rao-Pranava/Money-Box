# SSH

With the username `renu` and the password `987654321`, SSH into the target machine.

```
$ ssh renu@192.168.0.7
```

![Pasted image 20231120152447](https://github.com/Rao-Pranava/Money-Box/assets/93928268/6d03f8bd-b7ec-47b4-9667-19809bf79e3f)


And we find our first flag in the `user1.txt` file!.

![Pasted image 20231120152613](https://github.com/Rao-Pranava/Money-Box/assets/93928268/b83dc0a7-26b6-4c74-a02a-8b49b763cfe2)


----------------
---------

Now, let us find any way to get to the root user of this machine. First, find out how many users are present in the system.

```
renu@MoneyBox:~$ cat /etc/passwd | grep -iE "sh|bash|zsh"
```

![Pasted image 20231120154739](https://github.com/Rao-Pranava/Money-Box/assets/93928268/f5d776b0-22f9-4ed2-a2f2-026c183e810f)


We see that we have more users, `lily` and `root` in the sytem.

Browse to `lily`'s user directory located `/home/lily`

```
renu@MoneyBox:~$ cd /home/lily/
```

![Pasted image 20231120154918](https://github.com/Rao-Pranava/Money-Box/assets/93928268/d549e0f2-57ec-4753-b2a9-26e74cc2c20f)


Here, we found the 2nd Flag!!!

![Pasted image 20231120155035](https://github.com/Rao-Pranava/Money-Box/assets/93928268/fe6a7c5a-f740-4499-8812-f9db4a41e191)


---
--------------

Looking inside of the `.ssh` folder of `lily`, we can see `authorized_keys` of ssh.

![Pasted image 20231120155432](https://github.com/Rao-Pranava/Money-Box/assets/93928268/3239fe35-41b2-403d-a65d-eb88f6c15b39)


The user `renu` is authorized for the ssh keys. So if we go back to `renu`'s home directory and look at the `bash history` of the commands, we see that, indeed the user had access to `lily`'s SSH ID.

```
grep "ssh" -i .bash_history --color=auto
```

![Pasted image 20231120161028](https://github.com/Rao-Pranava/Money-Box/assets/93928268/809fd7db-d330-489c-92c2-cd7bbce38630)


Go to `renu`'s `.ssh` folder, in there we find the rsa id for our SSH login.

![Pasted image 20231120161205](https://github.com/Rao-Pranava/Money-Box/assets/93928268/2a14f4d4-6502-449c-81ba-97c3cf0b01d4)


Using the command same command of `renu`, SSH into the user `lily`.

```
ssh -i id_rsa lily@127.0.0.1
```

![Pasted image 20231120161316](https://github.com/Rao-Pranava/Money-Box/assets/93928268/0395d368-e0e8-4097-be83-063b551f0a9b)


List for the privileges that the user `lily` has.

```
lily@MoneyBox:~$ sudo -l
```

![Pasted image 20231120161627](https://github.com/Rao-Pranava/Money-Box/assets/93928268/bde7dc2a-60d7-4c61-8674-58040c6cdf42)


So, this means that, we don't have to use password if we are using `sudo` command if you are using the `perl` tool.

Our intension is to become the root or get access to `root`'s shell. If we can run the `/bin/bash` file with the root access, we become the root.

For that, using `perl`, execute the `/bin/bash` file.

```
lily@MoneyBox:~$ sudo perl -e 'exec "/bin/bash"'
```

![Pasted image 20231120163255](https://github.com/Rao-Pranava/Money-Box/assets/93928268/a3fbd074-580d-4fba-bf3a-6715005e9362)


Now that we are a root user, finding the flag at root's directory is a cake walk.

![Pasted image 20231120163449](https://github.com/Rao-Pranava/Money-Box/assets/93928268/adaf1a15-1e95-4257-9f63-ac786ce3b1fc)


------------
