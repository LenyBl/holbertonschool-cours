# 🔢 Fiche de Révision – C : Variables, if, else, while  
![Langage C](https://img.shields.io/badge/Language-C-blue.svg)
![Niveau](https://img.shields.io/badge/Level-Beginner-green.svg)
![Thème](https://img.shields.io/badge/Topic-Control_Flow-yellow.svg)
![Statut](https://img.shields.io/badge/Status-Ready-brightgreen.svg)

---

## 🎯 Objectifs du module
Apprendre à :
- Déclarer et manipuler des **variables**
- Utiliser les **conditions** (`if`, `else if`, `else`)
- Créer des **boucles `while`**
- Employer les **opérateurs logiques et arithmétiques**
- Contrôler le **flux d’un programme**

---

## 🧮 1. Les variables
Une **variable** est une case mémoire identifiée par un nom et un type.  
Elle permet de **stocker** et **manipuler** des valeurs.

### 🧱 Déclaration et initialisation :
```c
int age = 20;       // entier
char letter = 'A';  // caractère
float pi = 3.14;    // réel
```

### ⚙️ Types de base :
| Type | Taille (approx.) | Exemple | Description |
|------|------------------|----------|--------------|
| `int` | 4 octets | `int n = 42;` | Entier |
| `char` | 1 octet | `char c = 'C';` | Caractère ASCII |
| `float` | 4 octets | `float x = 3.14;` | Réel simple précision |
| `double` | 8 octets | `double y = 2.71828;` | Réel double précision |

📌 **Règle d’or :** toujours initialiser une variable avant de l’utiliser.

---

## ⚖️ 2. Les conditions : `if`, `else if`, `else`
Les **conditions** permettent d’exécuter un bloc de code selon un test logique.

### 🧩 Exemple simple :
```c
#include <stdio.h>

int main(void)
{
    int n = -5;

    if (n > 0)
        printf("Positif\n");
    else if (n == 0)
        printf("Nul\n");
    else
        printf("Négatif\n");

    return (0);
}
```

➡️ **Résultat possible :**
```
Négatif
```

### 🔍 Opérateurs de comparaison :
| Opérateur | Signification | Exemple | Résultat |
|------------|----------------|----------|-----------|
| `==` | Égal à | `a == b` | Vrai si a = b |
| `!=` | Différent de | `a != b` | Vrai si a ≠ b |
| `>` | Supérieur à | `a > b` | Vrai si a > b |
| `<` | Inférieur à | `a < b` | Vrai si a < b |
| `>=` | Supérieur ou égal | `a >= b` | Vrai si a ≥ b |
| `<=` | Inférieur ou égal | `a <= b` | Vrai si a ≤ b |

---

## 🔁 3. La boucle `while`
Répète un bloc de code **tant que** la condition est vraie.

### Exemple simple :
```c
#include <stdio.h>

int main(void)
{
    int i = 0;

    while (i < 5)
    {
        printf("%d\n", i);
        i++;
    }

    return (0);
}
```

➡️ **Affiche :**
```
0
1
2
3
4
```

---

## 🔠 4. Afficher des caractères avec `putchar()`
```c
#include <stdio.h>

int main(void)
{
    char c = 'a';

    while (c <= 'z')
    {
        putchar(c);
        c++;
    }

    putchar('\n');
    return (0);
}
```

➡️ **Résultat :**
```
abcdefghijklmnopqrstuvwxyz
```

---

## 🎲 5. Générer des nombres aléatoires
```c
#include <stdlib.h>
#include <time.h>
#include <stdio.h>

int main(void)
{
    int n;
    srand(time(0));
    n = rand() - RAND_MAX/2;
    printf("%d\n", n);
    return (0);
}
```

➡️ **Affiche un nombre aléatoire positif ou négatif.**

---

## 🧩 6. Exemple complet : dernier chiffre
```c
#include <stdlib.h>
#include <time.h>
#include <stdio.h>

int main(void)
{
    int n, last_digit;
    srand(time(0));
    n = rand() - RAND_MAX / 2;
    last_digit = n % 10;

    if (last_digit > 5)
        printf("Last digit of %d is %d and is greater than 5\n", n, last_digit);
    else if (last_digit == 0)
        printf("Last digit of %d is %d and is 0\n", n, last_digit);
    else
        printf("Last digit of %d is %d and is less than 6 and not 0\n", n, last_digit);

    return (0);
}
```

---

## 🧮 7. Opérateurs arithmétiques
| Opérateur | Fonction | Exemple | Résultat |
|------------|-----------|----------|-----------|
| `+` | Addition | `5 + 2` | 7 |
| `-` | Soustraction | `5 - 2` | 3 |
| `*` | Multiplication | `5 * 2` | 10 |
| `/` | Division entière | `5 / 2` | 2 |
| `%` | Modulo (reste) | `5 % 2` | 1 |

---

## ⚙️ 8. Compilation
```bash
gcc -Wall -Werror -Wextra -pedantic -std=gnu89 main.c -o main
./main
```

---

## ✅ 9. Bonnes pratiques
✔️ Initialiser toutes les variables  
✔️ Ajouter `\n` à chaque affichage (`printf`, `putchar`)  
✔️ Une seule instruction par ligne  
✔️ Pas de boucle infinie  
✔️ Code indenté et lisible  
✔️ Utiliser des commentaires `/* ... */`  
✔️ Compiler souvent pour repérer les erreurs tôt  

---

## 💪 10. Mini-exercice
💡 Afficher les chiffres de 0 à 9 avec `putchar()` :
```c
#include <stdio.h>

int main(void)
{
    int i = 0;

    while (i < 10)
    {
        putchar('0' + i);
        i++;
    }
    putchar('\n');

    return (0);
}
```

➡️ **Affiche :**
```
0123456789
```

---

## 👤 Auteur
**Projet Holberton School – Low Level Programming**  
👨‍💻 *Leny Bl*  
📁 Dossier : `variables_if_else_while`  
📅 Année : 2025  
📜 Licence : MIT
