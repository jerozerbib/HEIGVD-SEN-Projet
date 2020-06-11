# Auteurs : Lionel Burgbacher, Eric Noel, Jeremy Zerbib

# PROJET SEN : Spear Phishing

## Scénario d'attaque
 
### Objectifs

L'objectif principal de cette attaque sera de récupérer le mot de passe du compte LinkedIn de la cible.
Avoir cette information ne nous sert pas beaucoup à titre personnel mais dessert à la cible.
En effet, étant une figure mondiale de la cyber sécurité et ayant écrit des livres sur l'ingénierie sociale, ce genre d'attaques lui causerait énormément de tort.
Il serait imaginable que, si cette information venait à être publiée, notre cible perdrait énormément au niveau de sa réputation et pourrait perdre beaucoup de prestige vis à vis de ces employeurs.  
En revanche, nous pensons que la cible ne remplira pas son rôle car elle connait, à priori, ces techniques de phishing.

### Support de l'attaque
Ayant trouvé l'adresse mail connectée au compte LinkedIn de notre cible, nous pouvons imaginer faire une attaque de type phishing et de le faire se connecter sur un site répliqué.
Il faut commencer par poser les bases de l'attaques : 
- Il trouver le template type de mail envoyé par LinkedIn
- Générer à partir de ce template, un mail demandant de se connecter et de changer le mot de passe
    - Envoi depuis un serveur "clonant" le nom de Linkedin
    - Possibilité de faire en sorte que LinkedIn envoie le mail mais dans les headers, il sera possible de voir la source initiale
- Il est possible de récupérer les champs écrits par notre cible
    - Il faut faire un clone de la page d'accueil de LinkedIn avec `SEToolkit` par exemple
    - Quand on clique sur le lien "Log In", la cible est redirigée vers son compte LinkedIn comme si de rien n'était
    - Dans le cas où le mot de passe est un mot ou une phrase, il est possible qu'il soit utilisé autre part ...

A priori, ce type d'attaque est réaliste pour cette cible car elle est connectée de manière relativement récurrente sur LinkedIn.
### Payload de l'attaque

La modification du template du mail fera partie du payload de l'attaque.
Il faut faire en sorte de garder le phrasé et les couleur initiales.
Seul le lien demandant de se connecter sera différent et redirigera vers une page "piratée".  
Il faut aussi faire en sorte de cloner la page et intercepter les credentials.
`SEToolkit` permet de faire cette tache de manière relativement simple.



