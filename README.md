# 🌙 Halal Invest - Landing Page

Landing page professionnelle pour distribuer le Guide Complet de l'Investissement Halal 2025.

## 📋 Table des matières

1. [Installation et Setup](#installation-et-setup)
2. [Configuration Mailchimp](#configuration-mailchimp)
3. [Configuration Google Drive](#configuration-google-drive)
4. [Déploiement sur GitHub Pages](#déploiement-sur-github-pages)
5. [Personnalisation](#personnalisation)

---

## 🚀 Installation et Setup

### Fichiers du projet

```
halal-invest-landing/
├── index.html          # Page principale
├── styles.css          # Styles CSS
├── script.js           # JavaScript
├── logo.png            # Logo Halal Invest (à ajouter)
└── README.md           # Ce fichier
```

### Étape 1 : Ajouter le logo

1. Renomme ton logo en `logo.png`
2. Place-le dans le même dossier que `index.html`
3. Le logo doit être en format PNG avec fond transparent (idéalement)

---

## 📧 Configuration Mailchimp

### Créer un compte Mailchimp (gratuit jusqu'à 500 contacts)

1. Va sur [mailchimp.com](https://mailchimp.com)
2. Crée un compte gratuit
3. Vérifie ton email

### Créer une audience (liste)

1. Dans Mailchimp, va dans **Audience** → **Audience dashboard**
2. Clique sur **Create Audience**
3. Remplis les informations :
   - **Audience name** : "Abonnés Guide Halal Invest"
   - **Default From email** : ton email
   - **Default From name** : "Halal Invest"

### Créer un formulaire d'inscription

1. Va dans **Audience** → **Signup forms**
2. Sélectionne **Embedded forms**
3. Personnalise le formulaire (optionnel)
4. Copie le code du formulaire

### Intégrer le code dans ta landing page

**Méthode 1 : Code complet Mailchimp (recommandé)**

1. Dans le code que Mailchimp te donne, trouve la ligne qui commence par :
   ```html
   <form action="https://XXXXX.us21.list-manage.com/subscribe/post?u=XXXXX&amp;id=XXXXX"
   ```

2. Dans `index.html`, trouve cette ligne (autour de la ligne 153) :
   ```html
   <form class="email-form" id="mc-embedded-subscribe-form" name="mc-embedded-subscribe-form" method="post" action="#" target="_blank">
   ```

3. Remplace `action="#"` par l'URL complète de Mailchimp :
   ```html
   <form class="email-form" id="mc-embedded-subscribe-form" name="mc-embedded-subscribe-form" method="post" action="https://XXXXX.us21.list-manage.com/subscribe/post?u=XXXXX&amp;id=XXXXX" target="_blank">
   ```

**Méthode 2 : Utiliser le code complet de Mailchimp**

Tu peux aussi remplacer toute la section du formulaire (lignes 152-167 dans `index.html`) par le code HTML que Mailchimp te fournit, en gardant les classes CSS existantes.

### Configurer l'email de confirmation automatique

1. Dans Mailchimp, va dans **Audience** → **Signup forms** → **Form builder**
2. Clique sur **Settings** → **Confirmation email**
3. Personnalise l'email avec un lien vers ton PDF Google Drive

Ou configure une automatisation :
1. Va dans **Automations** → **Create** → **Welcome new subscribers**
2. Ajoute un email avec le lien de téléchargement du guide

---

## 📁 Configuration Google Drive

### Héberger le PDF sur Google Drive

1. Upload ton PDF "Guide Complet de l'Investissement Halal 2025" sur Google Drive
2. Clique droit sur le fichier → **Get link** / **Obtenir le lien**
3. Change les permissions à : **Anyone with the link can view** / **Tous ceux qui disposent du lien peuvent consulter**
4. Copie le lien

### Convertir le lien en lien de téléchargement direct

Le lien Google Drive ressemble à ça :
```
https://drive.google.com/file/d/1ABC123XYZ456/view?usp=sharing
```

Pour un téléchargement direct, modifie-le ainsi :
```
https://drive.google.com/uc?export=download&id=1ABC123XYZ456
```

### Intégrer le lien dans la landing page

Dans `index.html`, trouve cette ligne (autour de la ligne 170) :
```html
<a href="VOTRE_LIEN_GOOGLE_DRIVE" class="btn-secondary" target="_blank" rel="noopener">
```

Remplace `VOTRE_LIEN_GOOGLE_DRIVE` par ton lien modifié :
```html
<a href="https://drive.google.com/uc?export=download&id=1ABC123XYZ456" class="btn-secondary" target="_blank" rel="noopener">
```

---

## 🌐 Déploiement sur GitHub Pages (Hébergement gratuit)

### Créer un repository GitHub

1. Va sur [github.com](https://github.com) et connecte-toi
2. Clique sur **New repository** (bouton vert en haut à droite)
3. Nomme-le : `halal-invest-landing`
4. Laisse-le **Public**
5. Ne coche rien d'autre
6. Clique sur **Create repository**

### Upload les fichiers

**Option A : Via l'interface web (plus simple)**

1. Sur la page de ton nouveau repository, clique sur **uploading an existing file**
2. Glisse-dépose tous tes fichiers :
   - `index.html`
   - `styles.css`
   - `script.js`
   - `logo.png`
   - `README.md`
3. Clique sur **Commit changes**

**Option B : Via Git (si tu connais)**

```bash
git init
git add .
git commit -m "Initial commit - Halal Invest landing page"
git branch -M main
git remote add origin https://github.com/TON-USERNAME/halal-invest-landing.git
git push -u origin main
```

### Activer GitHub Pages

1. Dans ton repository, va dans **Settings**
2. Dans le menu de gauche, clique sur **Pages**
3. Sous **Source**, sélectionne **main** (branch) et **/ (root)**
4. Clique sur **Save**
5. Attends 1-2 minutes

Ton site sera accessible à :
```
https://TON-USERNAME.github.io/halal-invest-landing/
```

---

## 🎨 Personnalisation

### Changer les couleurs

Dans `styles.css`, modifie les variables CSS (lignes 9-16) :

```css
:root {
    --primary-green: #1a5f3f;    /* Vert principal */
    --primary-gold: #b8975a;      /* Or principal */
    --dark-green: #0f3d28;        /* Vert foncé */
    --light-green: #e8f5e9;       /* Vert clair (backgrounds) */
    /* ... */
}
```

### Modifier les textes

Tous les textes sont dans `index.html`. Cherche les sections :
- Hero (ligne ~45) : Titre et sous-titre principal
- Benefits (ligne ~84) : Les 6 bénéfices du guide
- About (ligne ~199) : Section "À propos"

### Ajouter un lien YouTube

Quand ta chaîne sera créée, dans `index.html` ligne ~191 :
```html
<a href="https://www.youtube.com/@TON-NOM-CHAINE" class="btn-youtube" target="_blank" rel="noopener">
```

### Personnaliser le mockup du guide

Si tu veux un vrai aperçu du guide au lieu du mockup actuel :
1. Crée une image de couverture de ton PDF (600x800px)
2. Nomme-la `guide-cover.jpg`
3. Dans `index.html`, remplace le contenu de `<div class="mockup-inner">` par :
   ```html
   <img src="guide-cover.jpg" alt="Couverture du guide" style="width: 100%; border-radius: 8px;">
   ```

---

## 📊 Statistiques et Analytics

### Ajouter Google Analytics

1. Crée un compte sur [analytics.google.com](https://analytics.google.com)
2. Crée une propriété pour ton site
3. Copie ton "Measurement ID" (format : G-XXXXXXXXXX)
4. Ajoute ce code dans `index.html` juste avant `</head>` :

```html
<!-- Google Analytics -->
<script async src="https://www.googletagmanager.com/gtag/js?id=G-XXXXXXXXXX"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());
  gtag('config', 'G-XXXXXXXXXX');
</script>
```

---

## 🐛 Résolution de problèmes

### Le formulaire ne fonctionne pas

- Vérifie que l'URL Mailchimp est bien configurée dans `index.html`
- Vérifie que l'URL commence par `https://` et non `http://`
- Teste l'inscription avec un email de test

### Le logo ne s'affiche pas

- Vérifie que `logo.png` est bien dans le même dossier que `index.html`
- Vérifie l'orthographe exacte du nom de fichier (sensible à la casse)
- Le fichier doit être en `.png` ou `.jpg`

### Le site ne s'affiche pas sur GitHub Pages

- Attends 2-5 minutes après activation de GitHub Pages
- Vérifie que le fichier s'appelle exactement `index.html` (pas `Index.html`)
- Force le refresh : Ctrl + Shift + R (Windows) ou Cmd + Shift + R (Mac)

### Le lien Google Drive ne télécharge pas

- Vérifie que tu as bien modifié le lien selon les instructions
- Vérifie que le fichier est bien en mode "Anyone with the link can view"
- Teste le lien dans une fenêtre de navigation privée

---

## 📱 Responsive Design

La page est **entièrement responsive** et s'adapte automatiquement à :
- 📱 Mobile (< 480px)
- 📱 Tablette (480px - 768px)
- 💻 Desktop (> 768px)

Teste ton site sur différents appareils !

---

## ✅ Checklist avant lancement

- [ ] Logo ajouté (`logo.png`)
- [ ] URL Mailchimp configurée dans le formulaire
- [ ] Lien Google Drive du PDF configuré
- [ ] Lien YouTube ajouté (quand disponible)
- [ ] Testé le formulaire d'inscription
- [ ] Testé le téléchargement du PDF
- [ ] Vérifié sur mobile
- [ ] Google Analytics ajouté (optionnel)
- [ ] Site déployé sur GitHub Pages

---

## 🎯 Prochaines étapes

1. **Promouvoir la page** :
   - Partage le lien sur tes réseaux sociaux
   - Crée des posts LinkedIn/Facebook/Instagram
   - Ajoute le lien dans ta bio Instagram/Twitter

2. **Lancer la chaîne YouTube** :
   - Enregistre 3-5 vidéos avant de publier
   - Mentionne le guide gratuit dans chaque vidéo
   - Ajoute le lien dans la description

3. **Construire ton audience** :
   - Envoie des emails réguliers à ta liste Mailchimp
   - Crée du contenu de valeur
   - Engage avec ta communauté

---

## 💡 Conseils SEO

Pour améliorer ton référencement Google :

1. **Ajoute un fichier `sitemap.xml`**
2. **Optimise les meta descriptions**
3. **Crée du contenu de blog** (articles sur l'investissement halal)
4. **Partage sur les forums/communautés** musulmanes francophones

---

## 🤝 Support

Si tu as des questions ou rencontres des problèmes, vérifie :
1. Ce README en détail
2. La documentation Mailchimp : [mailchimp.com/help](https://mailchimp.com/help)
3. La documentation GitHub Pages : [pages.github.com](https://pages.github.com)

---

## 📄 Licence

Ce projet est libre d'utilisation pour ton projet Halal Invest.

---

**Fait avec 💚 pour Halal Invest**

Bonne chance avec ton projet ! 🚀🌙
