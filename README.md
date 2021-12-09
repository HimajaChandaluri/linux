# Asssignment 4 CMPE 283

## Contributions
We connected over a zoom call to perform the task

### Himaja Chandaluri

I worked on the task of determining the correct command to disable ept, with Chandra Lekha and executed the 3rd assignment code to get the before 
and after results

### Chandra Lekha Mamidi

We as a team worked on the task of determining the correct command to disable ept, and executed the 3rd assignment code to get the before and after results

|With EPT enabled|With EPT desabled|
|---|---|
|![image](https://user-images.githubusercontent.com/67281829/145336577-3656d5ab-8802-4c45-a294-d60381ac6d21.png)|![image](https://user-images.githubusercontent.com/67281829/145336610-a55d3818-ef24-46d3-aa7d-c765ec31441f.png)|
|![image](https://user-images.githubusercontent.com/67281829/145336656-c4b505cc-af33-41a8-8d33-2262656dd991.png)|![image](https://user-images.githubusercontent.com/67281829/145336682-fa547669-ede5-4822-87ec-e8c4eb69f950.png)|
|![image](https://user-images.githubusercontent.com/67281829/145336714-097203df-b0f9-4558-8681-0cab7dfd7c8d.png)|![image](https://user-images.githubusercontent.com/67281829/145336730-1d6813d7-4e86-4bcf-b9cd-5268ed6c5ec6.png)|
|![image](https://user-images.githubusercontent.com/67281829/145336754-e9f11ad4-da68-4e97-9b74-73f3b4de7d9b.png)|![image](https://user-images.githubusercontent.com/67281829/145336766-335623df-5e99-454c-8747-c9f7fa4e8958.png)|
|![image](https://user-images.githubusercontent.com/67281829/145336791-a552dfc5-a76c-48fb-b524-07e7df609d46.png)|![image](https://user-images.githubusercontent.com/67281829/145336815-cf0753a3-d8dc-4186-a847-e329ea971c69.png)|
|![image](https://user-images.githubusercontent.com/67281829/145336840-251722f3-f2b1-40dc-b1ce-d890cbcced0a.png)|![image](https://user-images.githubusercontent.com/67281829/145336856-93332517-4108-4cce-8033-700ebb0b653b.png)|
|![image](https://user-images.githubusercontent.com/67281829/145336880-2be09461-eb7e-429d-86cf-6eb9eb072149.png)|![image](https://user-images.githubusercontent.com/67281829/145336901-62182a8e-6407-455e-9b10-0071c32ba984.png)|
|![image](https://user-images.githubusercontent.com/67281829/145341774-22a23db8-696c-4613-ac09-63f72b9ce50b.png)|![image](https://user-images.githubusercontent.com/67281829/145341869-dd7519c7-7c04-4c24-858f-ef2b7346bb34.png)|

Above are the Screen shots of the varios exit counts before and after the disabling ept.

### Answers

1) What did you learn from the count of exits? Was the count what you expected? If not, why not?

The number of exits with shadow paging mechanism are almost double than the values we got with nested paging. This is justifiable because the shadow paging architecture requires more exits to perform the task correctly 

2) What changed between the two runs (ept vs no-ept)?

The main difference that can be seen between the two runs is that the exit reasons 14 and 58 which initially had zero exit counts have exit counts of around 100000. Also the other exit resons that initially had some value have now increased. Overall shadow paging requires more number of exits to perform effectively.

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
I was responsible for implementing the `OX4FFFFFFC` leaf node functionality of the code. I changed the cpuid.c and vmx.c files. Icompiled and loaded the kernel and tested the code using the test file, which was created to test the leaf node functionality of the kernel.

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

| exit | First   | Add File | Reboot  | Delete File | Reboot  |
|------|---------|----------|---------|-------------|---------|
| 0    | 33004   | 33015    | 49868   | 49872       | 66675   |
| 10   | 282950  | 286970   | 427019  | 427772      | 565667  |
| 28   | 64397   | 64397    | 96629   | 96629       | 128375  |
| 29   | 5       | 5        | 7       | 7           | 9       |
| 30   | 424858  | 437764   | 645085  | 657672      | 861609  |
| 31   | 6074    | 7967     | 9980    | 11213       | 13156   |
| 40   | 14247   | 22238    | 24212   | 25093       | 26893   |
| 46   | 14      | 14       | 21      | 21          | 28      |
| 47   | 6       | 6        | 9       | 9           | 12      |
| 48   | 2277897 | 2586505  | 3557448 | 3590403     | 4624003 |
| 54   | 6       | 6        | 9       | 9           | 12      |
| 55   | 6       | 6        | 9       | 9           | 12      |

The exits increase at a stable rate on reboot. For example, we can see that the values for exit no 29,46,47,54, and 55 increase by 2,7,3,3,3 respectively. During VM reboot large number of VM exits are observed. Based on the observations we can see that approximately 1.4M VM exits occured during a reboot.

2) Of the exit types defined in the SDM, which are the most frequent? Least?

As we can see exit 48 and exit 30 are the most frequent exit types. Apart from the exit codes which have zero count, the least frequent exit codes are 29,47,54,55, and 46.
