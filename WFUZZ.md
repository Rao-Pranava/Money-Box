# WFUZZ 

Using the tool `wfuzz` and `seclists` as our payload, we can fuzz the website for any lead.

```
wfuzz -c -z file,<Location>/SecLists/Discovery/Web-Content/raft-large-directories.txt --hc 404,403 "http://192.168.0.7:80/FUZZ"
```

![Pasted image 20231120134753](https://github.com/Rao-Pranava/Money-Box/assets/93928268/8de59e20-ec17-45ea-b7dd-534d51e38aaa)


The results shows that there is a `blogs` file present in the application! Let us check what is present in the `Blogs` page.

