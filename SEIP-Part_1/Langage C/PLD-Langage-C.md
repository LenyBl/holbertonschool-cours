# 📘 Fiche de Révision – Langage C (Holberton / Low-Level Programming)

## 🧠 Partie 1 – Introduction au C

### Pourquoi le C est-il considéré comme puissant et intemporel ?
- Langage bas-niveau proche de la machine, mais portable.
- Donne un contrôle précis sur la mémoire.
- Utilisé pour les systèmes d’exploitation, compilateurs, embarqué, etc.
- Base de nombreux langages modernes (C++, C#, Java, Python...).

### Origine du C
- **Inventeur :** Dennis Ritchie (1972, Bell Labs)
- **Contexte :** Développement du système d’exploitation UNIX.

### Figures clés
- **Dennis Ritchie** → Créateur du langage C et co-créateur d’UNIX.  
- **Brian Kernighan** → Co-auteur du livre *“The C Programming Language”*, popularisation du C.  
- **Linus Torvalds** → Créateur du noyau Linux, écrit majoritairement en C.

### GCC
- **gcc** = *GNU Compiler Collection*  
- Rôle : compiler le code source C en programme exécutable.

### Étapes de `gcc main.c`
1. **Préprocesseur** : inclusion des fichiers `#include`, macros.
2. **Compilation** : transformation du code en assembleur.
3. **Assemblage** : génération d’un fichier objet `.o`.
4. **Édition de liens (linking)** : création de l’exécutable final.

### Entrée du programme
- **Entry point** = point de départ de l’exécution.
- En C : la fonction `main()`.

### Fonction `main()`
- Début du programme.
- Son **valeur de retour** (souvent `0`) indique le succès de l’exécution.

### Affichage à l’écran
| Fonction | Description | Exemple |
|-----------|--------------|----------|
| `printf()` | Formatage et affichage complexe | `printf("Hello %s\n", name);` |
| `puts()` | Affiche une chaîne + saut de ligne | `puts("Hello");` |
| `putchar()` | Affiche un seul caractère | `putchar('A');` |

### Taille d’une variable
- Opérateur : `sizeof`
- Exemple : `sizeof(int)` → taille en octets.

### Compilation et exécutable
- Compiler : `gcc main.c -o nom_executable`
- Par défaut : exécutable nommé **a.out**

### Style Betty (Holberton)
- Règles de style C obligatoires (lisibilité, indentation...).
- Vérification avec :
  ```bash
  betty filename.c
  betty main.h
  ```

### Trouver le bon header
- Utiliser la doc `man` :
  ```bash
  man 3 printf
  ```
  → indique `#include <stdio.h>`

### Commande GCC expliquée
```bash
gcc -Wall -Werror -Wextra -pedantic -std=gnu89 main.c
```
- `-Wall` → active tous les avertissements.
- `-Werror` → traite les avertissements comme des erreurs.
- `-Wextra` → avertissements supplémentaires.
- `-pedantic` → respecte strictement la norme.
- `-std=gnu89` → version du C standard utilisée.

---

## 🔢 Partie 2 – Variables, if, else, while

### Opérateurs arithmétiques
`+  -  *  /  %`

### Opérateurs logiques (booléens)
`&&` (ET), `||` (OU), `!` (NON)

### Opérateurs relationnels
`==`, `!=`, `>`, `<`, `>=`, `<=`

### Valeurs booléennes
- `0` → **FALSE**
- Toute autre valeur → **TRUE**

### Conditionnelles
```c
if (x > 0) { ... }
else { ... }
```

### Commentaires
```c
// Commentaire une ligne
/* Commentaire multi-ligne */
```

### Déclaration et affectation
```c
char c = 'A';
int n = 42;
unsigned int u = 10;
```

### Affichage avec printf
```c
printf("%c %d %u\n", c, n, u);
```

### Boucle while
```c
int i = 0;
while (i < 10) {
    printf("%d\n", i);
    i++;
}
```

### while vs for
- **while** → boucle indéterminée.
- **for** → boucle avec compteur connu.

### ASCII
- Table de correspondance entre caractères et valeurs numériques.
- Exemple : `'A'` = 65.

### Flags -m32 / -m64
- `-m32` : compile pour une architecture 32 bits.  
- `-m64` : compile pour 64 bits.

---

## 🔁 Partie 3 – Fonctions et boucles imbriquées

### Boucles imbriquées
```c
for (i = 0; i < 3; i++) {
    for (j = 0; j < 2; j++) {
        printf("%d,%d\n", i, j);
    }
}
```

### while dans un while
```c
while (i < 3) {
    j = 0;
    while (j < 2) { ... j++; }
    i++;
}
```

### Fonction
- **Déclaration :**
  ```c
  int add(int a, int b);
  ```
- **Définition :**
  ```c
  int add(int a, int b) { return a + b; }
  ```

### Prototype
- Permet au compilateur de connaître la fonction avant son utilisation.

### Portée (scope)
- **Locale** : déclarée dans une fonction.
- **Globale** : déclarée en dehors de toute fonction.

### Fichiers d’en-tête
- Contiennent prototypes et définitions partagées.
- Exemple :
  ```c
  #include "main.h"
  ```

### Organisation du projet
- Un header commun (`main.h`).
- Un fichier source par fonction.
- Compilation :
  ```bash
  gcc *.c -o prog
  ```

---

## ✅ Bonnes pratiques
- Commenter son code.
- Respecter le **style Betty**.
- Tous les prototypes dans un seul header.
- Compiler avec des **warnings activés**.
- Diviser le code en fonctions logiques.
