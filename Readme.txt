
#########################################################################################################################
***********************************************Course Information********************************************************
                            	     CSE 522: Real Time Embedded Systems           
                                                Sem - Spring 2021                     
                                            Arizona State University                    
                                          Instructor: Dr. Yann-Hang Lee                 
*************************************************************************************************************************
#########################################################################################################################



#########################################################################################################################
----------------------------------------------Assignment Information-----------------------------------------------------

Author: Viraj Savaliya          ; ASU ID - 

Assignment 2 : Thread programming and device driver in Zephyr RTOS

Date : 03/05/2021

-------------------------------------------------------------------------------------------------------------------------
---------------------------------------Instructions to Compile and Execute-----------------------------------------------

How patch was created:
Command - 'diff -Naur ./old_zephyr ./zephyr > hcsr04.patch'
This command was used to create a patch named hcsr04.patch from '~/zephyrproject' directory

How to use the patch:
Command - 'patch -p1 < hcsr04.patch'
Use this command from '~/zephyrproject' directory to apply the changes in zephyr directory

How to Compile:
1. Goto '~/zephyrproject/zephyr' and open terminal
2. Set zephyr environment using 'source zephyr-env.sh'
3. Export environment variables 'export ZEPHYR_TOOLCHAIN_VARIANT=zephyr', 
   'export ZEPHYR_SDK_INSTALL_DIR=<sdk installation directory>'
5. Goto '~/zephyrproject/zephyr/samples/HCSR_app' from terminal
6. Make the script (runall) executable using the command 'sudo chmod +x runall'
7. Now you can run the script file 'runall' to build. Execute it using './runall'
8. The script file will delete the existing (if any) build directory and zephyr.strip file from current directory
   And then make a new build directory use cmake and make and then copy the zephyr.strip to your current directory

How to execute:
1. Copy the zephyr.strip file you got in '~/zephyrproject/zephyr/samples/HCSR_app' to
   your sd card under directory name kernel.
2. Insert the sd card on galileo board and connect board via FTDI cable with the machine.
3. Power on the board.
4. ssh terminal using '/dev/ttyUSB0' on speed '115200'
5. Press Enter on boot option and then press enter for 'Zephyr Kernel'

-------------------------------------------------------------------------------------------------------------------------
#########################################################################################################################



#########################################################################################################################
------------------------------------------------Sample Output------------------------------------------------------------

uart:~$ CSE 522: RTES - HCSR04 App; All Devices are disabled

uart:~$ hcsr select 0
All Devices are now disabled

uart:~$ hcsr select 1
Device enabled is HCSR0

uart:~$ hcsr start 5
HCSR0 Channel get distance 6 cms

HCSR0 Channel get distance 6 cms

HCSR0 Channel get distance 6 cms

HCSR0 Channel get distance 9 cms

HCSR0 Channel get distance 11 cms

uart:~$ hcsr select 2
Device enabled is HCSR1

uart:~$ hcsr start 8
HCSR1 Channel get distance 14 cms

HCSR1 Channel get distance 6 cms

HCSR1 Channel get distance 7 cms

HCSR1 Channel get distance 9 cms

HCSR1 Channel get distance 13 cms

HCSR1 Channel get distance 14 cms

HCSR1 Channel get distance 16 cms

HCSR1 Channel get distance 16 cms

uart:~$ hcsr select 3
Devices enabled are HCSR0 and HCSR1

uart:~$ hcsr select 2
Device enabled is HCSR1

uart:~$ hcsr select 3
Devices enabled are HCSR0 and HCSR1

uart:~$ hcsr start 2
HCSR0 Channel get distance 11 cms

HCSR1 Channel get distance 19 cms

HCSR0 Channel get distance 21 cms

HCSR1 Channel get distance 17 cms

uart:~$ hcsr dump 1 8
Application start time = 25359 ms

Device HCSR0 Elapsed time 119968 ms:    Value 11 cms

Device HCSR1 Elapsed time 120497 ms:    Value 19 cms

Device HCSR0 Elapsed time 121026 ms:    Value 21 cms

Device HCSR1 Elapsed time 121555 ms:    Value 17 cms

Device HCSR1 Elapsed time 85099 ms:     Value 13 cms

Device HCSR1 Elapsed time 85628 ms:     Value 14 cms

Device HCSR1 Elapsed time 86157 ms:     Value 16 cms

Device HCSR1 Elapsed time 86685 ms:     Value 16 cms

uart:~$ hcsr clear
Buffer cleared!

uart:~$ hcsr dump 1 4
Application start time = 25359 ms

Device  Elapsed time 0 ms:      Value 0 cms

Device  Elapsed time 0 ms:      Value 0 cms

Device  Elapsed time 0 ms:      Value 0 cms

Device  Elapsed time 0 ms:      Value 0 cms

uart:~$ hcsr select 0
All Devices are now disabled

uart:~$ hcsr start 2
No measurements initiated, all Devices are disabled


-------------------------------------------------------------------------------------------------------------------------
#########################################################################################################################
