# OneStar3Gram - Keycloak

Ce repo contient l'ensemble de la configuration keycloak du projet OneStar3Gram, avec en plus une configuration Traefik permettant de simplifier la connexion au backend de l'application.

## Mise en place

Pour utiliser keycloak dans le projet, différentes étapes sont nécessaires afin de configurer l'environnement de développement sur la machine hôte.

### Configuration du DNS

La première étape va être de configurer le DNS de la machine hôte pour spécifier le hostname du reverse-proxy. 

Sur Windows, il est nécessaire d'ouvrir le bloc-note en tant qu'administrateur puis d'ouvrir le fichier  C:\Windows\System32\drivers\etc\hosts\
On peut ensuite ajouter à la fin de ce fichier la ligne suivante : 
```
127.0.0.1 proxy-onestar3gram
```

Sur Linux, il est nécessaire d'ouvrir le fichier /etc/hosts et d'y ajouter la même ligne à la fin de celui-ci.


### Configuration du Certificat TLS (OPTIONNEL)

Pour ne pas avoir l'avertissement de sécurité du navigateur au lancement de l'application, il est possible d'ajouter le certificat TLS du serveur aux autorités de certification racine de notre ordinateur.

#### Windows

Sur Windows, on peut ouvrir le menu "Gérer les certificats utilisateurs", se rendre dans le menu "Autorités de certification racines de confiance", dans les certificats et à la fin de ceux-ci, faire clic droit dans le vide pour sélectionner la tâche "Importer". Il faut ensuite sélectionner notre fichier traefik/cert.pem puis valider l'ensemble des menus.

#### Linux

Sur Linux, on peut utiliser les commandes suivantes : 
```
sudo cp traefik/cert.pem /usr/local/share/ca-certificates/cert.crt
sudo update-ca-certificates
```