# Asssignment 2 CMPE 283

## Contributions
We connected over a zoom call to run the updated kernel code with the functionalities. We resolved the errors in this process together.

### Himaja Chandaluri

I was responsible for cloning the kernel and building it. In the process I faced errors with the RSA certificate's. 
I resolved it by creating a certificate file and changing the .pem certificate reference in the .config file to the new certificate created.
Created the VM on top of the ubuntu system. Built a test file to test the kernel code. Executed the kernel code.

### Chandra Lekha Mamidi

I was responsible for implementing the two leaf node functionalities of the code. In this process i updated the cpuid.c and vmx.c files of the kernel.
I used variables `exit_count` and `time_spent` to keep track of number of exits and total time spent in exits.
Replaced the updates files in the kernel code and rebuilt the code.

## Steps followed

1. Forked the torvalds/linux tree
2. Cloned the forked repo into an ubuntu machine
3. Downloaded important libraries for building the kernel
4. Executed `sudo cp /boot/{config-name} ./.config`
5. Executed `sudo make oldconfig`
6. Edited code in `cpuid.c` and `vmx.c`, to satify the leaf nodes `0x4fffffff` ans '0x4ffffffe` requirments
7. Executed `sudo make -j 8 modules`
8. Executed `sudo make -j 8`
9. Executed `make INSTALL_MOD_STRIP=1 modules_install`
10. Loaded kvm using the command `modprobe kvm` and `modprobe kvm_linux`
11. Created a VM using VirtManager
12. Created a test file and executed it to see the results


## Screenshots

![image](https://user-images.githubusercontent.com/67281829/142979898-0aaad88d-3b84-4add-8e83-6357846fd31d.png)
![image](https://user-images.githubusercontent.com/67281829/142980036-a705e232-0b95-4332-98b2-c7aa08a389db.png)
