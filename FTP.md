# FTP

Connect to the File share server through the port `21` with the following credentials.

```
Username: anonymous
Password: anonymous
```

Command:

```
ftp 192.168.0.7 21
```



After a successful login to the FTP server, list out the files present in the share. We see a `JPG` file called `trytofind.jpg` to be present in the share.

```
ftp> ls
```

![[Pasted image 20231120124856.png]]

Download the file into your *attacker* system.

```
ftp> get trytofind.jpg
```

![[Pasted image 20231120125118.png]]

Open the image, you can see a *Hacker Cat* with a sticker *Nerd* and a picture on the wall which says **Hack The Planet**.

![[Pasted image 20231112093322.png]]

This gives no real data for continuing the exploit, but have a clue, the Image. Try to extract the meta data of the image using [[Steghide]] tool.
