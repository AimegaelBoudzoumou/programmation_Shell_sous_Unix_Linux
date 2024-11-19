# Introduction

Contenu : 

1. Définition du shell
2. Avec quel shell programmer ?

## 1. Définition du shell

Le shell est un terme générique désignant un programme qui a pour fonction d'assurer l'interface entre l'utilisateur et le système Unix. 

C'est un interpréteur de commande.

Plusieurs shell sont disponibles sur les plateformes Unix.

## 2. Avec quel shell programmer ?

Il faur privilégier un shell compatible avec la norme POSIX.

Programmer en utilisant la norme POSIX permet d'assurer une portabilité maximale entre les shells conforme à cette spécification, mais est très limité du point de vue des fonctionnalités.

## Quel interpréteur va exécuter un script ?

Pour savoir quel interpréteur sera utilisé, il faut regarder la première ligne du script. Si celle-ci commence par __#!__ , le nom de l'interpréteur est mentionné derrière ces deux caractères. Cette instruction est facultative.

Si cette instruction est absente, c'est le shell par défaut de l'utilisateur (ou du contexte) qui sera utilisé. L'interpréteur par défaut d'un utilisateur est contenu 
dans la variable d'environnement __SHELL__.

```sh
cat /etc/shells
```

```sh
nl /etc/rc4.d/S01cron
```
Le shell commun à tous les Linux est le bash (/usr/bin/bash ou /bin/bash).

_Note_: 

- En pages 25 et 26 du livre _[programmation-shell-sous-unix-linux](https://www.editions-eni.fr/livre/programmation-shell-sous-unix-linux-ksh-bash-norme-posix-avec-exercices-corriges-7e-edition-9782409038020)_ se trouve un tableau qui référence les shells disponibles en standard sur les plateformes Linux et Unix.

- Le livre détaille les fonctionnalités du Bourne Again shell et des Korn shell (ksh88 et ksh93) et signale la compatibilité Bourne shell et POSIX.
