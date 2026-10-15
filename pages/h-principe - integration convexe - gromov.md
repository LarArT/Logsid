- L'**intégration convexe** de Gromov est l'une des techniques les plus puissantes et spectaculaires de la topologie différentielle et de la géométrie différentielle moderne. Introduite par **Mikhail Gromov** dans les années 1970 (développée de manière systématique dans son ouvrage fondateur de 1986, *Partial Differential Relations*), cette méthode permet de résoudre de nombreux problèmes d'équations aux dérivées partielles (EDP) sous-déterminées et d'établir des théorèmes d'existence surprenants.
- ## 1. Origine et Contexte : L'effet "h-principe"
  
  L'intégration convexe s'inscrit dans le cadre plus large du **h-principe** (principe d'homotopie), concept forgé par Gromov.
  
  Un problème géométrique ou physique s'exprime souvent par une relation aux dérivées partielles (RDP). On cherche une section f d'un fibré (par exemple une application entre deux variétés) vérifiant une certaine contrainte sur sa différentielle df.
- **Le problème topologique (formel) :** Existe-t-il une application f *et* un champ de différentielles « virtuelles » F satisfaisant la relation algébrique ? C'est une condition purement topologique, généralement facile à tester.
- **Le problème géométrique (analytique) :** Peut-on trouver f telle que la vraie différentielle df soit égale à F et vérifie la relation ? C'est le problème d'EDP sous-jacent.
  
  On dit qu'un système vérifie le **h-principe** si toute solution formelle (topologique) peut être déformée (par homotopie) en une vraie solution analytique. L'intégration convexe est la principale technique constructive permettant de prouver qu'un h-principe est satisfait.
- ## 2. L'idée intuitive de la méthode
  
  L'idée de base dérive des travaux de **John Nash** sur les immersions isométriques C^1 et de **Nicolaas Kuiper** (théorème de Nash-Kuiper).
  
  Pour résoudre une EDP géométrique par intégration convexe :
- **Découpage unidirectionnel :** On décompose le domaine de définition (ou le problème) direction par direction (par exemple le long de coordonnées ou de fibrations).
- **Boutonnières / Oscillations à haute fréquence :** Si la dérivée souhaitée se trouve dans l'**enveloppe convexe** d'un ensemble de dérivées autorisées, on peut remplacer la fonction par une suite de fonctions qui **oscillent à très haute fréquence**.
- **Passement de la convexité à la réalisation :** Ces oscillations rapides permettent à la dérivée moyenne d'égaler la valeur ciblée, tout en restant localement à l'intérieur de l'ensemble des contraintes.
  
  ```
  ▲  Valeurs de la dérivée
       │
  A ───┼───/\/\/\/\/\/\/\/\/\─── (Oscillations rapides entre A et B)
       │  /  \  /  \  /  \  /
  y ───┼──--------------------- (Valeur moyenne souhaitée y ∈ conv{A,B})
       │ /    \/    \/    \/
  B ───┼/_______________________
       └────────────────────────► x
  ```
  
  En intégrant ces oscillations très rapides (d'où le nom d'**intégration** convexe), la fonction converge (souvent en norme C^0) vers une solution dont la dérivée appartient strictement à l'ensemble recherché.
- ## 3. Définition formelle (Aperçu)
  
  Soit X \to V un fibré de jets d'ordre k, et \mathcal{R} \subset X une relation aux dérivées partielles (un sous-ensemble de l'espace des jets).
  
  Une relation \mathcal{R} est dite **convexe-ouverte** si, pour chaque direction, les sections transverses de \mathcal{R} dans l'espace des jets ont des composantes connexes qui sont ouvertes et dont l'enveloppe convexe couvre un domaine suffisamment large (en général tout l'espace ambiant).
  
  > 
  
  **Théorème fondamental de l'intégration convexe (Gromov) :**
  Si une relation aux dérivées partielles d'ordre 1 (open 1-step relation) \mathcal{R} est ample (au sens de la convexité de ses fibres), alors \mathcal{R} satisfait le h-principe (sous forme paramétrique et relative).
- ## 4. Exemples emblématiques d'applications
- ### A. Immersions isométriques C^1 (Théorème de Nash-Kuiper)
  
  Il est possible d'immerger de manière isométrique (C^1) une sphère unité \mathbb{S}^2 dans une petite boule de \mathbb{R}^3 de rayon \epsilon > 0. La surface obtenue est uniformément C^1, mais fractalement froissée : ses dérivées secondes n'existent pas ou sont discontinues. L'intégration convexe permet de construire explicitement ces plongements par ajouts successifs de "gondolements" (corrugations).
- ### B. Sous-variétés isotropes et lagrangiennes
  
  En géométrie symplectique, l'intégration convexe permet de démontrer le h-principe pour les immersions isotropes. Si une forme différentielle n'impose pas de contraintes d'intégrabilité trop rigides (contrairement aux structures symplectiques ou de contact sur des variétés fermées), l'intégration convexe s'applique.
- ### C. Hydrodynamique et Turbulences (Équations d'Euler)
  
  Récemment (travaux de **Camillo De Lellis** et **László Székelyhidi Jr.** à partir de 2009), la méthode de l'intégration convexe de Gromov a été adaptée aux équations aux dérivées partielles de la mécanique des fluides.
- Elle a permis de résoudre la **conjecture d'Onsager** (prouvée par Philip Isett en 2016), en construisant des solutions faibles (non régulières) des équations d'Euler incompressibles qui ne conservent pas l'énergie cinétique.
- ## 5. Résumé des forces et limites
- **Forces :**
	- Outil systématique et universel pour prouver le h-principe.
	- Extrêmement puissant dans les régimes de faible régularité (C^0, C^1, ou L^\infty).
- **Limites :**
	- Ne fonctionne pas lorsque des obstructions rigides existent (par exemple pour des régularités élevées C^2 ou C^\infty, où la courbure limite la flexibilité).
	- Les solutions produites sont souvent « pathologiques » ou contre-intuitives d'un point de vue physique/géométrique classique (absence de régularité supérieure).