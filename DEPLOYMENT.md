# 🚀 Déploiement sur Render

## Prérequis
- Compte Render (gratuit)
- Repository Git (GitHub, GitLab, ou Bitbucket)

## Étapes de déploiement

### 1. Préparer le repository
```bash
git init
git add .
git commit -m "Initial commit"
git remote add origin <votre-repo-url>
git push -u origin main
```

### 2. Déployer sur Render

1. **Connectez-vous à [render.com](https://render.com)**
2. **Cliquez sur "New +" puis "Web Service"**
3. **Connectez votre repository Git**
4. **Configuration automatique :**
   - **Build Command** : `pip install -r requirements.txt`
   - **Start Command** : `gunicorn main:app`
   - **Python Version** : `3.11.9`

### 3. Variables d'environnement (optionnel)
Dans les paramètres de votre service sur Render, ajoutez :
- `FLASK_ENV` = `production`
- `SECRET_KEY` = (généré automatiquement par Render)

### 4. Déploiement automatique
- Render détectera automatiquement les changements dans votre repository
- Chaque push déclenchera un nouveau déploiement
- Les logs sont disponibles dans le dashboard Render

## 🔧 Configuration technique

### Fichiers créés pour le déploiement :
- `requirements.txt` - Dépendances Python
- `render.yaml` - Configuration Render
- Code modifié pour supporter les variables d'environnement

### Port et configuration :
- Render utilise automatiquement le port via la variable `PORT`
- Mode debug désactivé en production
- Secret key sécurisé via variable d'environnement

## 📱 Accès à l'application
Une fois déployé, votre application sera accessible via l'URL fournie par Render :
`https://votre-app-name.onrender.com`

## 🔐 Comptes de test
- **Admin** : `admin@ttrust.com` / `AdminSecure2024!`
- **Support** : `support@ttrust.com` / `SupportSecure2024!`
- **Test** : `a@gmail.com` / `aaaaaa`

## ⚠️ Notes importantes
- Le plan gratuit de Render met l'application en veille après 15 minutes d'inactivité
- Pour un usage en production, considérez un plan payant
- La base de données SQLite sera réinitialisée à chaque redémarrage (plan gratuit)
