# Nmap

Target IP Address: `192.168.0.7`

Perform a TCP connect scan again the target machine to find out about its open ports and services that it is running.

```
$ sudo nmap -p- -sT -sV --open 192.168.0.7 -oX MoneyBox
```
![Pasted image 20231120124348](https://github.com/Rao-Pranava/Money-Box/assets/93928268/493fee05-d9fe-4d62-b0c8-635bfbc0971a)

From the scan, the possible exploits are as follows:
* Try to login to the `FTP` server as anonymous user `FTP`
* Try to Go through the `Webpage` for more surface area for the exploitation.
* Try to Brute-Force for the `username` and `Password` using `Hydra` for logging into `SSH`.
