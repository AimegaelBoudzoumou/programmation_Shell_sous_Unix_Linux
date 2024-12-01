# Redirections

Contenu :

1. Redirection des sorties en écritures
   - Sortie standard
   - Sortie d'erreur standard
   - Sortie standard et sortie d'erreur standard
   - Se protéger d'un écrasement involontaire de fichier
   - Eliminer les affichages
2. Redirection de l'entrée standard
3. Rediriger les descripteurs 1 et 2 vers le même fichier
4. La double redirection en lecture

Les processus Unix ont, par défaut, leur fichier terminal ouvert trois fois, sous trois descripteurs de fichier différents.

Un descripteur peut se voir comme un canal de communication.

__Entrée standard :__ descripteur de fichier 0

__Sortie standart :__ descripteur de fichier 1

__Sortie d'erreur standard :__ descripteur de fichier 2

# 1. Redirection des sorties en écritures

## 1.1. Sortie standard

_Simple redirection_

Syntaxe :
```sh
commande 1> fichier
```
équivalent à :
```shell
commande > fichier
```
Le nom du fichier est exprimé en relatif ou en absolu.

Si le fichier n'existe pas, il est créé. Si le fichier existe déjà, il est écrasé.

Exemple : 
```bash
ls > resu
cat resu
```

_Double redirection_

Syntaxe :
```sh
commande 1>> fichier
```
équivalent à :
```sh
commande >> fichier
```
Si le fichier n'existe pas, il est créé. Si le fichier existe déjà, il est ouvert en mode ajout.

Exemple :

Ajouter le résultat de la commande __date__ à la fin du fichier __resu__ créé précédemment.
```sh
date 1>> resu
cat resu
```

## 1.2. Sortie d'erreur standard

_Simple redirection_

Syntaxe :
```sh
commande 2> fichier
```

Exemple :

Redirection de la sortie d'erreur standard. Les messages d'erreur partent dans le fichier d'erreur, les résultats restent à l'écran.

```sh
find / -name passwd 2> erreur
cat erreur
```

_Double redirection_

Elle permet de concatener les messages d'erreur d'une commande au contenu d'un fichier existant.

Syntaxe :
```sh
commande 2>> fichier
```
Exemple : 

Concatenation des messages d'erreur de __ls -z__ à la fin du fichier __erreur__.
```bash
ls -z
ls - z 2>> erreur
cat erreur
```

## 1.3. Sortie standard et sortie d'erreur standard
## 1.4. Se protéger d'un écrasement involontaire de fichier 
## 1.5. Eliminer les affichages

# 2. Redirection de l'entrée standard

# 3. Rediriger les descripteurs 1 et 2 vers le même fichier

# 4. La double redirection en lecture
