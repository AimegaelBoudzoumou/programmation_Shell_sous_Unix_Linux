# Commande internes et externes

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
