# 🧠 Fiche de révision – Les arguments `argc` et `argv` en C

## 🔍 Définition
Lorsqu’un programme C est exécuté, il peut recevoir des **arguments depuis la ligne de commande**.  
Ces arguments sont transmis à la fonction principale `main()` via les paramètres `argc` et `argv`.

```c
int main(int argc, char *argv[])
```
ou équivalent :
```c
int main(int argc, char **argv)
```

---

## ⚙️ Signification des paramètres

| Nom | Type | Rôle |
|-----|------|------|
| **argc** | `int` | Nombre d’arguments passés au programme (inclut le nom du programme) |
| **argv** | `char *argv[]` | Tableau de chaînes contenant les arguments |

---

## 🧩 Exemple simple

### Exemple de programme
```c
#include <stdio.h>

int main(int argc, char *argv[]) {
    int i;
    printf("Nombre d'arguments : %d\n", argc);
    for (i = 0; i < argc; i++) {
        printf("Argument %d : %s\n", i, argv[i]);
    }
    return 0;
}
```

### Exemple d’exécution
```bash
$ ./a.out Bonjour le monde
Nombre d'arguments : 4
Argument 0 : ./a.out
Argument 1 : Bonjour
Argument 2 : le
Argument 3 : monde
```

---

## 💡 Détails importants

- `argv[0]` → toujours le **nom du programme exécuté**  
- `argv[1]` à `argv[argc - 1]` → contiennent les **arguments réels**  
- `argv[argc]` → vaut toujours **NULL** (fin du tableau)  
- Les arguments sont **des chaînes de caractères (`char *`)** même s’ils contiennent des nombres  

---

## 🧮 Exemple avec conversion numérique
Pour utiliser un argument comme entier, il faut le convertir :

```c
#include <stdio.h>
#include <stdlib.h>

int main(int argc, char *argv[]) {
    if (argc < 2) {
        printf("Usage: %s <nombre>\n", argv[0]);
        return 1;
    }
    int n = atoi(argv[1]);
    printf("Le carré de %d est %d\n", n, n * n);
    return 0;
}
```
> `atoi()` (dans `<stdlib.h>`) convertit une chaîne en entier.

---

## ⚠️ Erreurs fréquentes

| Erreur | Explication |
|--------|--------------|
| Oublier de vérifier `argc` | Peut provoquer un accès mémoire invalide |
| Utiliser `argv` sans conversion | Donne un comportement inattendu si on traite un nombre comme texte |
| Débordement d’index | `argv[argc]` est toujours `NULL` → ne pas aller au‑delà |

---

## 📚 Fonctions utiles
| Fonction | Bibliothèque | Rôle |
|-----------|---------------|------|
| `atoi()` | `<stdlib.h>` | Convertit une chaîne en entier |
| `atof()` | `<stdlib.h>` | Convertit une chaîne en nombre à virgule |
| `strtol()` | `<stdlib.h>` | Conversion sécurisée en entier long |
| `printf()` | `<stdio.h>` | Affiche les arguments |

---

## 🧾 Récapitulatif
✅ `argc` = nombre total d’arguments (y compris le nom du programme)  
✅ `argv` = tableau contenant les arguments sous forme de chaînes  
✅ Toujours vérifier `argc` avant d’accéder à `argv[i]`  
✅ Les arguments sont toujours des **chaînes de caractères**  

---

## 🧠 Astuce mémoire
`argv` est un **tableau de pointeurs** vers des chaînes.  
Ainsi, `argv[i]` est une chaîne (type `char *`), et `argv` est de type `char **`.

---

## 📖 À retenir
> `argc` compte, `argv` contient.

---

## ✍️ Auteur
Fiche rédigée par **LenyBl – Holberton School 2025**  
Licence : MIT
