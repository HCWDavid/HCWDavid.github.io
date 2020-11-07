---
layout: post
title: Database Management System
date: 2020-09-30 11:00 +0530
categories: C/Cpp, GitHub
---

This project is a Project Course referred to CS 122C from Prof. Chen Li at the University of California, Irvine.
I will demonstrate my implementation of a database system ground up from the simplest basis (Page File Mangement)...
WITHOUT SHARING ANY OF MY CODE. Because it is a on-going class and for the best of student fairness, I do not want
student to have any unfair advatange using my code. Please understand this is a explanatory page for people wants to learn
and understand how database system works and why it is efficient.

Page File Management (PFM):
PFM contains 4 functions that act with clear purpose: create, destroy, open, and close the file. Particularly, this is
a single instance in the later object class that will only does these functionalities to create separation of layers for
clean design and optimization.

PFM is a file management that used very similar to the OS file management except for a few twists.
First of all it does not contain a pointer per se (with bunch of other information contain inside of the pointers).
PFM simply has a pass-by-reference variable of a Object called FileHandler (class of FileHandle) when to open the file
to manipulate the data into the disk. It contains some information about the opened file, such as number of read, write,
append, and of course, the file name. It does not really have a pointer point to the file because we did not want to leave
any dangling pointer (of course based on the implementation it should not be a problem if we are sophisticated). But the another
reason for not having a pointer is basically saving the resource.

In the Filehandler, you have four additional functions: read a page, write a page, append a page, and get the total number of page.
In context, a page is defined 4 KB which means 4096 (2^12) bytes each time you try to access a "page". It is used from a
database perspective to create a level of readability and simplicity.
