# wyoos
Source codes for the "Write your own Operating System" video-series on YouTube
## Requrements：
   >Environment:
   VMware Workstation Pro 14 
   Linux Mint 17.3 "Rosa"
   Kernel 3.19.0-32-generic 
   KDE Development Platform: 4.14.2 
   
   
## Step One:

   $ sudo apt-get update && sudo apt-get upgrade -y
   $ sudo apt-get g++ binutils libc6-dev-i386
   > When Start Computer 
      1. MainBoard will take the data from the BIOS,Copy content(firmware) from the BIOS to the RAM 
      2. The firmware will talk CPU to Hard drive,find partition tables or systems the boot sector or Master Boot Record.Load Data from Hard dirver to RAM
      3. Bootloader(Using grub bootloader) in RAM ,then find /boot/grub/grub.cfg (Contain some menu)
      4. Bootloader will print operating systems on your screen 
      5. Copy /boot/kernel.bin to RAM, so this is the point at which our code will start to be executed 
   > We have Problem:
      1. C++ programs expect the stack point would be set before thet start running
         1.1: Create loader.s file, basically set the stack point [using as assembler]
         1.2: Create kernel.cpp
         1.3: Create linker.ld, will combine two file(loader.s, kernel.cpp) to kernel.bin 
   
# FQA:
   
   1. How do I know my KDE version?
      A:
      $ kate --version
         Qt: 4.8.6
         KDE Development Platform: 4.14.2 
         Kate: 3.14.2 
      B: 
      $ konsole --version
         Qt: 4.8.6
         KDE Development Platform: 4.14.2 
         Konsole: 2.14.2 
   2. How to find Linux kernel version?
      A:
         $ uname -r 
            3.19.0-32-generic 
      

