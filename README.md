# WINDOWS

- Uma das possibilidades é usar o WSL [conforme esse post](https://rubyonrails.club/posts/como-instalar-o-wsl-no-windows-11)

# LINUX

# INSTALANDO O RUBY ON RAILS VIA ASDF NO LINUX

ASDF é uma ferramenta para o gerenciamento de versões para múltiplas linguagens de programções.
Nesse tutorial, vomos aprender a intalar e gerenciar as versões do Ruby e do framework Rails,


## Passo 1 -> Instalar ferramentas de desenvolvimento

Inicialmente, precisamos instalar as ferramentas base de desenvolvimento e utilitários, com o comando a seguir:

    sudo apt update
    sudo apt install -y build-essential autoconf libssl-dev libyaml-dev libreadline-dev libncurses-dev \  
    libxslt-dev libffi-dev libtool zlib1g-dev unzip zip git vim curl wget

## Passo 2 -> Instalar o ASDF

Agora, vomos instalar o ASDF usando o comando abaixo:

    git clone https://github.com/asdf-vm/asdf.git ~/.asdf
    cd ~/.asdf  
    git checkout "$(git describe --abbrev=0 --tags)"

## Passo 3 -> Bash

Nesse passo, precisamos adicionar as configurações de ambiente no **~/.bashrc**:

    echo -e '\n. $HOME/.asdf/asdf.sh' >> ~/.bashrc  
    echo -e '\n. $HOME/.asdf/completions/asdf.bash' >> ~/.bashrc
    source ~/.bashrc

Validando a instação do ASDF

    asdf --version

O resultado do comando acima deve ser semelhante a isso :

    ➜  ~ asdf --version
    v0.11.3-2f55f93
    ➜  ~ 

## Passo 4 -> Adicionando os Plugins  e Instando o Ruby

Nesse momento, vomos adicionar os plugins necessários para instalar o Ruby com seguinte comando:

    asdf plugin-add ruby
 
Agora podemos instalar o Ruby em nossa máquina: 

    asdf install ruby 3.3.0
    
Vomos definir a versão padrão do Ruby

    asdf global ruby 3.3.0

Vomos validar se o Ruby foi instaldo corretamente, com o comando abaixo:

    ruby -v
O resultado deve ser semelhante a isso: 

    ➜  ~ ruby -v
    ruby 3.3.0 (2023-12-25 revision 5124f9ac75) [x86_64-linux]
    ➜  ~

## Passo 5 -> Instalando o Rails
Por fim, mas não menos importante, vomos instalar o nosso framework Rails com o comando abaixo:

    gem install rails
    
Validando a Instalação do Rails:

    rails -v
    
  O resultado do seu terminal deve ser semelhante a isso:

    ➜  ~ rails -v
    Rails 7.1.3.2
    ➜  ~ 

  
## Adicional
Podemos instalar o NodeJs também usando o ASDF, com os comando semelhante aos que foram mostrados acima:

    asdf plugin-add nodejs
    asdf install nodejs 20.10.0
    asdf global nodejs 20.10.0
    node -v

Agora podemos visualizar os plugins, linguagens e versões que foram instaladas pelo ASDF com o seguinte comando:

    ➜ ~ asdf list  
    
E o resultado será semelhante a isso:

    ➜ ~ asdf list                                                         
    nodejs
      18.16.1
     *20.10.0
    ruby
      2.7.4
      2.7.8
      3.2.2
     *3.3.0
    ➜  ~ 

Se quiser saber mais informações sobre o ASDF, siga o link abaixo:

[https://asdf-vm.com](https://asdf-vm.com/#/)

[https://github.com/asdf-vm/asdf](https://github.com/asdf-vm/asdf)

# MAC
