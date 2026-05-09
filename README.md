# SWIP — Guide de mise en ligne

## Structure du projet

```
swip/
├── api/
│   └── generate.js       ← Fonction serverless (proxy API sécurisé)
├── public/
│   ├── index.html        ← Le site
│   └── manifest.json     ← PWA manifest
├── vercel.json           ← Config Vercel
└── README.md
```

---

## Mise en ligne étape par étape

### 1. Créer le dépôt GitHub

1. Va sur https://github.com/new
2. Nom du dépôt : `swip`
3. Laisse tout par défaut → clique **Create repository**
4. Sur la page suivante, clique **uploading an existing file**
5. Glisse-dépose TOUS les fichiers du dossier `swip/` (en respectant la structure)
6. Clique **Commit changes**

### 2. Déployer sur Vercel

1. Va sur https://vercel.com/dashboard
2. Clique **Add New → Project**
3. Sélectionne ton dépôt `swip`
4. Clique **Deploy** (pas besoin de changer les paramètres)

### 3. Ajouter ta clé API Anthropic (OBLIGATOIRE)

Sans cette étape, le site ne fonctionne pas.

1. Dans Vercel, va dans ton projet → **Settings → Environment Variables**
2. Clique **Add New**
3. Name : `ANTHROPIC_API_KEY`
4. Value : ta clé API (commence par `sk-ant-...`)
5. Clique **Save**
6. Va dans **Deployments** → clique **Redeploy** sur le dernier déploiement

### 4. Ton site est en ligne !

URL automatique : `swip.vercel.app` (ou similaire)

---

## Récupérer ta clé API Anthropic

1. Va sur https://console.anthropic.com
2. Clique **API Keys** dans le menu
3. Clique **Create Key**
4. Copie la clé — elle ne s'affiche qu'une fois

---

## Brancher un domaine custom (swip.news)

1. Achète le domaine sur OVH, Namecheap ou Cloudflare
2. Dans Vercel → **Settings → Domains**
3. Tape ton domaine → Vercel te donne les DNS à configurer
4. Chez ton registrar, mets à jour les DNS → propagation 24-48h

---

## Coût mensuel estimé

| Service | Coût |
|---------|------|
| Vercel (hébergement) | Gratuit |
| GitHub | Gratuit |
| Anthropic API | ~0,01€ par génération |
| Domaine .news | ~30€/an |

**Total : quasi gratuit pour commencer.**
