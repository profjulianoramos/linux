---
layout: post
title: Script Shell ou Programa em Shell?
date:   2022-04-06 10:36:00 +0530
categories: Shell 
---

Quando falamos a palavra script é natural já pensarmos no contexto de roteiro. Algo com começo meio e fim. Como um "script de peça de teatro". 

# Shell Script ou Programa em Shell?

No Shell, um script não é muito diferente disto. São comandos um após o outro, que são executados em sequência.
Quando comecei a usar o linux, no final da década de 90, scripts eram encarados como programas. 
Existia uma disciplina dos programadores ao criá-los. Eram estruturados, com cabeçalho, versionamento e dados do mantenedor. 
Com o passar do tempo e a chegada das certificações formando Administradores de Sistemas a toque de caixa, os scripts foram aos poucos sendo substituídos por ferramentas
prontas e observei que hoje em dia são poucos os sysadmins que se dedicam a criar bons scripts.

Em geral quando olhamos scripts criados por Administradores de Sistemas, dá aquela de impressão de algo feito nas coxas. Ainda tinha um jargão que ouvi muito:

**"Simplesmente, Funciona!"**

Mas não tem nada de simples. Por que sem comentário e um código limpo e estruturado, ele pode até atender aquele problema,
mas provavelmente não vai ser atualizado e vai acabar morrendo, como centenas e centenas de scripts criados temporariamente todo o tempo.

Como a grande maioria dos Sysadmins não são programadores é natural que os scripts sejam em maioria escritos em "cinco minutos". 
Eu mesmo não sou programador!, apesar de minha formação em engenharia da computação. 
Sempre atuei servidores linux diversos e segurança, mas raramente programo, no entanto, quando vou criar algo, tenho o cuidado de fazer o mínimo possível, para que outros possam entender e dar continuidade ao trabalho.

É pensando em tudo isto, que decidi escrever este artigo, ele é de **"Sysadmin para Sysadmin"**. Amigos, façam o melhor possível em seus Scripts Shell e transforme-os em programas em Shell.

## Qual a diferença entre um script e um programa?
No nosso contexto (servidores linux) eu sempre diferenciei um script de um programa em shell, analisando o seguinte:



- Script é escrito de qualquer maneira
- Código feito e mal estruturado, sem quebra de linha
- Sem manutenção
- Feito rapidamente para atender um problema cotidiano


Quando olho um programa em shell:

- Codificação estruturada
- Código limpo
- Feito por um Administrador experiente ou um Programador
- Bugs informados e corrigidos
- Programa em evolução

## Comece a escrever programas
Agora que entendemos esta diferença entre script e programa, vamos começar a conhecer o básico sobre como escrever bons programas em shell.

## Um bom cabeçalho
O cabeçalho deve dar uma explicação geral sobre o programa. O cabeçalho é um texto comentado (#). Exemplo:

```
# Este programa mostra informações dos dispositivos PCI da máquina.
# Você pode usar a sintaxe -d para mais detalhes, exemplo:
#﻿﻿ hardinfo -d
```
Um bom cabeçalho contêm:

- Nome
- Contatos
- Mantenedor
- Exemplo
- Versionamento
- Testado

Exemplo de um código estruturado:


```shell
#!/usr/bin/env bash

#

# Clonar Moodle

#

# Site:   http://www.profjulianoramos.com.br

# Autor:   Juliano Ramos

# Manutenção:  Juliano Ramos

#

# ------------------------------------------------------------------------ #

# Este programa irá clonar o moodle do servidor para o ambiente de homologação

#

# Exemplos:

#   $ ./clonarmoodle -h

#   Neste exemplo o script será executado no modo debug 

# ------------------------------------------------------------------------ #

# Histórico:

#

#  v1.0 17/05/2020, Juliano:

#    - Início do programa

#    - Conta com a funcionalidade X

#  v1.1 17/06/2020, Juliano

#    - Alterado parametro XXXXX

# ------------------------------------------------------------------------ #

# Testado em:

#  bash 4.4.19

# Ksh, Zsh, Dash, Fish 

# Ubuntu, Deepin, Debian, Suse

# ------------------------------------------------------------------------ #

# Agradecimentos:

#

# 	Tux - Encontrou um bug no parametro -h

# Licença: GPL	 
```




As  vezes o cabeçalho pode ficar maior que o programa, mas isto não é um problema, 
já que o interpretador ignora as linhas de comentário. Ou seja, isto não vai influenciar no desempenho do seu programa.


## Quebrando as linhas
É comum ver scripts assim:

```
dialog --title "Programa xyz" --msgbox "Programa de analise de hardware" 0 0 
```
Mas, para facilitar a leitura:

```
dialog﻿ \
--title "Programa xyz" \
--msgbox "Programa de analise de Hardware" \
0 0﻿
```

Na próxima parte deste artigo, vou abordar sobre os tipos de comentários que podemos adicionar aos nossos programas em shell. 
