# Toiture Prestige 33 — Site vitrine (démo)

Landing page premium pour une entreprise de couverture, traitement de toiture et de façade, basée à Ambarès-et-Lagrave (Gironde).

Site 100 % statique (HTML / CSS / JavaScript), sans framework ni étape de build : simple à comprendre, à modifier et à déployer.

## 📁 Structure du projet

```
toiture-prestige-33/
├── index.html          → Page unique contenant toutes les sections
├── css/
│   └── style.css       → Tous les styles (couleurs, typographie, responsive, animations)
├── js/
│   └── script.js       → Menu mobile, animations au scroll, formulaire
├── images/              → (dossier prêt à recevoir vos futures photos)
├── netlify.toml         → Configuration de déploiement Netlify
├── robots.txt / sitemap.xml → SEO de base
└── README.md
```

## ▶️ Lancer le site en local

Aucune installation n'est nécessaire. Deux façons simples de prévisualiser le site :

**Option 1 — le plus simple**
Double-cliquez sur le fichier `index.html` : il s'ouvre directement dans votre navigateur.

**Option 2 — avec un serveur local (recommandé pour tester le formulaire)**
Si vous avez Python installé :
```bash
cd toiture-prestige-33
python3 -m http.server 8000
```
Puis ouvrez `http://localhost:8000` dans votre navigateur.

## 🚀 Déployer sur Netlify

**Méthode la plus simple (glisser-déposer) :**
1. Rendez-vous sur [app.netlify.com](https://app.netlify.com) et créez un compte gratuit.
2. Sur la page d'accueil, glissez-déposez le dossier `toiture-prestige-33` complet dans la zone « Deploy manually ».
3. Netlify publie le site en quelques secondes et vous fournit une adresse en `.netlify.app`.
4. Dans **Site settings → Domain management**, vous pouvez ensuite associer votre propre nom de domaine (ex. `toiture-prestige33.fr`).

**Méthode recommandée pour la mise à jour continue (via Git) :**
1. Créez un dépôt (GitHub, GitLab...) et poussez-y le contenu de ce dossier.
2. Sur Netlify, cliquez sur « Add new site → Import an existing project » et connectez votre dépôt.
3. Laissez le champ *build command* vide et indiquez `.` comme *publish directory* (déjà préconfiguré dans `netlify.toml`).
4. Chaque futur envoi (`git push`) republiera automatiquement le site.

Le formulaire de devis utilise **Netlify Forms** : aucune configuration serveur n'est nécessaire, les demandes reçues via le formulaire apparaîtront automatiquement dans l'onglet **Forms** de votre tableau de bord Netlify (avec option d'être notifié par e-mail).

## ✏️ Informations fictives à remplacer avant mise en ligne réelle

Ce site est une **démonstration commerciale**. Toutes les informations suivantes sont fictives et doivent être remplacées par les vraies coordonnées de l'entreprise avant toute mise en ligne réelle :

| Élément | Valeur actuelle (fictive) | À faire |
|---|---|---|
| Nom de l'entreprise | Toiture Prestige 33 | Remplacer partout (logo, titre, footer, JSON-LD) |
| Adresse | 12 Rue des Artisans, 33440 Ambarès-et-Lagrave | Adresse réelle |
| Téléphone | 05 56 00 00 00 | Numéro réel (mis à jour dans le header, hero, footer, boutons d'appel) |
| WhatsApp | +33 6 12 34 56 78 (`wa.me/33612345678`) | Numéro WhatsApp réel |
| E-mail | contact@toiture-prestige33.fr | E-mail réel |
| Nom de domaine | toiture-prestige33.fr | Domaine réel une fois acheté |
| SIRET | 123 456 789 00012 | Numéro SIRET réel |
| Assurance décennale | « à compléter » | Numéro/assureur réels (obligatoire légalement en France pour ce type d'activité) |
| Avis clients | Noms et avis d'exemple (Sophie D., Marc L., Amandine B.) | Vrais avis de clients, avec leur accord |
| Chiffres clés (« 15 ans d'expérience », etc.) | Exemples | Chiffres réels de l'entreprise |
| Photos de réalisations | Illustrations vectorielles de remplacement | Vraies photos de chantiers (dossier `images/`) |
| Réseaux sociaux (footer) | Liens `#` | Vrais liens Facebook / Instagram / LinkedIn |
| Mentions légales / confidentialité | Liens `#` (pages à créer) | Rédiger ces pages obligatoires |
| Carte (zone d'intervention) | Ambarès-et-Lagrave (OpenStreetMap) | Peut être conservée ou remplacée par Google Maps |

💡 **Astuce** : la plupart de ces éléments sont regroupés en haut du fichier `index.html` (balises `<meta>`, script JSON-LD) et se répètent ensuite dans le header, le hero, la section devis et le footer — un remplacement global (rechercher/remplacer) suffit pour la majorité.

## 🎨 Personnaliser le design

Les couleurs, polices et espacements sont centralisés en haut du fichier `css/style.css`, dans la section `:root` :
```css
--color-dark:   #1a2332;  /* couleur principale sombre */
--color-accent: #d97742;  /* couleur d'accent (orange terracotta) */
```
Modifier ces valeurs suffit à changer l'identité visuelle de tout le site.

## ✅ Fonctionnalités incluses

- Design premium, responsive (mobile / tablette / desktop)
- Menu mobile animé
- Boutons d'appel et bouton WhatsApp flottant
- Formulaire de demande de devis prêt pour Netlify Forms (avec anti-spam honeypot)
- Animations légères au défilement
- Métadonnées SEO de base + données structurées (schema.org) + `robots.txt` / `sitemap.xml`
- Favicon vectoriel intégré (aucun fichier image externe requis)
- Accessibilité de base (lien d'évitement, attributs ARIA, contrastes, focus visible)
- Aucune dépendance externe lourde : chargement rapide
