# ansible-bigdata-cloudikoulaone
Ansible Playbook to deploy bigdata nodes in advanced zone Cloud Ikoula ONE 
==========================================================================

Ce Playbook Ansible vous permet de déployer très rapidement plusieurs instances (ex: Debian 8) masters et datanodes avec des volumes datadisks de la taille voulue (jusqu'à 2To par volume) dans un réseau en zone avancée sur Cloud Ikoula One.

Pour utiliser ce playbook Ansible vous devez :
----------------------------------------------

- Avoir un compte Cloud Ikoula ONE
- Avoir Ansible d'installé et fonctionnel (sous GNU/Linux ou Windows avec Cygwin par exemple)
- Avoir Apache Cloudmonkey d'installé et configuré avec votre compte Cloud Ikoula ONE
- Avoir les prérequis du modules CloudStack "cs" d'Ansible d'installés (cf. https://docs.ansible.com/ansible/guide_cloudstack.html)
- Cloner ce repository sur votre machine qui a les prérequis ci-dessus
- Configurer le fichier .cloudstask.ini avec la clé API et la clé privée de votre compte Cloud Ikoula ONE puis le copier dans le répertoire $HOME de votre utilisateur local (via lequel vous allez exécuter ce playbook Ansible)
- Adapter le fichier d'inventory "hosts" selon le nom, ip privée et port ssh publiques des instances que vous souhaitez déployer
- Adapter le fichier deploy_bigata.yml en fonction de votre fichier d'inventory "hosts"
- Configurer le fichier group_vars/all/vars_file.yml avec le nom de la zone avancée, le nom du réseau, l'id de l'offre de calcul, l'id de l'offre de disque, la taille des volumes datadisks, le nom du modèle à utiliser, etc. (les éléments tels que l'id de l'offre de calcul sont récupérables via l'API à l'aide de cloudmonkey par exemple).
