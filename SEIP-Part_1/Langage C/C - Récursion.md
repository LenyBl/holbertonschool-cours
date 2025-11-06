# 🧠 Fiche de révision – La Récursion en C

## 🔍 Définition
La **récursion** est une méthode de programmation où une fonction **s’appelle elle-même** pour résoudre un problème.
Chaque appel traite une **partie du problème** jusqu’à atteindre un **cas de base** (ou condition d’arrêt).

---

## ⚙️ Structure type
```c
type fonction_recursif(type paramètres) {
    if (condition_base) {
        return valeur_base;   // Cas de base
    }
    return fonction_recursif(paramètres_modifiés); // Cas récursif
}
```

---

## 🧩 Concepts clés

| Terme | Définition |
|-------|-------------|
| **Cas de base** | Condition qui met fin à la récursion |
| **Cas récursif** | Partie où la fonction s'appelle elle-même |
| **Pile d’appels** | Zone mémoire où sont stockés les appels de fonctions |
| **Déroulement / enroulement** | Processus d’empilement puis de retour des appels récursifs |

---

## 🧮 Exemples classiques

### 1. Factorielle
```c
int factorial(int n) {
    if (n <= 1)
        return 1;
    return n * factorial(n - 1);
}
```

### 2. Somme d’un tableau
```c
int sum_array(int *arr, int size) {
    if (size == 0)
        return 0;
    return arr[size - 1] + sum_array(arr, size - 1);
}
```

### 3. Suite de Fibonacci
```c
int fibonacci(int n) {
    if (n <= 1)
        return n;
    return fibonacci(n - 1) + fibonacci(n - 2);
}
```

---

## ⚖️ Récursion vs Itération

| Critère | Récursion | Itération |
|----------|------------|------------|
| **Principe** | Appels de fonction imbriqués | Boucles (for, while) |
| **Lisibilité** | Souvent plus claire | Souvent plus performante |
| **Mémoire** | Utilise la pile d’appels | Moins de mémoire |
| **Risque** | Stack overflow si mal contrôlée | Aucun stack overflow |

---

## 🚫 Erreurs fréquentes
- Oublier le **cas de base** → boucle infinie  
- Mauvaise **progression vers le cas de base**  
- Appel avec **paramètres inchangés**  
- Utilisation excessive → dépassement de pile  

---

## 🧠 Astuces de compréhension
- Tracer les appels avec un petit exemple sur papier  
- Visualiser la pile : chaque appel est suspendu jusqu’à ce que le suivant se termine  
- Commencer simple, puis complexifier  
- Penser “je divise le problème en plus petit”  

---

## 📚 Exercices typiques
1. Afficher une chaîne de caractères récursivement (`_puts_recursion`)  
2. Calculer la factorielle d’un entier (`factorial`)  
3. Calculer la longueur d’une chaîne (`_strlen_recursion`)  
4. Vérifier un palindrome récursivement  
5. Calculer la racine carrée naturelle (`_sqrt_recursion`)  

---

## 🧾 Récapitulatif
✅ Une fonction récursive doit :  
- Avoir **un cas de base clair**  
- Réduire le problème à chaque appel  
- Revenir au résultat via la pile d’appels  

---

## 📖 À retenir
> La récursion, c’est penser “problème + sous‑problème” et toujours savoir **quand s’arrêter**.

---

## ✍️ Auteur
Fiche rédigée par **LenyBl – Holberton School 2025**  
Licence : MIT
