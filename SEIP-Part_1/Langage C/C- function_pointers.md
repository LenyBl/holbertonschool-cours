# 🧠 Fiche de Révision -- Pointeurs de fonctions

## 📌 1. Définition

Un pointeur de fonction permet de stocker **l'adresse d'une fonction**.

Syntaxe :

``` c
int (*f)(int, int);
```

------------------------------------------------------------------------

## 📌 2. Affectation

``` c
int add(int a, int b) { return a + b; }

int (*f)(int, int) = add;
```

------------------------------------------------------------------------

## 📌 3. Appel via pointeur

``` c
int result = f(3, 4);
```

Equivalent à :

``` c
int result = (*f)(3, 4);
```

------------------------------------------------------------------------

## 📌 4. Tableaux de pointeurs de fonctions

``` c
int (*ops[4])(int, int) = {add, sub, mul, div};
result = ops[0](5, 2); // add
```

------------------------------------------------------------------------

## 📌 5. Callback : passer une fonction en paramètre

``` c
void apply(int *a, int b, int (*op)(int,int))
{
    *a = op(*a, b);
}
```

------------------------------------------------------------------------

## 📌 6. Utilisation courante : mini‑calculatrice

``` c
int (*get_op(char c))(int,int)
{
    if (c == '+') return add;
    if (c == '-') return sub;
    return NULL;
}
```

------------------------------------------------------------------------

## 📌 7. Points essentiels

✔ Une fonction = une adresse\
✔ On peut stocker plusieurs fonctions dans un tableau\
✔ Très utile pour remplacer de gros `switch`\
✔ Indispensable pour callbacks, handlers, etc.
