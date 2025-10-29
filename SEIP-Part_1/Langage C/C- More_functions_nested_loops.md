# Fiche de Révision : Fonctions et Boucles Imbriquées (Partie 2)

## Objectifs
- Approfondir l'utilisation des boucles imbriquées.
- Comprendre la modularisation du code avec des fonctions.
- Apprendre à utiliser les prototypes, les en-têtes (`.h`) et la compilation séparée.

## Concepts Clés

### 1. Fonctions
- Déclaration : `int add(int a, int b);`
- Définition : 
```c
int add(int a, int b) {
    return (a + b);
}
```
- Prototype obligatoire avant l'appel (ou inclusion via un header).

### 2. Boucles Imbriquées
- Permettent d’effectuer des opérations répétées sur plusieurs dimensions.
- Exemple :
```c
for (int i = 0; i < 5; i++) {
    for (int j = 0; j < 5; j++) {
        _putchar('#');
    }
    _putchar('\n');
}
```
- Applications : affichage de formes, tables de multiplication, etc.

### 3. Headers et Compilation
- Fichier d’en-tête : contient les prototypes et constantes.
```c
#ifndef MAIN_H
#define MAIN_H
int add(int a, int b);
void print_square(int size);
#endif
```
- Compilation : `gcc main.c functions.c -o prog`

## Bonnes Pratiques
- Nomme tes fonctions de façon claire (`print_square`, `mul`, etc.).
- Évite les variables globales.
- Garde ton code modulaire : une fonction = une tâche.

## Exercices Typiques
- Écrire une fonction qui affiche un carré de `#`.
- Écrire une fonction qui vérifie un caractère en majuscule.
- Multiplier deux entiers via une fonction `int mul(int a, int b)`.
- Écrire un programme qui imprime les nombres premiers de 1 à 100.

---
