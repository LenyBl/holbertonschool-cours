# 🧠 Notes de cours — Git & GitHub

## 📦 1. Installation et configuration de Git

### 🔧 Installation
**macOS :**
```bash
brew install git
```

**Ubuntu / Debian :**
```bash
sudo apt install git
```

**Windows :**
Télécharger depuis [https://git-scm.com/downloads](https://git-scm.com/downloads)

### 👤 Configuration de l’identité
```bash
git config --global user.name "Ton Nom"
git config --global user.email "ton.email@example.com"
```

| Commande | Description |
|-----------|-------------|
| `git config --global` | Configure une option pour **tous les dépôts**. |
| `git config --local` | Configure une option uniquement pour **le dépôt courant**. |
| `git config --list` | Affiche toutes les configurations actuelles. |

---

## 🗂️ 2. Créer et gérer un dépôt local et distant

### 🏗️ Créer un dépôt local
```bash
git init
```

### 🪣 Cloner un dépôt distant
```bash
git clone https://github.com/utilisateur/nom-du-repo.git
```

| Commande | Description |
|-----------|-------------|
| `git init` | Initialise un dépôt local. |
| `git clone <url>` | Copie un dépôt distant sur ta machine. |
| `git remote -v` | Liste les dépôts distants configurés. |
| `git remote add origin <url>` | Lie ton dépôt local à un dépôt GitHub. |
| `git remote remove origin` | Supprime la liaison distante. |

---

## 🔄 3. Suivre les changements et comprendre les zones

### Les 3 zones Git
| Zone | Description | Commande principale |
|-------|--------------|----------------------|
| **Working Directory** | Ton dossier de travail. | — |
| **Staging Area** | Zone d’attente avant commit. | `git add` |
| **Repository (HEAD)** | Historique des commits. | `git commit` |

### Commandes clés
```bash
git status          # Affiche l’état des fichiers
git add <fichier>   # Ajoute un fichier au staging
git add .           # Ajoute tous les fichiers modifiés
git commit -m "Message clair"   # Valide les changements
```

> 🔹 **Option `-m`** : permet de spécifier directement le message du commit.

---

## 🧹 4. Ignorer les fichiers inutiles avec `.gitignore`

Créer un fichier `.gitignore` à la racine du projet.

Exemple :
```
node_modules/
.env
*.log
```

| Exemple | Signification |
|----------|----------------|
| `*.log` | Ignore tous les fichiers se terminant par `.log`. |
| `folder/` | Ignore le dossier complet `folder`. |
| `!important.log` | N’ignore pas `important.log` même s’il correspond à une règle. |

---

## ☁️ 5. Synchroniser avec GitHub (Push & Pull)

### 🔐 Authentification avec un Personal Access Token (PAT)
GitHub n’autorise plus les mots de passe.  
Créer un token via :  
**Settings → Developer settings → Personal access tokens.**

### Commandes :
```bash
git push -u origin main
git pull origin main
```

| Commande | Description |
|-----------|-------------|
| `git push` | Envoie les commits locaux vers GitHub. |
| `git pull` | Récupère et fusionne les changements distants. |
| `-u` | Définit la branche distante par défaut pour les futurs `push`. |
| `-M` | Utilisé pour **renommer une branche** (ex : `git branch -M main`). |

---

## 🌿 6. Travailler avec les branches

Les branches permettent d’isoler le développement.

```bash
git branch                # Liste les branches
git branch nouvelle-fonction
git checkout nouvelle-fonction
git checkout -b nouvelle-fonction  # Crée + bascule directement
```

| Commande | Description |
|-----------|-------------|
| `git branch` | Liste / crée / supprime des branches. |
| `git checkout` | Change de branche. |
| `git switch` | Alternative moderne à `checkout`. |
| `git branch -M main` | Renomme la branche actuelle en "main". |

---

## 🔀 7. Fusionner des branches et gérer les conflits

```bash
git checkout main
git merge nouvelle-fonction
```

Si un **conflit** apparaît :
1. Git marque les fichiers avec `<<<<<<<`, `=======`, `>>>>>>>`.
2. Corrige manuellement les conflits.
3. Puis :
   ```bash
   git add .
   git commit -m "Résolution de conflit"
   ```

| Commande | Description |
|-----------|-------------|
| `git merge` | Fusionne une branche dans celle courante. |
| `git diff` | Montre les différences entre branches ou commits. |
| `git log` | Affiche l’historique des commits. |

---

## 🕐 8. Annuler / revenir en arrière

### 🧭 `git reset`
Annule des commits localement (peut modifier l’historique).

| Mode | Effet | Exemple |
|------|--------|----------|
| `--soft` | Garde les fichiers dans le staging. | `git reset --soft HEAD~1` |
| `--mixed` | Garde les fichiers modifiés, mais retire du staging. | `git reset --mixed HEAD~1` |
| `--hard` | Supprime tous les changements. | `git reset --hard HEAD~1` |

### 🧩 `git revert`
Crée un **nouveau commit inverse** pour annuler un commit sans casser l’historique partagé.

```bash
git revert <id-du-commit>
```

---

## 🚀 9. Le GitHub Flow complet

| Étape | Action | Commande |
|--------|---------|----------|
| 1️⃣ | Créer une branche | `git checkout -b feature/nom` |
| 2️⃣ | Modifier et commit | `git add . && git commit -m "Ajout fonctionnalité"` |
| 3️⃣ | Pousser sur GitHub | `git push -u origin feature/nom` |
| 4️⃣ | Créer une Pull Request | Sur GitHub |
| 5️⃣ | Relecture & Merge | “Merge Pull Request” |
| 6️⃣ | Gérer les conflits | `git merge` + corrections |
| 7️⃣ | Rollback si besoin | `git revert` ou `git reset` |

---

## 🧭 Résumé global des commandes

| Action | Commande | Description |
|---------|-----------|-------------|
| Initialiser un dépôt | `git init` | Crée un dépôt local |
| Ajouter un dépôt distant | `git remote add origin <url>` | Lie à GitHub |
| Ajouter des fichiers | `git add .` | Prépare les changements |
| Commit | `git commit -m "Message"` | Sauvegarde une version |
| Push | `git push -u origin main` | Envoie vers GitHub |
| Pull | `git pull origin main` | Récupère les modifications |
| Créer une branche | `git branch nom` | Crée une nouvelle branche |
| Basculer de branche | `git checkout nom` | Change de branche |
| Fusionner | `git merge nom` | Intègre une autre branche |
| Annuler un commit | `git reset` / `git revert` | Revient en arrière |

---

✍️ **Conseil :**
Toujours utiliser des messages de commit **clairs et concis**, par exemple :
> `git commit -m "Fix: correction du bug d'affichage du menu"`

---

📘 **Sources utiles :**
- [Documentation Git](https://git-scm.com/doc)
- [GitHub Docs](https://docs.github.com)
- [Git Cheatsheet PDF (officiel)](https://education.github.com/git-cheat-sheet-education.pdf)
