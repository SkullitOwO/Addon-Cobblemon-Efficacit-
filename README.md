# Efficacité des attaques — addon Cobblemon

Addon **client** pour Cobblemon. Il affiche pendant un combat l'efficacité de chaque attaque, qui
frappera en premier, les dégâts attendus et l'état du terrain.

**À installer côté joueur uniquement. Rien à ajouter sur le serveur.**

## Téléchargement

👉 **[efficacite-1.0.0.jar](../../raw/main/efficacite-1.0.0.jar)**

Déposez le fichier dans votre dossier `mods`.

## Ce qu'il affiche

**Sur chaque attaque**

- Un triangle d'ordre d'action : vert vers le haut, vous frappez en premier ; rouge vers le bas, il
  vous devance ; carré gris, les vitesses sont trop proches pour trancher.
- Le multiplicateur d'efficacité : `×4`, `×2`, `×1`, `×½`, `×¼`, `×0`. Un `?` signale qu'un talent
  possible de l'adversaire pourrait changer le résultat.

**Sur la barre de vie adverse**

En survolant une attaque, la part de la barre qui tomberait se teinte de rouge : rouge plein pour les
dégâts garantis, rouge pâle pour la marge d'incertitude.

**Dans le panneau de droite**

- La météo et le terrain, avec leur compteur de tours.
- Les murs, le Vent Arrière et les pièges au sol, de chaque côté.
- La fiche défensive de l'adversaire : ses types, ses faiblesses, ses résistances, ses immunités.
- L'objet qu'il a laissé voir en combat.

**Sur les tuiles de combat**

Un compteur de tours à côté du statut : `2/3` pour le sommeil, `×3` pour le poison grave.

## Comment il calcule

Rien n'est demandé au serveur, et aucune information cachée n'est révélée. Tout vient de ce que
l'écran de combat affiche déjà, ou du journal de combat.

Les dégâts suivent la formule des jeux principaux : STAB, efficacité des types, paliers d'Attaque et
de Défense des deux côtés, brûlure, météo, terrains, murs, objets révélés, et l'aléa de 85 à 100 %.
Les statistiques inconnues de l'adversaire sont estimées sur la fourchette des IV, à zéro EV et
nature neutre — d'où une fourchette plutôt qu'un chiffre précis.

La météo, les terrains, les murs, les pièges, les objets et les talents sont déduits des messages de
combat. La détection compare les phrases de Cobblemon **traduites dans votre langue**, elle
fonctionne donc quelle que soit la langue du client.

Restent hors du calcul : les coups critiques, les attaques à coups multiples, celles à puissance
variable, la Téracristallisation et les objets jamais révélés.

## Versions requises

| Dépendance | Version |
| --- | --- |
| Minecraft | 1.21.1 |
| Fabric Loader | 0.17.2 ou plus |
| Fabric API | 0.116.15+1.21.1 |
| Fabric Language Kotlin | 1.13.13 |
| Cobblemon | 1.7.3 |
