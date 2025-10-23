# 🔁 Fiche de Révision – C : Functions, Nested Loops  
![Langage C](https://img.shields.io/badge/Language-C-blue.svg)
![Niveau](https://img.shields.io/badge/Level-Intermediate-green.svg)
![Thème](https://img.shields.io/badge/Topic-Functions_and_Loops-yellow.svg)
![Statut](https://img.shields.io/badge/Status-Ready-brightgreen.svg)

---

## 🎯 Objectifs du module
Apprendre à :
- Définir et utiliser des **fonctions**
- Comprendre la **portée des variables**
- Manipuler les **boucles imbriquées**
- Utiliser le **prototype de fonction**
- Gérer les **retours de fonction** et **paramètres**

---

## ⚙️ 1. Qu’est-ce qu’une fonction ?
Une **fonction** est un bloc de code réutilisable qui effectue une tâche précise.

### 🧩 Exemple simple :
```c
#include <stdio.h>

void print_hello(void)
{
    printf("Hello, world!\n");
}

int main(void)
{
    print_hello();
    return (0);
}
```

➡️ **Résultat :**
```
Hello, world!
```

---

## 📐 2. Structure d’une fonction
```c
type_de_retour nom_de_fonction(type param1, type param2, ...)
{
    // Corps de la fonction
    return (valeur);
}
```

### Exemple :
```c
int add(int a, int b)
{
    return (a + b);
}

int main(void)
{
    int sum = add(3, 7);
    printf("La somme est : %d\n", sum);
    return (0);
}
```
➡️ **Affiche :**
```
La somme est : 10
```

---

## 🔄 3. Boucles imbriquées (nested loops)
Une boucle **à l’intérieur d’une autre boucle**.  
Souvent utilisée pour afficher des grilles ou parcourir des tableaux.

### Exemple :
```c
#include <stdio.h>

int main(void)
{
    int i, j;

    for (i = 0; i < 3; i++)
    {
        for (j = 0; j < 5; j++)
        {
            printf("* ");
        }
        printf("\n");
    }

    return (0);
}
```

➡️ **Résultat :**
```
* * * * *
* * * * *
* * * * *
```

---

## 🔁 4. Boucle `for`
La boucle `for` regroupe l’initialisation, la condition et l’incrémentation.

```c
for (initialisation; condition; incrémentation)
{
    // instructions
}
```

### Exemple :
```c
for (int i = 0; i < 10; i++)
    printf("%d ", i);
```

➡️ **Affiche :**
```
0 1 2 3 4 5 6 7 8 9
```

---

## 🔂 5. Boucle `while` vs `for`
| Type | Utilisation principale | Exemple |
|-------|------------------------|----------|
| `while` | Quand on ne connaît pas le nombre d’itérations | `while (x < 10)` |
| `for` | Quand on connaît le nombre d’itérations | `for (i = 0; i < 10; i++)` |

---

## 🔤 6. Exemple : alphabet avec boucle imbriquée
```c
#include <stdio.h>

int main(void)
{
    char a, b;

    for (a = 'a'; a <= 'z'; a++)
    {
        for (b = 'a'; b <= 'z'; b++)
        {
            putchar(a);
            putchar(b);
            putchar('\n');
        }
    }

    return (0);
}
```

➡️ **Affiche toutes les combinaisons de lettres :**
```
aa
ab
ac
...
zz
```

---

## ⚙️ 7. Prototype de fonction
Un **prototype** informe le compilateur de la signature d’une fonction avant sa définition.

```c
int add(int a, int b);  // prototype

int main(void)
{
    int sum = add(2, 5);
    printf("%d\n", sum);
    return (0);
}

int add(int a, int b)
{
    return (a + b);
}
```

💡 Toujours déclarer les prototypes dans un fichier d’en-tête (`.h`).

---

## 🧩 8. Exemple avec retour `void`
Une fonction peut ne rien renvoyer.

```c
void print_line(int n)
{
    for (int i = 0; i < n; i++)
        putchar('_');
    putchar('\n');
}
```

---

## 🧠 9. Exercice pratique – Multiplication
```c
#include <stdio.h>

int mul(int a, int b)
{
    return (a * b);
}

int main(void)
{
    printf("%d\n", mul(3, 5));
    return (0);
}
```
➡️ **Résultat :**
```
15
```

---

## 🔄 10. Exemple de boucle imbriquée avec compteur
```c
#include <stdio.h>

int main(void)
{
    int i, j, count = 0;

    for (i = 0; i < 3; i++)
    {
        for (j = 0; j < 3; j++)
        {
            printf("(%d, %d) ", i, j);
            count++;
        }
        printf("\n");
    }

    printf("Total : %d paires\n", count);
    return (0);
}
```

➡️ **Affiche :**
```
(0, 0) (0, 1) (0, 2)
(1, 0) (1, 1) (1, 2)
(2, 0) (2, 1) (2, 2)
Total : 9 paires
```

---

## ✅ 11. Bonnes pratiques
✔️ Définir un prototype pour chaque fonction  
✔️ Bien nommer les fonctions (`verbe_action`)  
✔️ Commenter le code avec `/* ... */`  
✔️ Garder les fonctions **courtes et claires**  
✔️ Tester chaque fonction séparément  
✔️ Utiliser des boucles imbriquées uniquement si nécessaire  

---

## ⚠️ 12. Erreurs fréquentes
| Erreur | Cause probable |
|--------|----------------|
| Fonction non déclarée | Oubli du prototype |
| Mauvais type de retour | Type incompatible (`int` vs `void`) |
| Boucle infinie | Condition mal définie |
| Mauvais indice | Erreur dans les bornes de boucle |
| Variable non initialisée | Oubli d’initialisation |

---

## 👤 Auteur
**Projet Holberton School – Low Level Programming**  
👨‍💻 *Leny Bl*  
📁 Dossier : `functions_nested_loops`  
📅 Année : 2025  
📜 Licence : MIT
