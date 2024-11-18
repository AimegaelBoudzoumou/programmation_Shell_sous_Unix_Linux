# Affichage à l'écran

## 1. La commande echo
La commande __echo__ permet de réaliser des affichages à l'écran.

Exemple : 

```sh
echo Voici un livre sur la programmation shell
```

Certains caractères ont, lorsqu'ils sont placés entre quotes (apostrophes ou guillements), une signification spéciales. Ce sont des caractères d'échappement.

La commande __echo__ du bash devra être avec l'option __-e__ pour que l'interprétation de ces caractères ait lieu.

## Liste des caractères d'échappement

| Caractères d'échappement   | Signification   |
| :------------------------- |:---------------:|
| \\                         |   Antislash     |
| \a                         |   Sonnerie      |

| Aligné à gauche  | Centré          | Aligné à droite |
| :--------------- |:---------------:| -----:|
| Aligné à gauche  |   ce texte        |  Aligné à droite |
| Aligné à gauche  | est             |   Aligné à droite |
| Aligné à gauche  | centré          |    Aligné à droite |
