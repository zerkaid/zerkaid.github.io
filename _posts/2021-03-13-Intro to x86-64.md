---
layout: post
title: Intro to x86-x64
---

# Intro to x86-64

Room start: 

``` ssh tryhackme@yourvirtmachineip ```

SSH'd into the machine and..... 

#Learning 

Many minuets of reading about assembly and breaking down the files on the system.

``` notes 
Break point to the address you want to read 
```

This didnt come across well to me from the room but you want to drop your break at the function instructions or the end of the loop to get the values you want



#Crack me time

Recalling some assembly, looking at the code and googling  function names and instructions

I found that the function that compares the strings 

```    :|   0x55862130689a      488b45b8       movq var_48h, %rax
|      :|   0x55862130689e      4889d6         movq %rdx, %rsi
|      :|   0x5586213068a1      4889c7         movq %rax, %rdi
|      :|   0x5586213068a4      e807feffff     callq sym.imp.strcmp    ; int strcmp(const char *s1, const char *s2)                             
```



Throughout the program you see things like this move into $rsi and $rdi 

```   0x5649994dd821      4889c6         movq %rax, %rsi```

``` px ``` the values here and it prints out everything stored in rdi and rsi including hopefully a correct password. While this worked for me I had to do some guessing as the password wasn't complete or in the correct format.

#Crack me 2 

I tried several of the same methods to get crackme2 and busted.

one of the methods calls a secret text file that contains the information you need.

Along with a tip I got from a classmate that led me to the answer reversing the text in the secret txt file.









