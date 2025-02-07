# LOCAPIC Backend

## Backend pour l'application LOCAPIC, fournissant des services basés sur la localisation et la gestion des utilisateurs.

### Prérequis
Avant de commencer, assurez-vous d'avoir installé :
- **Node.js** (version 14 ou supérieure)
- **npm** (généralement inclus avec Node.js)
- **MongoDB**

### Installation

#### Clonez le dépôt :
```bash
git clone https://github.com/tybouddha/LOCAPIC_BACKEND.git
cd LOCAPIC_BACKEND
```

#### Installez les dépendances :
```bash
npm install
```

#### Créez un fichier `.env` à la racine du projet et ajoutez vos variables d'environnement :
```env
PORT=3000
MONGODB_URI=mongodb://localhost:27017/locapic
JWT_SECRET=your_jwt_secret_key
```

### Configuration
Assurez-vous de configurer la connexion à MongoDB dans le fichier `.env`. Si vous utilisez un service cloud comme MongoDB Atlas, utilisez l'URI de connexion approprié.

### Exécution du serveur

#### Mode Développement
```bash
npm run dev
```

#### Mode Production
```bash
npm start
```
Le serveur démarrera sur le port spécifié dans votre fichier `.env` (par défaut : 3000).

### Points d'entrée de l'API

#### **Authentification**
- `POST /signup` - Inscription d'un nouvel utilisateur
- `POST /signin` - Connexion utilisateur

#### **Lieux**
- `GET /places` - Récupérer tous les lieux
- `POST /places` - Créer un nouveau lieu
- `PUT /places/:id` - Mettre à jour un lieu
- `DELETE /places/:id` - Supprimer un lieu

### Structure du projet
```
LOCAPIC_BACKEND/
├── config/
│   └── database.js
├── models/
│   ├── Place.js
│   └── User.js
├── routes/
│   ├── places.js
│   └── users.js
├── middlewares/
│   └── auth.js
├── .env
├── .gitignore
├── package.json
└── server.js
```

### Gestion des erreurs
L'API utilise les codes HTTP standards :
- `200` : Succès
- `400` : Mauvaise requête
- `401` : Non autorisé
- `404` : Non trouvé
- `500` : Erreur interne du serveur

### Sécurité
- **Authentification JWT** pour les routes protégées
- **Hachage des mots de passe** avec bcrypt
- **Variables d'environnement** pour les données sensibles

### Déploiement

#### **Déploiement sur Heroku**

1. Créez un compte Heroku et installez l'outil CLI Heroku.
2. Connectez-vous à Heroku :
   ```bash
   heroku login
   ```
3. Créez une nouvelle application Heroku :
   ```bash
   heroku create your-app-name
   ```
4. Configurez MongoDB en ajoutant un add-on ou en définissant la variable d'environnement :
   ```bash
   heroku config:set MONGODB_URI=your_mongodb_uri
   heroku config:set JWT_SECRET=your_jwt_secret
   ```
5. Déployez votre application :
   ```bash
   git push heroku main
   ```

#### **Déploiement sur d'autres plateformes**
L'application peut être déployée sur n'importe quelle plateforme supportant les applications Node.js. Assurez-vous de :
- Définir les variables d'environnement
- Configurer la connexion à MongoDB
- Installer les dépendances
- Exécuter l'application avec `npm start`

### Contribution
1. Forkez le dépôt
2. Créez une branche pour votre fonctionnalité :
   ```bash
   git checkout -b feature/AmazingFeature
   ```
3. Commitez vos modifications :
   ```bash
   git commit -m 'Ajout de AmazingFeature'
   ```
4. Poussez la branche :
   ```bash
   git push origin feature/AmazingFeature
   ```
5. Ouvrez une Pull Request

### Support
Pour toute question ou assistance, veuillez ouvrir une issue sur le dépôt GitHub.


