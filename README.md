# Projet Endurance

Depuis toujours, j'ai eu un grand intérêt pour tout ce qui tourne autour de l'aviation. C'est cet intérêt qui m'a notamment amené à passer mon BIA (Brevet d'Initiation Aéronautique) au collège et à faire des visites de musées et d'évènements aéronautiques, avec comme dernier évènement mon passage au championnat de France de course de navigation aérienne à [l'aérodrome Belfort - Chaux](https://maps.app.goo.gl/5u1Jz68SwWqnkzTF7) (photos de l'évènement dans le dossier "photo du championnat"). Cette intérêt à continué à grandir à la suite de mon initiation, il y a quelques années, à la CAO (Conception par Ordinateur Assisté) avec les logiciels [Fusion 360](https://www.autodesk.com/fr/products/fusion-360/overview) et [Onshape](https://www.onshape.com/en/).

## Complications
C'est donc dans cette optique que je me suis lancé le défi de faire un drone sous la forme d'un avion capable de voler le plus longtemps possible. Ne connaissant pas grand-chose à tout ce qui est mathématique de l'aviation, je sais que ce projet prendra du temps et qu'il demandera beaucoup de recherche. C'est pour cela que j'ai décidé de faire appel à une IA dans ce projet pour me donner des conseils, directives et suggestions.

## Mon idée pour le drone
Pour réaliser la forme de ce drone, je me suis inspiré de 3 types d'avion qui sont les [planeurs](https://fr.wikipedia.org/wiki/Planeur#), les [ailes volantes](https://fr.wikipedia.org/wiki/Aile_volante#) et les [BWB](https://fr.wikipedia.org/wiki/Fuselage_int%C3%A9gr%C3%A9#Avantages) (Blended Wing Body). Mon objectif est donc de faire un mélange de ces 3 types pour essayer de récupérer un maximum de leurs avantages et avoir un drone plutôt unique et performant.

## Organisation du dépôt
Pour faciliter la compréhension et l'évolution des drones au cours du temps et de mes découvertes, j'ai créé des dossiers pour chacune de mes tentatives (Endurance1, 2, 3, etc) avec à l'intérieur un README expliquant mon idée et mon cheminement vers le modèle que vous pourrez voir en photo. J'ai également déposé dans ces dossiers le fichier stl (fichier pour les modèles 3D) pour que vous puissiez les télécharger et les ouvrir dans le logiciel CAO de votre choix.

## Lexique de la CAO
Les outils de création 3D dans Onshape se divisent entre les modes d'action (communs à presque toutes les fonctions), les outils de génération primaire à partir d'esquisses, et les outils d'usinage ou de modification de corps existants.

### 1. Les modes d'opération universels
Lorsqu'une fonction 3D (extrusion, lissage, révolution, etc.) est lancée, une bannière supérieure définit la nature mathématique du résultat :
- **Solide :** Crée ou modifie un corps fermé, étanche et possédant une masse volumique.
- **Surface :** Génère une peau d'épaisseur nulle (idéal pour le travail de carrosserie, le raccordement aérodynamique complexe ou les surfaces d'outillage).
- **Mince (Thin) :** Crée un solide en donnant directement une épaisseur de paroi constante le long des contours d'une esquisse, sans avoir besoin de tracer deux lignes parallèles.

Ces fonctions se déclinent en quatre comportements d'assemblage :
- **Nouveau (New) :** Génère un corps solide indépendant (Part 2, Part 3, etc.) sans le lier aux pièces qu'il touche.
- **Ajouter (Add) :** Fusionne automatiquement la nouvelle matière avec une pièce existante sélectionnée dans le champ Étendue de fusion.
- **Retirer (Remove) :** Soustrait le volume généré de la matière existante pour creuser, percer ou évider.
- **Intersection :** Supprime tout pour ne conserver que la zone de volume commune entre la géométrie créée et les pièces déjà existantes.

### 2. Outils de génération volumique (d'après esquisse)
- **Extrusion (Maj + E) :** Projette un profil 2D fermé ou ouvert en ligne droite selon une direction et une profondeur définies (borgne, symétrique, ou jusqu'à une face cible).
- **Révolution (Maj + W) :** Fait pivoter un profil 2D autour d'un axe géométrique (segment ou ligne de construction) sur un angle allant jusqu'à 360° pour former des corps cylindriques, sphériques ou toriques.
- **Balayage (Sweep - Maj + S) :** Fait glisser une section droite le long d'une trajectoire courbe (fil-guide ou polyligne 3D), indispensable pour modéliser des tubes, tuyauteries ou câblages cintrés.
- **Lissage (Loft - Maj + L) :** Relie deux ou plusieurs profils de sections transversales différentes placés sur des plans distincts (ex. raccorder un profil aérodynamique large C1 vers un saumon étroit W1), éventuellement guidé par des lignes de guidage (guide curves).

### 3. Outils d'usinage, d'habillage et d'évidement
- **Congé (Fillet - Maj + F) :** Arrondit une arête vive ou crée un raccord tangent et évasé entre deux faces sécantes en appliquant un rayon de courbure cylindrique.
- **Chanfrein (Chamfer) :** Biseaute une arête vive selon une face plane définie par une distance et un angle (ex. 45°), souvent utilisé pour faciliter l'emboîtement mécanique ou ébavurer.
- **Dépouille (Draft) :** Incline une ou plusieurs faces planes selon un angle par rapport à un plan de référence (direction de démoulage), essentiel pour la conception de pièces moulées par injection.
- **Coque (Shell) :** Évide l'intérieur d'un volume plein pour ne laisser qu'une fine paroi constante, en supprimant une ou plusieurs faces choisies pour créer une ouverture.
- **Nervure (Rib) :** Génère une cloison de rigidification mince à partir d'un simple trait ouvert en étendant automatiquement la matière jusqu'aux parois environnantes.
- **Épaissir (Thicken) :** Convertit une surface d'épaisseur nulle en un solide tridimensionnel en lui appliquant une épaisseur vers l'intérieur, l'extérieur ou symétriquement.
- **Perçage (Hole) :** Génère des perçages mécaniques standardisés (trous lisses, lamés, fraisés ou taraudés avec normes ISO/ANSI) centrés sur des points d'esquisse.

### 4. Outils de modification, de découpe et d'arrangement
- **Booléen (Boolean) :** Réalise des opérations ensemblistes entre deux ou plusieurs solides distincts : Union (fusionner plusieurs pièces en une seule), Soustraction (retirer l'empreinte d'une pièce d'une autre) ou Intersection.
- **Scinder (Split) :** Découpe une pièce solide en plusieurs parties distinctes à l'aide d'un plan de référence, d'une surface ou d'une face, sans retirer de matière.
- **Symétrie (Mirror) :** Duplique une pièce entière, une face ou une fonction par rapport à un plan neutre (par exemple pour obtenir l'autre moitié d'un fuselage ou d'une aile).
- **Répétition linéaire (Linear Pattern) :** Duplique une entité (pièce, fonction ou face) selon une ou deux directions linéaires en définissant le pas et le nombre d'occurrences.
- **Répétition circulaire (Circular Pattern) :** Duplique une entité en cercle autour d'un axe de révolution régulier.
- **Transformer (Transform) :** Déplace, translate, pivote, met à l'échelle ou clone sur place une pièce existante sans modifier l'esquisse mère.
