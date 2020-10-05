# exercices-sql1

-   Partie 1 -
-   Connexion en tant que 'db_user'
    psql -d postgres -U db_user

-   Création de la base de donnée 'db_1' -
    postgres=> CREATE DATABASE db_1;

-   Connexion à la base de données 'db_1' -
    postgres=> \c db_1

-   Mise en forme de la Table -
    db_1=> CREATE TABLE users (id SERIAL PRIMARY KEY, name VARCHAR(30), password VARCHAR(30));

-   Ajout des utilisateurs -
    db_1=> INSERT INTO users (name, password) VALUES ('alice', '123'), ('bob', '456'), ('charlie', '789');

-   Contrôle des modifications de la Table 'users' -
    db_1=> SELECT \* FROM users;

-   Partie 2 -
-   Ajout de nouveaux utilisateurs -
    db_1=> INSERT INTO users (name, password) VALUES ('dan', '101112'), ('eve', '131415'), ('faythe', '161718');

-   Contrôle des modifications de la Table 'users' -
    db_1=> SELECT \* FROM users;

-   Partie 3 -
-   Filtrer les lignes dont les mdp utilisateurs font plus de 3 caratères -
    db_1=> SELECT \* FROM users WHERE length(password)>3;

-   Partie 4 -
-   Ajout d'une colonne avec texte par défaut -
    db_1=> ALTER TABLE users ADD COLUMN bio text DEFAULT 'Hello, world!';

-   Contrôle des modifications de la Table 'users' -
    db_1=> SELECT \* FROM users;

-   Partie 5 -
-   Ajout d'un texte de bienvenue dynamique -
    db_1=> UPDATE users SET bio = 'Hello, i am ' ||(name);

-   Contrôle des modifications de la Table 'users' -
    db_1=> SELECT \* FROM users;

-   Partie 6 -
-   Filtrer 2 résultats dont les id sont les plus grands -
    db_1=> SELECT \* FROM users ORDER by id desc limit 2;

-   Partie 7 -
-   Filtrer les utilisateurs dont les id sont impairs -
    db_1=> SELECT \* FROM users WHERE id%2=1;

-   Partie 8 -
-   Supprimer les utilisateurs dont les id sont pairs -
    db_1=> DELETE FROM users WHERE id%2=0;

-   Contrôle des modifications de la Table 'users' -
    db_1=> SELECT \* FROM users;

-   Partie 9 -
-   Supprimer la Table users -
    db_1=> DROP TABLE users;

-   Sortir de la base de données db_1 -
    db_1=> \c postgres;

-   Supprimer la base de données db_1 -
    postgres=> DROP DATABASE db_1;

-   Vérifier la suppression de la base de données -
    postgres=> \list
