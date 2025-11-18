# 🧠 Fiche de Révision -- `calloc`, `realloc`, gestion avancée

## 📌 1. `calloc` -- Allocation + initialisation

``` c
ptr = calloc(nb, sizeof(type));
```

-   Alloue de la mémoire **initialisée à 0**.
-   Évite les valeurs indéfinies.

------------------------------------------------------------------------

## 📌 2. `realloc` -- Redimensionnement

``` c
ptr = realloc(ptr, new_size);
```

Permet d'augmenter ou réduire une zone mémoire déjà allouée.

⚠ Attention : - Peut **déplacer** la mémoire ailleurs. - Toujours faire
:

``` c
tmp = realloc(ptr, new_size);
if (!tmp) { free(ptr); return NULL; }
ptr = tmp;
```

------------------------------------------------------------------------

## 📌 3. Libération d'un tableau 2D dynamique

``` c
for (int i = 0; i < h; i++)
    free(grid[i]);
free(grid);
```

------------------------------------------------------------------------

## 📌 4. Cas d'usage classique : concaténation dynamique

``` c
char *str = malloc(1);
str[0] = '\0';

str = realloc(str, strlen(str) + strlen(word) + 1);
strcat(str, word);
```

------------------------------------------------------------------------

## 📌 5. Points importants

✔ `calloc` = `malloc` + mise à zéro\
✔ `realloc` peut déplacer la mémoire\
✔ Toujours libérer les tableaux multidimensionnels
