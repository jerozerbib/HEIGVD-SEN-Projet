# Auteurs : Lionel Burgbacher, Eric Noel, Jeremy Zerbib

# PROJET SEN : Spear Phishing

## King Phisher

## Table des matières 

1. [ Introduction ](#intro)
2. [ Installation ](#instal)
3. [ Descritption approfondie](#desc)
4. [ Démonstrations des possibilités ](#demo)
5. [ Conclusion ](#conc)

<a name="intro"></a>
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

<a name="demo"></a>
## 4. Démonstrations des possibilités

<a name="conc"></a>
## 5. Conclusion


[Cheat Markdown](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet)

[Tools markdown](https://github.com/adam-p/markdown-here/wiki/Other-Markdown-Tools)
