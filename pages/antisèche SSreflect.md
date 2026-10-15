- Voici la conversion complète et fidèle du document de référence (Cheat Sheet SSReflect) au format Markdown.
  
  La mise en page a été structurée de manière claire et aérée à l'aide de tableaux, de blocs de code et d'une hiérarchie de titres pour faciliter la lecture et la navigation.
- # SSReflect Cheat Sheet
- ## 1. Terminology & Basics
- ### Context and Stack
- **Context:** Contains the declared variables and hypotheses (e.g., `x: T`, `S: {set T}`, `px: x \in S`).
- **The Bar (`|`):** Separates the context (top) from the goal (bottom).
- **Goal:** The statement that needs to be proven.
- **Assumptions (Stack):** The list of premises currently on the stack (below the bar, before the conclusion). The **Top** is the first assumption.
- **Conclusion:** The final statement to be proven.
- ## 2. Pushing and Popping the Stack
- ### Popping from the Stack ( `=>` )
  
  *Note: In these examples, `cmd` represents any command/tactique. If it does nothing (like `move`), we focus only on the effect of the intro pattern.*
  
  | Command / Pattern | Initial State (Goal / Stack) | Final State (Context & Goal) | Description |
  
  | **cmd=> x px** | \forall x, Px \rightarrow Qx \rightarrow C | `x: T`
  `px: Px`
  Goal: `Qx -> C` | Runs `cmd`, pops **Top**, puts it in the context naming it `x`, then pops the new **Top** and names it `px`. |
  
  | **cmd=> [lx xs] //** | (First branch trivial)
  Second branch: A \land B \rightarrow C \rightarrow D | `pa: A`
  `pb: B`
  Goal: `C -> D` | Runs `cmd`, reasons by cases on **Top**. Clears trivial goals (`//`). If immediately after `case` or `elim`, it names variables in different branches. |
  
  | **cmd=> /(x) h** | `x: nat`
  Goal: (\forall n, Pn) \rightarrow G | `x: nat`
  `h: Px`
  Goal: G | Introduces `h` specialized to `x`. |
  
  | **cmd=> /andP [pa pb]** | Goal: A \land B \rightarrow C \rightarrow D | `pa: A`
  `pb: B`
  Goal: `C -> D` | Runs `cmd`, applies the view `andP` to **Top**, destructs the conjunction, and introduces them as `pa` and `pb`. |
  
  | **cmd=> /= px** | `z: nat`
  `px: Px`
  Goal: Qx \rightarrow Rx | `x: nat`
  Goal: Qx \rightarrow Rx | Runs `cmd`, simplifies the goal (`/=`), then clears (discards) `px` from the context. |
  
  | **cmd=> [y -> {x}]** | `x: nat`
  Goal: (\exists y, x = y \land Qy) \rightarrow Px | `y: nat`
  Goal: Qy \rightarrow Py | Destructs the existential, introduces `y`, rewrites with **Top** left-to-right, discards the equation, and clears `x`. |
- ### Pushing to the Stack ( `:` )
  
  *Note: In these examples, `cmd` is not `apply` or `exact`. We display the goal state just before `cmd` is run.*
  
  | Command / Pattern | Initial State (Context & Goal) | Final State (Goal / Stack) | Description |
  
  | **cmd: (x) y** | `x, y: nat`
  `px: Px`
  Goal: `Qxy` | Goal: `forall x0 y0, ...` | Pushes `y` then `x` on the stack. `y` is also cleared from the context. |
  
  | **cmd: -{2}x (erefl x)** | `x: nat`
  `px: Px`
  Goal: `Px` | Goal: \forall x_0, x_0 = x \rightarrow P x | Pushes the type of `(erefl x)`, then pushes `x` on the stack binding all but the second occurrence. |
  
  | **cmd: +1 {px}** | `x: nat`
  `px: P x`
  Goal: \forall x_0, x < x_0 | `x: nat`
  Goal: 0 < \text{size}(x :: xs) \rightarrow P(x :: xs) | Clears `px` and generalizes the goal with respect to the first match of the pattern `+1`. |
- ## 3. Core Proof Commands
- **by []** Proves the goal by trivial means, or fails if it cannot. E.g., solves 0 \le n.
- **exact: H** Applies `H` to the current goal and asserts all remaining goals (if any) are trivial. Equivalent to `by apply: H`.
- **case: ab** Eliminates a conjunction or disjunction (where `ab : A \land B` or `ab : A \lor B`).
- **case: (leqP ab)** Reasons by cases using the `leqP` specification lemma (compares `a` and `b`).
- **elim: s** Performs induction on `s` (where `s` is of type `seq nat`).
- **elim/last_ind: s** Starts an induction on `s` using the alternative induction principle `last_ind` (induction from the end of the sequence).
- **have pa : Pa** Opens a new subgoal for `Pa`. Once resolved, introduces a new entry named `pa` in the context.
- ## 4. Rewrite and Simplification Rules
- ### Basic Syntax
- **rewrite Eab** : Rewrites with the equality `Eab : a = b` from left to right.
- **rewrite -Eab** : Rewrites with the equality `Eab : a = b` from right to left.
- **rewrite (Eab)** : Unfolds the definition of `Eab`.
- **rewrite /=** : Simplifies the goal (similar to `simpl`).
- **rewrite //=** : Simplifies the goal and solves trivial subgoals.
- **rewrite [a]/(0+a) -/c** Simplifies the goal, changes `a` into `0+a`, and finally folds back the local definition `c`.
- **rewrite Eab {Eac}** Rewrites with `Eab`, then clears `Eac` from the context.
- **rewrite lemi ?lem2 //** Rewrites using `lemi` with premises, then attempts to solve side conditions with `lem2`, and finally clears remaining trivial goals with `//`.
- ### Advanced Rewrite Patterns
- **rewrite [pat]lem [in pat2]lem2 [X in pat3] lem3** 1. Rewrites the subterms selected by `pat` with `lem`.
  2. In the subterms selected by `pat2`, matches the pattern inferred from LHS of `lem2` and rewrites them.
  3. In the subterms selected by `pat3`, rewrites with `lem3` the subterms identified by `X` exactly.
- **rewrite (3) [in X in pat1]lem1** Identifies subterms using `X` within `pat1`, and rewrites only the third occurrence.
  *Example:* `rewrite (3) [in X in f X]E` where `E : a = c` transforms `a + f a (a + a)` into `f a (c + a) + a`.
- **rewrite [e in X in pat1]lem1** Like above, but overrides the pattern inferred from `lem1` with `e`.
- **rewrite [e as X in pat1]lem1** Matches `pat1[X := e]` instead of just `pat1`.
- **rewrite/def1 [pat]/term/=** Unfolds all occurrences of `def1`, matches the goal against `pat` to replace its occurrences with `term`, and finally simplifies.
- **rewrite 3?lem2 // {hyp} => x px** Rewrites between 0 to 3 times with `lem2`, tries to solve all goals, clears `hyp`, and introduces `x` and `px`.
- ## 5. Pattern Matching Detailed Rules
  
  When a pattern is matched, the following steps occur:
- The goal is traversed outside-in, left-to-right, looking for verbatim occurrences of the **key** (head symbol).
- Subterms with matching keys are higher-order matched (up to definition unfolding and computation) against the pattern.
- If matching fails, the next matching key is tried.
- If it succeeds, that subterm is considered the unique instance of the pattern.
- All identical copies of this instance are selected.
- Occurrence numbers (e.g., `{2 4}`) refer to this final list of selected subterms.
- ### Context Localization ( `set` )
- **set n := {2 4}(_+b)** Replaces the 2nd and 4th occurrences matching the pattern `(_+b)` with a local definition named `n` in the context.
  *Example:* Transforms `a + c + (a + b) + (a + b) = a + (a + b) + (0 + a + b) + c`
  into `a + c + (a + b) + n = a + (a + b) + n + c` (where `n := a + b`).
- ## 6. Reflect, Views & Idioms
- ### Reflect Concepts
- **reflect P b** : States that the proposition `P` is logically equivalent to the boolean `b`.
  
  | Proposition | Boolean | Relation | Equivalent Condition |
  
  | `P: Prop` | `b: bool` | `reflect P b` | `b -> P` and `P -> b` |
- **apply: (iffP V)** Proves a reflection goal by applying the view lemma `V` to the propositional part of `reflect` (e.g., `apply: (iffP idP)`).
- **apply/V1/V2** Proves boolean equalities by interpreting them as double implications, applying `V1` to the LHS and `V2` to the RHS (e.g., `apply/idP/negP`) .
- **rewrite: (eqP Eab)** Rewrites using the boolean equality `Eab : a == b` by turning it into a propositional equality via `eqP`.
- ### Common Idioms
- **case: b => [h1 h2 h3]** Pushes `b` on the stack, reasons by cases, then pops `h1` in the first branch, and `h2`, `h3` in the second.
- **have /andP [x /eqP ->] : Pa && b == c** Opens a subgoal for `Pa && b == c`. Once proved, applies the `andP` view, destructs the conjunction, introduces `x`, applies the `eqP` view to turn `b == c` into `b = c`, rewrites with it, and discards the equation.
- **elim: n.+1 {-2}n (ltnSn n) => {n}// n** General induction over `n`. The first goal has a false assumption (\forall n, n < 0) and is solved by `//`.
- ## 7. Notations and Libraries
- ### Numbers ( `nat` )
- `n.+1` := `succn n`
- `n.-1` := `predn n`
- `m + n` := `addn m n`
- `m - n` := `subn m n`
- `m <= n` := `leq m n`
- `m < n` := `m.+1 <= n`
- `m * n` := `muln m n`
- `n.*2` := `double n`
- `m ^ n` := `expn m n`
- `n!` := `factorial n`
- `m %/ d` := `divn m d`
- `m %% d` := `modn m d`
- `m == n %[mod d]` := `m %% d == n %% d`
- `m %| d` := `dvdn m d`
- `p.-nat` := `pnat p`
- ### Sequences / Lists ( `seq T` )
- `x :: s` := `cons x s`
- `[::]` := `nil`
- `[:: x1]` := `x1 :: [::]`
- `[:: x & z]` := `x :: z`
- `[:: x1, x2, ..., xn & s]` := `x1 :: x2 :: ... :: xn :: s`
- `[:: x1, x2, ..., xn]` := `x1 :: x2 :: ... :: xn :: [::]`
- `s1 ++ s2` := `cat s1 s2`
- ### Miscellaneous Notations
- `f1 \o f2` := `comp f1 f2` (function composition)
- `x \in A` := `in_mem x (mem A)`
- `x \notin A` := `~~ (x \in A)`
- `[P1, P2 & P3]` := `and3 P1 P2 P3`
- `m <= n <= p` := `(m <= n) && (n <= p)`
- `#|A|` := `card (mem A)` (cardinality of set `A`)
- `n-tuple` := tuple of size n
- `'I_n` := ordinal n (finite set of natural numbers < n)
- `f1 =1 f2` := `eqfun f1 f2` (extensional equality of functions)
- `b1 (+) b2` := `addb b1 b2` (boolean XOR)
- ### Iterated Operations ( `bigop` )
  
  *Note: In their general form, iterated operations are displayed in prefix form. The string "big" occurs in every lemma concerning iterated operations.*
- `\big[op/idx]_(i < n) F`
- `\big[op/idx]_(i < n | P) F`
- `\big[op/idx]_(i \in A) F`
- `\sum_i F` (Iterated addition)
- `\prod_i F` (Iterated multiplication)
- `\max_i F` (Iterated maximum)
- `\bigcap_i F` (Iterated intersection)
- `\bigcup_i F` (Iterated union)
- ## 8. Searching the Library
- **Search** Finds lemmas in the active context.
- **Search addn (_) "C" in ssrnat** Searches for all theorems with no constraints on the main conclusion, talking about the `addn` constant, matching anywhere the pattern `(_)` and having a name containing the character `"C"` inside the module `ssrnat`.