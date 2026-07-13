- **SSReflect** (qui fait désormais partie intégrante de Coq / Rocq) introduit une approche très fluide et standardisée pour écrire des preuves. Contrairement aux tactiques classiques qui accumulent les étapes, SSReflect repose sur un principe clé : **faire circuler l'information** entre les hypothèses (le contexte) et le but à prouver (le goal).
  
  Voici une explication simple des mécanismes fondamentaux avec la structure demandée.
- ## 1. La base : L'écriture en mode tactique ( `by` )
  
  En SSReflect, le mot-clé `by` est utilisé pour clore une preuve ou une sous-étape. Il ne se contente pas de dire "fin", il essaie activement de résoudre le but courant en appliquant des simplifications de base, des réflexions booléennes ou des trivialités. Si la tactique qui suit `by` ne termine pas la preuve, Coq renvoie une erreur.
- ## 2. Les deux mouvements fondamentaux :  `move`  et  `case`
  
  Toute la philosophie de SSReflect tourne autour de la gestion de la pile de preuves. On utilise principalement des symboles de "flèches" (`=>` et `:`) combinés avec des tactiques.
- ### A. Introduire des éléments dans le contexte ( `=>` )
  
  On utilise `move=>` pour faire descendre des variables ou des hypothèses du but vers notre contexte de travail.
  
  ```
  Lemma exemple_infra (A B : Prop) : A -> B -> A.
  Proof.
  move=> hA hB.
  -- "Soient hA l'hypothèse que A est vrai, et hB l'hypothèse que B est vrai."
  
  by [].
  -- "La preuve est immédiate car le but A est exactement l'hypothèse hA."
  Qed.
  ```
- ### B. Remonter des éléments dans le but ( `:` )
  
  À l'inverse, si on veut appliquer une induction ou travailler sur une hypothèse spécifique, on la "remonte" dans le but en utilisant `:` associé à `move`.
  
  ```
  -- Si hA est dans le contexte et qu'on veut le remettre dans le but :
  move: hA.
  -- "Considérons à présent le cas où l'hypothèse hA est vraie dans notre objectif."
  ```
- ### C. L'analyse de cas immédiate ( `case` )
  
  La tactique `case` permet de faire une disjonction de cas ou de détruire un connecteur logique (comme un "et" \land). Combinée avec `=>`, elle devient extrêmement puissante.
  
  ```
  Lemma exemple_conj (A B : Prop) : A /\ B -> A.
  Proof.
  case=> hA hB.
  -- "Supposons que la conjonction est vraie, ce qui nous donne deux cas distincts : l'hypothèse hA et l'hypothèse hB."
  
  by [].
  -- "Le but étant A, l'hypothèse hA permet de conclure directement."
  Qed.
  ```
- ## 3. L'application et la généralisation :  `apply`  et  `elim`
- ### A. Appliquer un théorème ( `apply` )
  
  Pour utiliser une règle ou un lemme existant, on utilise `apply`. En SSReflect, on peut directement charger des hypothèses au moment de l'application.
  
  ```
  Lemma exemple_architecture (A B : Prop) : (A -> B) -> A -> B.
  Proof.
  move=> himpl hA.
  -- "Soit himpl l'implication de A vers B, et hA l'hypothèse que A est vrai."
  
  apply: himpl.
  -- "Par application de la règle d'implication himpl, il nous suffit maintenant de démontrer A."
  
  by [].
  -- "Le but étant A, l'hypothèse hA conclut la démonstration."
  Qed.
  ```
- ### B. Le raisonnement par récurrence ( `elim` )
  
  Pour les types inductifs (comme les entiers naturels), `elim` lance la récurrence et permet de nommer immédiatement l'hypothèse de récurrence grâce aux chevrons `=>`.
  
  ```
  -- Exemple théorique sur un entier n
  elim: n => [| n' IHn'].
  -- "Procédons par récurrence sur n. Cas de base (zéro), puis cas inductif pour n' avec l'hypothèse de récurrence IHn'."
  ```
- ## En résumé
  
  SSReflect évite d'avoir des noms d'hypothèses générés aléatoirement par Coq. On contrôle tout sur une seule ligne :
- **Tactique** (ex: `move`, `case`, `apply`)
- **Action sur le contexte** (ex: `:` pour pousser vers le but)
- **Action d'introduction** (ex: `=>` suivi des noms choisis pour ranger dans le contexte)