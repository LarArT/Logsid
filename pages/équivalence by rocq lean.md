- Dans **Lean 4**, la philosophie est très proche de celle de SSReflect : on cherche à garder un contrôle strict sur le nom des hypothèses et à enchaîner les actions de manière fluide.
  
  Voici comment retrouver les mécanismes fondamentaux de SSReflect transposés dans le style des tactiques de Lean 4.
- ## 1. L'équivalent du  `by`  : Le bloc  `by`  et  `exact`  /  `trivial`
  
  En Lean 4, le mot-clé `by` ouvre le mode tactique (ce qui est global à tout le système). Pour clore une preuve immédiatement de façon robuste comme le fait `by []` en SSReflect, on utilise principalement `exact` ou des tactiques de fermeture automatique.
  
  ```
  lemma exemple_infra (A B : Prop) : A → B → A := by
  intro hA hB
  -- "Soient hA l'hypothèse que A est vrai, et hB l'hypothèse que B est vrai."
  
  exact hA
  -- "La preuve est immédiate car le but à prouver correspond exactement à l'hypothèse hA."
  ```
- ## 2. L'équivalent de l'introduction ( `move=>` ) :  `intro`  et  `intros`
  
  Pour faire descendre des variables ou des hypothèses du but vers le contexte (ce que fait `move=> x hX` en SSReflect), Lean 4 utilise la tactique `intro` (ou `intros`).
  
  ```
  lemma exemple_intro (A B : Prop) : A → B → A := by
  intro hA hB
  -- "Introduisons l'hypothèse hA pour A et l'hypothèse hB pour B dans notre contexte de travail."
  
  exact hA
  -- "Par l'hypothèse hA, l'objectif est directement atteint."
  ```
- ## 3. L'équivalent de la généralisation ( `move: hX` ) :  `revert`
  
  Pour remonter une hypothèse du contexte vers le but (ce que fait `move: hX` en SSReflect afin de la préparer pour une induction par exemple), Lean 4 utilise `revert`.
  
  ```
  -- Supposons que hA soit dans le contexte :
  revert hA
  -- "Remontons l'hypothèse hA dans l'objectif pour la transformer à nouveau en une implication."
  ```
- ## 4. L'équivalent de l'analyse de cas ( `case=>` ) :  `rcases`  ou  `cases`
  
  Pour détruire un connecteur (comme un "et" \land) ou analyser des cas immédiatement en nommant les hypothèses, Lean 4 utilise de manière très élégante la tactique `rcases` (issue de *Mathlib*) avec des motifs de flèches ou de crochets, ou la tactique native `cases`.
  
  ```
  lemma exemple_conj (A B : Prop) : A ∧ B → A := by
  intro h
  -- "Soit h l'hypothèse de la conjonction de A et B."
  
  rcases h with ⟨hA, hB⟩
  -- "Décomposons l'hypothèse h pour obtenir séparément l'hypothèse hA et l'hypothèse hB."
  
  exact hA
  -- "Le but étant de prouver A, l'hypothèse hA permet de conclure immédiatement."
  ```
- ## 5. L'équivalent de l'application ( `apply:` ) :  `apply`
  
  L'application de lemme reste très similaire. En Lean 4, si on veut appliquer un théorème en lui passant immédiatement une hypothèse du contexte, on peut le faire directement entre parenthèses.
  
  ```
  lemma exemple_architecture (A B : Prop) : (A → B) → A → B := by
  intro himpl hA
  -- "Soit himpl l'implication de A vers B, et hA l'hypothèse que A est vrai."
  
  apply himpl
  -- "Par application de la règle d'implication himpl, notre nouvel objectif est de démontrer A."
  
  exact hA
  -- "L'hypothèse hA fournit directement la preuve de A."
  ```
- ## 6. L'équivalent de la récurrence ( `elim: n => [...]` ) :  `induction`
  
  Pour lancer une récurrence et nommer les variables ainsi que l'hypothèse de récurrence (ce que fait `elim: n => [| n' IHn']`), Lean 4 utilise `induction ... with`.
  
  ```
  -- Exemple structurel sur un entier naturel n
  induction n with
  | zero =>
  -- "Traitons le cas de base où n est égal à zéro."
  sorry
  | succ n' IHn' =>
  -- "Traitons le cas inductif pour le successeur de n', en disposant de l'hypothèse de récurrence IHn'."
  sorry
  ```
- ### Tableau de correspondance rapide
  
  | Action SSReflect | Équivalent Lean 4 | Fonction centrale |
  
  | `by []` | `by exact ...` ou `trivial` | Clore la preuve si c'est immédiat |
  
  | `move=> x h` | `intro x h` | Faire descendre dans le contexte |
  
  | `move: h` | `revert h` | Remonter dans le but (piles) |
  
  | `case=> h1 h2` | `rcases h with ⟨h1, h2⟩` | Destructurer une hypothèse / Cas |
  
  | `apply: lemme` | `apply lemme` | Appliquer une règle ou un théorème |
  
  | `elim: n => [...]` | `induction n with ...` | Lancer un raisonnement par récurrence |