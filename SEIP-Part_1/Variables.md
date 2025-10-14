# Variables & expansions

| Syntaxe | Description | Exemple |
|---------|-------------|---------|
| `VAR=value` | Assigne une variable | `NAME="Lorenzo"` |
| `$VAR` | Affiche valeur | `echo $NAME` |
| `${VAR:-default}` | Valeur par défaut | `${USER:-inconnu}` |
| `${#VAR}` | Longueur de la variable | `${#NAME}` |
| `export VAR` | Exporte la variable | `export PATH=$PATH:/new` |
| `$(cmd)` | Substitution de commande | `echo $(date)` |
| `` `cmd` `` | Ancienne syntaxe | `` echo `pwd` `` |
| `$?` | Code retour dernière commande | `echo $?` |
| `$$` | PID du shell | `echo $$` |
