- **Rocq** (le nouveau nom officiel du célèbre assistant de preuve **Coq**, formalisé en 2024/2025) repose lui aussi sur le calcul des constructions inductives et l'isomorphisme de Curry-Howard.
  
  Comme en Lean, les règles d'introduction et d'élimination de la déduction naturelle s'y traduisent par des tactiques spécifiques en mode preuve (`Proof. ... Qed.`).
  
  Voici la correspondance exacte des règles et la transcription du même exercice en Rocq.
- ## 1. Vue d'ensemble des correspondances : Lean vs Rocq
  
  Les concepts sont identiques, seules les dénominations des tactiques changent légèrement :
  
  | Connecteur | Règle d'Introduction | Règle d'Élimination |
  
  | **Implication (\to)** | `intro` | `apply` ou application directe |
  
  | **Conjonction (\land)** | `split` | `destruct` |
  
  | **Disjonction (\lor)** | `left` ou `right` | `destruct` (génère deux sous-buts) |
  
  | **Négation (\neg)** | `intro` (car \neg A \equiv A \to \text{False}) | `contradiction` ou `exfalso` |
- ## 2. Traduction de l'exercice : \neg(A \lor B) \to \neg A \land \neg B
  
  Voici le code exact tel qu'on l'écrit en Rocq (Coq) :
  
  ```
  Theorem not_or_to_and_not : forall A B : Prop, ~ (A \/ B) -> ~ A /\ ~ B.
  Proof.
  intros A B h.
  split.
  - intro ha.
    assert (hOr : A \/ B).
    + left. exact ha.
    + apply h in hOr. destruct hOr.
  - intro hb.
    assert (hOr : A \/ B).
    + right. exact hb.
    + apply h in hOr. destruct hOr.
  Qed.
  ```
- ## 3. Analyse pas à pas des règles appliquées
- ### L'Implication et le Contexte
- `intros A B h.` : **Règle d'introduction**. On introduit les variables propositionnelles A et B, ainsi que l'hypothèse de gauche h : \neg(A \lor B). Le but devient \neg A \land \neg B.
- ### La Conjonction (\land)
- `split.` : **Règle d'introduction**. Cette tactique sépare le but A \land B en deux sous-buts distincts : prouver \neg A (géré par la première puce `-`), puis prouver \neg B (géré par la seconde puce `-`).
- *(Pour l'élimination d'un \land, on utiliserait la tactique `destruct h as [ha hb]`)*.
- ### La Négation (\neg)
- En Rocq, `~ A` est une notation pour `A -> False`.
- `intro ha.` : **Règle d'introduction**. Pour prouver `~ A`, on suppose `ha : A` et le but devient `False` (l'absurde).
- ### La Disjonction (\lor)
- `assert (hOr : A \/ B).` : Permet d'ouvrir une parenthèse pour s'isoler et construire la disjonction.
- `left.` : **Règle d'introduction** à gauche. Le sous-but devient A. Comme on a `ha : A` dans le contexte, `exact ha.` clôt ce morceau.
- *(Pour le second sous-but principal, on utilise `right.` pour l'introduction à droite).*
- ### L'Élimination du Faux et Modus Ponens
- `apply h in hOr.` : **Règle d'élimination de l'implication**. On applique l'hypothèse h (qui est (A \lor B) \to \text{False}) à notre preuve hOr : A \lor B. L'hypothèse hOr se transforme alors en une preuve de `False`.
- `destruct hOr.` : **Règle d'élimination du Faux** (principe d'explosion). Puisque l'on a obtenu une contradiction absolue (`False`), le but courant est résolu de manière triviale.
- ### Une variante plus concise (style idiomatique Rocq)
  
  Rocq permet d'enchaîner l'élimination des connecteurs directement lors de l'introduction en utilisant des motifs d'introduction (*intro-patterns*) :
  
  ```
  Theorem not_or_to_and_not_short : forall A B : Prop, ~ (A \/ B) -> ~ A /\ ~ B.
  Proof.
  intros A B h.
  split; intro hX.
  - apply h. left. exact hX.
  - apply h. right. exact hX.
  Qed.
  ```
  
  *Ici, le point-virgule `;` applique la tactique `intro hX` aux deux sous-buts générés par `split`. L'application de `apply h` attend directement une preuve de A \lor B, qui lui est fournie immédiatement par les règles d'introduction `left` et `right`.*
  
  Souhaitez-vous observer l'exercice inverse, à savoir la preuve classique (qui requiert l'exclusion du tiers exclu) de \neg(A \land B) \to \neg A \lor \neg B en Rocq ?