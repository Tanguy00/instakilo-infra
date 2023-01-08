# Instakilo
Projet de gestion de projet, à l'Université de Picardie. Héberger une application web sur Linux.
<br />

Sur le serveur, les alias suivants sont présents :
- démarrer : qui permet de démarrer le service Instakilo
- arrêter : qui permet de d'arrêter le service Instakilo
*Ces deux alias sont à utiliser pour le jeu du « Devine qui est indisponible ? » (voir fiche de préparation pédagogique)*
<br />

## Installation et configuration du projet

**Installation du Raspberry Pi**
Il doit disposer du système d'exploitation Raspberry Pi OS Lite. Si ce n'est pas le cas, suivez cette procédure : https://www.tutos.eu/3330
Après l'avoir suivi, vous disposez d'un accès SSH à votre machine, elle même pleinnement fonctionnelle.
Tapez la commande `ip -c a` pour connaître son adresse IP.
<br />

**Configuration du Raspberry Pi (RPI)**
Clonnez ce dépôt Git sur votre machine qui peut accéder au RPI par SSH.
`git clone git@github.com:Tanguy00/instakilo-infra.git`
<br />

Modifiez le fichier `https://github.com/Tanguy00/instakilo-infra/blob/main/ansible/inventory.yml` en remplaçant `tanguynicolas.fr` par l'adresse IP de votre Raspberry.
<br />

**Installation d'Ansible sur votre machine**

Suivez cette procédure pour installer Python : https://wiki.python.org/moin/BeginnersGuide/Download
<br />

Ensuite, effectuez les commandes suivantes. Si vous n'êtes pas familier avec les environnements virtuels Python, consultez cette documentation : https://blog.stephane-robert.info/post/python-pyenv-pipenv/
```bash
python -m venv .pyenv
source .pyenv/bin/activate  # On entre dans l'env

python3 -m pip install ansible==6.6
ansible --version

deactivate               # On sort de l'env
```
<br />

Maintenant, déployez la configuration sur le Raspberry Pi !
```bash
ansible-playbook raspberrypi.yml -i inventory.yml
```
<br />

**Configuration du commutateur (optionnel)**
D'abbord, connectez vous au commutateur à l'aide d'un câble console pour accéder à la CLI de Cisco IOS.
Vous pouvez utiliser la précude officielle pour vous aider : https://www.cisco.com/c/en/us/support/docs/smb/switches/cisco-small-business-300-series-managed-switches/smb4984-access-the-cli-via-putty-using-a-console-connection-on-300-a.html
<br />

Une fois connecté, il ne reste plus qu'à copier/collez bêtement l'intégralité de ce fichier de configuration : https://github.com/Tanguy00/instakilo-infra/blob/main/switch-config.ios
Adaptez le en fonction de vos besoin.
