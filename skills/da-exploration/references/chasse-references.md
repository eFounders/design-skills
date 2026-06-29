# Chasse aux références : guider quelqu'un à trouver ses images

Ce fichier sert à l'étape 3 de la skill. Objectif : donner à un non-designer de quoi **ramener les
bonnes images** (celles qui définissent un territoire), pas juste des jolies images au hasard.

Deux niveaux complémentaires, et l'ordre compte : on **part de l'image**, la couleur et la typo en
découlent.

- **Amorce automatique (toi).** Pour rendre le concept tangible immédiatement, tu récupères 1-2 images
  toi-même via une source ouverte et hotlinkable (voir §0). Brutes mais réelles.
- **Curation humaine (la personne).** Les plateformes de goût (Cosmos, Pinterest…) sont derrière un
  login, tu ne peux pas les aspirer. Donc tu **fabriques la liste de courses** (§1-§4) et tu apprends
  à la personne à trier pour approfondir.

## Sommaire

0. Amorce automatique : images libres de droits sans login (Openverse)
1. Quelle plateforme pour quoi
2. Bien chercher : la recette
3. Trier : garder ou jeter
4. Déposer et organiser
5. Petit lexique de DA (les mots à donner à la personne)
6. Droits d'usage

---

## 0. Amorce automatique : images libres de droits sans login (Openverse)

Pour ne pas laisser le concept sans visuel, tu peux tirer toi-même quelques images via l'**API
Openverse** (agrège des images sous licence Creative Commons, **pas de clé requise**) :

```
https://api.openverse.org/v1/images/?q=<recherche>&page_size=6&license_type=all
```

La réponse est du JSON ; prends le champ `url` de quelques résultats (ce sont des liens directs, ils
s'affichent dans un `<img>`). Méthode :

1. lance une recherche par territoire, sur les mots du concept (ex : `espresso bar counter`,
   `pour over coffee brewing`, `morning coffee light`) ;
2. si tu as un preview, monte une **planche-contact** (toutes les vignettes) et **regarde** avant de
   choisir : garde les 1-2 plus justes, écarte les logos de marque et les portraits ;
3. intègre-les en haut du board comme **amorce**, en disant clairement que ce sont des images
   indicatives et un peu brutes, à approfondir avec la curation humaine.

Limites à assumer : Openverse ramène surtout du Flickr, donc une esthétique « photo amateur » plutôt
que l'éditorial léché de Cosmos. C'est voulu : à ce stade on veut *donner à voir le concept*, pas
livrer le mood final. La curation humaine (§1-§4) fait le reste.

---

## 1. Quelle plateforme pour quoi

Chaque plateforme a une force. Dis à la personne **laquelle ouvrir selon ce qu'elle cherche**.

- **Cosmos** (cosmos.so) : références d'art direction curatées, éditoriales, peu de bruit. La
  meilleure pour le **feeling** d'un territoire : mood, texture, mise en page, typo en contexte. À
  privilégier pour une marque.
- **Pinterest** : énorme volume, plus bruité. Bon pour les **ambiances larges** : histoires de
  couleur, packaging, matières, lifestyle, éditorial. Conseiller de créer un board par territoire
  pour ne pas se noyer.
- **Mobbin** (mobbin.com) : vraies interfaces d'apps réelles, écrans et flux complets. **La référence
  quand on explore un écran ou une UI produit** : comment de vraies apps structurent ce genre
  d'écran. On filtre par app, par pattern. À noter : Mobbin montre des *patterns d'UI*, pas du mood,
  donc il sert surtout au "comment c'est foutu", moins au "quelle ambiance".
- **Instagram** : les marques **en vrai**, leur voix, leurs systèmes d'identité. Bon pour le **ton** et
  l'exécution réelle d'une marque. Suivre des comptes de studios / agences de branding donne un flux
  de qualité.

Bonus, si la personne veut creuser : **Are.na** (channels curatés en profondeur), **Savee** (proche
de Cosmos), **Typewolf** (associations de polices réelles), **Brand New / underconsideration**
(études de cas d'identités de marque), **Land-book / Godly / Footer** (design web).

Règle simple à transmettre :
- **mood, matière, art direction** → Cosmos, Pinterest, Are.na
- **interface, écran, flux produit** → Mobbin
- **voix et identité de marque réelle** → Instagram, Brand New
- **typo** → Typewolf

## 2. Bien chercher : la recette

Le réflexe du débutant est de taper le produit ("appli banque"). Ça ramène du générique. La recette
qui marche : **nom + mot de feeling + médium**.

- nom = le sujet (skincare, fintech, café, dashboard…)
- feeling = les mots d'ambiance du brief (muted, warm, bold, editorial, organic, technical, playful…)
- médium = la forme cherchée (packaging, app UI, poster, typography, gradient, photography, texture…)

Exemples à donner clés en main :
- territoire "calme premium organique" → `skincare editorial muted grain`, `organic packaging warm
  neutral`, `serif typography soft minimal`
- territoire "punchy jeune direct" → `bold brand identity high contrast`, `fintech app dark neon`,
  `grotesque type poster vibrant`

Donne **3 à 5 recherches prêtes à copier par territoire**, construites sur ses mots de feeling. C'est
ça le vrai cadeau de cette étape.

## 3. Trier : garder ou jeter

Un seul critère, à répéter à la personne : **est-ce que cette image porte le parti pris du
territoire ?** Si oui, on garde. Si c'est juste joli mais que ça pourrait aller dans n'importe quel
territoire, on jette. Un board fort, c'est 10 images qui racontent la **même** histoire, pas 30 belles
images qui partent dans tous les sens.

Viser **8 à 15 images par territoire** : assez pour qu'un monde se dégage, pas trop pour rester net.

## 4. Déposer et organiser

Un dossier par territoire, à côté des fichiers HTML :

```
images/
├── territoire-1/   ← 8 à 15 images ici
├── territoire-2/
└── territoire-3/
```

Pas besoin de bien nommer les fichiers, tu les liras tels quels. Une fois déposées, tu remplaces les
placeholders du board par ces vraies images, et le territoire prend vie.

## 5. Petit lexique de DA (les mots à donner à la personne)

Un non-designer voit mais n'a pas toujours les mots. Donne-les au fil de l'eau, jamais en bloc.

- **Palette** : *dominante* (la couleur qui occupe le plus), *neutres* (les gris / beiges de fond,
  chauds ou froids), *accent* (la couleur qui attire l'œil, en petite dose), *saturé / désaturé*
  (vif vs éteint), *contraste* (l'écart clair-sombre).
- **Typo** : *display* (les gros titres, là où vit la personnalité) vs *texte* (le corps, là où prime
  la lisibilité) ; *serif* (avec empattements, classique / éditorial), *sans* (sans empattements,
  moderne / neutre), *mono* (chasse fixe, technique) ; *graisse* (light → black) ; *personnalité*
  (sérieux, joueur, technique, chic, brut…).
- **Texture / traitement** : *grain / bruit* (matière photo), *dégradé mesh* (dégradés doux
  multicolores), *verre / glassmorphism* (translucide flou), *papier*, *ombres douces vs dures*,
  *flat* (aucun effet).
- **Formes** : *rayons* (carré = sérieux / tech, doux = accessible, pilule = ludique), *géométrie*,
  *densité* (aéré = premium / calme, dense = riche / pro).
- **Personnalité** : les 3 mots d'ambiance. S'ils sont justes, tout le reste découle.

## 6. Droits d'usage

Les références servent à **explorer en privé** (moodboards, planches de décision). Ce n'est pas de la
matière à **expédier telle quelle** dans un produit en ligne : la photo de quelqu'un d'autre reste la
sienne. Pour de la vraie production, il faudra des visuels libres de droits, achetés, ou créés. À
dire simplement à la personne, sans en faire un drame : à ce stade on cherche une direction, pas des
assets finaux.
