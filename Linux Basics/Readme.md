Linux Basics - I <a name="TOP"></a>
===================

![image](https://github.com/Nirvan007/Analog_Electronics/assets/127144315/19139479-75a5-436c-8fbf-ef140cb835ab)

## Table of Contents
* [Introduction](#Introduction)
* [Purpose](#Purpose)
* [Linux Commands](#Linux-Commands)
* [Sources to learn Linux](#Sources-to-learn-Linux)
* [References](#References)
* [Acknowledgement](#Acknowledgement)

## Introduction
Linux is an open-source operating system which is the first choice of every technocrat. For VLSI Design Engineers also most of the EDA tools are only compatible with Linux. In Linux, we interact with OS majorly with Command-Line Interface (CLI). In beginning, it might look a bit tedious as you have to remember lots of commands and we are addicted to GUI interface but later you will definitely love it.

## Purpose
Linux is used extensively by all of the semiconductor-specific companies for chip development and is a must-know skill for Analog and Digital Design Engineers. Hence, in this repository we will be using a Linux environment to design and simulate our Analog designs.

## Linux Commands
* Command to view all the folders and files in a specific location: “ `ls` ”
* Command to view all the last state or changes in the OS: “ `ll` ”
* Command to view all the last state or changes in the OS: “ `ls -ltr` ”
* Command to enter into a file or folder location: “ `cd space file name` ”
* Command to go back to the previous file or folder location: “ `cd space ..` ”
* Command to open a specific file: “ `gvim space filename` ”
  * In GVIM, when you have opened up a file, there are 2 modes: 
    * Command mode (Thick blinking bar over the character)
    * Typing mode (regular line blinking)
  * NOTE: This change can be made by clicking the `insert` button on the keyboard
* To save the file in the GVIM, use “ `:w` ” in the command mode
* To exit the file in the GVIM, use “ `:q` ” in the command mode
* To search for any character/word in the GVIM, use “ `/searchword` ” in the command mode
* To delete a line in the GVIM, use “ `dd` ” in the command mode when the blinker is set on that line that has to be deleted.
* Command to copy a file: “ `cp space filename` ”
* Command to rename a file: “ `mv space existing_filename space renamed_filename` ”
* Command to copy a directory: “ `cp space -r space existing_filename space to_filename` ”
* Command to create a directory: “ `mkdir space folder_name` ”
* Command to view the present working directory: “ `pwd` ”
* Command to delete a file: “ `rm space filename` ”
* Command to delete a folder: “ `rm space -r space folder_name` ”
* Command to view the first line in a file: “ `head space filename` ”
* Command to view the last line in a file: “ `tail space filename` ”
* Command to view the last few line in a file: “ `tail space -no_of_lines space filename` ”



## Sources to learn Linux
* Javapoint.com: <https://www.javatpoint.com/what-is-linux>
* Lunux.com: <https://www.linux.com/what-is-linux/>
* TechTarget.com: <https://www.techtarget.com/searchdatacenter/definition/Linux-operating-system>

## References
 - [1] https://www.takshila-vlsi.com/
 - [2] https://www.javatpoint.com/what-is-linux
 - [3] https://www.linux.com/what-is-linux/

## Acknowledgement
#### Mentors
* Trainers @ Takshila Institue of VLSI Technologies, https://www.takshila-vlsi.com/ 
