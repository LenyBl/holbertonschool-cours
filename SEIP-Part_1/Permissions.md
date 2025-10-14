# Permissions & Propriété

| Commande | Description | Exemples |
|----------|-------------|----------|
| `chmod` | Change les permissions | `chmod 755 fichier`, `chmod u+x fichier` |
| `chown` | Change le propriétaire | `chown betty fichier` |
| `chown -h` | Propriétaire d’un lien symbolique | `chown -h betty link` |
| `chown --from` | Seulement si propriétaire actuel | `chown --from=guillaume vincent fichier` |
| `chgrp` | Change le groupe | `chgrp staff fichier` |
| `chmod --reference` | Copie les permissions | `chmod --reference=source cible` |
| `ls -l` | Vérifie les permissions | `ls -l fichier` |

## 📊 Codes Octaux
| Octal | u | g | o | Signification |
|-------|---|---|---|---------------|
| 7 | rwx | - | - | Lecture, écriture, exécution |
| 5 | r-x | - | - | Lecture, exécution |
| 0 | --- | - | - | Aucun droit |
