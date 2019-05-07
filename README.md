How to make a system call:
1. cd /usr/src/linux-4.13.1
2. mkdir test
3. cd test
4. test test.c
5. write the code in the test.c file
6. gedit Makefile
7. Write the code for makefile in the file
8. cd ..
9. gedit Makefile
   find this in makefile
	core-y += kernel/ mm/ fs/ ipc/ security/ crypto/ block/ 
   and replace it with 
	core-y += kernel/ mm/ fs/ ipc/ security/ crypto/ block/ test/
10. cd arch/x86/syscalls
11. gedit syscall_64.tbl
12. Write your system call in the end in the same pattern
13. cd ../../../..
14. cd include/linux
15. gedit syscalls.h
16. add the prototype of your system call in the end.
17. cd ../..
18. make install -j3
19. shutdown -r
20. run the program that we made as a test program.
