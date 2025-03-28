## Configuration du Stockage

- **Type de RAID** : RAID 6
- **Répertoire principal** : `/mnt/raid_stockage_raid6/`

## Autres Pools

- **Description** : Une autre pool est configurée avec un disque dur dédié pour le stockage des applications qui seront hébergées avec Docker.

## Partage Samba

- **Description** : Un partage Samba est configuré pour permettre l'accès aux fichiers sur le réseau, facilitant ainsi le partage de données entre différents systèmes d'exploitation.

## Utilisateurs Configurés

### 1. Utilisateurs Standards

- **Noms d'utilisateur** :
    
    - Swan
    - Datev
    - Sana
- **Méthode d'authentification** : Mot de passe
    
- **Restrictions** :
    
    - Accès au shell désactivé (uniquement SFTP).
    - Accès limité au répertoire : `/mnt/raid_stockage_raid6/`
- **Structure des permissions dans `/mnt/raid_stockage_raid6/`** :
    
    ```
    public
    sana
    swan
    datev
    ```
    
    - **datev, sana, swan** : Répertoires personnels avec droits exclusifs (propriétaire uniquement, `rwx------`).
    - **public** : Répertoire partagé, avec droits en lecture/écriture pour le groupe `villagoies`, aucun accès pour les autres.

### 2. Utilisateur Administrateur

- **Nom d'utilisateur** : truenas_admin
- **Méthode d'authentification** : Paire de clés SSH
- **Accès** : Complet (non restreint)

## Modification du Port SSH

- **Port par défaut** : Modifié de 22 à 6366
