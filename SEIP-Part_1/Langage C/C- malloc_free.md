# 🧠 Fiche de Révision -- `malloc` / `free`

## 📌 1. Qu'est‑ce que l'allocation dynamique ?

L'allocation dynamique permet de réserver de la mémoire **pendant
l'exécution** d'un programme.\
Elle est indispensable quand : - on ne connaît pas la taille à
l'avance, - on doit créer des structures flexibles (tableaux dynamiques,
listes, etc.).

------------------------------------------------------------------------

## 📌 2. `malloc` -- Allocation simple

``` c
ptr = malloc(sizeof(type) * nb);
```

-   Retourne un **pointeur** vers la mémoire allouée.
-   Retourne **NULL** si l'allocation échoue.
-   La mémoire n'est **pas initialisée**.

🔍 Exemple :

``` c
int *tab = malloc(sizeof(int) * 10);
if (!tab) return (NULL);
```

------------------------------------------------------------------------

## 📌 3. `free` -- Libération mémoire

``` c
free(ptr);
```

-   Libère la mémoire précédemment allouée.
-   **Obligatoire** pour éviter les memory leaks.
-   Ne jamais faire `free` sur :
    -   un pointeur déjà libéré,
    -   un pointeur non alloué dynamiquement.

------------------------------------------------------------------------

## 📌 4. Bonnes pratiques

✔ Toujours vérifier si `malloc` retourne `NULL`\
✔ Libérer toute allocation\
✔ Initialiser les pointeurs à `NULL` après `free`\
✔ Éviter les *dangling pointers*

------------------------------------------------------------------------

## 📌 5. Erreurs fréquentes

❌ Oublier un `free`\
❌ Libérer deux fois la même zone\
❌ Modifier un pointeur avant `free` (perte de référence)

------------------------------------------------------------------------

## 📌 6. Exemple complet

``` c
int *arr = malloc(sizeof(int) * 5);
if (!arr) return (1);

for (int i = 0; i < 5; i++)
    arr[i] = i * 2;

free(arr);
arr = NULL;
```
