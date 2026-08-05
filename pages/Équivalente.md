Tags:: équivalence de Quillen

- **Oui, absolument !** Il existe un parallèle très profond et rigoureusement formalisé sur le plan mathématique : c’est ce qu’on appelle l'**équivalence de Quillen** (ou équivalence de catégories) entre les ensembles simpliciaux et les ensembles cubiques.
  
  En topologie algébrique et en théorie des modèles, ces deux approches ne sont pas de simples analogies : ce sont deux « vues » d'un même monde homotopique.
- ## 1. Le dictionnaire de traduction (Le parallèle direct)
  
  Tout concept géométrique ou catégorique d'un côté possède son pendant exact de l'autre :
  
  | Concept | Approche Simpliciale (\Delta) | Approche Cubique (I) |
  
  | **Brique de base (1\text{D})** | Segment [0,1] | Intervalle I |
  
  | **Brique 2\text{D}** | Triangle (\Delta^2) | Carré (I^2) |
  
  | **Condition pour être une \infty-catégorie** | Remplissage des **cornets** (*horns*) \Lambda^n_k \subset \Delta^n | Remplissage des **boîtes ouvertes** (*open boxes* / *Kan fill*) |
  
  | **Définition de l'Égalité / Chemin** | Homotopie via \Delta^1 | Application depuis l'intervalle i : I |
  
  | **Produit géométrique** | Complexe (découpage du carré en 2 triangles : \Delta^1 \times \Delta^1 = \Delta^2_a \cup \Delta^2_b) | Trivial et exact : I^n \times I^m = I^{n+m} |
- ## 2. Le pont mathématique : L'équivalence de Quillen
  
  Dans les années 1970 (notamment avec Daniel Kan) puis réaffirmé dans le cadre des \infty-catégories :
- **Les foncteurs de réalisation et de triangulation :** On peut transformer tout ensemble simplicial en un ensemble cubique, et inversement, sans perdre d'information homotopique.
- **Le théorème de comparaison :** La catégorie des quasicatégories (modèle simplicial des \infty-catégories développé par Joyal et Lurie) est **équivalente** à la catégorie des catégories cubiques de Kan (ou quasi-catégories cubiques).
  
  > 
  
  **En clair :** Tout théorème démontré dans le monde simplicial admet un théorème jumeau dans le monde cubique. Ils décrivent exactement les mêmes espaces topologiques et les mêmes \infty-catégories.
- ## 3. Pourquoi utilise-t-on les deux ? (La dualité Pratique vs Théorie)
  
  Si le parallèle est continu et total, pourquoi la communauté mathématique n'en choisit-elle pas un seul ?
- **Le monde Simplicial est meilleur pour la théorie "sur papier" :**
  Les simplexes ont une combinatoire minimale (un triangle a 3 sommets, un carré en a 4). La littérature classique sur les \infty-catégories (comme les travaux fondateurs de Jacob Lurie) est écrite quasi-exclusivement en langage simplicial car la théorie y est historiquement très polie.
- **Le monde Cubique est meilleur pour l'informatique (Rocq, Agda) :**
  C'est le constat de Thierry Coquand. La structure de produit cartésien I \times I des cubes s'associe magnifiquement avec la théorie des types dépendants. Elle permet d'implémenter la **définition d'égalité sous forme d'algorithme** et de distribuer les calculs sans générer une explosion combinatoire de sous-triangles.
  
  Le parallèle entre les deux mondes est donc un pont constant entre la **géométrie abstraite** (simpliciale) et l'**informatique constructive** (cubique).