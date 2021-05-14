# Bandit Level 12 to 13 Writeup


Author: [Jhaansi Reddy](https://github.com/jhaansireddy) 

Problem Page: [bandit12](https://overthewire.org/bandit/bandit12) 
## List of Commands Used
```
ls - list files in a directory
file - used to determine the type of file
tar - stands for tape archive; used to create, extract and work with archive files
gzip - to compress or decompress files with extension .gz
bzip2 - to compress and decompress files with extension .bz2
xxd - to make or reverse an hexdump
cat - display content of the file
mkdir - make directory
mv - move or rename file
cp - copy file
cd - change directory
ssh - connect to server through ssh
sshpass - to provide password directly into the ssh command prompt

```

## Walkthrough
The data file given is a hexdump which was compressed and archived multiple times.
I have worked through this level by creating another directory and copying the file into it.
So, first I decode the hexdump. I have used redirection over here to store the decoded data into an other file. Then, I check the type of file. I rename the file according to its type by adding that particular extension so that it can be worked upon by commands used to decompress it. After several trials, at last I am left with a file type ASCII code, which contains the password.

## Password
`8ZjyCRiBWFYkneahHwxCv3wb2a1ORpYL`

## Bash/Python script to automate the process
```
!/usr/bin/bash
sshpass -p "5Te8Y4drgCRfCx8ugdwuEX8KFC6k2EUu" ssh bandit12@bandit.labs.overthewire.org -p 2220
ls
mkdir /tmp/banditl12
cp data.txt /tmp/banditl12
cd /tmp/banditl12
cat data.txt | xxd -r > df1
file df1
mv df1 df1.gz
gzip -d df1.gz
file df1
mv df1 df1.bz2
bzip2 -d df1.bz2
file df1
mv df1 df1.gz
gzip -d df1.gz
file df1
tar xfv df1
file data5.bin
tar xfv data5.bin
file data6.bin
mv data6.bin data6.bin.bz2
bzip2 -d data6.bin.bz2
file data6.bin
tar xfv data6.bin
file data8.bin
mv data8.bin data8.bin.gz
gzip -d data8.bin.gz
file data8.bin
cat data8.bin
exit


```

