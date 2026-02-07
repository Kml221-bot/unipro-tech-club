# UNIPRO TECH CLUB - Site Web

Site web professionnel pour le club UNIPRO TECH avec système d'authentification et de contact.

## Structure du projet

```
site web club inf/
├── accueil.html          # Page d'accueil
├── about.html            # Page à propos
├── portfolio.html        # Page portfolio
├── services.html         # Page services
├── contact.html          # Page contact
├── login.html            # Page connexion admin
├── css/
│   └── style.css        # Styles CSS personnalisés
├── js/
│   └── app.js           # JavaScript frontend
└── backend/
    ├── server.js        # Serveur Express
    ├── package.json     # Dépendances Node.js
    └── env.example      # Exemple de configuration
```

## Installation

### 1. Backend (API)

```powershell
cd backend
npm install
```

### 2. Configuration

Créez un fichier `.env` dans le dossier `backend` à partir de `env.example`:

```
PORT=3000
JWT_SECRET=votre_secret_jwt_tres_securise_changez_moi
ADMIN_USERNAME=admin
ADMIN_PASSWORD=admin
```

### 3. Démarrage du serveur

```powershell
cd backend
npm start
```

Pour le développement avec auto-reload:
```powershell
npm run dev
```

Le serveur démarre sur `http://localhost:3000`

## Utilisation

### Frontend

Ouvrez simplement `accueil.html` dans votre navigateur ou utilisez un serveur local comme Live Server.

### API Endpoints

- **POST** `/api/auth/login` - Connexion admin
  - Body: `{ "username": "admin", "password": "admin" }`
  
- **POST** `/api/auth/logout` - Déconnexion (nécessite token)

- **POST** `/api/contact` - Envoyer un message de contact
  - Body: `{ "name": "...", "email": "...", "message": "..." }`

- **GET** `/api/contact/messages` - Liste des messages (nécessite token admin)

- **GET** `/api/health` - Vérifier l'état de l'API

### Authentification

Les identifiants par défaut sont:
- Username: `admin`
- Password: `admin`

**Important**: Changez ces identifiants en production dans le fichier `.env`

## Technologies utilisées

### Frontend
- HTML5
- Tailwind CSS
- JavaScript vanilla
- Font Awesome

### Backend
- Node.js
- Express.js
- JWT pour l'authentification
- bcrypt pour le hashing de mots de passe
- CORS pour les requêtes cross-origin

## Fonctionnalités

- ✅ Navigation multi-pages
- ✅ Mode sombre/clair
- ✅ Design responsive
- ✅ Authentification admin avec JWT
- ✅ Formulaire de contact avec API backend
- ✅ Système de notifications toast
- ✅ Portfolio filtrable par catégorie
- ✅ Affichage des services
- ✅ Stockage local des données (localStorage)

## Notes de sécurité

1. Changez le `JWT_SECRET` dans le fichier `.env`
2. Changez les identifiants admin par défaut
3. En production, utilisez HTTPS
4. Ajoutez une validation et un rate limiting appropriés
5. Ne commitez jamais le fichier `.env` dans Git

## Développement futur

- Base de données (MongoDB/PostgreSQL)
- Upload d'images
- Panel admin complet
- Newsletter
- Blog
- Analytics
