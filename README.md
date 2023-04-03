# Passos GIT

## git config

- git config --global user.name "USER"
- git config --global user.email EMAIL

Obs: Onde tem user e email, substituir pelo seu usuário e email respectivamente 

## Geração de chave

Criação de um novo par de chaves rsa.

- ssh-keygen -t ed25519 -C "wesleycristiano@outlook.com"
- ssh-keygen -t rsa -b 4096 -C "wesleycristiano@outlook.com"

## Adicionar chave privada no ssh-agent

O ssh-agent é um gerenciador de chaves ssh. Para que a conexão funcione, devemos adicionar a chave privada nesse gerenciador. Para isso vamos executar os códigos:

### Rodar o ssh-agent

- eval $(ssh-agent -s)

### incluir a chave privada

- ssh-add ~/.ssh/id_ed25519

## Copiar chave pública

### Windows

- clip < ~/.ssh/id_ed25519.pub

### No Linux

- cat ~/.ssh/id_ed25519.pub

### No MacOS

- pbcopy < ~/.ssh/id_ed25519.pub

## Adicionar chave no Github

- Abra o Github e vá no ícone de perfil > Settings, no canto superior direito.
- Na barra lateral de configurações do usuário, clique em "SSH and GPG keys".
- Clique no botão "New SSH key"
- No campo "Título", adicione um rótulo descritivo para a nova chave. Por exemplo, se estiver usando seu computador pessoal, você pode chamar essa chave de "Computador pessoal".
- Cole a chave pública que está na área de transferência no campo "Chave".
- Clique em "Add SSH key" e pronto!

## Testando a conexão SSH

- Executar o seguinte comando: ssh -T git@github.com
- Aguardar as mensagens. Digitar "yes" para continuar.
- Verifique se a mensagem resultante contém seu nome de usuário e o sucesso da sua autenticação.

## Para erros

[Clique aqui](https://docs.github.com/en/authentication/troubleshooting-ssh/error-permission-denied-publickey)
