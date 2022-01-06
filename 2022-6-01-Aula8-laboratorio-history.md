---
layout: post
title: Aula 8 - Curso Red Hat RHCSA - Laboratório
date:   2022-06-01 13:59:00 +0530
categories: Certificação RHCSA
---

Laboratório com exercícios similares ao encontrado no exame oficial da certificação Red Hat RHCSA. 


# Lab Manual-Working with 'history' command

**Print all the commands that you have entered till now in the system from the user student.**

\# history



**Print the history in a page at a time**

\# history | more

To see other pages press the space bar.

**To see the last 5 commands you run in the shell**

\# history 5

**To rerun the command from the history**, give exclamation mark and then the line number of the command. For example:-

\# ! 29

Type **!c**, It prints the last command starting from c. Similarly, **!w** executes the last command that was run starting with w.

**To search a command in the history.**

\# ctrl+r

This leads you to reverse-i-search. Press any character or characters of the command set, you want to search. For example, I am searching for the command to **set hostname**. I just type ‘hos’. Then press enter to rerun the command. I am not going to execute this, so I don’t press enter. If the commands are similar, again press ctrl +r to switch between the commands.

**To execute the last command**

\# !!

**To see the history with time and date**

\# export HISTTIMEFORMAT=’%F %T’

Now if you run the history command, you can see the commands with date and time. This helps us to know when the command was run.

To search the commands in history, we can also use pipe and grep. For example, I want to see all the commands having the word ‘host’.

\# history | grep host

By default, in Red Hat 8, history contains the last 1000 commands. To verify it,

\# echo $HISTFILESIZE

**Modify number of commands to record as history**

\# HISTFILESIZE=2000

\# echo $HISTFILESIZE

**To remove or delete a line from the history**, use **history –d** and the line number. For example:-

\# history –d 42

\# history



**To set the system not to record the history**

\# HISTSIZE=0.

From now onwards, the history will not be recorded. Also, the current history will be cleared. To set back the system to record the history, specify the HISTFILESIZE= any number greater than 0.

There is another way to clear all the history. For this, type history –c.