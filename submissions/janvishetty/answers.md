Task 1 Submission 

GitHub Username: janvishetty 

Task 1 – Linux Installation & Linux Journey 

I installed Ubuntu Linux in a VMware virtual machine by following the provided tutorial.  

What I Learned 

Basic Linux commands and terminal navigation 

Working with files and directories 

File permissions and ownership 

Process management 

Text manipulation utilities 

Package management basics 

Introduction to Linux networking concepts 

The required screenshots for Linux installation and Linux Journey progress have been included in the submission. 

 

Task 2 – OverTheWire Bandit (Level 0–15) 

Level 0 → Level 1 

I connected to the Bandit server using SSH and explored the home directory. I found a file named readme and checked its contents to obtain the password for the next level. 

Commands: ls, cat readme 

 

Level 1 → Level 2 

The password was stored in a file named -. Since this character is normally treated as a command option, I referenced it using ./- to read the file. 

Commands: cat <- 

 

Level 2 → Level 3 

The password was stored in a filename containing spaces. I used quotes around the filename to access it correctly. 

Commands: cat ./"--spaces in this filename--” 

Level 3 → Level 4 

The challenge hinted that the password might be hidden. After listing all files, including hidden ones, I found the required file and viewed its contents. 

Commands: ls -la, cat './..Hiding-From-You' 

 

Level 4 → Level 5 

There were multiple files, so I used the file command to determine which one contained human-readable text. After identifying it, I opened the file and retrieved the password. 

Commands: file, cat 

 

Level 5 → Level 6 

The challenge provided specific file properties such as size. I used find with the given conditions to locate the correct file. 

Commands: find 

 

Level 6 → Level 7 

The target file had specific ownership and size requirements. I searched the filesystem using those criteria while suppressing permission errors. 

Commands: find / -user -group -size 2>/dev/null 

 

Level 7 → Level 8 

The password was stored next to a specific keyword inside a large text file. I searched for the keyword using grep. 

Commands: grep 

 

Level 8 → Level 9 

The password was the only unique line in the file. I sorted the contents and filtered for unique entries. 

Commands: sort, uniq -u 

 

Level 9 → Level 10 

The file contained binary data. I extracted readable text strings and searched through them to find the password. 

Commands: strings, grep 

 

Level 10 → Level 11 

The contents were Base64 encoded. I decoded the data to reveal the password. 

Commands: base64 -d 

 

Level 11 → Level 12 

The text was encoded using ROT13. I translated it back to normal text using the tr command. 

Commands: tr 

 

Level 12 → Level 13 

This level involved multiple layers of compression and file formats. I repeatedly checked the file type and extracted the contents until I finally reached the password file. 

Commands: xxd, file, gunzip, bunzip2, tar 

 

Level 13 → Level 14 

I used the provided SSH private key to authenticate as the next user and access the required password. 

 

Level 14 → Level 15 

The challenge required sending the current password to a service running on a specific port. I connected using Netcat and received the next password. 

Commands: nc 

 

Summary 

Through the Bandit wargame, I gained practical experience with: 

Linux command-line navigation 

File handling and permissions 

Searching and filtering data 

Text processing tools 

Encodings and compression formats 

SSH authentication 

Basic networking concepts and services 

All required terminal screenshots have been included in the submission folder. 
