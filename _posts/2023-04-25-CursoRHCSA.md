---
layout: post
title: Curso RHCSA 2023 - Aula 1
date:   2023-04-25 08:27:00 +0530
categories: RHCSA
---
Este curso é sobre o conteúdo da certificação RHCSA atualizado 2023. Acompanhe as próximas publicações.

# Introdução ao curso Red Hat RHCSA

![Bem Vindo](https://developers.redhat.com/sites/default/files/styles/large/public/RHEL-helloworld.png?itok=kTPVSU3E)

Este curso será dividido em publicações aqui no blog e em vídeos no meu canal.

> Meu canal no youtube: [https://www.youtube.com/profjulianoramos](https://www.youtube.com/profjulianoramos)

Para instalar o RHEL é necessário a seguinte configuração:

- 512 MB RAM
- 4GB Disco
- Placa ethernet

Recomendado

- 1GB RAM
- 10GB Disco
- Placa ethernet

![Red hat](https://developers.redhat.com/sites/default/files/styles/large/public/Logo-Red_Hat-Enterprise_Linux_8-B-Standard-RGB.png?itok=keWYSR8I)

O Red Hat precisa de uma licença e um cadastro para seu download. Na opção "Developers" isto é gratuito.

Acesse: [https://developers.redhat.com/sites/default/files/styles/large/public/Logo-Red_Hat-Enterprise_Linux_8-B-Standard-RGB.png?itok=keWYSR8I](https://developers.redhat.com/sites/default/files/styles/large/public/Logo-Red_Hat-Enterprise_Linux_8-B-Standard-RGB.png?itok=keWYSR8I)

Após a instalação do RHEL abra um terminal e digite:

```shell
# su root
# localectl list-locales | grep -i pt
# localectl set-locale pt_BR.UTF8
```

Reinicie a sessão.


## Elevar do mínimo para o Gnome desktop

Vamos nesta etapa usar o DVD do Red Hat. Para isto coloque em sua máquina de virtualização o DVD.

Verifique no Red Hat o disco:

```
# lsblk
```

Crie o diretório para ponto de montagem:

```
# mkdir /dvdinstall
```

Agora monte:

```
# mount /dev/srv0 /dvdinstall
```

Acesse o diretório de repositório:

```
# cd /etc/yum.repos.d/
```

Crie o arquivo de repositório:

```
# vi dvdinstall.repo
```

Coloque o conteúdo:

```
[BaseOS]
name=BaseOS
baseurl=file:///dvdinstall/BaseOS
gpgcheck=0
enable=1

[AppStream]
name=AppStream
baseurl=file:///dvdinstall/AppsStream
gpgcheck=0
enable=1
```

Limpe os repositórios:

```
# yum clean all
```

Execute

```
# yum repolist
```

Por fim:

```
# yum -y groupinstall "Server with GUI"
```

Defina o ambiente gráfico:

```
# systemctl set-default graphical.target
```

Reinicie o sistema.


> Documento atualizado no dia 25 de Abril de 2023.
