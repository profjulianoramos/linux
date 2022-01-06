---
layout: post
title: Instalando flathub no fedora
date:   2020-06-25 05:44 +0530
categories: Fedora
---

Flathub é um repositório de terceiros para o formato flatpak. Muitos aplicativos que estão no Flathub também estão nos repositórios Fedora, porém, este mantém softwares mais atualizados.

[clique aqui](https://dl.flathub.org/repo/flathub.flatpakrepo) para fazer download do repositório, selecione abrir com a loja de software e faça sua instalação.

![flathub](/blog/images/loja.png)

Após instalar. Feche a loja e abra um terminal. Execute:

```bash
gnome-software --quit
```

Isto irá fazer com que a loja leia novamente os repositórios, quando você abrir ela novamente. 

Agora, os softwares do Flathub, vão estar disponíveis na busca dentro da loja.


Commits
- 25/06/2020 - 05:55 - Upload da publicação.
