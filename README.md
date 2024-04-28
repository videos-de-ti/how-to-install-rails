# Requisitos Iniciais

## Windows

1. WSL [Instalar o WSL | Microsoft Learn](https://learn.microsoft.com/pt-br/windows/wsl/install)

2. Docker Desktop [Docker Desktop](https://www.docker.com/products/docker-desktop/)

3. Docker Settings

![Imagem da pagina settings do socker desktop mostrando a aba resources onde Enable integration esta ativado junto a distro Ubunto ](Captura%20de%20tela%202024-04-26%20134649.png)



4. Vscode [https://code.visualstudio.com/](https://code.visualstudio.com/)

> Mantenha todo o seu projeto no WSL para evitar lentidão

## Linux

1. Docker [Docker Desktop](https://www.docker.com/products/docker-desktop/)

2. Vscode [https://code.visualstudio.com/](https://code.visualstudio.com/)

## Mac

__________________________________________________________________________________________________

# Iniciando o Setup

1-Crie o arquivo com o nome do projeto

```
mkdir meu-app-rails
cd meu-app-rails
```

2-Baixe | abra no vscode

```
code .
```

3-Com o vscode aberto na pasta do projeto vá na aba extensões e verifique se a extensão dev containers já está habilitada, se não estiver procure no por dev containers e faça a instalação.

![image do marketplace do vscode mostrando a pesquisa dev containers com o resultado sendo a extesão da microsoft ](Captura%20de%20tela%202024-04-28%20141152.png)



4-Com a extensão no Vscode aperte o botão **F1** do seu teclado, um menu de opções do dev container aparecerá, escolha a opção **"Dev containers: Open Folder in Container..."**

![Imagem com o menu do dev containers contendo a opção dev containers: open folder in container](Captura%20de%20tela%202024-04-26%20141203.png)



5-Confirme o arquivo que vc abrirá no container

![menu de confirmação com o botão ok](Captura%20de%20tela%202024-04-26%20141420.png)



6-No próximo menu escreva “ruby” a extensão te retorna algumas opções de containers com Ruby, escolha opcao Ruby on Rails & Postgres e em seguida escolha a versão do Ruby (recomendado sempre escolher a primeira/default)

![Imagem com o menu do dev containers contendo a opção Ruby on Rails e Postgresql](Captura%20de%20tela%202024-04-26%20141550.png)


7-Agora no menu de features vamos escolher algumas ferramentas importantes para o desenvolvimento. Nesse menu vamos procurar por Redis Server,Node e github-cli.

![Imagem mostrando a feature Redis Server](Captura%20de%20tela%202024-04-26%20142029.png)

![Imagem mostrando a feature Node.js via nvm,yan e pnpm](Captura%20de%20tela%202024-04-26%20142150.png)

![Imagem mostrando a feature Github-cli](Captura%20de%20tela%202024-04-26%20142255.png)


Depois dessa etapa a extensão vai mostrar alguns prompts de versões das features, apenas escolha default e latest e prossiga com a instalação

> Redis escolha a versão 7

Após isso um novo container será criado.

### **Importante!**

Isto pode demorar um **bom** tempo, o Docker vai baixar as imagens e fazer todo o setup ,então não estranhe se demorar muito.

8-Após o término do setup é recomendado testar se tudo está funcionando corretamente

```
ruby -v
```

```
rails -v
```

```
node -v
```

```
redis-cli ping
```

![Imagem com o restorno dos comandos sendo redis: pong, Ruby: ruby mais a versão 3.3, rails 7.1.3, node v 20.12 e yarn 1.22](Captura%20de%20tela%202024-04-26%20145757.png)

Se os comandos tiverem retorno o seu setup já está pronto para o desenvolvimento.



9-Inicie um novo projeto com:

```
rails new . -d postgresql
```

> Usar o “.” após o “new” faz com que o seu projeto seja criado na pasta atual e com o nome da mesma.



10-Após isso adicione o host, user e password no config/database.yml.

```
development:
  <<: *default
  database: pr_test_development
  host: db
  username: postgres
  password: postgres

test:
  <<: *default
  database: pr_test_test
  host: db
  username: postgres
  password: postgres
```

11-agora é só iniciar a sua aplicação rails e fazer a migration:

```
rails s
```

## Extensões do Vscode

Para adicionar extensões e temas ao vscode pesquise pela extensão que deseja acionar e na pagina da extensão va no símbolo de engrenagem e escolha a opção **"Add to devcontainer.json"** e faça o Rebuild do container.Agora todas as vezes que iniciar o container tera sempre as extensões que você escolheu.



## Gems e comandos adicionais

As vezes precisamos de Gems no ambiente de desenvolvimento ,mas não da aplicação para isso existe uma maneira fácil de fazer usando containers.

1. Vá em devcontainers.json

2. Descomente a linha com  "postCreateCommand":

3. Agora adicione as gems e os comandos que você quiser ao seu ambiente

Exemplo:

```
"postCreateCommand": "gem install solargraph && bundle",
```

> Recomendo adicionar sempre o comando budle em todos os containers para que o container já faça o bundle install automaticamente ao iniciar.



Fim
