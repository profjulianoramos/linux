---
layout: post
title: Shell Script
date:   2023-05-22 19:50:00 +0530
categories: Shell
---
Por que devemos aprender o shell do linux?

## Aprender o shell Bash (Bourne Again SHell) pode ser benéfico por várias razões:

- Automação de tarefas: O Bash é uma linguagem de script poderosa que permite automatizar tarefas no sistema operacional. Com o Bash, você pode criar scripts para executar ações repetitivas, como copiar, renomear e excluir arquivos, manipular dados, executar comandos em sequência, entre outros.
- Administração de sistemas Unix/Linux: O Bash é o shell padrão em sistemas Unix e Linux, tornando-se uma habilidade essencial para administradores de sistemas. Com o Bash, você pode gerenciar usuários, permissões de arquivos, processos, serviços e configurar o ambiente do sistema.
- Interação com a linha de comando: O Bash permite que você interaja com o sistema operacional por meio da linha de comando de forma eficiente. Você pode executar comandos, utilizar redirecionamentos e pipes para manipular a entrada e saída de dados, além de utilizar expressões regulares para filtrar e processar informações.
- Personalização do ambiente: O Bash oferece recursos de personalização do ambiente de trabalho do usuário. Você pode criar e configurar variáveis de ambiente, definir aliases para comandos frequentemente utilizados, personalizar o prompt de comando, entre outras opções.
- Portabilidade: O Bash é amplamente suportado em diferentes sistemas operacionais, o que significa que os scripts escritos em Bash podem ser executados em uma variedade de ambientes. Isso torna a aprendizagem do Bash valiosa, independentemente do sistema operacional que você esteja utilizando.
- Compatibilidade com outros shells: O Bash é um shell que oferece suporte à maioria dos recursos dos shells anteriores, como o Bourne Shell (sh) e o C Shell (csh). Isso significa que, ao aprender o Bash, você também terá um bom entendimento desses shells e poderá trabalhar em ambientes que os utilizam.

Em resumo, aprender o shell Bash pode ajudar a melhorar a produtividade, a capacidade de automação e a compreensão do sistema operacional. É uma habilidade valiosa para administradores de sistemas, desenvolvedores e qualquer pessoa que deseje ter mais controle sobre seu ambiente de trabalho em um sistema Unix/Linux.

## Um pouco da história do shell bash
O Bash (Bourne Again SHell) é um shell de linha de comando e interpretador de script que se tornou um dos shells mais populares em sistemas Unix e Linux. Ele foi desenvolvido por Brian Fox e lançado pela primeira vez em 1989 como uma versão melhorada do Bourne Shell (sh), criado por Stephen Bourne.

O Bourne Shell foi lançado originalmente em 1979 como o shell padrão para o sistema operacional Unix. Ele oferecia uma maneira interativa de interagir com o sistema operacional por meio da linha de comando, permitindo a execução de comandos e scripts para manipular arquivos, processos e outros aspectos do sistema.

O desenvolvimento do Bash começou em 1987, quando Brian Fox foi contratado para criar um shell compatível com o Bourne Shell, mas com recursos adicionais e melhorias. O Bash foi desenvolvido como um software livre e de código aberto, licenciado sob a GNU General Public License (GPL).

Uma das principais melhorias introduzidas pelo Bash em relação ao Bourne Shell foi a adição de recursos avançados, como expansão de variáveis, expansão de nome de arquivo curinga (wildcard), redirecionamentos de entrada e saída, substituição de comando, histórico de comandos e suporte a scripts com controle de fluxo (loops, condicionais, etc.).

O Bash também incluiu várias melhorias de usabilidade, como edição interativa de linha de comando, autocompletar de comandos e nomes de arquivos, além de suporte a configuração de teclas de atalho personalizadas.

Ao longo dos anos, o Bash se tornou amplamente adotado como o shell padrão em sistemas Unix e Linux. Ele se beneficiou do crescimento desses sistemas operacionais e se tornou a escolha preferida de muitos administradores de sistemas, desenvolvedores e usuários avançados devido à sua poderosa funcionalidade e facilidade de uso.

O Bash também influenciou o desenvolvimento de outros shells, como o Zsh (Z Shell) e o Ksh (Korn Shell), que são compatíveis com a sintaxe e os recursos do Bash, mas adicionam recursos adicionais e aprimoramentos.

Atualmente, o Bash continua sendo amplamente utilizado e é considerado uma habilidade essencial para qualquer pessoa que trabalhe com sistemas Unix e Linux. Sua história rica e sua ampla adoção o tornaram uma ferramenta poderosa para automação de tarefas, administração de sistemas e interação com o sistema operacional por meio da linha de comando.

## Como faço meu primeiro script em shell bash?
Passo 1: Abra um editor de texto
Abra um editor de texto no seu sistema operacional. Pode ser o Bloco de Notas (Windows), Gedit (Linux) ou qualquer outro editor de texto de sua preferência.

Passo 2: Crie um novo arquivo
Crie um novo arquivo no editor de texto e defina sua extensão como ".sh" para indicar que é um script em shell Bash. Por exemplo, você pode nomear o arquivo como "meu_script.sh".

Passo 3: Defina o interpretador
Na primeira linha do seu arquivo de script, você precisa indicar qual interpretador de script será usado para executar o código. No caso do shell Bash, insira a seguinte linha no início do arquivo:

```shell
#!/bin/bash
```

Essa linha é chamada de shebang e informa ao sistema operacional que o script deve ser executado usando o interpretador "bash".

Passo 4: Escreva o código do script
Agora você pode começar a escrever o código do seu script em Bash. Você pode adicionar comandos Bash, variáveis, estruturas de controle, redirecionamentos de entrada/saída e muito mais. Por exemplo, vamos criar um script simples que exibe uma mensagem na tela:

```shell
#!/bin/bash
```


# Exemplo de script Bash

```shell
echo "Olá, mundo!"
```

Nesse exemplo, o comando echo é usado para imprimir a mensagem "Olá, mundo!" na saída padrão.

Passo 5: Salve o arquivo
Após escrever o código do seu script, salve o arquivo com as alterações feitas.

Passo 6: Tornar o script executável
Antes de executar o script, você precisa torná-lo executável. No terminal, navegue até o diretório onde o arquivo do script está localizado e execute o seguinte comando:

```shell
chmod +x meu_script.sh
```

Isso dará permissão de execução ao arquivo.

Passo 7: Execute o script
Agora você pode executar o script Bash. No terminal, navegue até o diretório onde o arquivo do script está localizado e execute o seguinte comando:

```shell
./meu_script.sh
```

Isso executará o script usando o interpretador Bash e você verá a mensagem "Olá, mundo!" exibida na saída.

Pronto! Você criou e executou seu primeiro script em shell Bash. A partir daqui, você pode continuar aprendendo e explorando recursos mais avançados do Bash para automatizar tarefas e realizar várias outras operações no sistema.

## Um exemplo básico para iniciantes
Aqui está um exemplo básico de um script em shell Bash para iniciantes:

```shell
#!/bin/bash

# Exemplo de script Bash para soma de dois números

# Solicitar ao usuário para inserir o primeiro número


echo "Digite o primeiro número:"
read numero1

# Solicitar ao usuário para inserir o segundo número
echo "Digite o segundo número:"
read numero2

# Realizar a soma dos números
soma=$((numero1 + numero2))

# Exibir o resultado da soma
echo "A soma de $numero1 e $numero2 é igual a $soma."
```

Nesse exemplo, o script solicita ao usuário que insira dois números e, em seguida, calcula e exibe a soma dos números fornecidos.


Para executar o script:

- Abra um editor de texto e salve o código acima em um arquivo com a extensão ".sh", por exemplo, "soma.sh".
- Abra o terminal e navegue até o diretório onde o arquivo do script foi salvo.
- Tornar o arquivo do script executável com o comando `chmod +x soma.sh`.
- Execute o script com o comando ./soma.sh.
- O script solicitará que você insira dois números. Digite os números e pressione Enter.
- O script calculará a soma dos números e exibirá o resultado.

Esse é apenas um exemplo básico para ajudar você a começar com o shell Bash. À medida que você se familiariza com a linguagem e seus recursos, poderá criar scripts mais complexos e realizar uma variedade de tarefas no sistema operacional.

Aprender shell pode ser muito divertido, não tenha medo, aventure-se.
