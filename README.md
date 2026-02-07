# MounjaGO API

API d'authentification Better Auth pour MounjaGO.

## Déploiement

1. Installer les dépendances :
   ```bash
   npm install
   ```

2. Configurer les variables d'environnement :
   ```bash
   cp .env.example .env.local
   # Éditer .env.local avec vos valeurs
   ```

3. Tester en local :
   ```bash
   npm run dev
   ```

4. Déployer sur Vercel :
   ```bash
   npm run deploy
   ```

## Variables d'Environnement

Configurer dans Vercel Dashboard :

- `VITE_SUPABASE_URL` : URL de votre projet Supabase
- `SUPABASE_SERVICE_ROLE_KEY` : Clé service role Supabase
- `BETTER_AUTH_SECRET` : Secret pour Better Auth (générer avec `openssl rand -base64 32`)
- `BETTER_AUTH_URL` : URL de votre API Vercel
- `VITE_APP_URL` : URL de votre frontend Netlify

## Endpoints

- `GET /api/auth/session` : Obtenir la session actuelle
- `POST /api/auth/signup` : Créer un compte
- `POST /api/auth/login` : Se connecter
- `POST /api/auth/logout` : Se déconnecter
