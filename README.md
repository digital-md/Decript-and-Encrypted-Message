<h1>Decript an Encrypted Message</h1>

<h2>Description</h2>
Encryption and decryption can be used to secure information online. By using basic Linux Bash shell commands I will be using Linux commands to decrypt files and reveal a hidden message below. 

-	list hidden files,
-	decrypt one of the earliest algorithms a Caesar cipher, and
-	decrypt an encrypted file.

<b>Scenario</b> 

All of the files in your home directory have been encrypted. You’ll need to use Linux commands to break the Caesar cipher and decrypt the files so that you can read the hidden messages they contain.
Here’s how you’ll do this task: First, you’ll explore the contents of the home directory and read the contents of a file. Next, you’ll find a hidden file and decrypt the Caesar cipher it contains. Finally, you’ll decrypt the encrypted data file to recover your data and reveal the hidden message.

<b>Read the contents of a file</b> 

1. Use the ls command to list the files in the current working directory.
Two files, Q1.encrypted and README.txt, and a subdirectory, caesar, are listed:
Q1.encrypted  README.txt caesar
The README.txt file contains an important message with instructions you need to follow.
2. Use the cat command to list the contents of the README.txt file.
The message in the README.txt file advises that the caesar subdirectory contains a hidden file.

<b>Find a hidden file</b> 

1. Used the cd command to change to caesar subdirectory of the home directory.
2. Used the ls -a command to list all files, including those hidden in the home directory.
3. Used the cat command to list the contents of .leftShift3 file. This file appears to be scrambled. This data has been encrypted using a Caesar cipher. By shifting each alphabet character to the left or right by a fixed number of spaces. For this the shift is three letters to the left. Thus "d" stands for "a", and "e" stands for "b."
4. You can decrypt the Caesar cipher in the .leftshift3 file by using the following command:
cat .leftShift3 | tr "d-za-cD-ZA-C" "a-zA-Z"  The tr translates the text from one set of characters to the other by mapping. In this case, the command tr "d-za-cD-ZA-C" "a-zA-Z" translates all the lowercase and uppercase letters in the alphabet back to their original position. The first character set, indicated by "d-za-cD-ZA-C", is translated to the second character set, which is "a-zA-Z".
5. Now, return to your home directory before completing the next task:
cd ~

<b>Decrypt a file</b>

1. Use the exact command revealed in the previous task to decrypt the encrypted file:
openssl aes-256-cbc -pbkdf2 -a -d -in Q1.encrypted -out Q1.recovered -k ettubrute
2.	Use the ls command to list the contents of your current working directory again.
The new file Q1.recovered in the directory listing is the decrypted file and contains a message.
3.	Use the cat command to list the contents of the Q1.recovered file.

![image](https://github.com/digital-md/Decript-and-Encrypted-Message/assets/156498985/84101102-c65e-43f5-8d85-d6550a231eed)

```
--!>
