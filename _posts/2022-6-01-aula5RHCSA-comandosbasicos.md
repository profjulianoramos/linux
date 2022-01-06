# Comandos básicos do Linux

```
uptime
```

Visualiza os usuários logados e o tempo de uso do servidor.

```
pwd﻿
```

Este comando mostra o diretório atual que você se encontra.

```
cd /etc
```

Este comando permite que você acesse outros diretórios

```
whoami
```

Mostra o usuário que está logado no sistema

```
ifconfig
```

Mostra as informações de interface de rede

clear

Limpa a tela. Mesmo que **ctrl + l**

```
ls
```

Lista arquivos e diretórios

```
ls -l
```

Lista arquivos e diretórios de uma forma longa

```
ls -la
```

Lista de uma foma longa e com arquivos ocultos

```
ls -lt
```

Lista os arquivos e diretórios em ordem

```
ls -ltr
```

Lista os arquivos e diretórios em ordem inversa

```
ls -R
```

Lista arquivos e diretórios em formato de árvore.

```
cat
```

O comando **cat** é muito importante já que grande parte das configurações do linux, estão em arquivos. 

```
hostname
```

Mostra o nome da sua máquina

```
hostnamectl set-hostname server.exemplo.com
```

Neste caso configuramos o nome da máquina e seu domínio como: server.exemplo.com

```
date
```

Mostra a hora e data do sistema

```
timedatectl
```

Mostra a timezone

```
timedatectl list-timezones
```

 Mostra a lista de timezones disponíveis.

```
timedatectl set-timezone America/Sao_Paulo
```

Ajusta a timezone para America - São Paulo.

```
date +%r
```

Mostra a hora no formato padrão e informação AM ou PM

```
date +%R
```

Mostra somente a hora

```
cal
```

Mostra um calendário

```
cal 2019
```

Mostra o calendário de 2019

```
cal 08 2019
```

Mostra o calendário de agosto de 2019

```
history
```

Mostra o histórico dos últimos comandos

```
!30
```

Executa o comando 30 da lista de histórico.

```
man
```

Abre as páginas de manual dos comandos.