# Live Vintage : site de vente des guides TikTok Shop

Site statique (HTML/CSS, aucun build) qui vend la série de guides PDF « Live Vintage » et attire du trafic Google avec 6 articles SEO. Il est hébergé sur Vercel, avec le domaine livevintage.fr acheté chez OVH. Les paiements passent par Payhip.

## Propriétaire
Tristan Morand (Rouen), micro-entrepreneur. Marque vêtements : Chez Gisèle – Atelier Vintage (TikTok @chezgisele.vintage). Compte GitHub : Varkeno.

## Structure
- `index.html` : page de vente (hero, couvertures, stats réelles, 4 tomes, pack, FAQ, JSON-LD Product + FAQPage)
- `guides/index.html` + 6 articles dans `guides/*.html` (JSON-LD Article + FAQPage + BreadcrumbList)
- `mentions-legales.html` : CONTIENT DES PLACEHOLDERS `[…]` À REMPLIR
- `style.css`, `favicon.svg`, `404.html`, `img/` (couvertures + og.jpg 1200x630)
- `robots.txt`, `sitemap.xml`, `vercel.json` (cleanUrls: true, trailingSlash: false)

## Valeurs de référence (ne pas modifier sans demande)
- Domaine canonique : https://www.livevintage.fr (le domaine nu redirige vers www)
- Liens Payhip :
  - Pack 24 € : https://payhip.com/b/MhjBk
  - Tome 1 gratuit : https://payhip.com/b/sXu0C
  - Tome 2, 9 € : https://payhip.com/b/YW3R8
  - Tome 3, 9 € : https://payhip.com/b/GbsDQ
  - Tome 4, 9 € : https://payhip.com/b/q4vVu

## Règles
- Pas de framework ni d'étape de build : on édite le HTML directement.
- Toute modification d'une URL ou d'un prix doit être reportée partout (grep) : canonical, og:url, JSON-LD, sitemap.
- Le guide est indépendant et NON affilié à TikTok : garder cette mention dans le footer.
- Chiffres réels uniquement (oct. 2026) : 6 lives en 4 jours, ≈180 pièces, 53,96 € de port perdus, 1 infraction annulée par recours. N'invente aucun chiffre ni témoignage.
- Ne jamais committer de token, de mot de passe ni de donnée bancaire.
- Pour ajouter un article : copier la structure d'un fichier de `guides/`, mettre à jour `guides/index.html`, les liens « Les autres guides », la section « Guides gratuits » de `index.html` et `sitemap.xml`.
