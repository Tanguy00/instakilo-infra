Le déploiement de configuration via Ansible suppose que :
 - Le serveur d'Instakilo est bien installé, ainsi que sa configuration IP ;
 - Vous accédez au serveur via `ssh <domain_name>`, et votre ~/.ssh/config est correctement configuré ;
 - Vous avez une version récente de Python et le module Pip.

À la racine du dépôt instakilo-infra ou dans son dossier ansible.
Pour installer Ansible :
`python3 -m venv .pyenv`
`source .pyenv/bin/activate`
`python3 -m pip install --user ansible==6.4`
Pour utiliser l'evironnement :
`source .pyenv/bin/activate`
Pour arrêter d'utiliser l'environnement :
`source .pyenv/bin/deactivate`

