# samsung-riscv-
Install VirtualBox on Ubuntu using sudo apt install virtualbox, launch it with virtualbox, create a new virtual machine, and load the .vdi file by selecting "Use an existing virtual hard disk file."
Inside the virtual machine, write a C program using nano sum.c to calculate the sum of numbers from 1 to 10.
Install the RISC-V toolchain , building it (./configure --prefix=/opt/riscv && make), and adding it to your PATH (export PATH=$PATH:/opt/riscv/bin).
Compile the program using riscv64-unknown-elf-gcc sum.c -o sum and run it with an emulator like QEMU (qemu-riscv64 ./sum).
below are the snapshots of the program

![ccode](https://github.com/user-attachments/assets/6143bc5d-b53a-4075-ac06-e35a33be2606)
![output](https://github.com/user-attachments/assets/227c8e38-48bd-4bd2-bf69-4e689d7a14a1)
![risc](https://github.com/user-attachments/assets/37b88885-e68d-46e7-826c-cc8c54376b84)

task 2
I created a basic C program that uses recursion to determine the factorial of a given number. 
Targeting the RISC-V architecture, the software was compiled using the spike simulator and the RISC-V GCC compiler. In particular, I compiled the code with optimization settings -O1 and -Ofast using the commands riscv64-unknown-elf-gcc -O1 -o factorial_O1 factorial.c and riscv64-unknown-elf-gcc -Ofast -o factorial_Ofast factorial.c. 
The commands riscv64-unknown-elf-objdump -d factorial_O1 > dump_O1.txt and riscv64-unknown-elf-objdump -d factorial_Ofast > dump_Ofast.txt were then used to create the object dumps
![fact](https://github.com/user-attachments/assets/5c83528b-d4e7-4414-a398-f491eb1a6305)
![fact-termi](https://github.com/user-attachments/assets/571db077-de12-468e-bde0-70bccbc418fe)
![O1](https://github.com/user-attachments/assets/e4dbf2ab-8017-4df1-9e85-d1ca948e4a6f)
![Ofast](https://github.com/user-attachments/assets/149464de-5fd4-4aea-a7c9-b3c92b76c62c)

The main distinction between the object dumps is that the recursive function is present in the -O1 dump but not in the -Ofast dump, where the factorial result (120 for the input 5) is loaded straight into the appropriate registers. 
This distinction is shown in the screenshots: Whereas the -Ofast dump lacks a recursive function and the result is hardcoded into the main function, the -O1 dump defines and calls the factorial function from the main function. 
