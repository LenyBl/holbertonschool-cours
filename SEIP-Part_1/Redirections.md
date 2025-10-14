# Redirections et pipes

| Syntaxe | Description | Exemple |
|---------|-------------|---------|
| `>` | Redirige stdout (écrase) | `echo "test" > file` |
| `>>` | Redirige stdout (ajoute) | `echo "test" >> file` |
| `<` | Redirige stdin | `wc -l < file` |
| `2>` | Redirige stderr | `commande 2> err.log` |
| `|` | Pipe — enchaîne deux commandes | `ls | wc -l` |
| `&&` | Exécute 2ᵉ si 1ʳᵉ réussit | `mkdir test && cd test` |
| `||` | Exécute 2ᵉ si 1ʳᵉ échoue | `false || echo "erreur"` |
