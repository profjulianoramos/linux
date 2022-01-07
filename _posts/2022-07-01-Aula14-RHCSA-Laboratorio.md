---
layout: post
title: Aula 14  - Curso RHCSA - Laboratório
date:   2022-01-07 08:41:00 +0530
categories: Curso RHCSA
---
Os exercícios de laboratório são baseados no conteúdo oficial da certificação Red Hat RHCSA. O laboratório está em *inglês*.


Lab Manual - Navigating & listing

**Navigating and listing files & directories**

**To know on which directory you are currently on, run**

\# pwd*.*

**Navigate to the directory Desktop using the command**

\# cd Desktop.

**Create a file**

\# touch testfile.txt.

First of all, list the contents of the directory ***log\*** using the absolute path. The names with blue are directories and names with black are files. If you run *cd* and hit enter, it leads you all the way back to the home directory.

**To list the parent directory of the current directory**

\#ls . . .

**To list a user’s home directory, type**

\# ls ~

**To list the root directory**

\# ls /

**Switch the current directory to /etc**

\# cd /etc/

**Long lists the files and directories**

\# ls –l

**To long list all the contents of the directory including the hidden**

\# ls –al.

Here, files or directories starting with dot were hidden.

**To long list in human readable format**

\# ls -lh

**To list with size,**

\# ls –ls*.*

**To list in reverse order**

\# ls –r

**To list in tree format**

\#ls –R

**To list sorted by file size**

\# ls –S

**To list in ascending alphabetical order**

\#ls –t

**And for descending alphabetical order**

\# ls –r.

You can also use ls –lr to long list in descending alphabetical order.

**To list or sort files by their extension**

\# ls –X.

**To list only the files with .txt extension in the current directory**

\# ls *.txt

Switch to /var/tmp.

**Then run the following command set to list the files and directories with full path**

\# ls –d $PWD/*