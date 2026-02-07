# 🚀 Déploiement sur Vercel

## Prérequis

- Compte Vercel : https://vercel.com
- Projet Supabase avec service role key
- Variables d'environnement configurées

## Étapes de Déploiement

### 1. Installer Vercel CLI

```bash
npm install -g vercel
```

### 2. Login

```bash
vercel login
```

### 3. Déployer

```bash
vercel --prod
```

### 4. Configurer les Variables d'Environnement

Aller sur https://vercel.com/dashboard → Votre projet → Settings → Environment Variables

Ajouter :

```
VITE_SUPABASE_URL=https://mglznogvuxwuhhlzicwu.supabase.co
SUPABASE_SERVICE_ROLE_KEY=<votre_service_role_key>
BETTER_AUTH_SECRET=<générer avec: openssl rand -base64 32>
BETTER_AUTH_URL=<votre_url_vercel>
VITE_APP_URL=<url_netlify_frontend>
```

### 5. Redéployer

```bash
vercel --prod
```

## Test

```bash
curl https://votre-api.vercel.app/api/auth/session
```

Devrait retourner : `{"session":null}` ou les détails de la session.

## Liens Utiles

- Dashboard Vercel : https://vercel.com/dashboard
- Logs : `vercel logs <project-name> --follow`
- Documentation Better Auth : https://better-auth.com

## Structure

```
.
├── api/
│   └── auth.js          # Handler Better Auth
├── package.json         # Dépendances
├── vercel.json          # Config Vercel
├── .env.example         # Exemple de variables
└── README.md            # Documentation
```
