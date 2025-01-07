# samsung-riscv-
Install VirtualBox on Ubuntu using sudo apt install virtualbox, launch it with virtualbox, create a new virtual machine, and load the .vdi file by selecting "Use an existing virtual hard disk file."
Inside the virtual machine, write a C program using nano sum.c to calculate the sum of numbers from 1 to 10.
Install the RISC-V toolchain , building it (./configure --prefix=/opt/riscv && make), and adding it to your PATH (export PATH=$PATH:/opt/riscv/bin).
Compile the program using riscv64-unknown-elf-gcc sum.c -o sum and run it with an emulator like QEMU (qemu-riscv64 ./sum).
below are the snapshots of the program

![ccode](https://github.com/user-attachments/assets/6143bc5d-b53a-4075-ac06-e35a33be2606)
![output](https://github.com/user-attachments/assets/227c8e38-48bd-4bd2-bf69-4e689d7a14a1)
![risc](https://github.com/user-attachments/assets/37b88885-e68d-46e7-826c-cc8c54376b84)
