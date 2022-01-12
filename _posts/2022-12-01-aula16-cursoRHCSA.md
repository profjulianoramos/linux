---
layout: post
title: Aula 16 - Curso RHCSA - Comprimindo e extraindo arquivos
date:   2022-01-12 08:44:00 +0530
categories: Curso RHCSA
---

Vamos aprender nesta aula como comprimir e extrair arquivos nos formatos bz2,gip e xz.
Para iniciar, Copie o conteúdo do diretório /etc para /tmp/laboratorio:

```
cp -rvf /etc/ /tmp/laboratorio
```

Criando um pacote .tar.bz2

```
tar -cvjf arquivo.tar.bz2 /tmp/laboratorio/
```

Veja o seu tamanho:

```
du -sh arquivo.tar.bz2
```

Veja o original:

```
du -sh /tmp/laboratorio
```

Listar o conteúdo:

```
tar -tvf arquivo.tar.bz2
```

Crie o diretório para extrair:

```
mkdir extrair
```

Agora:

```
tar -xvjf arquivo.tar.bz2 -C /tmp/extrair
```

Uma lista do comando tar

- -f = filename
- -v = verbose
- -c = create an archive
- -j = .bz2
- -z = .gz2
- -x = extract
- -t = list contents of an archive
- -C = change directory
