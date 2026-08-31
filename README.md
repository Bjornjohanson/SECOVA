# SECOVA — Site web

Site vitrine statique (HTML / CSS / JS, sans framework ni build) pour SECOVA,
société française de représentation commerciale et de sourcing de packaging
en verre (bouteilles et bocaux).

## Structure

```
index.html              Accueil
bouteilles.html          Bouteilles
bocaux.html               Bocaux
services.html              Nos services
sourcing.html               Sourcing & développement
a-propos.html                À propos
contact.html                  Contact (formulaire)
mentions-legales.html          Mentions légales
confidentialite.html            Politique de confidentialité
assets/css/style.css     Feuille de style unique
assets/js/main.js         Menu mobile, révélation au scroll, formulaire
assets/img/                Visuels (voir ci-dessous)
robots.txt, sitemap.xml   SEO technique
```

Aucune dépendance de build : le site fonctionne tel quel sur n'importe quel
hébergement statique classique (dépôt de fichiers en FTP/SFTP, ou tout
hébergeur mutualisé). Il suffit de pointer le domaine secova.fr vers le
dossier contenant ces fichiers.

## Remplacer les photos

Toutes les images sont actuellement des visuels placeholder (SVG générés,
fond anthracite avec silhouettes de bouteilles/bocaux et une légende
« SECOVA — Emplacement photo »), afin de baliser clairement les emplacements
à remplacer par de vraies photographies :

- `assets/img/placeholder-hero.svg` — bannière large (accueil)
- `assets/img/placeholder-bottles.svg` — bouteilles
- `assets/img/placeholder-jars.svg` — bocaux
- `assets/img/placeholder-industrial.svg` — ligne de production / palettes
- `assets/img/placeholder-texture.svg` — détail matière
- `assets/img/placeholder-team.svg` — équipe / bureau
- `assets/img/placeholder-network.svg` — réseau de partenaires

Pour remplacer une image, déposez votre photo (`.jpg` ou `.webp`
recommandés) dans `assets/img/` et changez le `src` de la balise `<img>`
correspondante dans le HTML — la mise en page (ratio, recadrage `object-fit:
cover`) s'adapte automatiquement.

## Formulaire de contact

Le formulaire de `contact.html` est fonctionnel côté navigateur (validation,
message de confirmation) mais n'est pas encore relié à un service d'envoi.
Pour le rendre opérationnel en production, connectez-le à une solution telle
que Formspree, Netlify Forms, ou un script serveur (PHP, API interne) en
renseignant l'attribut `action` du formulaire dans `contact.html` — voir le
commentaire dans `assets/js/main.js`.

## Mentions légales

`mentions-legales.html` contient des champs `[à compléter]` (SIRET, RCS,
hébergeur, etc.) : à renseigner avec les informations officielles de la
société avant mise en ligne.

## SEO

Chaque page a un `<title>` et une meta description dédiés, un `sitemap.xml`
et un `robots.txt` sont fournis. Pensez à mettre à jour les URLs
`https://secova.fr/...` si le nom de domaine final diffère.
