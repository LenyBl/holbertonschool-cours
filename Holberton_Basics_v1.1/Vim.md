# Vim — Cheat Sheet

Vim est un éditeur modal : il fonctionne avec différents modes.  
Les deux principaux sont :
- **Mode normal** : navigation et manipulation
- **Mode insertion** : écriture du texte
- **Mode commande** : pour exécuter des actions

---

## Modes de Vim

| Touche | Action |
|--------|--------|
| `i` | Passer en mode insertion (inserer avant le curseur) |
| `a` | Passer en mode insertion (après le curseur) |
| `Esc` | Revenir en mode normal |
| `:` | Passer en mode commande |

---

## Commandes de base

| Commande | Action |
|----------|--------|
| `vim fichier` | Ouvrir ou créer un fichier |
| `:w` | Sauvegarder |
| `:q` | Quitter |
| `:wq` ou `:x` | Sauvegarder et quitter |
| `:q!` | Quitter sans sauvegarder |
| `u` | Annuler |
| `Ctrl + r` | Rétablir |

---

## Navigation dans le texte

| Touche | Action |
|--------|--------|
| `h` | Gauche |
| `l` | Droite |
| `j` | Bas |
| `k` | Haut |
| `0` | Début de la ligne |
| `$` | Fin de la ligne |
| `w` | Mot suivant |
| `b` | Mot précédent |
| `G` | Dernière ligne |
| `gg` | Première ligne |
| `:n` | Aller à la ligne n |

---

## Insertion de texte

| Touche | Action |
|--------|--------|
| `i` | Insérer avant le curseur |
| `a` | Insérer après le curseur |
| `o` | Nouvelle ligne en dessous |
| `O` | Nouvelle ligne au-dessus |
| `Esc` | Retour en mode normal |

---

## Suppression, copie et collage

| Commande | Action |
|----------|--------|
| `x` | Supprimer le caractère sous le curseur |
| `dd` | Supprimer (couper) une ligne |
| `yy` | Copier une ligne |
| `p` | Coller après le curseur |
| `P` | Coller avant le curseur |
| `dw` | Supprimer jusqu’à la fin du mot |
| `d$` | Supprimer jusqu’à la fin de la ligne |

---

## Recherche et remplacement

| Commande | Action |
|----------|--------|
| `/mot` | Rechercher vers l’avant |
| `?mot` | Rechercher vers l’arrière |
| `n` | Rechercher l’occurrence suivante |
| `N` | Rechercher l’occurrence précédente |
| `:%s/ancien/nouveau/g` | Remplacer tout dans le fichier |
| `:s/ancien/nouveau/g` | Remplacer dans la ligne courante |

---

## Sélection visuelle

| Touche | Action |
|--------|--------|
| `v` | Mode visuel caractère |
| `V` | Mode visuel ligne |
| `y` | Copier la sélection |
| `d` | Supprimer la sélection |
| `p` | Coller après le curseur |

---

## Gestion de fichiers

| Commande | Action |
|----------|--------|
| `:e fichier` | Ouvrir un autre fichier |
| `:w nom` | Sauvegarder sous un autre nom |
| `:!commande` | Exécuter une commande shell |
| `:r fichier` | Insérer le contenu d’un fichier |
| `:set number` | Afficher les numéros de lignes |
| `:set nonumber` | Masquer les numéros de lignes |

---

## Astuces utiles

- Appuyer sur `Esc` plusieurs fois si vous êtes perdu pour revenir au mode normal.
- `u` annule la dernière action.
- `.` répète la dernière commande.
- `:help` affiche l’aide intégrée.
- `:w !sudo tee %` permet de sauvegarder un fichier avec les droits root si nécessaire.

---

## Raccourcis essentiels à retenir

| Commande | Action |
|----------|--------|
| `i` / `a` | Mode insertion |
| `Esc` | Revenir en mode normal |
| `:w` | Sauvegarder |
| `:q` | Quitter |
| `:wq` | Sauvegarder et quitter |
| `x` / `dd` | Supprimer |
| `yy` / `p` | Copier / coller |
| `/mot` | Rechercher |
| `u` / `Ctrl + r` | Annuler / rétablir |
