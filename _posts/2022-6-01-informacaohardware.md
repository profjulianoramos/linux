---
layout: post
title: Aula 11  - Curso RHCSA - Checando informações de hardware
date:   2022-01-06 15:26:00 +0530
categories: Curso RHCSA
---
Neste capítulo vamos aprender como obter informação sobre os dispositivos físicos do nosso host. 

Ver a informação do **release** usamos:

```
cat /etc/redhat-release
```

Outro modo (centos) é:

```
cat /etc/os-release
```

Uma outra opção (quando não se sabe a distro):

```
cat /etc/*-release
```

Ver o kernel:

```
uname -s
```

Ver o hostname:

```
uname -n
```

Ver versão do kernel:

```
uname -r
```

Arquitetura:

```
uname -i
```

Ver OEM:

```
dmidecode -s system-manufacturer
```

Outra opção:

```
dmidecode -s system-product-name
```

Ver o número serial do produto:

```
dmidecode -s system-serial-number
```

Ver informação de hardware:

```
dmidecode -t system
```

Informação de CPU:

```
cat /proc/cpuinfo
lscpu
dmidecode -t processor
```
- Vamos que vamos.
