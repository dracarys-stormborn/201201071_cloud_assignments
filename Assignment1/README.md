### Assignment 1
* The folder for assignment 1 consists of the program "add.c" written to calculate the sum of two numbers using a function.
* The assembly code for the program has been generated using "gcc inline assembler" in Intel assembly (not in AT&T) using the commands :

              gcc -S -masm=intel -m32 add.c (add.s renamed to 32_bit.asm)

              gcc -S -masm=intel -m64 add.c (add.s renamed to 64_bit.asm)
              
* I read some docs regarding the register names used in the assembly code and tried to understand what's going on.
* The interpretor is written in convertAssembly.cpp and convertAssembly.h. The program that translates the 32_bit.asm to 64_bit.asm is translator.cpp which depends on convertAssembly.cpp for the helper functions.
* You can run the translator using the following commands (All the files should be in the same folder) :

              g++ translator.cpp convertAssembly.cpp -o translator

              ./translator 32_bit.asm output.asm

* If you compare the files output.asm and 64_bit.asm, you will find they are the same. Hence, the interpretor does the conversion successfully.
* You can also check the assembly code's validity using the following command (rename output.asm to output.s first) :

              gcc -o prog-x86_64 output.s

              ./prog-x86_64

* If it exits without giving any errors, that proves the assembly code's validity. (You can also use gdb to run the binary).

* The screencast for this assignment : [Google drive link](https://drive.google.com/file/d/0B12fowx3-NjTbUNSZ2NjVjl4QXM/view?usp=sharing) and [Youtube link](https://www.youtube.com/watch?v=DySQcoia4dI&feature=youtu.be)
