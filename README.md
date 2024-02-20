Mise en place du site web pour Garage V.Parrot en local
Suivez ces instructions pour installer et exécuter le site web sur votre machine locale.

Prérequis
Installer Composer, disponible à l'adresse suivante : https://getcomposer.org/.
Instructions
Installation des sources

Téléchargez les dossiers Documentation et GarageSource sur votre machine.
Configuration du serveur local

Lancez un serveur local avec gestion de base de données (par exemple, XAMPP avec MariaDB 10.4.28).
Déploiement du code source

Placez le dossier GarageSourceCode dans le répertoire htdocs de votre serveur local.
Initialisation de la base de données

Ouvrez le fichier Documentation/Base de données/DBinit.sql.
Remplacez !NOM! par le nom souhaité pour votre base de données.
Exécutez le script SQL dans votre SGBD pour créer la base de données.
Configuration des utilisateurs

Allez dans GarageSourceCode/src/DataFixtures/UserFixtures.php.
Changez les valeurs !!!MDP!!! par les mots de passe désirés pour les différents types d'utilisateurs.
Paramétrage de l'environnement

Éditez le fichier GarageSourceCode/.env.
Configurez les valeurs pour DATABASE_URL, APP_SECRET et MAILER_DSN (utilisez Mailtrap pour les tests).
Installation des dépendances et mise en place de la base de données

Ouvrez un terminal, allez dans le dossier GarageSourceCode.
Exécutez les commandes suivantes :
bash
Copy code
composer install
php bin/console doctrine:migrations:migrate
php bin/console doctrine:fixtures:load
Cela configurera les tables et les données initiales dans votre base de données.
Accès au site

Visitez http://localhost/GarageSourceCode/public_html pour accéder au site en local.
Comptes par défaut
Administrateur
Email : admin@main.com
Mot de passe : (Le mot de passe que vous avez défini à l'étape 5)
Notes supplémentaires
Pour l'envoi d'e-mails lors de la création de nouveaux comptes, utilisez Mailtrap pour simuler un serveur SMTP.
L'espace personnel administrateur vous permet d'ajouter, modifier ou supprimer des comptes et des avis.
Les demandes de contact contiennent un champ "Sujet" indiquant l'origine de la demande pour une gestion facilitée.
N'oubliez pas de sauvegarder vos modifications. Pour toute question technique ou besoin d'assistance supplémentaire, n'hésitez pas à consulter la documentation ou à demander de l'aide auprès d'une communauté de développeurs.

David Nkpome
