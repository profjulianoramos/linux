---
layout: post
title: Aula 13  - Curso RHCSA - Lendo arquivo de texto.
date:   2022-01-07 08:36:00 +0530
categories: Curso RHCSA
---
Neste tópico vamos aprender como ler um arquivo de texto usando os comandos básicos do linux. Também indico um **pdf** para download com conteúdo sobre a estrutura de arquivos linux, conhecida como FHS - File Hierarchy Standard. 

# Estrutura de arquivos no linux FHS

https://www.pathname.com/fhs/pub/fhs-2.3.pdf

# Diferentes modos de ler um arquivo

Sem dúvida o comando **cat** é o mais utilizado para a leitura de um arquivo:

```
cat arquivo.txt
cat -n arquivo.txt
cat -b arquivo.txt
```

Outra opção:

```
less arquivo.txt
head arquivo.txt
head -n 2 arquivo.txt
tail arquivo.txt
tail -n 2 arquivo.txt
tail -f arquivo.txt
```

Ler dois arquivos

```
tail -n 5 arquivo.txt arquivo2.txt
head -n 2 arquivo.txt arquivo2.txt
```

Adicionando linha conteúdo com cat

```
cat >>arquivo.txt
novo conteudo aqui e <ctrl>+<c> para sair
```

# Navegar e listar diretórios

Usamos como padrão o **ls** para listar arquivos e diretórios.

```
touch cria_arquivo.txt
```

Diferentes modos de listar:

```
ls ~
ls /
ls /etc
ls -l
ls -al
ls -lh
ls -ls
ls -R
ls *.txt
```