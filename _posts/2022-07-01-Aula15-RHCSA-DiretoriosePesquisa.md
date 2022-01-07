---
layout: post
title: Aula 15  - Curso RHCSA - Trabalhando com diretórios e pesquisando arquivos
date:   2022-01-07 08:43:00 +0530
categories: Curso RHCSA
---
Neste tópico vamos aprender como criar diretórios e a realizar pesquisa em arquivos. 


# Trabalhando com diretórios

```
mkdir testedir
mkdir -p admin/secretaria/documentos
```

Para subir o nível de diretório:

```
cd ..
```

Copiando:

```
cp -r diretorio/ /tmp/
```

Mover diretório:

```
mv diretorio/ /tmp/
```

Remover diretório:

```
rmdir diretorio_vazio
rm -r diretório
```

# Pesquisando arquivos



Pesquisa simples, diretório e nome do arquivo:

```
find /etc -name passwd
```

Pesquisa simples, porém sem case sensitive:

```
find /etc -iname PASSWD
```

Pesquisando por extensão:

```
find /etc -name "*.txt"
```

Pesquisando arquivos vazios em um diretório. Crie 3 arquivos em um diretório:

```
touch arquivo.txt arquivo2.txt arquivo3.txt
```

Coloque conteúdo em um deles:

```
echo "Ola mundo" > arquivo3.txt
```

Agora execute:

```
find /tmp/arquivos/ -type f -empty
```

Procurando e deletando arquivos vazios:

```
find /tmp/arquivos/ -type f -empty -exec rm -rf {} +
```

Encontrando e exibindo conteúdo:

```
find /tmp/arquivos -type f -iname file3.txt -exec cat {} +
```

Documentos modificados nos últimos 10 minutos:

```
find /tmp/arquivos -type f -mmin -10
```