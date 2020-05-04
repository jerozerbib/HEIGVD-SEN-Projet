# Projet SEN : Spear Phishing

**ATTENTION : Compte tenu des implications éthiques importantes concernant ce travail, veuillez suivre attentivement les règles que nous vous décrivons. Nous ne seront pas tenus responsables si vous vous mettez en mauvaise posture avec vos actions.**

**Le rendu consiste en un rapport à rendre en format PDF. Vous transmettrez le rapport utilisant l'interface du "devoir" correspondant sur le site Cyberlearn du cours.**

**Le travail est à effectuer par groupes de 2.**

## Table de matières

[Introduction](#introduction)

[Recherches et descriptions d'outils](#recherche-et-descriptions-doutils)

[Recherche d'informations sur sa cible](#recherche-dinformations-sur-sa-cible)

[Description d'un scénario d'attaque](#description-dun-sc%c3%a9nario-dattaque)

[Simulation d'attaque](#simulation-dattaque)

[Structure du rapport](#structure-du-rapport)

[Echéance](#ech%c3%a9ance)


## Introduction

L'objectif de ce projet est de vous entraîner à mener une attaque de spear phising de la manière la plus réaliste possible, tout en respectant les normes éthiques requises.

Le projet sera découpé en plusieurs parties :

- une description des outils simplifiant la récupération d'informations sur sa cible
- une description des outils permettant la mise en place d'une attaque de type spear phishing
- une recherche approfondie d'informations publiques sur sa cible
- mise en place d'un scénario d'attaque
- simulation de l'attaque

Chaque étape est décrite dans la suite de ce document. Veuillez lire et suivre correctement ce qui est demandé.

## Recherche et descriptions d'outils

Il vous est demandé de rechercher et décrire au minimum **trois outils**.
Ces outils peuvent avoir deux objectifs différents :

- faciliter la récupération d'informations dans le cadre d'une campagne ou d'une attaque de phishing (par exemple, Maltego)
- faciliter la mise en place et l'attaque de phishing (par exemple, Setoolkit)

**Aucune restriction** sur les outils n'est imposée; système d'exploitation libre, payant ou gratuit (sachant que si vous dépensez de l'argent dans le test d'un outil, ce sera à vos frais).

Il est bien-sûr **interdit** de prendre Setoolkit ou Maltego comme outil pour votre recherche et description.

**Vous devez présenter au minimum un outil de chaque type (récupération d'informations ou mise en place d'attaque). Le troisième sera à choix entre les deux.**

> <span style="color:green; font-weight:bold">
> Livrable dans le rapport : 
> </span>
>
> Chaque outil doit être décrit avec au minimum les points suivants :
>
>- introduction (Système d'exploitation, modèle économique, objectif, description brève)
>- description d'installation
>- description approfondie (actions possibles, cas d'utilisation etc...)
>- démonstrations des possibilités à travers (en autres) des screenshots
>- conclusion (votre avis sur son utilité, intérêt, facilité d'utilisation)
</span>

## Recherche d'informations sur sa cible

Premièrement, il vous faut déterminer votre cible. Cette dernière doit impérativement être humaine et encore vivante. Vous pouvez, par exemple, choisir une personnalité connue, un(e) ami(e), un(e) professeur(e), un(e) patron d'entreprise. Une personne appartenant à une entreprise peut être une cible particulièrement intéressante. Ceci permettrait de simuler un scénario d'attaque à l'entreprise par intermédiaire de la compromission d'une cible humaine. 

Plus la personne vous est proche, plus le travail demandé sera conséquent. Il est conseillé donc d'éviter de choisir une personne de votre entourage proche.

Si vous ne trouvez aucune information qualitative, changez de cible afin que votre travail soit intéressant et ait du sens à être évalué (vous en aurez le temps...). Pour ne pas "gaspiller" vos efforts, toute tentative pas aboutie (donc, jugée pas intéressante par vous même) peut être inclue dans le rapport.

Pour cette phase, vous pouvez vous servir des outils que vous avez présentés dans la partie [Recherches et descriptions d'outils](#outils) **mais aussi** des logiciels que vous avez déjà utilisés dans les laboratoires précédents (Maltego, Setoolkit).

L'objectif de cette tâche est donc de regrouper un maximum d'informations possibles sur cette personne :

- sexe, âge, date de naissance, religion, lieu d'habitation etc...
- métier, hobbies, passions, habitudes, amis, familles, relations etc...
- journée type
- personnalité
- biais d'attaques possibles (email, réseaux sociaux, blogs etc...)
- points forts et points faibles (naïveté, utilisation courante d'outils en ligne etc...)

Certains points demandent une petite analyse psychologique, par exemple : déterminer la personnalité d'un personne à travers des photos, postes Facebook, Instagram ou autres (se met-elle en avant, parle t'elle en "je" ou en "nous" etc...)

**Chaque information compte**. Si la personne porte régulièrement les habits d'une marques, si elle est inscrite sur un site de vente ou commande régulièrement dessus, si vous arrivez à déterminer sa banque etc...

Par exemple, une personne ayant un tatouage sera surement plus sensible à un email parlant d'une offre chez un tatoueur que parlant du dernier modèle de WC fraicheur de chez super-Cuvette.

Suivant le choix de la cible, un nombre plus ou moins grand d'informations sera disponible pour vous. Ne stressez pas à l'idée de ne pas en trouver assez (par exemple la religion). Les points ci-dessus sont des exemples. Trouvez en un maximum et faites vos propres conclusions.

Afin de récupérer ces informations, tous les moyens sont autorisés sauf ceux cités ci-dessous :

> <span style="color:red; font-weight:bold">
> Règles éthiques :
> </span>
>
> Dans le cas où votre cible n'est pas un proche, il est <span style="color:red; font-weight:bold"> INTERDIT </span> de
>
> - communiquer avec la cible d'une quelconque manière
> - obtenir des informations au moyen d'un piratage ou un vol d'informations privées
> - d'usurper l'identité d'une autre personne et se faire passer pour elle
> - d'aller espionner la personne à son domicile ou autre (Covid-19 oblige, tout le monde à la maison)
> - de ne pas respecter les conditions d'utilisations de chaque service en ligne, site web etc...
</span>


> <span style="color:green; font-weight:bold">
> Livrable pour le rapport :
> </span>
>
> Le rapport doit contenir toutes les informations récupérées et jugées un minimum utile.
>
> - premièrement, vous décrirez les raisons qui vous ont poussé à choisir cette cible
> - ensuite, vous décrirez tous les éléments découverts, leurs sources, leurs utilités (en quelques mots)
> - pour finir, vous proposerez un portrait de la cible comportant vos conclusions, points faibles, caractères etc...
>
> Si vous récupérez énormément d'informations sur la cible, triez ces informations pour en garder les plus importantes. N'oubliez pas que ces recherches ont pour but final une attaque de spear phishing.
</span>

## Description d'un scénario d'attaque

Maintenant que vous avez un volume d'information important sur votre cible, il est temps de réfléchir au scénario de l'attaque.

L'objectif de votre attaque :

- récupérer des informations secrètes, privées
- escroquer de l'argent
- installer un spyware dans l'ordinateur de la cible
- faire exécuter une tâche spécifique à la cible (par exemple : création d'accès SSH à une machine)
- etc..

Vous allez aussi devoir réfléchir par quel support l'attaque va être menée :

- attaquer à travers un réseau social (lequel ?, pourquoi ?)
- un phishing par email (quel thème ?)
- des sms
- etc...

Déterminez aussi le payload de votre attaque si vous en avez un :

- Faux site web
- Trojan (pdf ? exe ? etc...)
- etc...

Tout en sachant que vous allez devoir simuler l'attaque.

> <span style="color:green; font-weight:bold">
> Livrable pour le rapport :
> </span>
>
> Vous décrirez les points suivants dans le rapport :
>
> - Objectif de l'attaque :
>   - en quoi cela vous intéresse ? Vous pouvez imaginer votre rôle. (pas de preuves nécessaires pour ce point)
>   - qu'est ce qui vous fait penser que cette cible remplira votre objectif?, pourquoi l'attaque vous vous avez imaginée aura un effet sur votre cible ?
> - Support de l'attaque :
>   - pourquoi avez-vous choisis tel support et pas un autre ?
>   - ce support est-il adapté à la cible ? (par exemple : à elle un compte sur ce réseau social ?, y est-elle souvent connectée ?)
>   - quel thème sera abordé dans votre attaque ?, pourquoi ?
> - Payload de l'attaque :
>   - dans le cas ou vous avez besoin d'un payload pour contenir votre attaque, décrivez la raison qui vous pousse à l'utiliser et en quoi vous pensez que la personne tombera dans le piège.
>
> Pour tous les points ci-dessus, vous devrez fournir des preuves. Vous les obtiendrez à travers votre recherche précédente. Il est possible que certains choix doivent être fait délibérément, sans preuves connues. Dans ce cas explicitez les.
</span>

## Simulation d'attaque

Cette dernière partie consiste en une simulation d'attaque et c'est un exercice d'imagination. Vous exécuterez et commenterez toutes les étapes de votre attaque. 

Vous pouvez utiliser l'outil de votre choix.

Vu que le destinataire de votre attaque ne peut être la cible réelle, vous pouvez prendre l'autre membre du groupe en tant que destinataire. Ce dernier répondra aux communications ou effectuera les actions requises pour l'attaque comme si elle était la cible. On imagine que la personne se fait avoir par l'attaque et exécute les actions demandées par l'adversaire.

Dans le cas où vous utilisez un payload dans votre attaque, par exemple, un virus, veillez à ne pas vous faire vous-même infecter... Franchement il y a assez de gens infectés ces jours.

> <span style="color:red; font-weight:bold">
> Règles éthiques :
> </span>
>
> Il est bien-sûr formellement <span style="color:red; font-weight:bold">INTERDIT</span> de mener réellement votre attaque. Vous simulerez seulement l'attaque.
>
</span>

> <span style="color:green; font-weight:bold">
> Livrable pour le rapport :
> </span>
>
> Votre rapport doit décrire les points suivants :
>
> - descriptions et explications de chaque étape de l'attaque
> - descriptions et actions effectuées par la cible (ouverture d'un trojan, faux site web etc...)
> - descriptions des résultats obtenus dans le cas d'une attaque réussie.
>
> Chaque point sera agrémenté de screenshots lorsque cela fait sens.
</span>


## Structure du rapport

Nous ne proposons pas de structure définie ou d'exemple. Vous avez suffisamment fait de rapports pour être structuré. Les points majeurs sont décrits au long de la donnée, à vous d'y correspondre au mieux.

Vous pouvez vous inspirer sur la structure de base d'un rapport d'audit, et remplir les éléments que vous aurez à disposition suite à vos recherches.

Soyez concis dans vos explications. Nous demandons un rapport technique et structuré, pas une dissertation de 50 pages.


## Echéance

Ce projet devra être rendu en PDF utilisant le "devoir" sur la page Cyberlearn du cours au plus tard **le 11 juin 2020, à 23h59.**