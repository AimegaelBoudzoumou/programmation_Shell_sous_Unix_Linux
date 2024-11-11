# 1. Définition du shell

Le shell est un terme générique désignant un programme qui a pour fonction d'assurer l'interface entre l'utilisateur et le système Unix. 

C'est un interpréteur de commande.

Plusieurs shell sont disponibles sur les plateformes Unix.

# 2. Avec quel shell programmer ?

Il faur privilégier un shell compatible avec la norme Posix.

Programmer en utilisant la norme Posix permet d'assurer une portabilité maximale entre les shells conforme à cette spécification, mais est très limité du point de vue des fonctionnalités.

## Quel interpréteur va exécuter un script ?

Pour savoir quel interpréteur sera utilisé, il faut regarder la première ligne du script. Si celle-ci commence par __#!__ , le nom de l'interpréteur est mentionné derrière ces deux caractères. Cette instruction est facultative.

Si cette instruction est absente, c'est le shell par défaut de l'utilisateur (ou du contexte) qui sera utilisé. L'interpréteur par défaut d'un utilisateur est contenu dans la variable d'environnement __SHELL__.

file:///home/chris/Downloads/Screenshot%20from%202024-11-11%2018-57-14.png![image](https://github.com/user-attachments/assets/2c839757-ed27-4b0d-aeef-fec4375d451e)


