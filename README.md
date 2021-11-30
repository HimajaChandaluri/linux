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

# Assignment 3 CMPE 283

## Contributions
We connected over a zoom call to run the updated kernel code with the functionalities. We resolved the errors in this process together.

### Himaja Chandaluri
I was responsible for implementing the `0x4FFFFFFD` leaf node functionality of the code. In the process I updated the cpuid.c and vmx.c files of the kernel. I wrote the code referencing the SDM Manual for the exit reasons. I created the test file to test the leaf node functionality of the kernel. I compiled and loaded the kernel and tested the code using the test file.

### Chandra Lekha Mamidi

## Steps followed

Updated the kernal code in `cpuid.c` and `vmx.c` files and executed the following commands

1. `make -j 8 modules`
2. `make INSTALL_MOD_STRIP=1 modules_install`
3. `lsmod | grep kvm`
4. `rmmod kvm_intel`
5. `rmmod kvm`
6. `lsmod | grep kvm`
7. `modprobe kvm`
8. `modprobe kvm_intel`
9. `lsmod | grep kvm`

## Screenshots

![image](https://user-images.githubusercontent.com/67281829/143991924-b223cf12-e0bf-42bd-914d-f6c428b154b3.png)

![image](https://user-images.githubusercontent.com/67281829/143991960-f708117e-9bcb-4e03-9d59-39997bcca15a.png)

![image](https://user-images.githubusercontent.com/67281829/143991987-9425c531-bc15-459c-861e-9bd17f25a2d3.png)

![image](https://user-images.githubusercontent.com/67281829/143992006-d67171c6-05e8-4a8d-8a8e-577a1a0b2294.png)

![image](https://user-images.githubusercontent.com/67281829/143992033-27a5491e-06c6-47ab-a18d-f91092e485d3.png)

![image](https://user-images.githubusercontent.com/67281829/143992057-d3782234-a978-40fb-ae37-53f041bdb27c.png)

![image](https://user-images.githubusercontent.com/67281829/143992079-89886c33-10df-418d-a723-0a03e12e082a.png)

### Answers 

1) Comment on the frequency of exits – does the number of exits increase at a stable rate? Or are there 
more exits performed during certain VM operations? Approximately how many exits does a full VM 
boot entail?

