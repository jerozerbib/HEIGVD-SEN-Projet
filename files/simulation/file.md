# Auteurs : Lionel Burgbacher, Eric Noel, Jeremy Zerbib

# PROJET SEN : Spear Phishing

## Simulation d'attaque

### Descriptions et explications de chaque étape de l'attaque

#### Cloning du mail

Lors de cette étape, nous avons cloné un mail sur une base connue.
En effet, nous avons créé un compte fictif et simulé le comportement suivant :
- Tentative de login depuis une source inconnue
- Réception d'un mail nous signalant la tentative
- Copier-coller le contenu du mail en `HTML` et ajustement des champs de manière à faire croire que le mail est vraiment destiné à notre cible.
Le résultat est celui-ci :  
![](./assets/mail.png)

#### Cloning du site afin de se logger
En utilisant `SEToolkit`, il est possible de répliquer la page d'accueil de LinkedIn.
En suivant les étapes `Website Attack Vector -> Credential Harvester Method -> Site Cloner`, le site est repliqué sur l'adresse locale ou globale de notre choix.
Le résultat nous donne ceci :  
![](./assets/site.png)

