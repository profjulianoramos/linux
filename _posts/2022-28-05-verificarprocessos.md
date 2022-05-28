---
layout: post
title: Verificar processos em porta específica
date:   2022-28-05 07:07:00 +0530
categories: Sysadmin
---

Neste pequeno guia, mostraremos diferentes maneiras de encontrar o processo/serviço escutando em uma determinada porta no Linux.

## Usando o comando netstat
O comando `netstat` (estatística de rede) é usado para exibir diversas informações sobre sua rede, como: Tabelas de roteamento e estatística da interface. O comando está disponível para Unix, Linux e também para Microsoft Windows.

Para instalar o comando abra um terminal e execute:

| Distro | Comando |
|--- |--- |
| Debian/ubuntu/mint | sudo apt install net-tools |
| RHEL/Fedora   | sudo dnf install net-tools |
| Arch Linux | pacman -S netstat-nat |
| Opensuse/SUSE | sudo zypper install net-tools |


Uma vez instalado, usaremos o comando `netstat` com o comando `grep`, para analisar qual processo/serviço esta escutando determinada porta.

```
$ netstat -ltnp | grep -w ':80'
```

No comando acima os parametros: 

| parametro | Definição | 
|--- | --- |
| l | Diz ao netstat para listar apenas sockets. |
| t | Listar apenas conexões tcp | 
| n | Mostrar endereços números | 
| p | Mostra o ID do processo e seu nome |
| grep -w | Mostra a correspondência exata da string (:80)|

## Comando lsof
O comando `lsof` (List Open Files) é usado para listar todos os arquivos abertos em um sistema linux.

Para instalar:

| Distro | Comando | 
|--- |---| 
| Debian/Ubuntu/Mint | sudo apt install lsof |
| RHEL/Fedora | sudo yum install lsof |
| Arch Linux | sudo pacman -S lsof |
| Suse/Opensuse | sudo zypper install lsof |

Para localizar o processo/serviço use:

```
$ lsof -i :80
```


## Usando o comando fuser
O comando `fuser` mostra os PIDs dos processos. Para instalar:

| Distro | Comando |
|--- |--- |
| Debian/Ubuntu/Mint | sudo apt install psmisc |
| RHEL/Fedora | sudo yum install psmisc |
| arch | sudo pacman -S psmisc |
| Suse/Opensuse | sudo zypper install psmisc |

O comando:

```
$ fusser 80/tcp
```

## Conclusão
O gerenciamento de processos é parte do cotidiano de um administrador de sistemas linux. Para quem pretende seguir esta profissão é recomendável a certificação LPIC-1 101. Eu ofereço um treinamento completo de administração de sistema 101 através do site:
https://certificacoes.net.br/cursoslinux/
