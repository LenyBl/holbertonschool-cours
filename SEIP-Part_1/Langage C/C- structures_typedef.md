# 🧠 Fiche de Révision -- Structures & `typedef`

## 📌 1. Pourquoi des structures ?

Elles permettent de regrouper plusieurs variables dans un seul ensemble
logique.

Exemple :

``` c
struct dog {
    char *name;
    float age;
};
```

------------------------------------------------------------------------

## 📌 2. Utilisation

``` c
struct dog mydog;
mydog.age = 3.5;
```

------------------------------------------------------------------------

## 📌 3. Pointeurs sur structures

``` c
struct dog *d = malloc(sizeof(struct dog));
d->age = 4.2;
```

------------------------------------------------------------------------

## 📌 4. `typedef` -- Simplifier les noms

``` c
typedef struct dog {
    char *name;
    float age;
} dog_t;
```

Usage :

``` c
dog_t mydog;
```

------------------------------------------------------------------------

## 📌 5. Passer une structure à une fonction

``` c
void print_dog(dog_t *d)
{
    printf("%s – %.1f ans\n", d->name, d->age);
}
```

------------------------------------------------------------------------

## 📌 6. Structures + malloc

``` c
dog_t *d = malloc(sizeof(dog_t));
d->name = strdup("Rex");
```

------------------------------------------------------------------------

## 📌 7. Concepts clés

✔ `.` pour structure\
✔ `->` pour pointeur de structure\
✔ `typedef` = alias de type\
✔ Toujours libérer les champs alloués
