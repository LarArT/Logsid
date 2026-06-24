- L'omission est tout à fait juste. Le **Calcul des Constructions (CoC)**, formulé par Thierry Coquand et Gérard Huet en 1985, ne s'est pas construit comme un bloc monolithique, mais comme la convergence de trois axes conceptuels précis.
  
  Dans une décomposition analytique, ces trois axes représentent les trois extensions orthogonales du $\lambda$-calcul qui permettent de fusionner la programmation et la logique d'ordre supérieur au sein d'un formalisme unique.
  
  Pour analyser l'architecture du Calcul des Constructions, on se réfère au **Cube de Barendregt** (ou cube des types), où le CoC occupe le sommet le plus élevé, combinant simultanément les trois dimensions du typage avancé :
- ### Axe 1 : Les types dépendants (Les types dépendant de valeurs)
- **Le mécanisme :** Cet axe permet de définir des types qui prennent pour paramètre une valeur concrète. Mathématiquement, il introduit le produit dépendant (noté $\Pi$). Par exemple, le type `Vect n` représente un tableau de taille $n$ (où $n$ est un entier naturel, donc une valeur).
- **L'implication logique :** Par la correspondance de Curry-Howard, cet axe introduit les **quantificateurs universels** ($\forall$) et l'**implication généralisée**. Dire qu'une propriété $P(x)$ est vraie pour tout entier $x$ devient équivalent à écrire une fonction qui prend en entrée un entier $x$ et renvoie une valeur de type $P(x)$. C'est l'outil fondamental pour exprimer des spécifications mathématiques précises dans le code.
- ### Axe 2 : Le polymorphisme (Les types dépendant de types)
- **Le mécanisme :** Issu du Système F de Jean-Yves Girard, cet axe permet à une fonction ou un type de prendre un type comme paramètre. C'est l'équivalent de la programmation générique. Par exemple, la fonction `identité` prend en paramètre un type $A$, puis une valeur de ce type $A$, pour renvoyer cette même valeur.
- **L'implication logique :** Cet axe permet d'exprimer la **logique du second ordre** (et d'ordre supérieur). Il donne la capacité de quantifier sur des propositions elles-mêmes (*"Pour toutes les propositions $P$, si $P$ est vraie alors..."*). C'est ce qui permet au Calcul des Constructions de formaliser des raisonnements mathématiques extrêmement abstraits sans avoir besoin d'ajouter des axiomes externes.
- ### Axe 3 : Les opérateurs de types (Les valeurs dépendant de types / Fonctions de types)
- **Le mécanisme :** Issu du système $\lambda\omega$, cet axe introduit des fonctions qui prennent un type en entrée et renvoient un nouveau type en sortie. Un exemple classique est l'opérateur `Liste`. `Liste` n'est pas un type en soi, c'est une fonction qui attend un type (comme `Entier`) pour produire un type concret (`Liste d'Entiers`).
- **L'implication logique :** Cet axe dote le langage d'une puissance d'abstraction conceptuelle en permettant de définir des structures logiques complexes (comme des algèbres ou des structures catégoriques) directement au niveau des types, facilitant la modularité et la réutilisation des preuves.
- ### Synthèse : Le calcul des constructions comme point de convergence
  
  Le génie de l'architecture de Thierry Coquand a été de démontrer que l'unification de ces trois axes (qui formaient auparavant des systèmes logiques isolés) restait cohérente :
  
  $$\text{Calcul des Constructions (CoC)} = \text{Types Dépendants} (\lambda P) + \text{Polymorphisme} (\lambda 2) + \text{Opérateurs de Types} (\lambda \omega)$$
  
  En combinant ces trois axes, le CoC permet de traiter les types et les propositions de manière totalement uniforme : **les preuves sont des programmes, les propositions sont des types, et les univers permettent de manipuler le tout sans paradoxe.** C'est précisément cette triple structure que le compilateur d'un assistant de preuves (ou les modèles formels de DeepMind) vérifie ligne par ligne pour valider un raisonnement.