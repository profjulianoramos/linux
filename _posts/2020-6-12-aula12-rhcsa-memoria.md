---
layout: post
title: Aula 12  - Curso RHCSA - Checando memória e Disco
date:   2022-01-06 15:46:00 +0530
categories: Curso RHCSA
---
Neste capítulo vamos aprender mais sobre a verificação de memória e discos.

Para obter informação sobre a memória do seu computador, utilize os comandos:

```
cat /proc/meminfo
free
free -m
free -h
top
gnome-system-monitor
```

Observação: *gnome-system-monitor* é somente para modo gráfico.



# Inspecionando Hard Disk e outros dispositivos de armazenamento

```
cat /proc/partitions
file -s /dev/sda
file -sL /dev/sda
lsblk
fdisk -l
df
df -Tha /dev/sda1
```