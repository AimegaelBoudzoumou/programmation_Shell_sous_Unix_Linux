# Substitution de noms de fichiers

1. Expressions basiques : *, ?, []
2. Expressions étendues

1. Expressions basiques

1.1. Le caractère *

Il représente une suite de caractères quelconques (entre 0 et n caractères).

Exemple 1 : Afficher tous les noms de fichier se terminant par .c :
```sh
ls *.c
```

Exemple 2 : Afficher tous les noms de fichier commençant par la lettre f :
```sh
ls f*
```

1.2. La caractère ?

Il représente un caractère quelconque.

Exemple 1 : afficher tous les noms de fichier ayant une extension composée d'un seul caractère
```sh
ls *.?
```

Exemple 2 : afficher tous les noms de fichier composés de quatre caractères
```sh
ls ????
```

1.3. Les caractères []

Une paire de crochets représente l'emplacement d'un seul caractère.

Exemples de syntaxe d'intervalles et de négations :

_Intervalles_

__[a-z]__ : une minuscule comprise entre a et z
__[a-zB-F]__ : une minuscule comprise entre a et z OU une majuscule comprise entre B et F
__[A-Z0-9i]__ : une majuscule OU un chiffre OU la lettre i

_Négation_
Le __!__ se positionne uniquement en première position à l'intérieur des crochets et exprime la négation de tous les caractères cités dans les crochets.

__[!159a]__ : un caractère qui ne fait pas partie de la liste 1 5 9 a
__[!A-Z0-9i]__ : un caractère qui n'est ni une majuscule, ni un chiffre, ni la lettre i

1.3. , []
