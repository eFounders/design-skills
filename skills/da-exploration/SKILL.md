---
name: da-exploration
description: "Explorer plusieurs directions artistiques (DA) pour une marque ou un écran, en guidant pas à pas quelqu'un qui n'est pas designer : tirer 3 angles distincts d'une idée, l'aider à aller chercher ses images de référence (Cosmos, Mobbin, Pinterest, Instagram), puis traduire chaque angle en un univers graphique HTML qui part de l'image (référence visuelle d'abord, puis couleur, typo, texture) + un écran d'intention à iso-contenu, pour comparer et trancher une direction visuelle avant de prototyper. À utiliser dès que quelqu'un dit 'explore des DA', 'donne-moi des directions visuelles / des pistes créatives', 'quel mood / style / univers pour ce produit ou cet écran', 'aide-moi à trouver un territoire de marque', même s'il n'emploie pas le mot 'DA'. Pensée pour des non-designers : elle coache, elle ne suppose aucun jargon."
---

# DA Exploration : explorer des directions artistiques, même sans être designer

Cette skill aide quelqu'un à **trancher une direction visuelle** pour une marque ou un écran,
*avant* d'investir dans des écrans finis. On ne cherche pas l'écran parfait : on cherche **3 mondes
visuels distincts**, comparables, pour faire un choix éclairé.

Elle est pensée pour **un non-designer**. Ton rôle n'est pas de pondre une DA tout seul, c'est de
**guider la personne** : lui expliquer les choix en langage simple, lui donner les mots qui manquent,
et l'emmener jusqu'à des fichiers qu'elle peut regarder et comparer. Pas de jargon balancé sans
traduction.

Elle se place **en amont de `prototype`** : ici on cherche *la* direction ; `prototype` conçoit
ensuite des écrans une fois la direction choisie.

## Le principe : des territoires, pas des skins

Un **territoire** n'est pas une couleur ou une police, c'est un **monde** cohérent : une ambiance,
une typo, une palette, une texture, une personnalité, qui ensemble racontent quelque chose. Trois
territoires bien faits sont **trois paris différents** sur ce que la marque pourrait être, pas trois
nuances de la même chose.

Deux règles tiennent toute la skill :

- **Distincts, pas des variantes.** Si on pouvait passer d'un territoire à l'autre en changeant juste
  la couleur d'accent, ce ne sont pas des territoires. Chacun doit pouvoir se défendre comme un choix
  stratégique : à qui il parle, ce qu'il promet, ce qu'il risque.
- **Iso-contenu.** On rend le **même écran (ou composant) dans chaque territoire**, avec le même
  texte. C'est la seule façon de comparer honnêtement : sinon on compare des contenus, pas des DA.

## La méthode, étape par étape

### 1. Brief (court, on ne bloque pas)

Récupère juste ce qu'il faut pour diverger, en langage simple. Remplis ce que tu peux depuis ce que
la personne a déjà dit, puis pose au plus 2-3 questions. Ce qu'on veut :

- **C'est quoi ?** la marque ou l'écran, en une phrase (le quoi, pour qui).
- **Quel feeling ?** 3 ou 4 mots d'ambiance (ex : "calme, premium, organique" ou "punchy, jeune,
  direct"). Ces mots sont de l'or : ils pilotent et la DA et la recherche d'images.
- **Marque ou écran ?** explorer un univers de marque, un écran précis, ou les deux.
- **Refs / anti-refs ?** un produit qu'elle adore, un qu'elle déteste, une contrainte (couleur
  imposée, nom, secteur). Optionnel.

Un brief flou donne une sortie floue, mais une longue interrogation est pire. Une ou deux questions
ciblées plus des défauts raisonnables battent un questionnaire. Au moindre doute, propose une piste
et avance.

### 2. Tirer 3 angles distincts de l'idée

C'est l'étape qui fait ou défait l'exploration. Pour garantir des territoires vraiment différents,
trouve d'abord **les tensions** du sujet : des axes sur lesquels la marque pourrait pencher d'un côté
ou de l'autre (calme ↔ énergique, premium ↔ accessible, organique ↔ technique, sobre ↔ expressif,
intemporel ↔ tendance). Place chaque territoire à un **endroit différent et défendable** sur ces axes.

Pour chacun des 3, écris en clair :

- **un nom** (court, évocateur : "Atelier", "Néon", "Jardin"),
- **le parti pris en une phrase** (le monde qu'il ouvre),
- **à qui il parle** et **le pari / le risque** (ce qu'on gagne et ce qu'on perd à le choisir).

**Test de divergence.** Si deux territoires partagent la même *température* (chaud / froid) ET la
même *énergie* (calme / punchy), ils sont trop proches, même si les concepts ont des noms différents
(ex : "café artisanal heritage" et "café rituel du matin" finissent tous deux chaud-cosy). Repousse-en
un vers un autre coin : franchement plus froid, plus graphique, ou plus saturé. Trois vrais coins
valent mieux que trois nuances voisines.

Montre ces 3 angles **en mots à la personne avant de coder**, et laisse-la réagir. C'est rapide, et
ça évite de construire 3 mondes pour découvrir qu'aucun ne lui parle.

### 3. Amorcer chaque territoire par l'image, pas par la palette

Une DA se ressent d'abord en image. Donc avant la couleur et la typo, ancre chaque territoire avec
**1 ou 2 images de référence**, pour rendre le concept tangible tout de suite. La couleur et la typo
en découlent ensuite. Deux niveaux, complémentaires :

- **Amorce automatique (toi, maintenant).** Tu peux récupérer 1-2 images libres de droits et
  hotlinkables via l'API ouverte **Openverse** (pas de clé) :
  `https://api.openverse.org/v1/images/?q=<recherche>&page_size=6&license_type=all`, et prends le
  champ `url` de quelques résultats. Si tu peux les afficher (preview), fais une planche-contact et
  garde les 1-2 plus justes ; évite les images de marque (logos) et les portraits. Ce sont des images
  *indicatives et un peu brutes* : annonce-les comme telles, elles servent à donner à voir, pas à
  arrêter la DA.
- **Curation humaine (la personne, ensuite).** Pour approfondir, fabrique-lui une "liste de courses" :
  où chercher (Cosmos = mood, Mobbin = écrans, Pinterest = ambiance, Instagram = voix de marque, voir
  `references/chasse-references.md`), 3-5 recherches prêtes à copier construites sur les mots de
  feeling (pas juste le produit), viser 8-15 images par territoire, déposées dans
  `images/territoire-N/`. Tu liras ce dossier et tu remplaceras les amorces.

On ne bloque **jamais** sur les images : les amorces suffisent pour avancer, la curation approfondit.
Lis `references/chasse-references.md` avant cette étape.

### 4. Construire le board, dans l'ordre où l'œil le lit

Un fichier HTML auto-portant par territoire. L'ordre des blocs raconte la déduction, **de l'émotion
vers le système** :

1. **Concept** : le nom, le parti pris en une phrase, à qui ça parle, le pari.
2. **Référence(s)** : les 1-2 images d'amorce en grand (puis la grille des images curatées quand elles
   arrivent dans `images/territoire-N/`). C'est le point de départ visuel, pas une vignette en bas.
3. **Palette** : 4 à 6 couleurs nommées + hex, **tirées des images** (dominante, neutres, 1 accent).
4. **Typo** : un specimen display + un specimen texte, vraies polices chargées (une Google Font
   suffit), pour qu'on *sente* la personnalité.
5. **Texture / formes** : la matière (grain, dégradé, verre, papier, ombres) et les rayons / la
   densité, en CSS/SVG.

Puis, en bas, **l'écran d'intention** : le **même** écran/contenu rendu dans ce territoire (home,
hero, onboarding, ou l'écran précis si on explore un écran). C'est ce qui prouve que le monde tient
sur de l'usage réel, pas juste sur une planche.

**Coache à chaque bloc.** Pour un non-designer, ajoute une ligne *pourquoi ça marche* à la palette et
à la typo (ex : "le brun domine pour la chaleur, le rouille en petite dose réveille l'appétit", ou
"un serif pour l'émotion, un sans pour garder la lecture simple"). Le board doit **expliquer**, pas
seulement montrer : c'est là que la personne apprend à voir.

Côté technique, aligne-toi sur `prototype` : tokens sur `:root`, chaque valeur via `var(--…)`, grille
de 4px, pas de valeurs arbitraires, fichier auto-portant. Différence avec `prototype` : ici pas de
design system à respecter, **on invente la DA**, donc chaque fichier définit ses propres tokens.

### 5. Comparer côte à côte

Crée un `index.html` qui aligne **les 3 écrans d'intention à iso-contenu, à la même hauteur**
(recadrés sur l'écran lui-même, pas le board entier), pour décider d'un coup d'œil. Ajoute un mot par
territoire (parti pris, à qui, risque) et un lien pour ouvrir chaque board en grand. Sans cette vue
alignée, on compare de mémoire, et la mémoire ment.

### 6. Choisir, ou croiser

Aide la personne à trancher : qu'est-ce que chaque piste évoque, à qui elle parle, ses risques. Le
résultat peut être **une direction**, ou **un croisement** (la typo de l'une, la couleur de l'autre).
Tu éclaires le choix, tu ne l'imposes pas.

Une fois le territoire validé, on quitte la divergence : on **converge sur le gagnant** et on
l'approfondit. Les étapes 7 et 8 sont la *phase 2* de la skill.

## Phase 2 : du territoire retenu au handoff

La phase 1 sert à choisir. La phase 2 transforme le territoire choisi en quelque chose qu'une autre
skill (`ds-bootstrap`, `prototype`) peut consommer. On ne recommence pas tout : on approfondit **un
seul** monde.

### 7. Approfondir le territoire retenu

- **Curation réelle, enfin rentable.** Maintenant que le choix est fait, la curation d'images sérieuse
  (Cosmos/Pinterest, 8-15 images) vaut le coup, **pour ce seul territoire** : l'effort est divisé par
  trois. La personne dépose dans `images/territoire-retenu/`, tu remplaces les amorces, et tu
  **raffines la palette et la typo à partir de ces vraies images** (une DA tirée d'images réelles est
  toujours plus juste qu'une DA inventée de tête).
- **Stress-test sur du vrai usage.** Passe de 1 écran d'intention à **2-3 écrans clés** (ex : home +
  page produit + une étape de tunnel). Un seul hero peut mentir ; un monde qui tient sur trois écrans
  différents est crédible. C'est aussi là qu'on attrape les manques (états, densité, composants qui
  reviennent).
- **Si c'est un croisement**, dis explicitement ce que tu prends à chaque parent (ex : « la chaleur et
  le serif de Rituel, l'aplomb typographique et l'accent franc de Comptoir ») : un croisement réussi
  est une synthèse nommée, pas un mélange flou.

### 8. Consolider en handoff

Fige le monde dans un livrable que la suite peut manger :

- **Un jeu de tokens** : les variables CSS (`--couleur-*`, `--font-*`, `--radius-*`, l'échelle
  d'espace), prêtes à copier. C'est le pont direct vers `ds-bootstrap`, qui en fera le design system
  du projet.
- **Une page « DA retenue »** : le monde raffiné (images réelles, palette, typo, texture) + les 2-3
  écrans + le bloc de tokens, en un seul endroit partageable.
- **Le passage de relais**, énoncé clairement : `ds-bootstrap` pour créer le design system à partir de
  ces tokens, puis `prototype` pour designer le reste des écrans sur ce DS. À partir d'ici, **le code
  devient la source de vérité** (logique de `prototype`) : la DA n'est plus une exploration, c'est une
  fondation.

## Le livrable

```
<projet>-da/
├── index.html              ← comparateur : les 3 écrans d'intention côte à côte
├── territoire-1-<nom>.html ← board d'univers + écran d'intention
├── territoire-2-<nom>.html
├── territoire-3-<nom>.html
└── images/
    ├── territoire-1/        ← la personne dépose ici ses refs Cosmos/Pinterest/…
    ├── territoire-2/
    └── territoire-3/
```

Livre les chemins en `file:///…` cliquables, plus un résumé par territoire (ce que c'est, le pari,
ce qu'il faut tester). Itère ensuite **comme un dialogue** : la première sortie ouvre la conversation,
elle n'est jamais le livrable final.

## Garde-fous

- **Distincts, pas des variantes.** Si deux territoires se ressemblent, force la divergence : repars
  des tensions (étape 2).
- **Iso-contenu**, sinon la comparaison ment.
- **Coache, ne jargonne pas.** Chaque terme technique vient avec sa traduction. Le but est qu'un
  non-designer comprenne *pourquoi* une piste marche, pas juste qu'elle est jolie.
- **Partir de l'image, jamais bloquer dessus.** Le board s'ouvre sur 1-2 images (amorce auto via
  Openverse), puis la palette et la typo en découlent. Si aucune image n'est encore disponible, on
  avance quand même avec des placeholders légendés : on ne reste pas coincé.
- **C'est une exploration, pas une décision.** Tu donnes les moyens de choisir, tu ne choisis pas à
  la place.
