- En théorie des catégories et en géométrie algébrique, la notion de **site** est le fondement qui permet de généraliser la notion de topologie usuelle (ouverts, intersections, recouvrements) à des structures abstraites où les "ouverts" ne sont plus des sous-ensembles, mais des **objets** d'une catégorie.
  
  Un **site** est une catégorie C munie d'une structure supplémentaire appelée **topologie de Grothendieck**.
- ## 1. Pourquoi généraliser la notion de topologie ?
  
  Dans la topologie classique sur un espace topologique X :
- On manipule une famille d'ouverts U \subseteq X.
- L'inclusion de sous-ensembles U \subseteq V définit un ordre partiel (une catégorie).
- Un ouvert U peut être recouvert par une famille d'ouverts (U_i)_{i \in I} tel que U = \bigcup_{i \in I} U_i.
  
  Cependant, en géométrie algébrique (notamment avec Alexander Grothendieck), les ouverts usuels sont trop peu nombreux pour capturer des propriétés fondamentales (comme le groupe fondamental ou la cohomologie étale). Pour y remédier, au lieu de considérer de simples inclusions U \subseteq V, on considère des **morphismes** f : U \to V.
- ## 2. Définition formelle d'un site
  
  Un **site** est un couple (C, J) constitué :
- D'une catégorie C (généralement supposée à limites projectives finies, c'est-à-dire possédant des produits produits fibrés et un objet terminal).
- D'une **topologie de Grothendieck** J sur C.
- ### La topologie de Grothendieck (J)
  
  La topologie J associe à chaque objet U \in \text{Ob}(C) une collection de familles de morphismes de même cible U, appelées **recouvrements** (ou *cribles de recouvrement*).
  
  Une famille (f_i : U_i \to U)_{i \in I} est un **recouvrement** de U si elle satisfait trois axiomes fondamentaux :
- **Isomorphismes (Base) :** Si f : U' \to U est un isomorphe, alors la famille à un seul élément \{f\} est un recouvrement de U.
- **Stabilité par changement de base (Tirage en arrière) :** Si (f_i : U_i \to U)_{i \in I} est un recouvrement de U, et si g : V \to U est n'importe quel morphisme, alors les produits fibrés U_i \times_U V existent et la famille des projections :
  `(U_i \times_U V \to V)_{i \in I}`
  
  est un recouvrement de V.
- **Transitivité (Composition) :** Si (f_i : U_i \to U)_{i \in I} couvre U, et si pour chaque i \in I, on a un recouvrement (g_{ij} : V_{ij} \to U_i)_{j \in J_i} de U_i, alors la famille des composées :
  `(f_i \circ g_{ij} : V_{ij} \to U)_{i \in I, j \in J_i}`
  
  est un recouvrement de U.
- ## 3. Exemples clés
  
  | Type de site | Catégorie C | Morphismes | Notion de recouvrement |
  
  | **Topologie usuelle** | Ouverts d'un espace X | Inclusions U \hookrightarrow V | Recouvrement usuel : U = \bigcup U_i |
  
  | **Site Étale** | Schémas locaux sur un schéma X | Morphismes étales Y \to X | Familles (Y_i \to Y) telles que \bigcup \text{Im}(Y_i) = Y |
  
  | **Site Canonomique** | Tout ensemble muni d'une action de groupe G | Applications G-équivariantes | Recouvrements d'ensembles G-observables |
- ## 4. Lien entre Sites et Topos
  
  Le concept de site n'est qu'une étape intermédiaire pour construire la structure centrale : le **topos de Grothendieck**.
- **Préfaisceaux :** On considère d'abord la catégorie des préfaisceaux \widehat{C} = \text{Set}^{C^{\text{op}}}.
- **Faisceaux sur un site :** La topologie de Grothendieck J permet d'imposer la condition de recollement (propriété de faisceau) aux préfaisceaux. Un préfaisceau F est un **faisceau** sur le site (C, J) si pour tout recouvrement (U_i \to U), l'application restreinte est exacte :
  `F(U) \longrightarrow \prod_{i} F(U_i) \rightrightarrows \prod_{i,j} F(U_i \times_U U_j)`
- **Le Topos :** Le **topos de Grothendieck** associé au site (C, J), noté \text{Sh}(C, J), est la catégorie de tous les faisceaux d'ensembles sur ce site.
  
  > 
  
  **Remarque de sous-jacence :** Plusieurs sites différents (non isomorphes) peuvent engendrer des topos équivalents. Un topos est une notion intrinsèque et invariante, tandis qu'un site est un "système de coordonnées" particulier permettant de le présenter.