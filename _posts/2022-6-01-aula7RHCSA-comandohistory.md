---
layout: post
title: Aula 7  - Curso RHCSA - Trabalhando com o History
date:   2022-06-01 08:30:00 +0530
categories: Curso RHCSA
---

Neste tópico, vamos aprender um pouco sobre o comando history, que permite a navegação por comandos realizados anteriormente no sistema. 

Ao executar o comando **history** você terá acesso ao histórico de comandos. Se você tiver muitos comandos no histórico, você pode desejar paginar, neste caso, execute:

```
history | more
```

Visualizar os últimos 5 comandos:

```
history 5
```

Executar um comando específico:

```
!29
```

Executar o último comando que se inicio com a letra **c**

```
!c
```

Tecla **ctrl + r** inicia a busca por comandos do histórico.

```
!!
```

Para executar o último comando

```
export HISTTIMEFORMAT='%F %T '
```

Este comando altera o formato com que o comando history exibe o histórico. Colocando agora a data e a hora. O comando **export** altera a variável global HISTTIMEFORMAT.

```
history | grep host
```

Retorna comandos que iniciam com **host** .  A variável que mostra a quantidade de comandos do histório é HISTFILESIZE, por padrão o Red Hat mostra os últimos 1.000 comandos. Você pode alterar:

```
export HISTFILESIZE=2000
```

Para deletar uma linha, você pode usar:

```
history -d 42
```

Neste caso ele remove a linha 42. Para não manter um histórico, você pode definir a variável como:

```
history HISTSIZE=0
```