# Affichage à l'écran

Contenu :
1. La commande echo
2. Les commandes print et printf

## 1. La commande echo
La commande __echo__ permet de réaliser des affichages à l'écran.

Exemple : 

```sh
echo Voici un livre sur la programmation shell
```

Certains caractères ont, lorsqu'ils sont placés entre quotes (apostrophes ou guillements), une signification spéciales. Ce sont des caractères d'échappement.

La commande __echo__ du bash devra être avec l'option __-e__ pour que l'interprétation de ces caractères ait lieu.

## Liste des caractères d'échappement

| Caractères d'échappement   | Signification                                    |
| :------------------------- |:------------------------------------------------:|
| \\\                        |   Antislash                                      |
| \a                         |   Sonnerie                                       |
| \b                         |   Effacement du caractère précédent              |
| \c                         |   Suppression du saut de ligne en fin de ligne   |
| \f                         |   Saut de page   |
| \n                         |   Saut de ligne  |
| \r                         |   Retour chariot |
| \t                         |   Tabulation horizontale |
| \v                         |   Tabulation verticale       |
| \0xxx                      |   Valur d'un caractère exprimé en octal |

## Le caractère \n

Il sert à provoquer un saut de ligne.

Exemple avec Bourne ou Korn shell

```sql
echo "Voici un saut de ligne\net encore un autre\net le saut de ligne naturel de la commande echo"
```

Les quotes sont obligatoires :
```sh
echo a\nb
echo "a\nb"
```

Exemple avec un bash
```bash
echo "a\nb"
echo - e "a\nb"
```

## Le caractère \c

Il sert à éliminer le saut de ligne natuel de la commande __echo__

_Le caractère **\c** doit se situer impérativement en dernière position de l'argument de *echo* (juste avant le guillement fermant)._

Exemple avec un Bourne ou Korn shell
```sh
echo "première ligne" ; echo "Deuxième ligne"
echo "Première ligne\c" ; echo "Deuxième ligne"
```

Exemple avec un bash
L'option __-e__ est indispensable pourl'interprétation de \c.

```bash
echo -e "Première ligne\c" ; echo -e "Deuxième ligne\c"
```

L'option **\n** remplace **\c**
```bash
echo -n "Première ligne" ; echo -n "Deuxième ligne"
```

## Le caractère \f

Il permet d'afficher une tabulationn.

Exemple avec Bourne ou Korn shell

```sh
echo "Voici 2 tabulationd\t\tEt voila ..."
```

Exemple avec un bash
```bash
echo -e "Voici 2 tabulations\t\tEt  voila..."
```

## 2. Les commandes print et printf
Ces deux commandes d'affichage sont présentées au chapître _Aspects avancés de la programmation shell - Commandes d'affichage_
