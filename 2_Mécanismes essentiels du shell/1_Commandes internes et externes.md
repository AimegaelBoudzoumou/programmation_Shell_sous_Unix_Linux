# Commande internes et externes

Contenu : 

1. Commandes externes
2. Commandes internes
3. Implémentation interne et implémentation externe

## 1. Commandes externes
Une commande externe est un fichier localisé dans l'arborescence. Par exemple, lorsqu'un utilisateur lance la commande __ls__, le shell demande au noyau Unix de charger en mémoire le fichier __/usr/bin/ls__.

La commande __file__ donne une indication sur le type de données contenues dans un fichier.

```bash
file /bin/ls
```

L'argument de la commande __file__ est un nom de fichier exprimé en _relatif_ ou en _absolu_.

## 2. Commandes internes
Une commande interne est un mot-clé du shell.

La  commande __type__ indique si une commande possède une implémentation interne.

Exemples :

La commande __cd__ est une commande interne. La commande __ls__ est une commande externe.

```bash
type cd; type ls
```
![image](https://github.com/user-attachments/assets/a535cb38-9043-4434-a64c-e419648cc9e8)

__type__ prend en argument le nom d'une commande. Si cette dernière n'est pas interne, elle est recherchée dans les répertoires cités dans __*PATH*__

__type__ elle-même est une commande interne.


## 3. Implémentation interne et implémentation externe
Certaines commandes ont une implémentation interne et une implémentation externe.
Dans ce cas :

- la commande interne est lancée en priorité ;
- l'exécution d'une commande interne est plus rapide que l'exécution d'une commande externe ;
- la commande __type__ indique la commande est interne, mais ne précise pas qu'il existe également une implémentation externe. 

Exempmle : la commande __pwd__ est une commande interne du shell.

```sh
type pwd
```

La commande __pwd__ possède également une implémentation externe.
```sh
ls -l /usr/bin/pwd
```

C'est la commande interne  qui est exécutée en priorité :
```sh
pwd
```

Pour forcer l'exécution de la commande externe, il faut indiquer explicitement l'emplacement de la commande (en absolu ou en relatif) :

```bash
/bin/pwd
```
```bash
cd /bin
./pwd
```

Exemple : 
```sh
cd Documents/
mkdir shell_sous_Unix_Linux
cd shell_sous_Unix_Linux/
mkdir scripts
ln -s scripts lienscript
ls -l
cd lienscript
pwd # la commande interne pwd affiche le nom du lien : /home/aimegael/Documents/shell_sous_Unix_Linux/lienscript
/bin/pwd # la commande externe affiche le nom du répertoire réel : /home/aimegael/Documents/shell_sous_Unix_Linux/scripts
```
Le fichier __lienscript__ est un lien symbolique vers le un répertoire Nous voyons que la commande interne __pwd__ affiche le nom du lien comme répertoire, tandis que la commande externe affiche le nom du répertoire.
