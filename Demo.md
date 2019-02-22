stagldnr@debian-java-ldnr:~$ git
usage: git [--version] [--help] [-C <path>] [-c name=value]
           [--exec-path[=<path>]] [--html-path] [--man-path] [--info-path]
           [-p | --paginate | --no-pager] [--no-replace-objects] [--bare]
           [--git-dir=<path>] [--work-tree=<path>] [--namespace=<name>]
           <command> [<args>]

Ci-dessous les commandes Git habituelles dans diverses situations :

démarrer une zone de travail (voir aussi : git help tutorial)
   clone      Cloner un dépôt dans un nouveau répertoire
   init       Créer un dépôt Git vide ou réinitialiser un existant

travailler sur la modification actuelle (voir aussi : git help revisions)
   add        Ajouter le contenu de fichiers dans l'index
   mv         Déplacer ou renommer un fichier, un répertoire, ou un lien symbolique
   reset      Réinitialiser la HEAD courante à l'état spécifié
   rm         Supprimer des fichiers de la copie de travail et de l'index

examiner l'historique et l'état (voir aussi : git help revisions)
   bisect     Trouver par recherche binaire la modification qui a introduit un bogue
   grep       Afficher les lignes correspondant à un motif
   log        Afficher l'historique des validations
   show       Afficher différents types d'objets
   status     Afficher le statut de la copie de travail

agrandir, marquer et modifier votre historique
   branch     Lister, créer ou supprimer des branches
   checkout   Basculer de branche ou restaurer la copie de travail
   commit     Enregistrer les modifications dans le dépôt
   diff       Afficher les changements entre les validations, entre validation et copie de travail, etc
   merge      Fusionner deux ou plusieurs historiques de développement ensemble
   rebase     Réapplication des commits sur le sommet de l'autre base
   tag        Créer, lister, supprimer ou vérifier un objet d'étiquette signé avec GPG

collaborer (voir aussi : git help workflows)
   fetch      Télécharger les objets et références depuis un autre dépôt
   pull       Rapatrier et intégrer un autre dépôt ou une branche locale
   push       Mettre à jour les références distantes ainsi que les objets associés

'git help -a' et 'git help -g' listent les sous-commandes disponibles et
quelques concepts. Voir 'git help <commande>' ou 'git help <concept>'
pour en lire plus à propos d'une commande spécifique ou d'un concept.
stagldnr@debian-java-ldnr:~$ pwd
/home/stagldnr
stagldnr@debian-java-ldnr:~$ git init Demo
Dépôt Git vide initialisé dans /home/stagldnr/Demo/.git/
stagldnr@debian-java-ldnr:~$ pwd/home/stagldnr/Demo
bash: pwd/home/stagldnr/Demo: Aucun fichier ou dossier de ce type
stagldnr@debian-java-ldnr:~$ touch Demo
stagldnr@debian-java-ldnr:~$ CD Demo
bash: CD : commande introuvable
stagldnr@debian-java-ldnr:~$ CD/home/stagldnr/Demo
bash: CD/home/stagldnr/Demo: Aucun fichier ou dossier de ce type
stagldnr@debian-java-ldnr:~$ cd/home/stagldnr/Demo
bash: cd/home/stagldnr/Demo: Aucun fichier ou dossier de ce type
stagldnr@debian-java-ldnr:~$ cd/home
bash: cd/home: Aucun fichier ou dossier de ce type
stagldnr@debian-java-ldnr:~$ cd home
bash: cd: home: Aucun fichier ou dossier de ce type
stagldnr@debian-java-ldnr:~$ cd Home
bash: cd: Home: Aucun fichier ou dossier de ce type
stagldnr@debian-java-ldnr:~$ cd home Demo
bash: cd: trop d'arguments
stagldnr@debian-java-ldnr:~$ cd stagldnr
bash: cd: stagldnr: Aucun fichier ou dossier de ce type
stagldnr@debian-java-ldnr:~$ cd Demo
stagldnr@debian-java-ldnr:~/Demo$ touch Demo
stagldnr@debian-java-ldnr:~/Demo$ vim
bash: vim : commande introuvable
stagldnr@debian-java-ldnr:~/Demo$ vi
stagldnr@debian-java-ldnr:~/Demo$ ls
Demo
stagldnr@debian-java-ldnr:~/Demo$ rm Demo 
stagldnr@debian-java-ldnr:~/Demo$ ls
stagldnr@debian-java-ldnr:~/Demo$ touch Demo.md
stagldnr@debian-java-ldnr:~/Demo$ ls
Demo.md
stagldnr@debian-java-ldnr:~/Demo$ vi Demo.md 
stagldnr@debian-java-ldnr:~/Demo$ more Demo.md 
TEST1
stagldnr@debian-java-ldnr:~/Demo$ git add Demo.md
stagldnr@debian-java-ldnr:~/Demo$ git status
Sur la branche master

Validation initiale

Modifications qui seront validées :
  (utilisez "git rm --cached <fichier>..." pour désindexer)

	nouveau fichier : Demo.md

stagldnr@debian-java-ldnr:~/Demo$ git commit -m "first commit"
[master (commit racine) a0a2a31] first commit
 Committer: Stag LDNR <stagldnr@debian-java-ldnr.ldnr.local>
Votre nom et votre adresse e-mail ont été configurés automatiquement en se
fondant sur votre nom d'utilisateur et le nom de votre machine. Veuillez 
vérifier qu'ils sont corrects. Vous pouvez supprimer ce message en les 
paramétrant explicitement. Lancez les commandes suivantes et suivez les
instruction dans votre éditeur pour éditer votre fichier de configuration :

    git config --global --edit

Après ceci, vous pouvez corriger l'identité utilisée pour cette validation avec :

    git commit --amend --reset-author

 1 file changed, 1 insertion(+)
 create mode 100644 Demo.md
stagldnr@debian-java-ldnr:~/Demo$ git status
Sur la branche master
rien à valider, la copie de travail est propre
stagldnr@debian-java-ldnr:~/Demo$ touch Demo2
stagldnr@debian-java-ldnr:~/Demo$ touch Demo2.md
stagldnr@debian-java-ldnr:~/Demo$ vi Demo.md
stagldnr@debian-java-ldnr:~/Demo$ echo "TEST2"
TEST2
stagldnr@debian-java-ldnr:~/Demo$ echo "Test2">>Demo2.md
stagldnr@debian-java-ldnr:~/Demo$ more Demo2.md
Test2
stagldnr@debian-java-ldnr:~/Demo$ cmp Demo.md Demo2.md
Demo.md Demo2.md sont différents: octet 2, ligne 1
stagldnr@debian-java-ldnr:~/Demo$ git add Demo2.md
stagldnr@debian-java-ldnr:~/Demo$ git status
Sur la branche master
Modifications qui seront validées :
  (utilisez "git reset HEAD <fichier>..." pour désindexer)

	nouveau fichier : Demo2.md

Modifications qui ne seront pas validées :
  (utilisez "git add <fichier>..." pour mettre à jour ce qui sera validé)
  (utilisez "git checkout -- <fichier>..." pour annuler les modifications dans la copie de travail)

	modifié :         Demo.md

Fichiers non suivis:
  (utilisez "git add <fichier>..." pour inclure dans ce qui sera validé)

	Demo2

stagldnr@debian-java-ldnr:~/Demo$ git commit -m "second commit"
[master 4652939] second commit
 Committer: Stag LDNR <stagldnr@debian-java-ldnr.ldnr.local>
Votre nom et votre adresse e-mail ont été configurés automatiquement en se
fondant sur votre nom d'utilisateur et le nom de votre machine. Veuillez 
vérifier qu'ils sont corrects. Vous pouvez supprimer ce message en les 
paramétrant explicitement. Lancez les commandes suivantes et suivez les
instruction dans votre éditeur pour éditer votre fichier de configuration :

    git config --global --edit

Après ceci, vous pouvez corriger l'identité utilisée pour cette validation avec :

    git commit --amend --reset-author

 1 file changed, 1 insertion(+)
 create mode 100644 Demo2.md
stagldnr@debian-java-ldnr:~/Demo$ git branch -r
stagldnr@debian-java-ldnr:~/Demo$ git push origin master
fatal: 'origin' does not appear to be a git repository
fatal: Impossilble de lire le dépôt distant.

Veuillez vérifier que vous avez les droits d'accès
et que le dépôt existe.
stagldnr@debian-java-ldnr:~/Demo$ git remote add origin https://github.com/Pino27/Demo.git
stagldnr@debian-java-ldnr:~/Demo$ git push -u origin master
Username for 'https://github.com': Pino27
Password for 'https://Pino27@github.com': 
Décompte des objets: 6, fait.
Delta compression using up to 4 threads.
Compression des objets: 100% (3/3), fait.
Écriture des objets: 100% (6/6), 485 bytes | 0 bytes/s, fait.
Total 6 (delta 0), reused 0 (delta 0)
To https://github.com/Pino27/Demo.git
 * [new branch]      master -> master
La branche master est paramétrée pour suivre la branche distante master depuis origin.
stagldnr@debian-java-ldnr:~/Demo$ git remote rm origin
stagldnr@debian-java-ldnr:~/Demo$ git remote add origin https://github.com/Pino27/hbc
stagldnr@debian-java-ldnr:~/Demo$ git push -u origin master
Username for 'https://github.com': Pini27
Password for 'https://Pini27@github.com': 
remote: Invalid username or password.
fatal: Authentication failed for 'https://github.com/Pino27/hbc/'
stagldnr@debian-java-ldnr:~/Demo$ git remote add origin https://github.com/Pino27/hbc
fatal: la distante origin existe déjà.
stagldnr@debian-java-ldnr:~/Demo$ git remote rm origin
stagldnr@debian-java-ldnr:~/Demo$ git remote add origin https://github.com/Pino27/hbc
stagldnr@debian-java-ldnr:~/Demo$ git push -u origin master
Username for 'https://github.com': Pino27
Password for 'https://Pino27@github.com': 
Décompte des objets: 6, fait.
Delta compression using up to 4 threads.
Compression des objets: 100% (3/3), fait.
Écriture des objets: 100% (6/6), 485 bytes | 0 bytes/s, fait.
Total 6 (delta 0), reused 0 (delta 0)
To https://github.com/Pino27/hbc
 * [new branch]      master -> master
La branche master est paramétrée pour suivre la branche distante master depuis origin.
stagldnr@debian-java-ldnr:~/Demo$ 
