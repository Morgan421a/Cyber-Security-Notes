A command-line application

Used to brute-force directory/file, DNS and virtual host

It can:

Find hidden directories and files on web servers

Find subdomains with wildcard support

Identify virtual hosts on target web servers

Discover open Amazon S3 and Google Cloud storage buckets

Find files on TFTP servers

Flexible Fuzzing with custom parameters

https://github.com/Oj/gobuster

Example use in command line:

```bash
gobuster -u http://fakebank.thm -w wordlist.txt dir
```

^ prints:

![[Gobuster example.png]]

-u is used to state the website to scan

-w takes a list of words and iterates through them to find hidden pages. 

In this scenario we found a hidden page called images and another called bank-transfer

entering /bank-transfer at the end of the url gives us unauthorised access to a page whereby we can send from one account to our own (stealing) 

This is an example of a tool used for [[Offensive Cyber Security]]

