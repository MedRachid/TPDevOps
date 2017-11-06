					# TPDevOps

-------------------------------------------------------------

1 - Tout d'abord il a fallu recuper une image fonctionnelle du serveur SSH à l'aide de la commande : 

 		dockerpullregistry.mrzee.fr/ynov/ssh-server:0.1

-------------------------------------------------------------

2- J'ai creer d'abord des clés privées et publiques avec : 
		
						ssh-keygen

-------------------------------------------------------------

3 - J'ai donc ajouter ensuite la clé privée fourni a mon agent SSH local en la copiant grâce à la commande : 

        		nano ~/.ssh/id_rsa_key_ssh

-------------------------------------------------------------

4 - On a pu ensuite creer nos 3 conteneurs grâce à :

dockerrun-d--name="ssh-server-1"registry.mrzee.fr/ynov/ssh-server:0.1

-------------------------------------------------------------

4bis - On ajoutera la clé privée au client avec :

				ssh-add ~/.ssh/id_rsa_key_ssh

-------------------------------------------------------------

5 - Pour pouvoir acceder à nos conteneurs on utilisera la commande : 

				ssh root@172.17.0.(2)/(3)/(4)

-------------------------------------------------------------

6 - On va ensuite creer un fichier hosts dans le dossier /etc/ansible dans lesquels on va y rentrer les ip de nos conteneurs ainsi que de creer un groupe pour nos conteneurs avec un : 

				sudo nano /etc/ansible/hosts

-------------------------------------------------------------

7 - Enfin on lance le playbook avec la commande : 

			ansible-playbook chemin/d'acces/playbook.yml





