# Papy Oiseaux -- Règles d'humanisation du contenu

Adapté du framework snake (b2b-ai-toolbox) pour un contexte B2C émotionnel.

## Équipe projet

- **Lucas** -- Dev web, configurateur, tech
- **Antoine** -- Opérations, logistique, production
- **Valentin** -- Commercial, distribution, partenariats
- **Le Papy** -- Artisan bois, fabrication, âme du projet

## Les 5 techniques d'humanisation (adaptées B2C)

### T1 -- Perplexité (choix de mots inattendus)
- Pas "une solution complète" → "un kit qui tient la route"
- Pas "personnalisable" → "avec le gribouillis de ta fille gravé dessus"
- Pas "artisanat de qualité" → "du bois qui sent bon quand tu ouvres la box"
- Registre mixte : français soutenu + familier dans le même paragraphe

### T2 -- Burstiness (variation des phrases)
- Alterner : phrase de 25 mots → phrase de 4 mots → fragment → phrase complexe
- Exemple : "Ton enfant dessine un oiseau sur papier. N'importe lequel. Tu prends une photo. Et là, le configurateur fait le reste -- le dessin apparaît en temps réel sur le bois, exactement comme la gravure laser le reproduira."
- Cible : std_dev / mean_length >= 0.4

### T3 -- Imperfection (naturel humain)
- Contractions mixtes : parfois "c'est", parfois "ce n'est pas"
- Parenthèses conversationnelles : "(oui, les oiseaux l'adoptent vraiment)"
- Opinions directes : "On adore ce modèle" pas "Ce modèle est apprécié"
- Tirets longs pour les apartés -- comme ici

### T4 -- Éléments personnels
- Anecdotes du papy : "La première fois qu'un rouge-gorge a emménagé..."
- Micro-histoires sensorielles : sciure, odeur du bois, rire de la petite-fille
- Opinions assumées : "On a choisi le peuplier, pas le pin. Parce que le peuplier..."

### T5 -- Rhétorique
- Questions rhétoriques : "Et si chaque famille pouvait vivre ce moment ?"
- Callbacks : reprendre un élément du début à la fin
- Anaphore douce : "C'est pas un sticker. C'est pas un transfert. C'est gravé."
- Litote : "Ça fait quelque chose" au lieu de "C'est incroyablement émouvant"

## Mots interdits (jargon IA -- Tier 1)

Ne JAMAIS utiliser dans le contenu Papy Oiseaux :
- leverage, synergy, cutting-edge, innovative, game-changing
- seamlessly, robust, unlock, empower, streamline
- revolutionize, delve, tapestry, realm, landscape
- nuance, moreover, furthermore, testament, pivotal
- intricate, elucidate, harness, groundbreaking

## Mots interdits B2C (ajout Papy Oiseaux)

- "solution" (c'est un kit, pas une solution)
- "offre" / "opportunité" (c'est un projet, pas une offre commerciale)
- "unique en son genre" (montrer, pas dire)
- "exceptionnel" / "extraordinaire" (trop marketing)
- "n'attendez plus" / "profitez" (pas de pression commerciale)

## Patterns structurels à éviter

- Jamais "Not just X, but Y" → dire les deux choses séparément
- Jamais 3 adjectifs en liste ("beau, solide et unique") → en garder 1 ou 2
- Jamais "serves as / stands as" → utiliser "c'est" tout simplement
- Jamais de conclusion générique ("En définitive..." / "Pour conclure...")
- Jamais d'attribution vague ("Les experts s'accordent à dire...")

## Ton spécifique Papy Oiseaux

| Au lieu de... | Écrire... |
|---------------|-----------|
| Un produit éco-responsable | Du bois français, traité à l'huile de lin |
| Une expérience unique | Le gribouillis de ta fille de 4 ans, gravé dans le bois |
| Fabrication artisanale | Le papy dans son atelier, la sciure dans les cheveux |
| Personnalisable | TON dessin, pas un dessin stock |
| Assemblage facile | Emboîtement sans colle -- conçu pour qu'un enfant de 4 ans participe |
| Cadeau original | Dans 20 ans, le nichoir sera toujours dans le jardin |
| Made in France | L'atelier est en France, le bois aussi, le papy aussi |

## Scoring cible

- Burstiness : >= 0.4 (variation de longueur de phrases)
- Compression ratio : 0.45-0.60 (entropie humaine)
- Tier 1 banned words : 0
- Tier 2 cluster : max 1
- Score composite humanisation : >= 7/10

## Registre émotionnel B2C

Le contenu Papy Oiseaux doit déclencher ces émotions dans cet ordre :

1. **Nostalgie** -- "tu te souviens quand tu construisais des trucs avec ton grand-père ?"
2. **Tendresse** -- le dessin maladroit d'un enfant qui devient quelque chose de permanent
3. **Fierté parentale** -- "mon enfant a fait ça de ses mains"
4. **Connexion familiale** -- 3 générations autour d'un même projet
5. **Urgence douce** -- "ce moment où ils sont petits, ça passe vite"

Jamais de culpabilité. Jamais de FOMO agressif. Jamais de "dépêchez-vous".
L'urgence vient du temps qui passe avec les enfants, pas d'un countdown marketing.
