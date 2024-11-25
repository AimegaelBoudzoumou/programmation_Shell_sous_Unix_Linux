# Substitution de noms de fichiers

Contenu :

1. Expressions basiques : *, ?, []
2. Expressions étendues

## 1. Expressions basiques

### 1.1. Le caractère *

Il représente une suite de caractères quelconques (entre 0 et n caractères).

_Exemple 1_ : Afficher tous les noms de fichier se terminant par .c :
```sh
ls *.c
```

_Exemple 2_ : Afficher tous les noms de fichier commençant par la lettre f :
```sh
ls f*
```

### 1.2. La caractère ?

Il représente un caractère quelconque.

_Exemple 1_ : afficher tous les noms de fichier ayant une extension composée d'un seul caractère
```sh
ls *.?
```

_Exemple 2_ : afficher tous les noms de fichier composés de quatre caractères
```sh
ls ????
```

## 1.3. Les caractères []

Une paire de crochets représente l'emplacement d'un seul caractère.

Exemples de syntaxe d'intervalles et de négations :

_Intervalles_

__[a-z]__ : 
une minuscule comprise entre a et z

__[a-zB-F]__ : 
une minuscule comprise entre a et z OU une majuscule comprise entre B et F

__[A-Z0-9i]__ : 
une majuscule OU un chiffre OU la lettre i

_Négation_
Le __!__ se positionne uniquement en première position à l'intérieur des crochets et exprime la négation de tous les caractères cités dans les crochets.

__[!159a]__ : 
un caractère qui ne fait pas partie de la liste 1 5 9 a

__[!A-Z0-9i]__ : 
un caractère qui n'est ni une majuscule, ni un chiffre, ni la lettre i

_Exemples 1_ :
Fichier dont le nom commence par __f__ ou __o__ et se termine par le caractère "." suiv d'une minuscule.
```bash
ls ls [fo]*.[a-z]
```

_Exemples 2_ :
Fichier dont le nom comporte en deuxième caractère une majuscule ou un chiffre ou la lettre __i__. Les deux premiers caractères seront suivis d'une chaîne quelconque. 
```bash
ls ?[A-Z0-9i]*
```

_Exemples 3_ :
Noms de fichier ne commençant pas par une minuscule. 
```bash
ls [!a-z]* # ou ls [![:lower:]]
```
Il est possible d'obtenir le même résultat en utilisant les classes de caractères __POSIX__ (__bash__, __ksh__).
L'expression [:lower:] représente une minuscule.
```sh
ls [![:lower:]]*
```
Une classe de caractère POSIX doit être placée entre []

_Exemple 4_ :
Supprimer tous les fichiers dont le nom se termine par __.c__ ou __.s__
```bash
rm -i *.c *.s
```
Ce qui peut sécrire également :
```sh
rm -i *.[cs]
```

__Bonus Perso !__

_Exemple 1_ :
Compter le nombre de fichier se terminant par s
```sh
ls -l *.s | wc -l
```

## 2. Expressions étendues

Pour utiliser les expressions étendues en bash, il faut préalablement activer l'option __extglob__. Cette option peut s'activer à l'aide de la commanbde __shopt__.

```bash
shopt -s extglob
```
Elle peut se désactiver de cette manière :
```bash
shopt -u extglob
```

Note : voici les fichiers qui seront utilisés dans les exemples suivants.
```bash
touch fic
touch fic866866.log
touch fic867.log
touch typescript
touch fic.log
touch fic866866866.log
touch fic868.log
touch fic866.log
touch fic866868.log
touch readme.txt 
```

_Exemple_ :
```sh
shopt -s extglob
ls fic?(866).log
```

Cette option pourra être positionnée de manière permanente par l'intermédiaire du fichier __.bashrc__ (Cf. chapitre Paramétrage de l'environnement de travail - Les fichiers d'environnement).

## 2.1. ?(expression)
L'expression sera présente 0 ou 1 fois.

_Exemple_ :
Fichier dont le nom commence par "fic" suivi de 0 ou 1 occurence de "866", suivi de ".log"
```bash
ls fic?(866).log
```

## 2.2. *(expression)
L'expression sera présente 0 ou n fois.
_Exemple_ : 
Fichier dont le nom commence par "fic", suivi de 0 à n occurrence(s) de "866", suivi de ".log"
```bash
ls fic*(866).log
```

## 2.3. +(expression)
L'expression sera présente entre 1 et n fois.
_Exemple_ : 
Fichier dont le nom commence par "fic", suivi d'au moins une occurrence de "866", suivi de ".log"
```bash
ls fic+(866).log
```

## 2.4. @(expression)
L'expression sera présente exactement 1 fois.
_Exemple_ : 
Fichier dont le nom commence par "fic", suivi exactement d'une occurrence de "866", suivi de ".log"
```bash
ls fic@(866).log
```

## 2.5. !(expression)
L'expression ne sera pas présente.
_Exemple 1_ : 
Fichier dont le nom commence par "fic", suivi d'une expression qui n'est pas la chaîne "866", suivi de ".log"
```bash
ls fic!(866).log
```

_Exemple 2_ : 
Fichier dont le nom ne commence pas par "fic".
```sh
ls !(fic*)
```

## 2.6. Alternatives
Une barre verticale à l'intérieur d'une expression étendue prend le sens de "ou bien".

?(expression|expression|...)

*(expression|expression|...)

+(expression|expression|...)

@(expression|expression|...)

!(expression|expression|...)

_Exemple 1_ :

Fichier dont le nom commence par "fic", suivi de "866" ou "867", suivi de ".log".
```bash
ls fic@(866|867).log
```

_Exemple 2_ :

Fichier dont le nom commence par "fic", suivi de 1 à n occurrence de "866" ou "868", suivi de ".log".
```bash
ls fic+(866|868).log
```

_Exemple 3_ :

Fichier dont le nom commence par "fic", suivi de 1  occurrence de 1 à n fois de "866" ou de 1 à n fois "868", suivi de ".log".
```bash
ls fic@(+(866)|+(868)).log
```
