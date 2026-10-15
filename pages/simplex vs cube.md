## 1. La différence géométrique : Simplexes vs Cubes

Pour construire des espaces de haute dimension ou des \infty-catégories :
- **L'approche Simpliciale (comme dans la vidéo d'Emily Riehl) :**
	- **Brique de base :** Le **simplexe** (\Delta^n) : le point (0D), le segment (1D), le triangle (2D), le tétraèdre (3D), etc.
	- **Comment on compose :** On colle des triangles par leurs côtés ou leurs sommets commun (les « cornet » ou *horns*).
	- **Inconvénient :** La combinatoire des simplexes devient très vite extrêmement complexe dès qu'on essaie d'exprimer des produits d'espaces (le produit de deux triangles n'est pas un triangle, c'est un assemblage de plusieurs tétraèdres).
- **L'approche Cubique (Thierry Coquand) :**
	- **Brique de base :** Le **cube / hypercube** (I^n) : le point (I^0), le segment (I^1), le carré (I^2), le cube (I^3), etc.
	- **Comment on compose :** Tout est géré par des variables d'intervalle i, j \in [0, 1]. Un carré a des coordonnées (i, j).
	- **Avantage :** Le produit de deux cubes est *directement* un cube de dimension supérieure (I^a \times I^b = I^{a+b}). La géométrie algébrique y est beaucoup plus régulière.
- ## 2. La vraie différence pour l'ordinateur : Le Calcul ( *Can it run?* )
  
  Si cette distinction est si cruciale pour Thierry Coquand et les chercheurs en assistants de preuve, c'est pour une raison informatique précise :
- ### L'approche Simpliciale (Axiomatique)
  
  Dans la version originale de la théorie des types homotopiques (HoTT de Voevodsky), le principe d'univalence et les équivalences sont ajoutés comme des **axiomes**.
- **Résultat :** En logique, c'est parfait. Mais pour l'ordinateur, un axiome est une « boîte noire ». Si vous demandez à Rocq (Coq) de calculer la valeur d'une preuve qui utilise l'univalence simpliciale, la machine s'arrête et dit : *« Je ne sais pas calculer avec un axiome abstrait »*.
- ### L'approche Cubique de Coquand (Constructive)
  
  En utilisant les coordonnées des cubes, Thierry Coquand et ses collaborateurs ont réussi à définir les opérations de déformation, de transport et d'équivalence de manière **algébrique et explicite**.
- **Résultat :** L'Axiome d'Univalence n'est plus un axiome abstrait, mais un **théorème démontrable qui s'exécute** !
- ## En résumé
  
  |  | Approche Simpliciale (\infty-catégories usuelles) | Approche Cubique (Coquand / Cubical) |
  
  | **Géométrie** | Triangles, Tétraèdres (\Delta^n) | Carrés, Cubes, Hypercubes (I^n) |
  
  | **Opération clé** | Remplissage de cornets (*Horn filling*) | Algèbre des intervalles et des faces |
  
  | **Rôle dans les prouveurs** | Idéal pour la théorie formelle "sur papier" | **Calculable par la machine** (ex: *Cubical Agda*) |