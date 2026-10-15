- Voici le tableau adapté pour Logseq, avec l'ensemble des expressions et variables mathématiques soigneusement encadrées par des symboles dollars `$` :
- Le **triangle de Curry-Howard-Lambek** (parfois appelé la *trinité algorithmique*) est l'extension naturelle de la correspondance de Curry-Howard. Il établit une équivalence profonde et formelle entre trois domaines des mathématiques et de l'informatique théorique : la **Logique**, la **Théorie des Types** (Programmation) et la **Théorie des Catégories**.
- ## 1. Les trois sommets du triangle
  
  Chaque concept fondamental dans un domaine possède un équivalent exact dans les deux autres :
  
  ```
  Logique (DÉMONSTRATION)
                 /          \
                /            \
               /              \
              /                \
  Théorie des Types  ─────────  Théorie des Catégories
  (CALCUL / CODE)                (STRUCTURE)
  ```
  
  | Logique (Séquents / Déduction naturelle) | Théorie des Types (Langages fonctionnels) | Théorie des Catégories (Structures algébriques) |
  
  | **Proposition** A | **Type** A | **Objet** A |
  
  | **Preuve / Dérivation** \pi : A | **Programme / Terme** t : A | **Morphisme / Flèche** f : 1 \to A |
  
  | **Implication** A \implies B | **Type Fonction** A \to B | **Objet Exponentiel** B^A |
  
  | **Conjonction** A \land B | **Type Produit (Paire)** A \times B | **Produit Catégoriel** A \times B |
  
  | **Disjonction** A \lor B | **Type Somme (Union disjointe)** A + B | **Croduit / Coproduit** A \amalg B |
  
  | **Vrai** (\top) | **Type Unité** (`Unit` / `()`) | **Objet Terminal** 1 |
  
  | **Faux / Absurde** (\bot) | **Type Vide** (`Void` / `Never`) | **Objet Initial** 0 |
  
  | **Modus Ponens** / Élimination de \implies | **Application de fonction** f(x) | **Évaluation** \text{ev} : B^A \times A \to B |
  
  | **Coupure / Normalisation** | **Évaluation / Réduction \beta** | **Composition de morphismes** g \circ f |
- ## 2. Le rôle clé de Joachim Lambek
  
  Là où **Curry et Howard** ont montré que *prouver une formule équivaut à exécuter un programme*, **Joachim Lambek** (dans les années 1970–1980) a apporté le troisième pilier : **la géométrie structurelle**.
  
  Il a prouvé que :
- La **logique intuitionniste** (sans tiers exclu) et le **\lambda-calcul simplement typé** sont la théorie interne des **catégories cartésiennes fermées (CCC)**.
- Une preuve ou un programme n'est autre qu'une **trajectoire/morphism** dans un espace catégoriel.
  
  > 
  
  **Ce que cela change :**
- La **Logique** donne le *sens* (ce qui est vrai).
- Le **Calcul** donne le *mouvement* (comment on l'exécute).
- La **Catégorie** donne la *forme* (l'espace algébrique dans lequel cela vit).
- ## 3. L'extension aux systèmes modernes (dont HoTT)
  
  Le triangle s'étend à des niveaux d'expressivité plus élevés :
  
  ```
  Logique Ordre 1 / Dépendante  <--->  Théorie des Types Dépendants (MLTT)  <--->  Topos Éléments / Faisceaux
  Logique Homotopique           <--->  HoTT (Cubical)                      <--->  $(\infty, 1)$-Topos
  ```
- **Quantificateur universel (\forall x : A, B(x)) :** Devient un **Produit dépendant (\Pi-type)** en types, et une **limite / section** en catégories.
- **Quantificateur existentiel (\exists x : A, B(x)) :** Devient une **Somme dépendante (\Sigma-type)** en types, et un **colimite / objet coproduit dépendant** en catégories.
- **Égalité / Identité (x =_A y) :** Devient le **Type Identité** (un espace de chemins en HoTT), interprété catégoriquement comme le **fibré de diagonale** ou un **objet chemin** dans un \infty-topos.
  
  > 
  
  **L'intuition fondamentale :** Une preuve n'est pas une simple donnée textuelle ou abstraite. C'est un **programme exécutable** qui circule le long des **morphismes géométriques** d'un espace (la catégorie).
- | Type Theory | Logic | Set Theory | Homotopy Theory |
  
  | A (type)| proposition | set | space |
  
  | x : A (terme) | proof | element | point |
  
  | \emptyset, 1 | \bot, \top | \emptyset, \{\emptyset\} | \emptyset, * |
  
  | A \times B | A and B | set of pairs | product space |
  
  | A + B | A or B | disjoint union | coproduct |
  
  | A \to B | A implies B | set of functions | function space |
  
  | P : A \to \text{Type} (type dependant | predicate | family of sets | fibration |
  
  | f : \prod_{x:A} P(x) | conditional proof | family of elements | section |
  
  | \prod_{x:A} P(x) | \forall x . P(x) | product | space of sections |
  
  | \sum_{x:A} P(x) | \exists x . P(x) | disjoint union | total space |
  
  | p : x =_A y | proof of equality | x = y | path from x to y |
  
  | \sum_{x,y:A} x =_A y | equality relation | diagonal | path space for A |