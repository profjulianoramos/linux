---
layout: post
title: Boas práticas em Shell Script
date:   2022-01-12 07:16:00 +0530
categories: Shell Script
---

Vamos começar a falar um pouquinho de boas práticas ao criarmos um programa em shell script.

# Caminho Absoluto
É muito comum aprendermos que um script em shell começa com ``#!/bin/bash``. Mas este é o caminho absoluto do shell, ou seja, estamos com a certeza que o executável do bash está dentro do diretório /bin. Mas e se isto não for uma verdade? A resposta é simples, seu script não irá funcionar.

## Buscando o executável
Uma forma de contornarmos a situação do *caminho absoluto* é usando:

```
#!/usr/bin/env bash
```

O seu script então ficaria assim:

```
#!/usr/bin/env bash
echo "Olá mundo" 
```
# Exibindo uma variável com formatação
Podemos criar uma saída para uma variável (formatada) com espaços. Exemplo:

```
NOME="Juliano 
Ramos"
```
É comum imprimirmos a vaviável da seguinte forma:

```
echo $NOME
```

Neste caso o resultado será:

```
Juliano Ramos
```

Ou seja, na mesma linha. Para que o resultado seja exatamente como definimos na variável, coloque ela em aspas:

```
echo "$NOME"
``` 

Neste caso o resultado será:

```
Juliano 
Ramos
```

Para cálculos não mantemos as aspas:

```
NUMERO_1=24
NUMERO_2=30
TOTAL=$(($NUMERO_1+$NUMERO_2))
```

Na próxima dica, vamos falar sobre variáveis reservadas do Shell. 





 
