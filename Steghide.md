# Steghide

Using the tool `steghide`, we can extract the metadata of an image.

```
$steghide extract -sf trytofind.jpg
```

![Pasted image 20231120125557](https://github.com/Rao-Pranava/Money-Box/assets/93928268/3444988b-e5a5-426a-9c3c-85a72c20a245)


We hit a challenge.....! We have no idea about the Passphrase for extracting the meta data from this image file. We can try to brute force with the possible clues from the image itself.

Now, let us try to switch the path to find more information or places to exploit, we can try exploiting the `Web application`.

----------

Try the secret key found from the `Blogs` page to extract the meta data of the image.

```
steghide extract -sf trytofind.jpg
```

![Pasted image 20231120150607](https://github.com/Rao-Pranava/Money-Box/assets/93928268/dae68f8d-6823-4879-938c-ab6e845437d1)


Print our the information from the `data.txt` file.

![Pasted image 20231120150733](https://github.com/Rao-Pranava/Money-Box/assets/93928268/e5188e60-4e1f-4236-a92b-f2eec10ce564)


We can guess that we have a user called `renu` and the password is too weak.

Assuming that we have a username `renu`, we need to find the password for this user. we can use the tool `Hydra` to bruteforce the password using the SSH Service.
