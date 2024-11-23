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
