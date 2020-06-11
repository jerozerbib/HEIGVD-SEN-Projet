# Auteurs : Lionel Burgbacher, Eric Noel, Jeremy Zerbib

# PROJET SEN : Spear Phishing

## Wayback Machine

## Table des matières 

1. [ Introduction ](#intro)
2. [ Utilisation ](#utili)
3. [ Descritption ](#desc)
4. [ Exemple d'utilisations ](#demo)
5. [ Conclusion ](#conc)
6. [ Sources ](#sources)

<a name="intro"></a>
## 1. Introduction

La Wayback Machine est une archive d'internet maintenu par l'organisation à but non lucratif, The Internet Archive.
L'idée d'origine est qu'il existait déjà de nombreuses archives pour les autres médias comme les journaux, les livres, la télévision 
mais aux débuts d'internet personne n'archivait ce nouveau média The Internet Archive a donc prit l'initiative de le faire.
Elle à commencer à archiver internet en 1996 et à aujourd'hui atteint près de 330 miliards de pages web archivées.
A l'origine elle avait pour objectif d'archiver l'ensemble d'internet mais aujourd'hui avec l'ampleur qu'a prit internt ce n'est plus possible.
A noter qu'en plus des pages web l'archive contient aussi :

- 20 millions de livres et textes
- 4,5 millions d'enregistrements audio
- 4 millions de vidéos
- 3 millions d'images
- 200 milles programmes


<a name="utili"></a>
## 2. Utilisation

Le moyen le plus simple d'utilisation est via la page web archive.org.
Puisque c'est une page web ça permet à n'importe quel système ayant accès à internet peut l'utiliser, un smartphone est donc déjà suffisant pour y accèder.
La Wayback Machine a aussi été intégrée dans d'autre outil, je citerai notamment Metasploit que nous avons vu dans notre cour pour lequel il existe un module Wayback Machine.
La page archive.org :

![archive_org](assets/archive_org.png)

<a name="desc"></a>
## 3. Descritption

Lorsqu'on arrive sur archive.org on est directement sur la partie web et donc sur la Wayback Machine.
Si on l'on veut une recherche sur un média en particulier on peut aller sous l'onglet en question (ex. Book, Video, etc), mais pour notre part on va se concentrer sur la Wayback Machine.
Tout d'abord il faut donner un url, cela peut-être n'importe quoi, un compte twitter, le site d'une entreprise ou une image.
En suite il y a deux possibilitées :

- la Wayback Machine va nous afficher un calendrier des snapshots qu'elle a prises de cette page
- la Wayback Machine va nous indiquer que cette page n'est pas archivée.

En effet comme abordé dans l'introduction il n'est aujourd'hui plus possible d'archiver tout internet, la Wayback Machine utilise donc des systèmes pour essayer de détérminer l'importance de chaque page internet.
Cette importance va déterminer si une page doit être archivée ou non et à quelle fréquance, car certaines pages ne sont archivées qu'une fois par année et d'autres des dizaines de fois par jour.
A noter que si une page n'est pas encore archivée on peut faire une demande pour qu'elle le soit.

Si notre page est bien archivée nous pouvons voir plusieurs choses :

- Sur la barre du haut on peut séléctionner l'année qui nous intéresse.
- Sur la patie calendrier il y a un ou plusieur cerlce, les bleus sont des snapshots les verts sont des erreurs de redirection 3xx.
- La taille des cercles est propotionnel aux nombre de snapshot prises ce jour là.
- On voit chaque snapshot avec l'heure à laquelle elle à été prise en cliquant ou en mettant le curseur sur la date voulu.

Une fois que l'on a trouvé le moment qui nous intéresse il suffis de cliquer sur l'heure de la snapshot voulu et la page que nous avons demandé est affichée telle qu'elle était ce jour ci.

<a name="demo"></a>
## 4. Exemple d'utilisations

Vous l'aurez sans doute déjà compris mais la Wayback Machine n'est pas un outil très puissant pour faire de massives recherches, c'est un outil plutôt ciblé.
Par consequent c'est un outil qu'on va le plus souvent utiliser avec d'autres outils, par exemple pour étendre le champ de recherche.

Voici un exemple de petit sénario dans lequel la Wayback Machine peut être utilisée :

Imaginons que l'on cherche à s'introduire dans une entreprise, on fait d'abord une recherche sur les informations disponible publiquement sur le site officiel de cette entreprise.
On trouvent plusieurs adresses emails alors on chercher des informations intéressantes lier à ces emails mais l'entreprise à bien fait son travail et on ne trouve rien d'utile.
C'est là que la Wayback Machine entre en jeu, on peut se demander si les adresses emails disponible sur le site de l'entreprise on toujours été les mêmes ou si par le passer d'autres emails étaient afficher.
On fait donc quelques recherche sur la Wayback Machine, dans cette exemple imaginons que l'on trouve de nouvelles adresses emails.
Ces adresses étaient sur le site par le passer mais plus aujourd'hui néanmoins on peut se demander si ces adresses sont toujours utilisées dans l'entreprise.
On fait alors de nouvelles recherches d'informations lier à ces nouvelles adresses et pourions potentiellement trouve des choses utile pour une attaque.

Ce genre de situation pourrait arriver par exemple quand une entreprise met à jour sa sécurité et se concentrer sur ses récents systèmes et donnés et néglige ses anciens.

<a name="conc"></a>
## 5. Conclusion

En resumé la Wayback Machine est un outil un peu situationnel mais peut être un très bon outil en soutien d'autres outils.
C'est un outil qui est plus efficace quand on a déjà une idée de ce que l'on chercher.
Elle aide dans la collecte d'information et permet parfois d'étendre la surface d'attque.

Petite parenthèse la Wayback Machine est un outil "menacé", en effet plusieurs groupes de personnes et entreprises voient d'un mauvaise oeil une archive qui donne gratuitement accès à beaucoup d'informations et contenu.
Evidemment ces entreprises préfèreraient faire une quantité ridicule d'argent avec ces données.
Ils attaque donc régulièrement archive.org en justice et recemment ces attaques se sont fait de plus en plus violente. 

<a name="sources"></a>
## 6. Sources

https://archive.org