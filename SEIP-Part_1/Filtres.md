# Filtres & traitement de texte

| Commande | Description | Exemple |
|----------|-------------|---------|
| `grep` | Recherche une chaîne | `grep "mot" fichier` |
| `grep -v` | Inverse la recherche | `grep -v "mot" fichier` |
| `cut` | Découpe les lignes | `cut -d: -f1 /etc/passwd` |
| `sort` | Trie les lignes | `sort fichier` |
| `uniq` | Supprime doublons | `sort fichier | uniq` |
| `wc` | Compte les lignes | `wc -l fichier` |
| `tr` | Substitution de caractères | `tr 'a-z' 'A-Z'` |
| `head` / `tail` | Affiche début/fin | `head -n 5 fichier` |
| `sed` | Remplace dans un flux | `sed 's/foo/bar/' fichier` |
| `awk` | Manipulation par colonne | `awk '{print $1}' fichier` |
