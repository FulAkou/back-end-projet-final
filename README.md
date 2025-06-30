# FoodSaver Backend

## Description

FoodShare Backend est l'API RESTful du projet FoodSaver, une application visant à réduire le gaspillage alimentaire en facilitant le partage d'offres alimentaires entre utilisateurs. Ce backend gère l'authentification, la gestion des offres et des réservations, ainsi que la sécurité des échanges.

## Fonctionnalités principales

- Authentification JWT (inscription, connexion, profil)
- Création, consultation, modification et suppression d'offres alimentaires
- Réservation d'offres, gestion des réservations
- Sécurité des routes via middleware

## Technologies utilisées

- Node.js
- Express.js
- MongoDB & Mongoose
- JWT (jsonwebtoken)
- bcryptjs
- multer (gestion des fichiers)
- dotenv

## Installation

1. **Cloner le dépôt**
   ```bash
   git clone <url-du-repo>
   cd backend
   ```
2. **Installer les dépendances**
   ```bash
   npm install
   ```
3. **Configurer les variables d'environnement**
   - Créez un fichier `.env` à la racine avec :
     ```env
     MONGO_URI=<votre_url_mongodb>
     JWT_SECRET=<votre_clé_secrète>
     ```

## Lancement du serveur

- En mode développement (avec hot reload) :
  ```bash
  npm run dev
  ```
- En mode production :
  ```bash
  npm start
  ```

Le serveur démarre par défaut sur le port 5000 (modifiable via la variable d'environnement `PORT`).

## Structure du projet

```
backend/
  config/           # Configuration (base de données)
  controllers/      # Logique métier (auth, offres, réservations)
  middleware/       # Middlewares (authentification)
  models/           # Modèles Mongoose (User, Offer, Reservation)
  routes/           # Définition des routes API
  server.js         # Point d'entrée principal
```

## Modèles de données

### Utilisateur (`User`)

- nom: String (requis)
- email: String (requis, unique)
- password: String (requis, hashé)

### Offre (`Offer`)

- titre: String (requis)
- description: String (requis)
- image: String (requis)
- dateExpiration: Date (requis)
- localisation: String (requis)
- statut: String ("disponible" ou "reserve")
- userId: Référence à l'utilisateur créateur
- reservedBy: Référence à l'utilisateur réservant

### Réservation (`Reservation`)

- userId: Référence à l'utilisateur
- offerId: Référence à l'offre
- nom: String (requis)
- lieuLivraison: String (requis)
- message: String (optionnel)
- dateReservation: Date
- statut: String ("en_cours", "complete", "annule")

## Principales routes API

### Authentification

- `POST /api/auth/register` : Inscription
- `POST /api/auth/login` : Connexion
- `GET /api/auth/profile` : Profil utilisateur (protégé)

### Offres

- `GET /api/offers` : Liste des offres
- `POST /api/offers` : Créer une offre (protégé)
- `GET /api/offers/me` : Mes offres (protégé)
- `GET /api/offers/:id` : Détail d'une offre
- `PUT /api/offers/:id` : Modifier une offre (protégé)
- `DELETE /api/offers/:id` : Supprimer une offre (protégé)

### Réservations

- `POST /api/reservations` : Créer une réservation (protégé)
- `GET /api/reservations/me` : Mes réservations (protégé)
- `DELETE /api/reservations/:id` : Annuler une réservation (protégé)

## Sécurité

- Authentification par JWT sur toutes les routes protégées
- Validation des entrées via express-validator
- Hash des mots de passe avec bcryptjs

## Auteur / Contact

Pour toute question ou suggestion, contactez : [Votre Nom] - [votre.email@exemple.com]
