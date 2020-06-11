<# Auteurs : Lionel Burgbacher, Eric Noel, Jeremy Zerbib

# PROJET SEN : Spear Phishing

## King Phisher

## Table des matières 

1. [ Introduction ](#intro)
2. [ Installation ](#instal)
3. [ Descritption approfondie](#desc)
4. [ Démonstrations des possibilités ](#demo)
5. [ Conclusion ](#conc)

a name="intro"></a>
## 1. Introduction

`King Phisher` est un *toolkit* de logiciels open source de campagne de phishing.
Il permet de tester et promouvoir le la sensibilité au *phishing* à l'utilisateur en simulant des attaques réelles.
Son architecture flexible et simple d'utilisation permet de garder le contrôle complet sur les emails envoyés et le contenu des serveurs.
Il existe aussi une multitude de *plugins* et de modèles d'attaques, qui seront détaillés plus tard.  
Il est possible à travers les outils de `King Phisher` de collecter les *credentials* d'un utilisateur, d'envoyer des mails avec des images integrées et des *trackers*.  
La suite est codée en `Python` et utilise les serveurs Web integrés dans le standard, ce qui rend inutile la configuration d'une instance séparée.  
De par sa nature open source, cette solution logicielle est très maléable et ne présente que très peu de limites quant à la taille des campagnes que l'on peut lancer.
Il est possible de modifier le code source aux besoins de l'utilisateur grace à l'utilisation de `Python`.  
En revanche, il n'existe pas d'interface Web, ce qui rend l'identification des serveurs plus complexes pour les cibles.
De plus, cela rend l'exploitation de certaines failles Web impossible, comme le `XSS`.

<a name="instal"></a>
## 2. Installation

Le *serveur* `King Phisher` n'est disponible que sur Linux.
En revanche, le *client* l'est sur Linux et Windows.

### Linux

#### Spécification minimale

- CPU : 2 coeurs, 1.5GHz
- RAM : 2048 MB
- Storage : Pas de mesure mais suffisament pour installer les modules
- Pour le client, un écran de résolution minimale 1024x800

#### OS à préférer

- Server : [Ubuntu Server LTS](https://ubuntu.com/download/server)
- Client : [Ubuntu GNOME](https://ubuntugnome.org/download/)

#### Compabilité des différentes OS 

| Linux OS  | Min Version | Client Support  | Server Support |
| ----------|:-----------:| :--------------:| :------------: |
| `BackBox` | 5           | yes             | yes            |
| `CentOS`  | 7.0         | **no**          | yes            |
| `Debian`  | 8           | yes             | yes            |
| `Fedora`  | 24          | yes             | yes            |
| `Kali`    | rolling     | yes             | yes            |
| `Red Hat` | 7.0         | **no**          | yes            |
| `Ubuntu`  | 16.04       | yes             | yes            |

#### Installation

##### Simple

Cette installation marche pour les distributions ci-dessus.

```bash
wget -q https://github.com/securestate/king-phisher/raw/master/tools/install.sh && \
sudo bash ./install.sh
```

##### Manuelle

Il est recommandé de mettre la suite `King Phisher` dans un dossier autonome comme `/opt/king-phisher`.

Il faut donc faire les étapes suivantes : 

```bash
cd /opt/ # or your desired installation directory
git clone https://github.com/securestate/king-phisher.git
cd king-phisher
sudo tools/install.sh
```

Il est aussi possible de rajouter quelques options à l'installation qui sont : 

- `-h, --help` : Affiche le message d'aide et quitte
- `-n --no` : Répond non à toutes les questions
- `-y, --yes` : Répond oui à toutes les questions
- `--skip-client` : Saute l'installation des composants client
- `--skip-server` : Saute l'installation des composants serveur

### Windows

Il est possible de télécharger une version [ici](https://github.com/rsmusllp/king-phisher/releases)

#### Windows 10 Subsystem For Linux (WSL)

Il est recommandé de faire ces étapes pour une amélioration des performances et plus de fonctionnalités.

- Autoriser [`WSL`](https://docs.microsoft.com/en-us/windows/wsl/install-win10)
    - Lors de la sélection de la distribution Linux, choisissez Kali ou Ubuntu 18.04
- Télécharger et installer un Serveur X Window System. Les deux suivants sont les plus populaires :
    - [`Xming`](https://sourceforge.net/projects/xming/)
    - [`VcXsrv`](https://sourceforge.net/projects/vcxsrv/)
- Depuis `Powershell`, lancer un terminal `bash`
- Lancer : `echo "export DISPLAY=127.0.0.1:0.0" >> ~/.bashrc`
- Installer `King Phisher` depuis le tuto ci-dessus
- Changer de dossier et lancer le client : 
    - `cd /opt/king-phisher`
    - `./KingPhisher`

<a name="desc"></a>
## 3. Descritption approfondie

Après l'installation, il faut lancer le serveur avant le client afin qu'il puisse se connecter.
Ce dernier se connecte via `SSH` au serveur poru la communication.
Ce service doit être installé indépendamment, configuré et démarré avant de lancer `King Phisher`.
Lors de l'établissement de la connexion, des credentials seront demandés au client. 
Ces credentials sont les mêmes que ceux utilisés par le serveur pour se connecter en utilisant `SSH`.

### Authentification d'un utilisateur 

L'application `King Phisher` utilise le service d'authentification `PAM` (Pluggable authentication modules).
Les utilisateurs souhaitant s'authentifier vers le serveur doivent avoir un compte système valide avec un mot de passe non-vide.
Le client utilise les credentials fournis pour ouvrir une connection `SSH` vers le serveur, avec une redirection de port pour les requêtes `RPC` (remote procedure call -> équivalent à un VNC).
Chaque requête RPC est authentifiée, utilisant les mêmes credentials.
Le serveur a la possiblité de restreindre l'accès à certains utilisateurs en utilisant les configurations de `authentication.group`.
Par défaut, tout utilisateur valide est autorisé à se connecter, à condition qu'il puisse se connecter via `SSH` et rediriger un port `TCP` vers `localhost`.  
Grace au *ssh-agent*, le client `King Phisher` va se connecter automatiquement en utilisant les clés `SSH` disponibles sur le système.
Sur *Kali Linux*, le *ssh-agent* ne tourne pas de base et doit être démarré manuellement ou grace à un système de management de clés comme `Seahorse`. 
Le *ssh-agent* doit évidemment tourner et avoir une clé configurée pour que l'étape énoncée marche.  
**Seules les clés DSA et RSA dans le style OpennSSh sont supportées**.
Si plusieurs clés sont présentes dans le système, il est possible d'en sélectionner une dans le fichier de configuration `~./config/king_phisher/config.json` avec l'attribut `ssh_prefered_key`.
Le fait d'utiliser une clé `SSH` n'exclue pas l'utilisation d'un mot de passe, qu'il faut aussi spécifier.

### Base de données

Le serveur doit être configuré avec une base de données qui est utilisée pour stocker les campagnes d'information.
A partir de la version `0.1.6`, *postgresql* est recommandé en backend.

#### Configuration de la base de données

Normalement, le script d'installation crée un utilisateur qui est le seul à avoir accès à la base de données.
Si ce n'est pas le cas, il faut suivre les étapes suivantes :
- Trouver le fichier `pg_hba.conf` et rajouter la ligne suivante 
    - `host     king_phisher    king_phisher   127.0.0.1/32            md5`
- Dans le terminal, créer un utilisateur :
    - `createuser king_phisher -P`
    - Enter password for new role: yournewpassword
    - Enter it again: yournewpassword
- Et finalement, assigner un nouveau propriétaire de la base de données :
    - `createdb --owner=king_phisher king_phisher`  
Suite à cela, le service peut être redémarré et le fichier de configuration du serveur aura besoin d'être mis à jour avec la chaine de caractères de connexion à la base de données.
La syntaxe est la suivante : `postgresql://username:password@localhost/database_name`

#### Sauvegarde de la base de données

Il est possible de faire un backup complet de la base de données avec la commande :
`su postgres -l -c "pg_dump -Fc king_phisher | gzip > king-phisher-database.pgsql.gz"`

### Serveur SMTP
Afin que `King Phisher` puisse envoyer des mails, il est nécessaire de configurer un serveur `SMTP`.
Il peut s'agir d'un relai ouvert où le client peut se connecter ou alors d'un autre serveur afin de pouvoir transférer des messages, action qui requiert normalement une authentification.
Sur la page des [serveurs SMTP publics](https://github.com/rsmusllp/king-phisher/wiki/Public-SMTP-Servers), il est possible de trouver toutes les configurations les plus communes pour un serveur public.
Si un serveur requiert une authentification, le champ `Username` doit être spécifié dans `Edit > Preferences`.
Lors de la phase d'envois, l'utilisateur va devoir rentrer son mot de passe.  

Il est recommandé d'utiliser un serveur SMTP privé pour ce genre de taches.
Le client `King Phisher` peut être configuré avec une redirection de ports *SSH* afin de s'y connecter.  

Le serveur SMTP sur lequel se connecte le client `King Phisher` peut être différent du serveur `King Phisher`.
Les deux systèmes et les connections sont gérées de manière indépendante l'un de l'autre.

### Connection à un serveur SMTP par SSH
Si le client permet l'option `Tunnel Over SSH` dans la fenêtre de configuration, alors le serveur SMTP spécifié  sera une addresse IP ou le nom d'hote auquel il voudra se connecter depuis le serveur *SSH*.  
Par exemple, si un relai ouvert SMTP existe à l'addresse `smtp.king-phisher-lan`, qui écoute simplement sur l'interface locale, alors le serveur SSH sera attribué à `smtp.king-phisher.lan:22` et le serveur SMTP sera `localhost:25`.

### Modèles de pages
Des modèles de messages et de pages de serveurs sont disponibles [ici](https://github.com/rsmusllp/king-phisher-templates).
Il est possible d'envoyer des modèles via une *PR* sur le repository directement.

<a name="demo"></a>
## 4. Démonstrations des possibilités

<a name="conc"></a>
## 5. Conclusion

