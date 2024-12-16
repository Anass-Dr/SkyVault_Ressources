# Cahier des Charges : Plateforme de Cloud Storage

## Contexte

Créer une plateforme de stockage cloud similaire à Google Drive permettant aux utilisateurs d’uploader, gérer, et partager leurs fichiers en toute sécurité, en utilisant AWS S3 pour le stockage des fichiers.

## Objectifs du Projet

- Permettre aux utilisateurs d'uploader, télécharger, supprimer et organiser leurs fichiers.
- Intégrer des fonctionnalités de partage (liens publics ou avec des autorisations).
- Fournir une interface utilisateur intuitive et réactive.

## Fonctionnalités Principales

### Côté Utilisateur

1. Gestion des fichiers :

    - Upload, téléchargement, suppression.
    - Organisation en dossiers.
    - Aperçu des fichiers compatibles (PDF, images, vidéos, etc.).
    - Recherche et tri des fichiers.

2. Partage des fichiers :

    - Génération de liens de partage publics/privés.
    - Attribution d'autorisations (lecture seule, lecture/écriture).

3. Compte utilisateur :

    - Inscription, connexion (email + mot de passe, social login).
    - Gestion du profil (nom, email, mot de passe).
    - Suivi de l’espace utilisé.

4. Notifications :

    - Confirmation d’upload.
    - Notifications sur les fichiers partagés.

### Côté Admin

1. Gestion des utilisateurs :

    - Liste des utilisateurs inscrits.
    - Capacité à désactiver un compte.

2. Monitoring :

    - Suivi des fichiers stockés.
    - Statistiques sur l’utilisation du stockage global.

## Architecture Technique

### Front-end

- `Framework` : React.js.
- `Gestion d'état` : Redux Toolkit.
- `Styling` : TailwindCSS.
- `Fonctionnalités principales` :
    - Pages principales : Authentification, tableau de bord, gestion des fichiers.
    - Intégration d'une barre de recherche, prévisualisation des fichiers.

### Back-end

- `Framework` : NestJS.
- `Base de données` : MongoDB (pour la gestion des utilisateurs et des métadonnées des fichiers).
- `Gestion des fichiers` : AWS S3 pour le stockage, AWS SDK pour l’interaction.
- `Sécurité` :
    - JWT pour l’authentification.
    - Middleware pour la gestion des erreurs.
    - Chiffrement des données sensibles.
- `APIs principales` :
    - CRUD pour les fichiers et dossiers.
    - APIs de partage de fichiers.
    - APIs de gestion d'utilisateur.

## Stockage et Infrastructure

- `Stockage des fichiers` : AWS S3.
- `Déploiement` :
    - Back-end : AWS EC2.
    - Front-end : AWS S3 avec CloudFront pour la distribution.
    - Base de données : MongoDB Atlas.

## Sécurité

1. Chiffrement des fichiers côté client (facultatif).
2. Sécurisation des URLs générées (signées pour les fichiers privés).
3. Contrôle des autorisations basé sur les rôles (utilisateur, admin).

## Livrables

1. Une application web fonctionnelle (front-end + back-end).
2. Documentation technique.
3. Images Docker pour le déploiement.
4. Tests unitaires et fonctionnels validés.
