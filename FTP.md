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

![Pasted image 20231120124652](https://github.com/Rao-Pranava/Money-Box/assets/93928268/74939199-a4fa-45bb-b8b9-6b7b92ccbf4e)


After a successful login to the FTP server, list out the files present in the share. We see a `JPG` file called `trytofind.jpg` to be present in the share.

```
ftp> ls
```

![Pasted image 20231120124856](https://github.com/Rao-Pranava/Money-Box/assets/93928268/c55ccd21-b13a-460e-899b-0a75e88de918)


Download the file into your *attacker* system.

```
ftp> get trytofind.jpg
```

![Pasted image 20231120125118](https://github.com/Rao-Pranava/Money-Box/assets/93928268/6be29ffd-e58c-4a2c-9b29-b79aebfda727)


Open the image, you can see a *Hacker Cat* with a sticker *Nerd* and a picture on the wall which says **Hack The Planet**.

![Pasted image 20231112093322](https://github.com/Rao-Pranava/Money-Box/assets/93928268/4f573ad2-d1ed-40e8-b95b-ced2b6f2ea00)


This gives no real data for continuing the exploit, but have a clue, the Image. Try to extract the meta data of the image using `Steghide` tool.
