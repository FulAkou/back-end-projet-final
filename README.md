# 🧠 FoodShare - API Backend (MERN)

> Projet Back-End pour l'application **FoodShare**, conçu avec **Express.js** et **MongoDB**.  
> Ce backend permet la gestion des utilisateurs, des offres alimentaires et des réservations.

------------------------------------------------------------------

## 🚀 Présentation

FoodSaver est une application MERN (MongoDB, Express, React, Node.js) destinée à :

- Lutter contre le gaspillage alimentaire
- Connecter des commerces et des utilisateurs pour partager des invendus encore consommables
- Gérer les réservations et les échanges de produits

------------------------------------------------------------------




## ⚙️ Installation

### 🔧 Prérequis

- Node.js (v16 ou supérieur)
- MongoDB (local ou cloud - ex : MongoDB Atlas)
- npm

### 🛠 Étapes


bash
git clone https://github.com/FulAkou/back-end-projet-final.git
cd back-end-projet-final
npm install

Crée un fichier .env :
PORT=5000
MONGO_URI=<votre_url_mongodb>
JWT_SECRET=<votre_clé_secrète>


Lance le serveur :
npm start
🔌 API REST – Points d’accès
🏠 Route racine
Méthode	URL	Description
GET	/	Vérifie que l’API tourne

🔐 Authentification (/api/auth)
Méthode	URL	Description
POST	/login	Connexion utilisateur
POST	/register	Inscription utilisateur

📦 Offres (/api/offers)
Méthode	URL	Description
GET	/api/offers	Liste toutes les offres
POST	/api/offers	Ajouter une offre
PUT	/api/offers/:id	Modifier une offre
DELETE	/api/offers/:id	Supprimer une offre

📅 Réservations (/api/reservations)
Méthode	URL	Description
GET	/api/reservations	Liste des réservations
POST	/api/reservations	Créer une réservation
PUT	/api/reservations/:id	Modifier une réservation
DELETE	/api/reservations/:id	Annuler une réservation

🧪 Tests
Lancer les tests (si disponibles) :
npm test

🔒 Sécurité
Authentification via JWT

Middleware cors et express.json() pour sécuriser les requêtes

Protéger les routes privées avec des middlewares (authMiddleware, etc.)

📘 À propos
Ce projet constitue la base back-end d’un système complet de réduction du gaspillage alimentaire via mise en relation entre commerçants et consommateurs.

✅ À faire (suggestions)
Ajouter des rôles (admin, commerce, client)

Valider les entrées avec express-validator

Ajout d’un dashboard admin (statistiques, logs)

Déploiement sur Render / Vercel (avec frontend React)

📎 Liens utiles
MongoDB Atlas
Express.js Docs

🧑‍💻 Auteur
FulAkou
GitHub : @FulAkou
