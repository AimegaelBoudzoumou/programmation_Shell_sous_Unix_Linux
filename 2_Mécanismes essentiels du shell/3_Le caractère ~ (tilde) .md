# Le caractères ~ (tilde)

Le caractère ~ représente le répertoire d'accueil de l'utilisateur courant.

Rappel : la commande __id__ retourne ceci :
uid=1002(aimegael) gid=1002(aimegael) groups=1002(aimegael)

```bash
cd /tmp
pwd
touch f1
cp f1 ~
cp f1 ~/Documents
```

Si le caractère ~ est immédiatement suivi d'un mot, ce dernier est considéré comme un nom d'utilisateur.

Exemple 1 : 

La commande suivante permet de recopier le fichier __f1__ vers sous le répertoire d'accueil de l'utilisateur __sebastien__ (vérifier que les permissions adéquates sont positionnées).

```bash
cp f1 ~sebastien
ls /home/sebastien/f1
```

Exemple 2 :

Recopier le fichier f1 sous le répertoire /home/sebastien/rep
```bash
cp f1 ~sebastien/rep
ls /home/sebastien/rep
```
