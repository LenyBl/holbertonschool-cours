# 🧠 0x00 - C : Hello, World  
![C](https://img.shields.io/badge/Language-C-blue.svg)
![Level](https://img.shields.io/badge/Difficulty-Beginner-green.svg)
![Concept](https://img.shields.io/badge/Topic-Compilation-yellow.svg)

---

## 🎯 Objectifs
- Comprendre **le processus de compilation**
- Découvrir la **structure de base d’un programme C**
- Utiliser les fonctions d’affichage : `printf`, `puts`, `putchar`

---

## 🧩 Étapes de compilation
| Étape | Commande | Résultat |
|--------|-----------|-----------|
| Préprocesseur | `gcc -E main.c > main.i` | Code préparé |
| Compilation | `gcc -S main.c` | Assembleur |
| Assemblage | `gcc -c main.c` | Fichier objet |
| Édition de liens | `gcc main.c -o main` | Exécutable |

---

## 💡 Exemples
```c
#include <stdio.h>

int main(void)
{
    printf("Hello, World!\n");
    return (0);
}
