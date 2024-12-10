# SETUP RUBY ON RAILS - GERENCIADOR RBENV

## O.S UBUNTU 24.04

### CONFIGURANDO RUBY

```bash
# INSTALAR DEPENDÊNCIAS:
sudo apt install -y git curl libssl-dev libreadline-dev zlib1g-dev autoconf bison build-essential libyaml-dev libreadline-dev libncurses5-dev libffi-dev libgdbm-dev

# INSTALAR GERENCIADOR RBENV:
curl -fsSL https://github.com/rbenv/rbenv-installer/raw/HEAD/bin/rbenv-installer | bash
echo 'export PATH="$HOME/.rbenv/bin:$PATH"' >> ~/.zshrc
echo 'eval "$(rbenv init -)"' >> ~/.zshrc
source ~/.zshrc

# LISTAR VERSÕES RUBY:
rbenv install -l

# INSTALAR VERSÃO ESPECÍFICA:
rbenv install 3.3.6

# DEFINIR VERSÃO ESPECÍFICA:
rbenv global 3.3.6
ruby -v

# ATUALIZAR BIBLIOTECAS:
gem update --system
gem -v

# INSTALAR BUNDLER:
gem install bundler

# CONCLUIR INSTALAÇÃO:
rbenv rehash
# Reiniciar terminal

# ATUALIZAR:
cd ~/.rbenv
git pull
```

### CONFIGURANDO RUBY-LSP

```bash
# ACESSAR DIRETÓRIO RUBY:
cd /home/usuario/projeto/nome_projeto/

# CRIAR ARQUIVO GEMFILE:
touch Gemfile
nano Gemfile

# EDITAR ARQUIVO GEMFILE:
source 'https://rubygems.org'
ruby '3.3.6'

gem 'rubocop'
gem 'rubocop-packaging'
gem 'rubocop-performance'
gem 'rubocop-rspec'
gem 'rubocop-shopify'
gem 'rubocop-thread_safety'
gem 'ruby-lsp'

# CRIAR ARQUIVO .RUBY-VERSION:
touch .ruby-version
nano .ruby-version

# EDITAR ARQUIVO .RUBY-VERSION:
3.3.6

# INSTALAR EXTENSÕES DO PROJETO:
bundle install
```

### CONFIGURANDO RAILS

```bash
# LISTAR VERSÕES RAILS: 
gem search '^rails$' --all

# INSTALAR VERSÃO RAILS:
gem install rails --version=7.2.2
rails -v

# CRIAR APLICAÇÃO RAILS:
rails new nome_projeto --database=postgresql
cd nome_projeto

# INICIAR APLICAÇÃO RAILS:
rails s

# VERIFICAR STATUS APLICAÇÃO POSTGRESQL:
sudo service postgresql status

# CRIAR USUÁRIO POSTGRES:
sudo -u postgres createuser -s $USER

# CRIAR BANCO DE DADOS POSTGRES:
rails db:create
rails db:migrate
```
