- En Lean 4, les **règles d'introduction et d'élimination** issues de la déduction naturelle ne sont pas seulement des concepts théoriques : elles se traduisent directement par des **tactiques** spécifiques ou par des structures de termes (via l'isomorphisme de Curry-Howard).
  
  Prouver une proposition en Lean consiste à appliquer ces règles pas à pas pour manipuler le but (*Goal*) et les hypothèses du contexte.
- ## 1. Vue d'ensemble des correspondances
  
  | Connecteur | Règle d'Introduction (Construire le but) | Règle d'Élimination (Utiliser une hypothèse) |
  
  | **Implication (\to)** | `intro h` | Application directe ou `apply` |
  
  | **Conjonction (\land)** | `constructor` ou les chevrons `⟨h1, h2⟩` | `rcases`, `cases` ou `.1`, `.2` |
  
  | **Disjonction (\lor)** | `left` ou `right` | `rcases h with h1 |
  
  | **Négation (\neg)** | `intro h` (car \neg A \equiv A \to \color{red}\bot) | `contradiction` ou application |
- ## 2. L'Implication (A \to B)
  
  L'implication exprime un raisonnement conditionnel.
- ### Introduction :  `intro`
  
  Pour prouver A \to B, on suppose A en lui donnant un nom (par exemple `h`), et le but devient B.
  
  ```
  example (A B : Prop) : A → B := by
  intro h
  -- Le contexte contient désormais h : A, et le but est B
  ```
- ### Élimination : L'application
  
  Si l'on dispose d'une hypothèse `h : A → B` et d'une preuve `ha : A`, l'élimination consiste à appliquer `h` à `ha` pour obtenir B. Cela s'écrit exactement comme une application de fonction : `h ha`.
  
  ```
  example (A B : Prop) (h : A → B) (ha : A) : B := by
  exact h ha
  ```
- ## 3. La Conjonction (A \land B)
  
  La conjonction matérialise le « ET ».
- ### Introduction :  `constructor`  ou  `⟨ , ⟩`
  
  Pour prouver A \land B, Lean doit diviser le travail en deux sous-buts : prouver A, puis prouver B.
  
  ```
  example (A B : Prop) (ha : A) (hb : B) : A ∧ B := by
  constructor
  · exact ha  -- Preuve du premier but (A)
  · exact hb  -- Preuve du second but (B)
  
  -- Variante directe avec des constructeurs anonymes :
  -- exact ⟨ha, hb⟩
  ```
- ### Élimination :  `rcases`  ou  `.left`  /  `.right`
  
  Si l'on a une hypothèse `h : A ∧ B`, on l'élimine en la décomposant pour extraire les preuves individuelles de A et de B.
  
  ```
  example (A B : Prop) (h : A ∧ B) : A := by
  rcases h with ⟨ha, hb⟩
  exact ha
  
  -- Variante par projection directe :
  -- exact h.left
  ```
- ## 4. La Disjonction (A \lor B)
  
  La disjonction matérialise le « OU ».
- ### Introduction :  `left`  et  `right`
  
  Pour prouver A \lor B, il faut choisir quelle branche on souhaite démontrer. La tactique `left` transforme le but en A, tandis que `right` le transforme en B.
  
  ```
  example (A B : Prop) (ha : A) : A ∨ B := by
  left
  exact ha
  ```
- ### Élimination : Le raisonnement par cas ( `rcases` )
  
  Si l'on sait que A \lor B est vrai (hypothèse `h`), on élimine ce connecteur en ouvrant deux branches exclusives : le cas où A est vrai, et le cas où B est vrai.
  
  ```
  example (A B C : Prop) (h : A ∨ B) (hA : A → C) (hB : B → C) : C := by
  rcases h with ha | hb
  · exact hA ha  -- Cas où A est vrai
  · exact hB hb  -- Cas où B est vrai
  ```
- ## 5. La Négation (\neg A) et l'Absurde (\bot)
  
  En Lean, \neg A est purement une notation pour définie par A \to \bot. Les règles d'introduction et d'élimination découlent donc de celles de l'implication.
- ### Introduction :  `intro`
  
  Pour prouver \neg A, on introduit l'hypothèse que A est vrai, et on cherche à obtenir une contradiction (\bot).
  
  ```
  example (A : Prop) (h : A → False) : ¬A := by
  intro ha
  exact h ha
  ```
- ### Élimination :  `contradiction`  ou  `False.elim`
  
  Si le contexte contient une proposition et sa négation (par exemple `ha : A` et `hna : ¬A`), le système est contradictoire. L'élimination du `False` permet de clore instantanément le but, conformément au principe d'explosion (*ex falso sequitur quodlibet*).
  
  ```
  example (A B : Prop) (ha : A) (hna : ¬A) : B := by
  contradiction 
  -- Détecte automatiquement le conflit entre ha et hna
  ```
- ## 6. Exemple complet : Équivalence constructive
  
  Voici la mise en pratique de ces règles pour démontrer de manière interactive que \neg(A \lor B) \to \neg A \land \neg B :
  
  ```
  example (A B : Prop) : ¬(A ∨ B) → ¬A ∧ ¬B := by
  intro h
  constructor
  · intro ha
    have hOr : A ∨ B := Or.inl ha
    exact h hOr
  · intro hb
    have hOr : A ∨ B := Or.inr hb
    exact h hOr
  ```
- ### Analyse des tactiques utilisées :
- `intro h` : **Introduction de l'implication**. On stocke l'hypothèse \neg(A \lor B).
- `constructor` : **Introduction de la conjonction**. Le but est divisé en deux parties : prouver \neg A puis prouver \neg B.
- `intro ha` : **Introduction de la négation** (qui agit comme une implication). On suppose A.
- `Or.inl ha` : **Introduction de la disjonction** à gauche (équivalent de la tactique `left` en mode terme) pour construire A \lor B.
- `h hOr` : **Élimination de l'implication** (Modus Ponens) : on applique l'hypothèse `h` à `hOr` pour atteindre la contradiction \bot requise. La seconde branche pour \neg B suit une logique identique.
  
  Souhaitez-vous analyser les règles d'introduction et d'élimination spécifiques aux quantificateurs (\forall et \exists) ?