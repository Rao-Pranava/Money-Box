# MoneyBox

1. Scan the Network to find the vulnerable machine and the ports available to exploit using [[Nmap]].
	* Port `21` for `FTP`
	* Port `22` for `ssh`
	* Port `80` for `http`

2. With this recon data, try to access the `FTP server` using the tool [[FTP]]. 
	* `trytofind.jpg`

3. Let's try to fuzz the [[Web application]] using [[WFUZZ]] tool.
	* Pages: `blogs`

4. Search for information in the [[Blogs]] page.
	* Secret Key: `3xtr4ctd4t4`

5. Using the Secret Key found, find the data inside of the `JPG` file using [[Steghide]]
	* User: `renu`

6. With the user found as `renu`, try to find the Password of that user. We can use [[Hydra]] for cracking the password based on SSH.
	* Password: `987654321`

7. [[SSH]] into the machine with the user `renu`'s credentials.
	* Found the 1st Flag: `us3r1{F14g:0ku74tbd3777y4}`
	* Found a user: `lily`
	* Found the 2nd Flag: `us3r{F14g:tr5827r5wu6nklao}`
	* Found the 3rd Flag: `r00t{H4ckth3p14n3t}`

--------
# Flags

Flag 1: `us3r1{F14g:0ku74tbd3777y4}`
Flag 2: `us3r{F14g:tr5827r5wu6nklao}`
Flag 3: `r00t{H4ckth3p14n3t}`

------