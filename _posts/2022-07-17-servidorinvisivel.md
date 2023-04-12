---
layout: post
title: Servidor Camuflado e Invisivel
date:   2022-07-17 20:22:00 +0530
categories: Segurança
---
É possível deixar o servidor invisível na internet e mesmo assim acessá-lo em um ambiente seguro via linha de comando shell. 

## Port Knocking
O servidor pode ser camuflado para o mundo externo (internet) fechando-se todas as portas, esta técnica chama-se *Port Knocking*. 
O conceito de *Port Knocking* é pré-configurar algumas portas para acesso via shell seguro (SSH) *secure shell* e após o acesso fechá-las novamente. 

Quem já usou alguma ferramenta de segurança como o *NMAP* sabe que ele muitas vezes consegue distinguir se as portas estão fechadas ou se existe serviços enscondidos através dela. 

Uma forma de mascarar uma porta é usando o próprio firewall do linux inserindo o argumento:

```
-j REJECT-reject-with tcp-reset
```

Usando esta técnica, podemos ficar seguros de que nenhuma informação desnecessária sobre o sistema seja revelada. Existe uma discussão sobre a regra REJECT e a regra DROP (qual seria mais segura) neste endereço:

https://www.chiark.greenend.org.uk/~peterb/network/drop-vs-reject.html

### Instalação do Knockd
O *knockd* é uma aplicação que permite usar a técnica de *Port Knocking* no nosso servidor. No Debian, instalamos com:

```
# apt install knockd
```

No Red Hat :

```
# yum install knockd
```
Instale o `iptables` necessário para o knockd:

```
# apt install iptables
```


No Debian o arquivo de configuração está em: `/etc/knockd.conf`, exemplo do arquivo:

```
[options]
	UseSyslog

    Interface = enp0s3


[openSSH]
	sequence    = 7000,8000,9000
	seq_timeout = 5
    command     = /sbin/iptables -I INPUT -s %IP% -p tcp --dport 22 -j ACCEPTACCEPT
	tcpflags    = syn

[closeSSH]
	sequence    = 9000,8000,7000
	seq_timeout = 5
	command     = /sbin/iptables -D INPUT -s %IP% -p tcp --dport 22 -j ACCEPT
	tcpflags    = syn

[options]
        LogFile = /var/log/portknocking.log


```

Eu precisei adicionar manualmente minha interface de rede no arquivo `Interface = enp0s3`. Assim como um local para obter só o log do serviço:

```
[options]
        LogFile = /var/log/portknocking.log
```

Outra mudança que eu fiz no arquivo original foi:

```
command     = /sbin/iptables -I INPUT -s %IP% -p tcp --dport 22 -j ACCEPT
```

Que garante que as regras de abertura de porta tenha precedência sobre as demais. 

Ative o serviço na inicialização:
```
# systemctl enable knockd
```

E adepois suba o serviço:

```
# systemctl start knockd
```

Configure o firewall para bloquear todas as conexões:

```
# iptables -A INPUT -j DROP
```

Agora instale na máquina cliente o knockd :

```
# sudo apt install knockd 
```

No Opensuse existe um pacote separado só para o cliente:

```
# zypper install knock
```

Feito isto, execute a sequença para habilitar a conexão ssh:

```
# knock 192.168.0.28 7000:tcp 8000:tcp 9000:tcp
```

Feito isto, acesse normalmente seu servidor via SSH:

```
ssh usuario@servidor
```

Quando desejar fechar as portas:

```
# knock 192.168.0.28 9000:tcp 8000:tcp 7000:tcp
```

Você deve alterar este padrão de porta no */etc/knockd.conf* para mais segurança. 