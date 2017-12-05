# os-malloc
This directory contains:

myAllocator.c: a first-fit allocator
myAllocator.h: its header file

myAllocatorTest1.c: a test program for my allocator 

malloc.c: a replacement for malloc that uses my allocator
test1.c: a test program that uses this replacement malloc

There are two different testers as some implementations of printf
call malloc to allocate buffer space. This causes test1 to behave
improperly as it uses myAllocator as a malloc replacement. In this
case myAllocatorTest1 will function correctly. The only difference
between the programs is that test1 uses myAllocator as a malloc
replacement and myAllocatorTest1 uses myAllocator directly.

Makefile: a fairly portable "makefile", targets "all" and "clean"

To compile: 
 $ make 
To clean:
 $ make clean

The cygwin runtime uses malloc() and brk() extensively.  It is
interesting to compare the output of test1 & myAllocatorTest1.  All
those extra allocated regions are being used by cygwin's libraries!

Submission Date December 10 2017
Author Hector Cervantes
Class Operating Systems

// Finished implementing the resize region and implemented the Best Fit Algorithm

The program allocates and resizes any region by a specified size.

    BestFit: The code is supposed to allocate region of excact or similar size if it exists, other wise create a new region if all regions are allocated or fill an empty a region of exact size or similar.

    ResizeRegion: My extension of the resize region should grab an already allocate region and expand it to a specified size. If the current region is not sufficient it will store the newly created region to another region of a more suitable size.
    
