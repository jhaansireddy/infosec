# Bandit Level 14 to 15 Writeup


Author: [Jhaansi Reddy](https://github.com/jhaansireddy) 

Problem Page: [bandit14](https://overthewire.org/bandit/bandit14) 

## List of Commands Used
```
ls - list files in a directory
ssh - connect to server through ssh
sshpass - to provide password directly into the ssh command prompt
nc - netcat; command to read and write across networks
echo - display strings passed to it

```

## Walkthrough
Here, I had to submit the password to port 30000 on the local host. This meant I had to "share" something across the network. So netcat came into use here.


## Password
`BfMYroe26WYalil77FoDi9qh59eK5xNr`

## Bash/Python script to automate the process
```
!/usr/bin/bash
sshpass -p "4wcYUJFw0k0XLShlDzztnTBHiqxU3b3e" ssh bandit14@bandit.labs.overthewire.org -p 2220
echo "4wcYUJFw0k0XLShlDzztnTBHiqxU3b3e" | nc localhost 30000
exit

```

