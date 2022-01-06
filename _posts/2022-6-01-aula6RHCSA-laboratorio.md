---
layout: post
title: Aula 6  - Curso RHCSA - Laboratório
date:   2022-06-01 08:23:00 +0530
categories: Curso RHCSA
---

Exercícios de laboratório, conteúdo muito similar ao cobrado no exame prático da certificação RHCSA, em inglês.


Lab Manual-Basic Commands

**Linux basic commands**

**Print the system uptime, number of logged on users and average load to the system.**

\# uptime

**Print the currently working directory**

\# pwd

**Change the current directory to /etc directory**

\# cd /etc/

\# pwd

**See, network interfaces and their configurations**

\# ifconfig

Or,

\# ip addr show

**To clear the terminal**

\# clear

**Listing Files & Directories**

\# ls –l

\# ls –al

\# ls –lt

\# ls –ltr

\# ls -R

**Read contents of file in the Bash Terminal**

\# cat /etc/passwd

**Verify and change hostname**

\# hostnamectl

\# hostnamectl set-hostname server.example.com

**Verify and change time, date and time-zone**

Print full date and time

\# date

To see the time, time zone, clock status,

\# timedatectl

\# timedatectl set-timezone and press ‘tab’ key twice. It will display all the timezones. Find your timezone > Here, for this demonstration, I assume my timezone as Asia/Bankok > copy it > press ‘escape’ key and paste.

Again, you need to authenticate. Enter the password > click on *authenticate.* Clearing the screen, verify.

\# timedatectl

\# date +%

\# date +%R

\# cal

\# cal 08 2019

**See what commands you’ve run so far**

\# history

To study or know in detail about any command, the available options and arguments, open manual page of the command. For example, to read the manual page of *ls* command

\# man ls.

Press, space bar to go to other pages. Press ‘q’ to quit from here.

To know details of any command, just type *man* and the name of the command.