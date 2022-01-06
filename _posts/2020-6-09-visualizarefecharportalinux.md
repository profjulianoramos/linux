---
layout: post
title: Verificar portas abertas no linux e fechá-las
date:   2020-06-17 22:19:00 +0530
categories: servidor linux
---

É tarefa de um administrador linux, localizar e se necessário fechar portas indesejadas no servidor. Para esta tarefa, tudo de que precisa, é uma instância linux em execução e um usuário com previlêgio administrativo.

O comando **netstat** foi descontinuado e não deve ser usado, usaremos então o comando **ss**. 

```bash
sudo ss -tulwn | grep LISTEN
```

As opções usadas são:

- -t Mostra apenas conexões TCP 
- -u Exibe apenas conexões UDP
- -l Mostra conexões de escuta (por exemplo, a porta 22 aberta pelo servidor SSHD)
- -p Lista o nome do processo que abriu a conexão
- -n Não resolve nomes de serviço

![portas](https://profjulianoramos.github.io/linux/blog/images/portas.png)

Se você visualiza uma porta, mas não sabe a qual serviço ela pertence. Consulte esta lista:

```bash
less /etc/services
```

Digamos que eu quero fechar a porta 22. Para isto eu executo o comando:

```bash
sudo ufw deny 22
```

![ufw](https://profjulianoramos.github.io/linux/blog/images/ufw.png)

Para abrir a porta, usamos:

```bash
sudo ufw allow 22
```

![ufwallow](/blog/images/ufw.png)

O UFW (Uncomplicated FireWall) não está presente em todas as distribuições. Por isto, eu ainda recomendo que você aprenda os comandos do bom e velho iptables.


Commits
- 17/06/2020 - 22:41 - Upload da publicação.
- 17/06/2020 - 22:43 - Reeditei o título que estava com o mesm nome da publicação anterior. 
