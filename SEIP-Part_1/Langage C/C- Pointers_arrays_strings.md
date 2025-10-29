# Fiche de Révision : Pointeurs, Tableaux et Chaînes de caractères

## Objectifs
- Comprendre les pointeurs en C : adresse, valeur, déréférencement.
- Manipuler les tableaux et leurs relations avec les pointeurs.
- Travailler avec les chaînes de caractères (tableaux de char).
- Éviter les erreurs de segmentation et les fuites mémoire.

## Concepts Clés

### 1. Pointeurs
- Déclaration : `int *p;`
- Adresse et valeur : `p = &x;` → `*p` permet d'accéder à la valeur.
- Pointeur NULL : `int *q = NULL;`
- Pointeur sur pointeur : `int **pp;`
- Incrémentation : `p++` fait avancer le pointeur d’un élément du type pointé.

### 2. Tableaux
- Un tableau est une zone contiguë de mémoire.
- Le nom du tableau est un pointeur sur son premier élément : `arr == &arr[0]`.
- `arr[i]` ≡ `*(arr + i)`.
- Attention : la taille n’est pas transmise automatiquement aux fonctions.

### 3. Chaînes de caractères
- Une chaîne est un tableau de `char` terminé par `\0`.
- Fonctions standards : `strlen`, `strcpy`, `strcmp`, `strcat`.
- Exemple :
```c
char str1[] = "Hello";
char str2[10];
strcpy(str2, str1);
printf("%s\n", str2);
```

## Bonnes Pratiques
- Vérifier les pointeurs avant utilisation (`if (p != NULL)`).
- Toujours ajouter `\0` à la fin d'une chaîne.
- Libérer la mémoire allouée dynamiquement avec `free()`.

## Exercices Typiques
- Implémenter `_strlen`, `_strcpy`, `_strcmp`.
- Inverser une chaîne (`rev_string`).
- Copier un tableau d’entiers avec des pointeurs.

---
