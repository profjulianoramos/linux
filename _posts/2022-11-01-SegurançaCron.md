---
layout: post
title: Segurança em Servidor Linux - Cron e AT
date:   2022-01-11 09:55:00 +0530
categories: Segurança
---
Uma falha de segurança comum em servidores linux é deixar todos os usuários com o direito de criar agendamento no cron, padrão em quase todas as distribuições de linux.

Dois exemplos que isto pode resultar:
- Um usuário malicioso pode gerar copias de arquivos (sobrecarregando o disco)
- Um usuário malicioso pode tentar de algum modo obter acesso administrativo

O primeiro passo é excluir os arquivos ``/etc/cron.deny`` e ``/etc/at.deny``:


```
sudo rm /etc/cron.deny 
sudo rm /etc/at.deny
```

Em seguida recomendo a criação dos arquivos ``/etc/cron.allow`` e ``/etc/at.allow`` com as devidas permissões:

```
sudo touch /etc/cron.allow
sudo touch /etc/at.allow
sudo chown root:root cron.allow at.allow
sudo chmod 400 cron.allow at.allow
```

Reinicie os serviços cron e at:

```
sudo systemctl restart cron
sudo systemctl restart at
```

Nos arquivos criados, você pode definir o nome dos usuários que "podem" usar a cron.



