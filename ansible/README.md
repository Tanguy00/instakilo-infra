Le déploiement de configuration via Ansible suppose que :
 - Le serveur d'Instakilo est bien installé, ainsi que sa configuration IP ;
 - Vous accédez au serveur via `ssh <domain_name>`, et votre ~/.ssh/config est correctement configuré ;
 - Vous avez une version récente de Python.

Pour installer Ansible :
`python3 -m venv .pyenv`
`source .pyenv/bin/activate`
`python3 -m pip install ansible==6.4`
Pour utiliser l'evironnement :
`source .pyenv/bin/activate`
Pour arrêter d'utiliser l'environnement :
`deactivate`

Pour lancer le playbook :
`ansible-playbook raspberrypi.yml -i inventory.yml`
