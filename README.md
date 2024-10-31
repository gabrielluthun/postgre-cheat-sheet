# Cheatsheet PostgreSQL

Dans cette cheatsheet, nous allons couvrir les bases de PostgreSQL, un système de gestion de base de données relationnelle open-source.

## Table des matières :

- [Différences entre MySQL et PostgreSQL](#différences-entre-mysql-et-postgresql)
- [Avantages de PostgreSQL](#avantages-de-postgresql)
- [Installation et Configuration](#installation-et-configuration)
    - [Installation de PostgreSQL](#installation-de-postgresql)
        - [Pour Windows](#pour-windows-)
        - [Pour Linux](#pour-linux-)
        - [Pour macOS](#pour-macos-)
- [Commandes de base](#commandes-de-base)
    - [Démarrer le serveur PostgreSQL](#démarrer-le-serveur-postgresql)
    - [Arrêter le serveur PostgreSQL](#arrêter-le-serveur-postgresql)
    - [Redémarrer le serveur PostgreSQL](#redémarrer-le-serveur-postgresql)
    - [Se connecter à PostgreSQL](#se-connecter-à-postgresql)
    - [Lister les bases de données](#lister-les-bases-de-données)
    - [Se connecter à une base de données](#se-connecter-à-une-base-de-données)
    - [Lister les tables](#lister-les-tables)
    - [Quitter PostgreSQL](#quitter-postgresql)
- [Commandes SQL](#commandes-sql)
    - [Bases de données](#bases-de-données)
        - [Créer une base de données](#créer-une-base-de-données)
        - [Supprimer une base de données](#supprimer-une-base-de-données)
        - [Sélectionner une base de données](#sélectionner-une-base-de-données)
    - [Tables](#tables)
        - [Créer une table](#créer-une-table)
        - [Supprimer une table](#supprimer-une-table)
        - [Afficher les données d'une table](#afficher-les-données-dune-table)
        - [Insérer des données dans une table](#insérer-des-données-dans-une-table)
    - [Utilisateurs](#utilisateurs)
        - [Créer un utilisateur](#créer-un-utilisateur)
        - [Supprimer un utilisateur](#supprimer-un-utilisateur)
    - [Les rôles](#les-rôles)
        - [Créer un rôle](#creer-un-role)
        - [Supprimer un rôle](#supprimer-un-rôle)
        - [Attribuer un rôle à un utilisateur](#attribuer-un-rôle-à-un-utilisateur)
        - [Retirer un rôle à un utilisateur](#retirer-un-rôle-à-un-utilisateur)
## Avantages de PostgreSQL
| Avantage                              | Description                                                                                           |
|---------------------------------------|-------------------------------------------------------------------------------------------------------|
| **Meilleure prise en charge des données volumineuses et complexes** | PostgreSQL est conçu pour gérer des bases de données de grande taille et des requêtes complexes de manière efficace. |
| **Conformité aux standards SQL**      | PostgreSQL est très conforme aux standards SQL, ce qui facilite la portabilité des applications.       |
| **Extensibilité**                     | PostgreSQL permet aux utilisateurs de définir leurs propres types de données, fonctions, opérateurs, et même méthodes d'indexation. |
| **Support des transactions ACID**     | PostgreSQL garantit l'intégrité des données grâce à la prise en charge complète des transactions ACID : |
|                **A**                       | - **Atomicité** : *« ça passe ou ça casse »* : Les transactions sont soit entièrement exécutées, soit entièrement annulées. |
|                 **C**                      | - **Cohérence** : Les transactions doivent laisser la base de données dans un état cohérent.          |
|                **I**                       | - **Isolation** : Les transactions doivent être isolées les unes des autres.                          |
|                **D**                      | - **Durabilité** : Les données sont stockées de manière durable, même en cas de panne du système.     |
| **Sécurité**                          | PostgreSQL offre des fonctionnalités de sécurité avancées, telles que l'authentification basée sur les rôles, le chiffrement SSL, et le contrôle d'accès granulaire. |

---
## Différences entre MySQL et PostgreSQL
| Critère                | **PostgreSQL**                              | **MySQL**                                 |
|------------------------|---------------------------------------------|-------------------------------------------|
| **Performance**        | Très fiable pour les applications complexes | Rapide, idéal pour les sites web          |
| **Types de données**   | Large choix (JSON, géospatiaux, etc.)       | Standard (support JSON basique)           |
| **Personnalisation**   | Très flexible et personnalisable            | Flexible mais moins que PostgreSQL        |
| **Compatibilité SQL**  | Respecte bien les normes SQL (strict)               | Parfois moins strict avec les normes SQL  |
| **Gestion des données**| Excellent pour gérer plusieurs utilisateurs | Suffisant pour des besoins basiques       |
| **Sécurité**           | Contrôle avancé des accès                   | Sécurité standard                         |
| **Utilisation typique**| Applications complexes, finance, analyses   | Sites web, CMS, e-commerce                |

En résumé, les cas d'utilisation courants de PostgreSQL sont les applications **complexes**, les systèmes financiers, et les analyses de données, tandis que MySQL est plus adapté aux supports plus **légers** tels que les sites web, aux CMS, et à l'e-commerce.

--- 
## Installation et Configuration

### Installation de PostgreSQL

#### Pour Windows :
1. Télécharger l'installeur depuis le site officiel de PostgreSQL.
2. Exécuter l'installeur.
3. Suivre les instructions à l'écran.

#### Pour Linux :
1. Ouvrir un terminal.
2. Exécuter la commande suivante :
    ```bash
    sudo apt-get install postgresql
    ```
3. Entrer le mot de passe utilisateur pour confirmer l'installation.

#### Pour macOS :
1. Ouvrir un terminal.
2. Si nécessaire, installer Homebrew (un gestionnaire de paquets pour macOS).
3. Une fois Homebrew installé, exécuter la commande suivante pour installer PostgreSQL :
    ```bash
    brew install postgresql
    ```
4. Suivre les instructions à l'écran.

--- 
### Commandes de base


- **Se connecter à PostgreSQL :**
    ```sh
    psql -U <nom_utilisateur>
    ```
- **Lister les bases de données :**
    ```sql
    \l
    ```
- **Se connecter à une base de données :**
    ```sql
    \c <nom_base_de_données>
    ```
- **Lister les tables :**
    ```sql
    \dt
    ```
- **Quitter PostgreSQL :**
    ```sql
    \q
    ```
---
## Commandes SQL 
### Bases de données

- **Créer une base de données :**
    ```sql
    CREATE DATABASE <nom_base_de_données>;
    ```
- **Supprimer une base de données :**
    ```sql
    DROP DATABASE <nom_base_de_données>;
    ```
- **Sélectionner une base de données :**
    ```sql
    \c <nom_base_de_données>;
    ```
### Tables

- **Créer une table :**
    ```sql
    CREATE TABLE <nom_table> (
        <nom_colonne> <type_donnée>,
        ...
    );
    ```
- **Supprimer une table :**
    ```sql
    DROP TABLE <nom_table>;
    ```
- **Afficher les données d'une table :**
    ```sql
    SELECT * FROM <nom_table>;
    ```
- **Insérer des données dans une table :**
    ```sql
    INSERT INTO <nom_table> (<colonne1>, <colonne2>, ...) VALUES (<valeur1>, <valeur2>, ...);
    ```
### Utilisateurs
*Note : les utilisateurs sont des rôles ayant le privilège de se connecter à la base de données.*

- **Créer un utilisateur :**
    ```sql
    CREATE USER <nom_utilisateur> (WITH PASSWORD
    '<mot_de_passe>');
    ```
- **Supprimer un utilisateur :**
    ```sql
    DROP USER <nom_utilisateur>;
    ```

### Les rôles
*Note : un rôle est un ensemble de privilèges qui peut être attribué à un utilisateur.*

#### Les rôles principaux et leurs droits :
- **LOGIN** : peut se connecter à la base de données.
- **SUPERUSER** : possède **tous** les droits.
- **NOSUPERUSER** : ne peut **pas** être un superutilisateur.
- **CREATEDB** : peut créer des bases de données.
- **CREATEROLE** : peut créer des rôles.
- **REPLICATION** : peut initier la réplication.
- **BYPASSRLS** : peut ignorer les politiques de lignes de sécurité.


#### Commandes liées aux rôles
- **Créer un rôle :**
    ```sql
    CREATE ROLE <nom_rôle>;
    ```
- **Supprimer un rôle :**
    ```sql
    DROP ROLE <nom_rôle>;
    ```
- **Attribuer un rôle à un utilisateur :**
    ```sql
    GRANT <nom_rôle> TO <nom_utilisateur>;
    ```
- **Retirer un rôle à un utilisateur :**
    ```sql
    REVOKE <nom_rôle> FROM <nom_utilisateur>;
    ```
