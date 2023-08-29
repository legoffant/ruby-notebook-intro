# Environnement de développement en Ruby

On va donc configurer un environnement basic pour la programmation en Ruby qui utilise:

* RVM packet manager
* Neovim et auto-completion
* Interpréteur avancé REPL Pry
* Debugger
* Jupyter Notebook

#### A. Nous devons installer les pré-requis. Sous GNU/Linux dans un terminal:

```bash
$ sudo pacman -S base-devel tar gzip diffutils curl
```

En utilisant un packet manager en Ruby RVM
```bash
$ gpg --keyserver hkp://keys.gnupg.net --recv-keys \
  409B6B1796C275462A1703113804BB82D39DC0E3 \
  7D2BAF1CF37B13E2069D6956105BD0E739499BDB

$ \curl -sSL https://get.rvm.io | bash -s stable --auto-dotfiles

$ source ~/.rvm/scripts/rvm

$ rvm pkg install openssl

$ rvm install ruby --with-openssl-dir=$HOME/.rvm/usr

$ ruby -v
```

Modifier `zshrc` pour ajouter le PATH des gems en fonction de votre version ruby
```
export PATH=$PATH':/home/trivial/.local/share/gem/ruby/3.0.0/bin'
source ~/.rvm/scripts/rvm
```

#### B. Installer pry et debugger

```bash
$ gem install pry pry-byebug
```

Pour utiliser Pry
```bash
$ pry
help
```

#### C. Configurer Neovim

```bash
$ gem install solargraph
```

Une fois que vous avez installé Neovim, configurer le gestionnaire de plugin avec Coc

```txt
:CocInstall coc-solargraph coc-json
```

Configuration recommandé

```txt
:CocConfig
```
Editer le fichier
```
{
  "codeLens.enable": true,
  "solargraph.useBundler": false
}
```

Et vous devriez avoir la gestion et support en Ruby, tel que l'auto-completion.

#### D. Mon premier programme en Ruby

D'abord on configure l'environnement de travail, dossier root de nos fichiers sources en `.rb`.

```bash
$ mkdir src-rb
$ cd src-rb
```

Puis on initialise solargraph dans notre dossier de travail

```bash
solargraph config
```

Qui va générer un fichier de configuration dans notre projet `.solargraph.yml`

hello world
```bash
nvim hello.rb
```

```ruby
#!/usr/bin/ruby

puts "Hello World"
```

Pour lancer le script
```bash
$ ruby hello.rb
```

ou alors
```bash
$ sudo chmod +x hello.rb
$ ./hello.rb
```

#### E. Jupyter Notebook

Installation des pré-requis
```bash
$ sudo pacman -S libtool libffi ruby python python-pipx
$ pipx install jupyterlab ipython

$ gem install --user-install iruby rspec ffi-rzmq
$ iruby register --force
```

Ajout d'un Gemfile dans notre dossier root de projet:
```bash
$ mkdir ~/iruby
$ bundle init
$ nvim Gemfile

source 'https://rubygems.org'

gem 'rspec'
gem 'iruby'
gem 'ffi-rzmq'
```

Commande pour lancer les notebooks:
```
$ jupyter-lab
```
