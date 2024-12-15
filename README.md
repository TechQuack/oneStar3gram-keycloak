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


