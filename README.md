# Jef Toiture — Démo de refonte (Noval Agency)

Démo de refonte du site vitrine de **Jef Toiture**, couvreur à Paris et en
Île-de-France (basé à Ormesson-sur-Marne, 94), réalisée pour montrer à
l'entreprise ce que sa présence en ligne pourrait devenir.

Site 100 % statique (HTML / CSS / JavaScript), sans framework ni étape de
build : simple à comprendre, à modifier et à déployer.

## 🎯 Objectif de cette démo

Le site actuel (`toiture-jef.com`) est très chargé visuellement : beaucoup
de blocs, d'affiches et d'informations présentées en même temps. Cette
démo propose une version :

- épurée, premium et moderne
- lisible en quelques secondes
- parfaitement responsive (mobile / tablette / desktop)
- orientée conversion (CTA clairs, formulaire de devis, clic-to-call)

## ✅ Informations réelles utilisées

Toutes les informations d'entreprise affichées sont **réelles et
publiques** (site actuel, fiches professionnelles publiques) :

| Élément | Valeur |
|---|---|
| Nom | Jef Toiture |
| Téléphone | 06 33 05 72 16 |
| E-mail | contact@toiture-jef.com |
| Adresse | 38 Rue Henry, 94490 Ormesson-sur-Marne |
| Horaires | Lundi – Samedi, 8h – 20h |
| Zone d'intervention | Paris et Île-de-France (basé dans le Val-de-Marne) |
| Services | Couverture, zinguerie, charpente & bois, étanchéité, nettoyage/démoussage, pose de Velux |
| Garanties | Devis gratuit sous 48h, garantie décennale, équipe d'artisans agréés, +25 ans d'expérience |

⚠️ **Limite technique de cette session** : l'accès direct au site
`toiture-jef.com` était bloqué par le pare-feu réseau de cet environnement
d'exécution. Le contenu ci-dessus a donc été reconstitué à partir des
informations publiques indexées (registres d'entreprises, annuaires
professionnels, extraits de pages indexées par les moteurs de recherche)
plutôt que d'un scraping direct de chaque page. Avant mise en ligne
réelle, il est recommandé de **relire cette démo face au site actuel**
pour confirmer chaque donnée (en particulier les horaires et la liste
exacte des villes desservies) et pour remplacer la section
« Réalisations » — volontairement illustrée par des visuels génériques
par type de prestation — par de vraies photos de chantiers.

Aucun avis client, chiffre ou projet fictif n'a été inventé.

## 📁 Structure du projet

```
Demo-couverture/
├── index.html          → Page unique contenant toutes les sections
├── css/
│   └── style.css       → Tous les styles (couleurs, typographie, responsive, animations)
├── js/
│   └── script.js       → Menu mobile, animations au scroll, formulaire
├── netlify.toml         → Configuration de déploiement Netlify
├── robots.txt / sitemap.xml → SEO de base
└── README.md
```

## ▶️ Lancer le site en local

**Option 1 — le plus simple** : double-cliquez sur `index.html`, il
s'ouvre directement dans votre navigateur.

**Option 2 — avec un serveur local**
```bash
python3 -m http.server 8000
```
Puis ouvrez `http://localhost:8000`.

## 🚀 Déployer sur Netlify

1. Glissez-déposez le dossier complet sur [app.netlify.com](https://app.netlify.com) (« Deploy manually »), ou connectez ce dépôt Git pour un déploiement continu.
2. *Build command* : vide — *Publish directory* : `.` (déjà préconfiguré dans `netlify.toml`).

Le formulaire de contact est une démonstration front-end uniquement (aucune
donnée n'est envoyée) — un message l'indique clairement aux visiteurs.

## 🎨 Personnaliser le design

Les couleurs, polices et espacements sont centralisés en haut de
`css/style.css`, dans la section `:root` :
```css
--color-dark:   #14181f;  /* couleur principale sombre */
--color-accent: #c17a4a;  /* couleur d'accent (terracotta/cuivre) */
```

## ✨ Améliorations apportées par rapport au site actuel

- Structure resserrée en 8 sections claires (héros, services, atouts,
  réalisations, à propos, zone d'intervention, appel à l'action, contact)
  au lieu d'un empilement de blocs et d'affiches.
- Hiérarchie visuelle nette : un message par section, beaucoup d'espace
  blanc, gros titres, peu de texte.
- Navigation sticky avec effet de flou, menu mobile plein écran.
- CTA « Demander un devis » toujours accessible (header, hero, bandeau
  CTA, bouton d'appel flottant).
- Cartes de services modernes et minimalistes plutôt que de longs
  paragraphes.
- Micro-interactions et animations d'apparition subtiles au scroll.
- Design 100 % responsive, testé mobile/tablette/desktop.
- Aucune information inventée : coordonnées, services, garanties et
  zone d'intervention reprennent les données réelles de l'entreprise.
