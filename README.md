# WINDOWS

- Uma das possibilidades é usar o WSL [conforme esse post](https://rubyonrails.club/posts/como-instalar-o-wsl-no-windows-11)

# LINUX

# Instalando o Ruby e Rails via ASDF no macOS

## Pré requisitos

- Ter instalado o gerenciador de pacotes do macOS chamado Homebrew. [https://brew.sh/pt-br/](https://brew.sh/pt-br/)

## 1) Instalando a ferramenta de versionamento ASDF

Segundo o site oficial do ASDF [https://asdf-vm.com/guide/getting-started.html](https://asdf-vm.com/guide/getting-started.html) você pode instalar da seguinte maneira:

1. Instalando dependências do ASDF, caso ainda não tenha instalado em sua máquina. São eles o git e o curl
    
    ```bash
    brew install coreutils curl git 
    ```
    
2. Download do core do ASDF
    
    ```bash
    brew install asdf
    ```
    
3. Instalando o ASDF
    
    Neste exemplo, será instalado no terminal Bash e Git, porém caso use algum outro terminal, poderá seguir o passo 3 do link citado a cima.
    
    Adicionar as seguintes linhas na configuração do seu bash localizado em `~/.bashrc` :
    
    ```bash
    . "$HOME/.asdf/asdf.sh"
    . "$HOME/.asdf/completions/asdf.bash"
    ```
    

## 2) Instalando o Ruby via ASDF

1. Instalando o plugin do ruby
    
    ```bash
    asdf plugin add ruby
    ```
    
2. Instalando a versão 3.3.0 do ruby
    
    ```bash
    asdf install ruby 3.3.0
    ```
    
3. Definindo a versão do Ruby como global
    
    ```bash
    asdf global ruby 3.3.0
    ```
    
4. verificando se a versão do ruby instalada está rodando
    
    ```bash
    ruby -v
    ```
    

## 3) Instalando o Rails

Para instalar o Rails basta rodar o gerenciador de pacotes (gems) do ruby pedindo para instalar o Rails na versão 7.1.2

```bash
gem install rails -v 7.1.2
```
