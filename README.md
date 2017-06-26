# TomEE-server
Création d'un serveur TomEE dans un conteneur LXC avec Ansible

# Jenkins-server
Création d'un serveur Jenkins dans un container LXC avec Ansible (autre container)

Fonctionnalités et choses à savoir :
* On suppose évidemment que deux containers LXC sont déjà créés (via le premier script par exemple)
* Le fichier _inventory.ini_ est à modifier selon les IP des container LXC
* _NOUVEAU_ : ajout de la configuration du manager du serveur TomEE pour permettre le déploiement continu à partir d'un build Jenkins

# Précisions
* Nous n'avons rien variabilisé de spécial concernant le déploiement avec Cargo, car nous n'avons pas jugé cela nécessaire : 
  * La configuration de l'utilisateur pour le manager de TomEE aurait pu être faite depuis une variable dans _vars/main.yml_
  * Certaines valeurs auraient pu être renseignées pour le projet Java EE dans le _pom.xml_ via des propriétés ou encore des variables d'environnement.
    Mais cela aurait rajouté un peu de complexité (ne pas oublier de renseigner toutes les variables), cela n'est pas essentiel au TP
* Il vous faudra donc modifier certaines valeurs en dur pour que cela fonctionne :
  * Dans _tomee-server/templates/tomcat-users.xml_ pour le projet Ansible
  * Dans le _pom.xml_ de l'appli Java EE à déployer

# Membres du groupe
Projet effectué par :
* Gabriel Fruhauf
* Maxime Chevallier-Pichon
* Benjamin Eguimendia