# 📘 Conventional Commits - Mémo visuel

## Structure d’un commit
```
<type>[<scope>]: <description>
[body]
[footer]
```

## 🔧 Types de commit

| Type | Symbole | Couleur | Description | SemVer |
|------|---------|---------|-------------|--------|
| feat | ✨      | vert    | Nouvelle fonctionnalité | MINOR |
| fix  | 🐛      | rouge   | Correction de bug        | PATCH |
| BREAKING CHANGE | 💥 | orange | Changement majeur       | MAJOR |
| docs | 📝      | bleu    | Documentation            | -     |
| style| 🎨      | violet  | Formatage / style        | -     |
| refactor | ♻️    | cyan    | Refactor sans ajout/fix  | -     |
| perf | ⚡      | jaune   | Amélioration perf        | -     |
| test | ✅      | gris    | Tests                    | -     |
| chore | 🛠️     | marron  | Divers / CI / build      | -     |
| ci   | 🤖      | marron  | Intégration continue     | -     |
| build| 🏗️      | marron  | Build / config           | -     |

---

## ⚠️ Changement majeur
- Pied-de-page :  
```
BREAKING CHANGE: ancienne API obsolète
```
- Ou `!` après type/scope :  
```
feat(api)!: nouvelle API
```

---

## ✅ Bonnes pratiques
- Choisir le type adapté  
- Message clair et concis  
- Maintenir la cohérence  
- Automatiser avec Commitlint / Standard Version / semantic-release

---

## 📚 Liens utiles
- [Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/)  
- [Commitlint](https://commitlint.js.org/)  
- [Standard Version](https://github.com/conventional-changelog/standard-version)  
- [semantic-release](https://semantic-release.gitbook.io/semantic-release/)