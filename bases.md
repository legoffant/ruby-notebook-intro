# Bases

Date d'apparition du langage : 1995

Créateur : **Yukihiro "Matz" Matsumoto** (Japon)

Type : langage de script orienté objet

Licence : Licence Ruby, licence publique générale GNU version 2 et BSD 2-clauses

Paradigmes : Interprété, objet, impératif, concurrent, fonctionnel

#### Philosophie :

* Développer rapidement et en y prenant du plaisir,
* Principe de moindre surprise.
* toute donnée est un objet, y compris les types primitifs ;
* toute fonction est une méthode ;
* toute variable est une référence à un objet ;

#### Principaux traits :

* Syntaxe simple dérivée d'Algol et Pascal, proche de Lua,
* Blocs de code passables comme paramètres,
* Gestion automatique de la mémoire (ramasse-miettes),
* Gestion de niveaux de confiance,
* Gestion des exceptions.
* Principaux concurrents : JavaScript, Python, Perl, PHP.

Version actuelle à la date d'écriture : 3.2.2 (2023)

Standardisation : ISO 30170:2012 (payant)

Extension d'un fichier Ruby : **rb**

Exécuter mon_fichier.rb : `ruby mon_fichier.rb`

Accéder aux options de l'interpréteur : `ruby -h`

Première ligne d'un fichier sous Linux : `#!/usr/bin/ruby`

Accéder à la console interactive : **irb, pry**

Affichage sur la sortie standard (console) : `puts`

Le programme le plus simple en Ruby : `puts "Hello World!"`

Interprétation de code dans une chaîne : `puts "#{a+1}"`

Gestion de package et environnement: RVM, rbenv

Interpréteur de référence: MRI (CRuby)

Bibliothèques: Gems

Documentation CLI: ri

#### Mots réservés

Mots réservés (39) : 
```text
BEGIN, END, alias, and, begin, break, case, class, def, defined?, do, else, elsif, end, ensure, false, for, if, in, module, next, nil, not, or, redo, rescue, retry, return, self, super, then, true, undef, unless, until, when, while, yield, __FILE__, __LINE__
```
#### Commentaires

Commentaires en Ruby : `# mon commentaire jusqu'à la fin de la ligne`

Commentaires sur plusieurs lignes :
```text
=begin
  vos lignes
=end
```
