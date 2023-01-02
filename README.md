# Instakilo
Projet de gestion de projet, à l'Université de Picardie. Héberger une application web sur Linux.

Sur le serveur, on ajoute les alias suivants :
```bash
alias démarrer='docker compose --file compose-pull_remote.yaml up -d && echo -e "\n\n\e[32mLe serveur a bien démarré !!!\e[0m\n"'

alias stopper='docker compose --file compose-pull_remote.yaml stop && echo -e "\n\n\e[31mLe serveur est bien à l arrêt...\e[0m\n"'
```
