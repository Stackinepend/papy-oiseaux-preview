# Papy Oiseaux -- Maquette Ulule

## Objectif

Reproduire une page de campagne Ulule 2026 pixel-perfect, standalone, avec le contenu fictif de Papy Oiseaux. Maquette de travail interne pour pitcher le projet avant de lancer la vraie campagne.

## Stack

- **Un seul fichier** : `index.html` (~1200 lignes, CSS + JS inline)
- HTML / CSS / JS vanilla, zéro dépendance
- Google Fonts : Nunito (UI) + Lora (citations/titres émotionnels)
- Responsive mobile-first

## Référence visuelle

Clone fidèle de l'interface Ulule 2026 (DOM rendu de `chevaliers-notabene`). On reproduit la structure, les composants, les espacements et les couleurs Ulule -- pas le contenu Nota Bene.

## Palette

| Usage | Couleur |
|-------|---------|
| Accent principal (vert Ulule) | `#1dba95` |
| Accent secondaire (orange) | `#ff6b35` |
| Fond page | `#f7f8fa` |
| Fond header | `#232221` |
| Texte principal | `#232221` |
| Texte secondaire | `#6b6b6b` |
| Bordures / séparateurs | `#e3ddd3` |
| Background hero Papy Oiseaux | `#1a1208` (bois sombre) |

## Structure de la page

### 1. Header sticky (60px)

- Logo texte "ulule" en minuscules, police sans-serif bold, couleur `#232221`
- Logo hibou SVG inline (repris du source Ulule)
- Nav : Lancer une collecte | Formation | Communauté
- Bouton "Se connecter" avec icône personne
- Barre de recherche (placeholder, non fonctionnelle)
- Fond blanc, border-bottom `#e3ddd3`

### 2. Hero section

**Background** : couleur `#2d5016` (vert nature) avec overlay dégradé sombre.

**Colonne gauche (60%)** :
- Titre H1 : "Papy Oiseaux -- Le kit nichoir avec le dessin de ton enfant gravé dedans"
- Sous-titre : "Un papy, sa petite-fille, et un kit nichoir en bois personnalisable avec gravure laser du dessin de votre enfant. Fabriqué en France."
- Placeholder vidéo (div fond bois `#1a1208`, emoji 🐦, bouton play SVG)
- Tags pillules : Écologie / Famille / Artisanat / France
- Bloc créateur : avatar emoji 👴, nom "Papy Oiseaux", localisation "France", catégorie "Enfants & famille"

**Colonne droite (sidebar sticky, 380px)** :
- Icône oeuf Ulule (SVG vert `#1dba95`)
- Montant collecté : **9 240 €** (compteur animé 0 → 9240 en 1.2s)
- Objectif : sur 15 000 €
- Barre de progression : 62%, animation CSS 0 → 62% (dégradé vert)
- "Financé à 62%"
- Stats : 187 contributions | 14 jours restants
- Bouton CTA "Contribuer" -- fond `#1dba95`, hover darken, pleine largeur
- "Paiement sécurisé et sans engagement"
- Boutons Partager / Suivre (outline)

### 3. Menu sticky secondaire

Barre d'onglets sous le hero, sticky au scroll :
- Collecte (actif) | Contreparties | FAQ | Actualités (badge "2") | Contributions (badge "187") | Commentaires

### 4. Contenu principal (2 colonnes)

**Colonne gauche (contenu)** :

#### Section "À propos de cette collecte"

**"Le jour où tout a commencé"**
- Encart citation fond bois (#1a1208, border-left `#1dba95`) :
  > "Mon papy adore les oiseaux. Ma petite-fille voulait faire quelque chose de ses mains. On a passé toute une journée à construire ensemble une niche pour les oiseaux du jardin. Elle était belle, mais surtout -- elle était à nous."
- Placeholder image : 👴👧 "Photo -- Le papy et sa petite-fille dans l'atelier"

**"Le produit"**
- Liste avec emoji icônes :
  - 🏠 Kit nichoir bois contreplaqué peuplier -- planches prédécoupées, assemblage sans outil
  - ✏️ Planche avant gravée au laser avec le vrai dessin de l'enfant
  - 🏔️ Toiture interchangeable par aimants
  - 📌 Pins oiseaux à collectionner
  - 🎨 Autocollants pour décorer
- Grille 3 placeholders images (🏠 ✏️ 🏔️)

**"La magie : le dessin gravé"**
- Texte descriptif du processus (upload photo → simulation gravure → gravure laser)
- Placeholder image large

**"Les toitures aimantées"**
- Texte descriptif (interchangeables, modèle Lego, saisonnier)

**"Pourquoi Ulule ?"**
- Prototype existant, atelier équipé, besoin 15 000 € pour 250 premiers kits + packaging + collection Noël

#### Section "À quoi servira le financement"
- Accordéon (ouvert par défaut)
- Répartition textuelle des fonds

#### Section "Qui porte la collecte"
- Accordéon
- Avatar emoji 👴 + nom "Papy Oiseaux"
- Localisation "France"
- Bio : Le Papy (artisan), Lucas (dev web), Les associés (commercial)
- Placeholder photo équipe

#### Section FAQ
- 3 questions/réponses en accordéon :
  1. Comment envoyer le dessin de mon enfant ?
  2. Le kit est adapté à quel âge ?
  3. Le nichoir tient-il en extérieur ?

**Colonne droite (sidebar sticky, 380px)** :

#### Contreparties (reward cards)

5 paliers, chacun dans une card Ulule avec :
- Image placeholder
- Prix en gras
- Nom du palier
- Description courte
- Bouton "Choisir" (`#1dba95`)
- Date livraison + nombre de contributions
- Hover : border `#1dba95` + ombre

**Palier 1 -- 5 €** : Soutien symbolique (23 contributions)
**Palier 2 -- 25 €** : Kit Découverte (41 contributions)
**Palier 3 -- 59 €** : Box Essentielle ⭐ (98 contributions)
**Palier 4 -- 75 €** : Box Découverte (19 contributions)
**Palier 5 -- 95 €** : Coffret Collector (6/50 contributions, badge "limité")

#### Bloc "Faire un don"
- Input montant + bouton "Faire un don"

#### Infos livraison
- Date estimée : Avril 2026
- Expédition : France, Europe

### 5. Section contributions récentes
- 5 dernières contributions avec avatar, nom, contrepartie choisie, temps relatif

### 6. Section "Comment fonctionne ce crowdfunding ?"
- 3 colonnes avec illustrations SVG Ulule (reprises du DOM) :
  1. Donnez des ailes à ce projet
  2. Tout ou rien
  3. Sécurisé et sans engagement

### 7. Footer
- Multi-colonnes : Ulule Crowdfunding, Formation, Camp de base, À propos
- Sélecteurs langue/devise (placeholder)
- Icônes réseaux sociaux
- B Corp badge
- Trustpilot placeholder
- Liens légaux
- **Mention claire** : "Ceci est une maquette non officielle -- aucun vrai paiement"

## Placeholders visuels

Toutes les images = `<div>` avec :
```css
background: radial-gradient(ellipse at center, #2a1f0a 0%, #1a1208 100%);
color: rgba(255,255,255,0.7);
font-size: 3rem; /* emoji */
display: flex;
align-items: center;
justify-content: center;
flex-direction: column;
```
Label en `text-transform: uppercase; font-size: 0.7rem; letter-spacing: 2px;`

## Interactions JS

| Interaction | Détail |
|-------------|--------|
| Compteur animé | 0 → 9 240 € en 1.2s, easeOutQuart, au chargement |
| Barre progression | CSS animation 0 → 62% en 1s, ease-out |
| Onglets menu | Switch visibility des sections, sans rechargement |
| Bouton Contribuer | Click → texte "✓ Merci ! 🐦", bg `#15956f`, reset après 2s |
| Accordéons | Toggle open/close avec CSS max-height transition |
| Hover cards | border-color `#1dba95` + box-shadow `0 4px 12px rgba(0,0,0,0.1)` |
| Sidebar sticky | `position: sticky; top: 80px;` en desktop |

## Responsive

| Breakpoint | Comportement |
|------------|-------------|
| Mobile (<768px) | 1 colonne, sidebar sous le contenu, header simplifié (burger), hero empilé |
| Tablette (768-1024px) | 2 colonnes si possible, sidebar réduite |
| Desktop (>1024px) | Layout 2 colonnes, sidebar sticky 380px, max-width 1200px centré |

## Rédaction -- Ton & Contenu

### Principes rédactionnels

Inspiré du style "snake" (stackindepend-content) mais adapté B2C émotionnel :

- **Tutoiement "tu"** -- intimité immédiate, comme un ami qui te montre son projet
- **Micro-histoires sensorielles** -- l'odeur du bois, le bruit de la scie, le rire de la petite-fille
- **Anti-industriel** -- on ne vend pas un produit, on vend un souvenir
- **Validation émotionnelle** -- "tu te souviens de ce moment avec ton grand-père ?"
- **Honnêteté artisanale** -- pas de marketing gonflé, du vrai, du concret
- **Urgence douce** -- pas "achète maintenant", mais "ce moment ne reviendra pas"

### Textes finalisés

#### Titre H1
**Papy Oiseaux -- Le kit nichoir avec le dessin de ton enfant gravé dedans**

#### Sous-titre hero
Un papy passionné d'oiseaux. Sa petite-fille qui voulait créer de ses mains. Et un kit nichoir en bois où le vrai dessin de ton enfant est gravé au laser sur la façade. Fabriqué en France, assemblé en famille.

#### Citation fondatrice (encart bois)
> "Mon papy adore les oiseaux. Un samedi matin, ma petite-fille m'a tiré par la manche : 'Papy, on construit une maison pour les oiseaux du jardin ?'
>
> On a passé la journée entière dans l'atelier. La sciure dans les cheveux. Le bruit de la ponceuse. Son petit dessin d'oiseau scotché sur le bois comme modèle.
>
> Le soir, on a posé la niche ensemble sur le muret du fond. Elle a dit : 'Papy, c'est la plus belle maison du monde.'
>
> Elle avait raison. Pas parce qu'elle était parfaite. Parce qu'elle était à nous."

#### Section "Le produit" -- intro
Ce jour-là, on s'est dit : et si chaque famille pouvait vivre ce moment ?

Pas un jouet en plastique qu'on oublie. Pas un kit Ikea sans âme. Un vrai projet à construire ensemble, avec les mains, avec le coeur -- et avec le dessin de ton enfant gravé dessus pour toujours.

#### Contenu de la box (liste)
- 🏠 **Kit nichoir en bois de peuplier** -- planches prédécoupées, assemblage sans outil, sans colle. Conçu pour que même les plus petits participent.
- ✏️ **Planche avant gravée au laser** -- avec LE vrai dessin de ton enfant. Fait main sur papier, photographié, gravé dans le bois. Unique au monde.
- 🏔️ **Toiture interchangeable par aimants** -- chalet, japonais, chaumière... Facile même pour les plus petits. Change de toit, change de saison.
- 📌 **Pins oiseaux à collectionner** -- 3 espèces dans chaque box. Le début d'une collection nature.
- 🎨 **Autocollants Papy Oiseaux** -- pour décorer, personnaliser, s'amuser.

#### Section "La magie : le dessin gravé"
C'est là que ça devient unique.

Ton enfant dessine un oiseau sur papier. N'importe quel oiseau -- un griffonnage de 3 ans ou un chef-d'oeuvre de 8 ans. Tu prends une photo. Tu l'uploades sur notre configurateur.

Et là, tu vois le dessin apparaître en temps réel sur le bois. La simulation montre exactement ce que la gravure laser va produire. Les traits du crayon deviennent des sillons dans le peuplier.

Personne ne fait ça. Personne ne grave le vrai dessin de ton enfant sur un nichoir. C'est pas un sticker. C'est pas un transfert. C'est gravé dans le bois, pour toujours.

Dans 20 ans, quand ton enfant reviendra dans le jardin de ses grands-parents, le nichoir sera toujours là. Avec son dessin de quand il avait 5 ans.

#### Section "Les toitures aimantées"
On a appliqué le modèle Lego au jardin.

Les toitures se clipsent par aimants en 3 secondes. Toit chalet pour l'hiver. Toit japonais pour le printemps. Toit chaumière pour l'automne.

Chaque saison, une nouvelle occasion de renouveler la niche. Et chaque nouvelle toiture, une excuse pour retourner dans le jardin avec les enfants.

#### Section "Pourquoi Ulule ?"
On ne part pas de zéro. Le prototype existe. L'atelier est équipé. L'équipe est en place. Le configurateur web fonctionne.

Ce qu'il nous manque : **15 000 €** pour financer les 250 premiers kits, le packaging premium qui protège le bois pendant l'expédition, et la première collection de toitures saisonnières spéciale Noël.

On a choisi Ulule parce qu'on croit au financement participatif pour les projets qui ont du sens. Pas de gros investisseur. Pas de plateforme froide. Juste des familles qui croient au projet et qui veulent le premier kit.

#### Section "L'équipe"
- 👴 **Le Papy** -- Artisan bois depuis 40 ans. C'est lui qui a eu l'idée, c'est lui qui fabrique. Il sent le bois, la colle et le café du matin. L'âme et les mains du projet.
- 💻 **Lucas** -- Développeur web. C'est lui qui a construit le configurateur qui transforme le dessin de ton enfant en gravure. L'expérience digitale, c'est son truc.
- 🔧 **Antoine** -- Le bras droit opérationnel. Logistique, packaging, production -- c'est lui qui s'assure que chaque box arrive chez toi en parfait état.
- 📞 **Valentin** -- Commercial et distribution. Réseau solide, partenariats B2B. Il ouvre les portes pour que Papy Oiseaux arrive dans les bonnes boutiques.

#### FAQ

**Comment envoyer le dessin de mon enfant ?**
Après ta contribution, tu reçois un lien vers notre configurateur en ligne. Tu uploades une photo du dessin -- peu importe la qualité, on s'occupe du reste. Tu vois le rendu en temps réel avant validation.

**Le kit est adapté à quel âge ?**
Dès 4 ans avec un adulte. L'assemblage fonctionne par emboîtement, sans colle ni outil. C'est conçu pour être simple et sûr -- le but, c'est de passer un bon moment ensemble, pas de se battre avec une notice.

**Le nichoir tient-il en extérieur ?**
Oui. Contreplaqué peuplier traité à l'huile de lin naturelle. Conçu pour rester dehors toute l'année, pluie ou soleil. Et oui, les oiseaux l'adoptent vraiment -- on a testé.

#### Actualité 1 (il y a 3 jours)
**🐦 60% atteints -- merci !**
*Par Le Papy 👴*

En moins de 3 semaines, 187 d'entre vous ont cru au projet. Je suis dans mon atelier en ce moment, j'assemble les premiers prototypes pour vérifier que tout est nickel avant la production.

Les premiers kits seront prêts bien avant les délais prévus. Je vous tiens au courant avec des photos de l'atelier très bientôt.

Merci du fond du coeur. Chaque contribution, c'est un nichoir de plus dans un jardin, et un souvenir de plus dans une famille.

#### Actualité 2 (il y a 12 jours)
**🔧 Le configurateur est en ligne**
*Par Lucas 💻*

Grosse nouvelle : vous pouvez maintenant tester le configurateur sur notre site. Uploadez une photo du dessin de votre enfant et voyez-le s'appliquer en temps réel sur la niche avec la simulation gravure bois.

C'est encore en bêta, mais ça marche. Et franchement, la première fois qu'on voit le gribouillis de sa fille de 4 ans apparaître gravé dans le bois... ça fait quelque chose.

#### Section "À quoi servira le financement"
Soyons transparents :

- **Les matériaux** -- Bois de peuplier français, aimants, huile de lin. On ne prend pas du MDF chinois. Le bois a un coût, mais c'est ce qui fait la différence.
- **La gravure laser** -- Chaque planche est gravée individuellement avec le dessin unique de chaque enfant. C'est du sur-mesure, pas de la série.
- **Le packaging** -- Un nichoir en bois, ça se protège. On développe un emballage premium qui fait aussi partie de l'expérience d'ouverture.
- **La collection Noël** -- Les premières toitures saisonnières, avec des designs spéciaux.
- **Ulule** -- Notre partenaire prend un pourcentage, c'est logique et légitime.
- **L'expédition** -- Envoyer du bois par la poste, c'est un sport. On optimise pour que tout arrive intact.

#### Bloc presse (placeholder)
> "Un projet qui allie émotion, nature et artisanat français comme on en voit rarement sur les plateformes de financement participatif."
>
> -- *À remplacer par une vraie citation presse*

### Contreparties -- Textes

**5 € -- Soutien symbolique**
Tu crois au projet et tu veux nous encourager. Ton nom apparaîtra dans les remerciements officiels et tu auras accès à toutes les actualités en avant-première.
*23 contributeurs -- livraison numérique*

**25 € -- Kit Découverte**
3 pins oiseaux à collectionner, des autocollants Papy Oiseaux, et une carte signée à la main par le papy. Le début de l'aventure.
*41 contributeurs -- livraison mars 2026*

**59 € -- Box Essentielle ⭐ POPULAIRE**
Le coeur du projet. Le kit nichoir complet en bois avec la planche avant gravée au laser avec LE dessin de ton enfant. Plus la toiture aimantée de base, les pins, les autocollants, et la notice d'assemblage illustrée.
*98 contributeurs -- livraison avril 2026*

**75 € -- Box Découverte**
Tout le contenu de la Box Essentielle + le livre découverte illustré (34 espèces d'oiseaux à reconnaître dans ton jardin) + livraison offerte.
*19 contributeurs -- livraison avril 2026*

**95 € -- Coffret Collector Édition Ulule** *(limité 50 exemplaires)*
La totale. Box Découverte + 2 toitures supplémentaires au choix + emballage cadeau premium + numéro de série gravé + signature du papy. Livraison offerte.
*6 contributeurs -- livraison mai 2026*

## Ce que cette maquette n'est PAS

- Pas la vraie page Ulule (maquette de travail interne)
- Aucun vrai paiement, aucune vraie contribution
- Pas de configurateur (module séparé)
- Pas d'optimisation SEO/perf

## Fichier de sortie

```
papy-oiseaux/
  index.html    ← fichier unique, ouvrir dans un navigateur
```
