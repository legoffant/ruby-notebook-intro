# Eco-Système en Ruby

Bref analyse pour ce plonger dans l'éco-système Ruby, et bien commencer l'apprentissage.

### Sites web

* **Sites principaux**
    * Site officiel du langage : [https://www.ruby-lang.org](https://www.ruby-lang.org)
    * Site de la documentation : [http://ruby-doc.org/](http://ruby-doc.org/)
* **Tester Ruby en ligne**
    * Console Ruby en ligne : [https://ruby.github.io/TryRuby/](https://ruby.github.io/TryRuby/)
* **Site d'actualités**
    * Ruby Inside, actualités et tutoriels (jusqu'à 2014): [http://www.rubyinside.com/](http://www.rubyinside.com/)
    * Ruby community IRC Channel: [https://ruby-community.com/pages/user_rules](https://ruby-community.com/pages/user_rules)
    * News, infos, aggregated Rubyland: [https://rubyland.news/titles](https://rubyland.news/titles)
* **Apprendre et progresser en Ruby**
    * Site de tutoriels Tutorials Point : [http://www.tutorialspoint.com/ruby/](http://www.tutorialspoint.com/ruby/)
    * Ruby Quicktips, des bouts de code utile : [http://rubyquicktips.com/](http://rubyquicktips.com/)
    * Geeks For Geeks for Ruby: [https://www.geeksforgeeks.org/ruby-programming-language/](https://www.geeksforgeeks.org/ruby-programming-language/)
* **Liste de bibliothèques pour Ruby**
    * Dépôt RubyGems : [https://rubygems.org/](https://rubygems.org/)
    * Dépôt The Ruby Toolbox : [https://www.ruby-toolbox.com/](https://www.ruby-toolbox.com/)
    * Ruby On Rails (RoR), le framework qui a fait connaître Ruby : [http://rubyonrails.org/](http://rubyonrails.org/)
    * Gosu, une bibliothèque pour faire des jeux 2D : [https://www.libgosu.org/](https://www.libgosu.org/)

### Principaux livres et ressources pour apprendre Ruby

* Une introduction à Ruby - Zeste de Savoir (français): [https://zestedesavoir.com/tutoriels/634/une-introduction-a-ruby/](https://zestedesavoir.com/tutoriels/634/une-introduction-a-ruby/)
* Learn Ruby The Hard Way: [https://learnrubythehardway.org/book/](https://learnrubythehardway.org/book/)
* Ruby Best Practices (PDF): [https://web.archive.org/web/20120108191027/https://majesticseacreature.com/rbp-book/pdfs/rbp_1-0.pdf](https://web.archive.org/web/20120108191027/https://majesticseacreature.com/rbp-book/pdfs/rbp_1-0.pdf)
* Ruby Hacking Guide: [https://ruby-hacking-guide.github.io/](https://ruby-hacking-guide.github.io/)
* Rubyfu (Black Hat Ruby): [https://rubyfu.net/](https://rubyfu.net/)
* I love Ruby: [https://i-love-ruby.gitlab.io/book.html](https://i-love-ruby.gitlab.io/book.html)
* The Well-Grounded Rubyist, 2nd ed (PDF): [https://archive.org/details/wellgroundedruby0000blac](https://archive.org/details/wellgroundedruby0000blac)
*  Eloquent Ruby (PDF): [https://www.programmer-books.com/eloquent-ruby-by-russ-olsen-pdf/](https://www.programmer-books.com/eloquent-ruby-by-russ-olsen-pdf/)

### Cheatsheet

* Ruby Standard Library: [https://docs.ruby-lang.org/en/master/standard_library_rdoc.html](https://docs.ruby-lang.org/en/master/standard_library_rdoc.html)
* Aide-mémoire Ruby: [https://xitog.github.io/dgx/informatique/ruby.html](https://xitog.github.io/dgx/informatique/ruby.html)
* My beloved Ruby Cheat Sheet: [https://dev.to/ericchapman/my-beloved-ruby-cheat-sheet-208o](https://dev.to/ericchapman/my-beloved-ruby-cheat-sheet-208o)

### Autres ressources

La documentation `ri`. Voir: [https://ruby.github.io/rdoc/RI_rdoc.html](https://ruby.github.io/rdoc/RI_rdoc.html) qui permet de documenter une fonction, class, methode, etc en ligne de commande. Pour l'utiliser installer l'interpreteur REPL `Pry` et lancer `help` pour plus d'info.


### Environnement Datascience

Pour plus de détails sur les librairies en datascience et ML: [http://ruby-data.org/](http://ruby-data.org/)

Pour avoir un environnement datascience basic en Ruby je recommande d'utiliser:

* NMatrix: A Versatile Numerical Computing Library
* Daru: Data Analysis and Visualization in Ruby
* Statsample: Statistical Analysis Made Easy
* Rubyvis: Interactive Data Visualization
* SymEngine: Fast Symbolic Manipulation CAS


### Pour les SysAdmin

Ruby permet d'invoquer des commandes systèmes OS du shell et donc s'utilise comme un langage de scripting pour les tâches d'automatisation. Mais également c'est utile pour intéragir avec l'OS pour écrire des Apps. Utiliser également le module [FileUtils](https://ruby-doc.org/3.2.0/stdlibs/fileutils/FileUtils.html?ref=akshaykhot.com) pour copier, déplacer et supprimer des fichiers et dossiers. Pour cela utiliser la syntaxe:

```ruby

`ls docs`

%x{ ls docs }

exec 'ls'

system('ls', '-l', '.')

# PID
pid = spawn("tar xf ruby.tar.bz2")
Process.wait pid

IO.popen('ls') do |pipe|
  puts pipe.readlines
end
```

### Metasploit Modules
 
Ruby est très pratique pour les hackers et le framework Metasploit pour écrire ces propres exploits, c'est une fonction avancée nécessaire. Petit tour d'horizon:

* Metapsploit Unleashed - Building a module: [https://www.offsec.com/metasploit-unleashed/building-module/](https://www.offsec.com/metasploit-unleashed/building-module/)
* Metasploit docs - Writing an auxiliary module: [https://docs.metasploit.com/docs/development/developing-modules/guides/how-to-get-started-with-writing-an-auxiliary-module.html](https://docs.metasploit.com/docs/development/developing-modules/guides/how-to-get-started-with-writing-an-auxiliary-module.html)
* H 312: Writing a Custom Metasploit Module (25 pts): [https://bowneconsultingcontent.com/pub/EH/proj/H312.htm](https://bowneconsultingcontent.com/pub/EH/proj/H312.htm)

Template type pour écrire un module:

```ruby
require 'msf/core'

class MetasploitModule < Msf::Auxiliary

  include Msf::Auxiliary::Scanner

  def initialize(info = {})
    super(update_info(info,
      'Name'           => 'Module name',
      'Description'    => %q{
        Say something that the user might want to know.
      },
      'Author'         => [ 'Name' ],
      'License'        => MSF_LICENSE
    ))
  end

  def run
    # use `print_status` to print to the metasploit console, instead of `puts`
  end

end
```
