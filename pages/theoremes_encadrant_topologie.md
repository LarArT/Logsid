# Les théorèmes qui encadrent chaque branche de la topologie

Convention : un théorème « encadre » une branche quand il en fixe soit les limites (ce qui est possible / impossible), soit l'outil de calcul central. Quand l'élément cité est un axiome ou une définition plutôt qu'un théorème démontré, c'est signalé explicitement — les deux ne doivent pas être confondus.

---

## 1. Fondations et théories apparentées

### Topologie générale
- **Théorème de Tychonoff** — un produit (même infini) d'espaces compacts est compact ; équivalent à l'axiome du choix.
- **Lemme d'Urysohn** — dans un espace normal, deux fermés disjoints peuvent être séparés par une fonction continue à valeurs dans [0,1].
- **Théorème de métrisation d'Urysohn** — tout espace régulier à base dénombrable est métrisable.
- **Théorème de métrisation de Nagata-Smirnov** — condition nécessaire et suffisante générale de métrisabilité (sans hypothèse de dénombrabilité).
- **Théorème d'extension de Tietze** — toute fonction continue définie sur un fermé d'un espace normal s'étend continûment à l'espace entier.
- **Théorème de Baire** — dans un espace métrique complet (ou localement compact Hausdorff), une intersection dénombrable d'ouverts denses est dense.
- **Théorème de Heine-Borel** — cas particulier dans ℝⁿ : compact ⟺ fermé borné (ne se généralise pas tel quel hors des espaces métriques de dimension finie).

### Topologie ensembliste avancée
- **Indépendance de l'hypothèse de Suslin** (Solovay–Tennenbaum, 1971) — l'énoncé « toute droite de Suslin ordonnée dense complète sans plus petit ni plus grand élément et satisfaisant la condition de chaîne dénombrable est isomorphe à ℝ » est indécidable dans ZFC.
- **Théorème de Jensen** — le principe combinatoire ◊ (vrai dans L) implique l'existence d'une droite de Suslin.
- *Point de rigueur* : il ne s'agit pas ici de « théorèmes » au sens classique d'énoncés prouvés vrais dans ZFC, mais de résultats de cohérence/indépendance — la nuance est le cœur du sujet de cette sous-branche.

### Topologie sans points (locales, frames)
- **Dualité de Stone** — équivalence entre la catégorie des algèbres de Boole et celle des espaces de Stone (compacts, totalement discontinus).
- **Dualité d'Isbell** — équivalence entre les frames compacts réguliers et les espaces compacts Hausdorff.
- **Dualité de Hofmann-Lawson** — équivalence entre les frames continus et les espaces sobres localement compacts.
- **Théorème de représentation des frames spatiaux** — un frame est isomorphe au frame des ouverts d'un espace topologique si et seulement s'il est spatial ; tout frame spatial correspond à un espace sobre.

### Théorie des topos
- **Théorème de Giraud** — caractérise axiomatiquement les topos de Grothendieck parmi les catégories (existence d'un petit ensemble de générateurs, colimites commutant aux produits fibrés, sommes disjointes) : ces axiomes sont équivalents à « catégorie des préfaisceaux sur un site ».
- **Théorème de complétude de Deligne** — tout topos cohérent a « assez de points » (il existe une famille de foncteurs fibres conjointement fidèle).
- **Théorème de Barr** — généralisation : tout topos de Grothendieck (même sans point au sens de Deligne) admet une surjection depuis un topos booléen ; interprété comme un analogue du théorème de complétude de Gödel-Henkin.

---

## 2. Topologie géométrique et des variétés

### Basse dimension
- **Théorème de classification des surfaces compactes** — toute surface compacte connexe est déterminée, à homéomorphisme près, par son genre et son orientabilité.
- **Conjecture de Poincaré** (démontrée, Perelman 2003, via le flot de Ricci de Hamilton) — toute 3-variété fermée simplement connexe est homéomorphe à S³.
- **Théorème de géométrisation de Thurston** (démontré par Perelman) — toute 3-variété fermée se décompose en morceaux portant l'une des huit géométries modèles.
- **Théorème de Freedman** — classification topologique des 4-variétés simplement connexes fermées par leur forme d'intersection.
- **Théorème de Donaldson** — une forme d'intersection définie positive d'une 4-variété lisse fermée est nécessairement diagonalisable sur ℤ ; sépare la classification lisse de la classification topologique en dimension 4.
- **Théorème de Rokhlin** — pour une 4-variété fermée spin, la signature est divisible par 16.

### Théorie des nœuds
- **Théorème de Reidemeister** — deux diagrammes de nœuds représentent le même nœud si et seulement si on passe de l'un à l'autre par une suite finie de trois mouvements élémentaires.
- **Théorème de Schubert** — décomposition unique de tout nœud en somme connexe de nœuds premiers.
- **Théorème de Gordon-Luecke** (1989) — un nœud dans S³ est entièrement déterminé, à réflexion près, par son complémentaire.

### Grandes dimensions (dim ≥ 5)
- **Théorème du h-cobordisme** (Smale) — un h-cobordisme simplement connexe entre deux variétés de dimension ≥ 5 est trivial (produit) ; d'où la démonstration de la conjecture de Poincaré généralisée en dimension ≥ 5.
- **Théorème du s-cobordisme** (Barden–Mazur–Stallings) — généralisation sans l'hypothèse de simple connexité, avec obstruction dans la torsion de Whitehead.

### Topologie différentielle
- **Théorème de Sard** — l'ensemble des valeurs critiques d'une application lisse est de mesure nulle.
- **Théorème de plongement de Whitney** — toute variété lisse de dimension n se plonge dans ℝ²ⁿ.
- **Théorème de Stokes** (version générale sur les variétés à bord) — relie l'intégrale d'une forme différentielle exacte sur une variété à son intégrale de bord.
- **Théorème de de Rham** — isomorphisme entre la cohomologie de de Rham et la cohomologie singulière à coefficients réels ; *c'est ce théorème précis qui légitime de rattacher, avec réserve, la cohomologie de de Rham à la topologie algébrique (cf. échange précédent).*

---

## 3. Topologie algébrique

### Théorie de l'homotopie
- **Théorème de van Kampen** — calcule le groupe fondamental d'une union de deux ouverts à partir des groupes fondamentaux de chacun et de leur intersection.
- **Théorème de Hurewicz** — pour un espace (n-1)-connexe, le premier groupe d'homotopie non trivial est isomorphe au premier groupe d'homologie non trivial correspondant.
- **Théorème de Whitehead** — une application entre CW-complexes qui induit un isomorphisme sur tous les groupes d'homotopie est une équivalence d'homotopie.

### Homologie et cohomologie
- **Axiomes d'Eilenberg-Steenrod** — caractérisation axiomatique de ce qu'est une théorie homologique (homotopie, excision, additivité, dimension) ; *ce sont des axiomes définissant la notion, pas un théorème d'existence en soi — l'existence de théories les satisfaisant (singulière, simpliciale) est un résultat séparé.*
- **Théorème d'excision** — retirer un sous-espace « bien à l'intérieur » d'un autre ne change pas l'homologie relative.
- **Suite exacte de Mayer-Vietoris** — relie l'homologie d'une union à celle de deux ouverts recouvrants et de leur intersection.
- **Dualité de Poincaré** — pour une variété fermée orientée de dimension n, isomorphisme entre homologie de degré k et cohomologie de degré n−k.
- **Théorème des coefficients universels** — relie l'homologie à coefficients dans un anneau A à l'homologie entière, via un terme de torsion (Tor).

### K-théorie topologique
- **Théorème de périodicité de Bott** — la K-théorie topologique complexe est périodique de période 2 (réelle : période 8).
- **Théorème de l'indice d'Atiyah-Singer** — relie l'indice analytique d'un opérateur elliptique sur une variété à un invariant topologique construit en K-théorie.

---

## 4. Applications et domaines croisés

### Analyse topologique des données
- **Théorème de stabilité des diagrammes de persistance** (Cohen-Steiner, Edelsbrunner, Harer, 2005/2007) — un petit changement de la fonction filtrante n'entraîne qu'un petit changement (au sens de la distance bottleneck) du diagramme de persistance.
- **Théorème de structure des modules de persistance** (cas d'un paramètre, Zomorodian–Carlsson ; cas général, Crawley-Boevey) — un module de persistance se décompose en somme directe d'intervalles (« barcode »).

### Topologie et physique
- **Axiomes d'Atiyah pour les TQFT** — définition axiomatique d'une théorie quantique des champs topologique comme foncteur monoïdal symétrique des cobordismes vers les espaces vectoriels ; *ce sont, là encore, des axiomes de définition, pas un théorème.*
- **Théorème de classification des TQFT en dimension 2** — équivalence entre TQFT 2D et algèbres de Frobenius commutatives.
- **Théorème de l'indice d'Atiyah-Singer** (déjà cité) — sous-jacent à la robustesse topologique des isolants topologiques via la K-théorie.

### Dynamique topologique
- **Théorème de récurrence de Poincaré** — dans un système préservant une mesure finie, presque tout point revient arbitrairement près de sa position initiale.
- **Théorème du point fixe de Lefschetz** — un critère algébrique (le nombre de Lefschetz) garantissant l'existence d'un point fixe pour une application continue.
- **Principe variationnel pour l'entropie topologique** (Goodwyn, Dinaburg, Goodman) — l'entropie topologique est le supremum des entropies métriques sur toutes les mesures invariantes.

---

## Remarque de rigueur transversale

Plusieurs entrées ci-dessus (axiomes d'Eilenberg-Steenrod, axiomes d'Atiyah pour les TQFT, axiomes de Giraud) sont des **caractérisations axiomatiques**, pas des théorèmes au sens d'un résultat déduit d'hypothèses plus faibles. Les avoir listées ici sans cette précision aurait été une confusion de catégorie — d'où la mention systématique quand c'est le cas.
