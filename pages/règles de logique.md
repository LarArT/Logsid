- Pour rendre le compte rendu compatible avec le format **LGSSEq**, la structure a été entièrement réorganisée
  
  Toutes les formules de logique mathématique, règles d'inférence et systèmes de séquents sont désormais encapsulés sous forme d'équations hors-texte rigoureuses au format LaTeX, isolées du texte brut. L'arborescence des concepts a également été aplatie pour garantir une lecture séquentielle et une compatibilité maximale avec les parseurs de documents structurés.
- [[implémentation des règles de logique en rocq et Lean]]
- ## 1. La Déduction Naturelle (Fondation)
  La déduction naturelle formalise le raisonnement mathématique en manipulant des jugements de la forme \Gamma \vdash A, signifiant que sous les hypothèses du contexte \Gamma, on démontre la proposition A. Elle repose sur un équilibre entre des règles d'introduction et des règles d'élimination.
- ### Implication
  L'introduction de l'implication ajoute l'hypothèse à gauche du séquent, tandis que son élimination correspond au *Modus Ponens*.
  $$ \frac{\Gamma, A \vdash B}{\Gamma \vdash A \to B} (\to I) $$
  $$ \frac{\Gamma \vdash A \to B \quad \Gamma \vdash A}{\Gamma \vdash B} (\to E) $$
- ### Conjonction
  L'introduction de la conjonction exige la preuve des deux composants. L'élimination permet d'isoler l'un des membres.
  $$ \frac{\Gamma \vdash A \quad \Gamma \vdash B}{\Gamma \vdash A \land B} (\land I) $$
  $$ \frac{\Gamma \vdash A \land B}{\Gamma \vdash A} (\land E_1) \quad \frac{\Gamma \vdash A \land B}{\Gamma \vdash B} (\land E_2) $$
- ### Disjonction
  L'introduction valide la disjonction dès qu'un membre est prouvé. L'élimination correspond au raisonnement par cas.
  $$ \frac{\Gamma \vdash A}{\Gamma \vdash A \lor B} (\lor I_1) \quad \frac{\Gamma \vdash B}{\Gamma \vdash A \lor B} (\lor I_2) $$
  $$ \frac{\Gamma \vdash A \lor B \quad \Gamma, A \vdash C \quad \Gamma, B \vdash C}{\Gamma \vdash C} (\lor E) $$
- ### Absurde et Négation
  La négation est définie par la relation \neg A \equiv A \to \bot. La logique classique se distingue par l'inclusion de la règle du raisonnement par l'absurde (RAA), en plus de l'élimination du faux (*Ex Falso*).
  $$ \frac{\Gamma \vdash \bot}{\Gamma \vdash A} (\bot E) $$
  $$ \frac{\Gamma, \neg A \vdash \bot}{\Gamma \vdash A} (RAA) $$
- ## 2. Le Calcul des Séquents et Règles Structurelles
  Le calcul des séquents formalise les opérations directement sur des couples de contextes de la forme \Gamma \vdash \Delta. Il explicite la gestion de la mémoire logique via les règles structurelles.
- ### Règles d'Identité
  L'axiome initialise la preuve, tandis que la règle de coupure (*Cut*) permet l'utilisation de lemmes intermédiaires.
  $$ \frac{}{A \vdash A} (Ax) $$
  $$ \frac{\Gamma \vdash A, \Delta \quad \Gamma', A \vdash \Delta'}{\Gamma, \Gamma' \vdash \Delta, \Delta'} (Cut) $$
- ### Règles Structurelles Gauchies
  Ces règles contrôlent la persistance et la duplication des hypothèses dans le contexte gauche.
  * **Affaiblissement (Weakening) :**
   $$ \frac{\Gamma \vdash \Delta}{\Gamma, A \vdash \Delta} (W_L) $$
  * **Contraction :**
   $$ \frac{\Gamma, A, A \vdash \Delta}{\Gamma, A \vdash \Delta} (C_L) $$
- ## 3. Raffinements Successifs et Déclinaisons
- ### La Logique Intuitionniste
  La logique intuitionniste restreint la logique classique en interdisant le raisonnement par l'absurde non constructif.
  * **Raffinement LGSSEq :** La partie droite du séquent est contrainte à contenir au maximum une formule unique.
   $$ \Gamma \vdash A \quad \text{ou} \quad \Gamma \vdash \emptyset $$
  * **Conséquence :** Les principes du tiers-exclu A \lor \neg A et de la double négation \neg\neg A \to A ne sont plus des théorèmes du système.
- ### La Logique Linéaire
  La logique linéaire supprime les règles structurelles d'affaiblissement (W) et de contraction (C). Les formules deviennent des ressources qui s'épuisent lors de leur utilisation.
  * **Dédoublement des connecteurs :** Les connecteurs se divisent en versions multiplicatives (partage strict des ressources) et additives (choix parmi les ressources).
   $$ \otimes \text{ (multiplicatif)}, \quad \multimap \text{ (implication)}, \quad & \text{ (additif)}, \quad \oplus \text{ (choix)} $$
  * **Contrôle exponentiel :** Les modalités de contrôle réintroduisent localement la logique classique pour les ressources infinies.
   $$ !A \quad \text{(autorisation de W et C à gauche)} $$
- ### Les Logiques Modales
  Les logiques modales étendent le système avec les opérateurs de nécessité \Box et de possibilité \Diamond.
  * **Système K (Base) :**
   $$ \Box(A \to B) \to (\Box A \to \Box B) $$
  * **Axiome de Réflexivité (Système T) :**
   $$ \Box A \to A $$
  * **Axiome de Transitivité (Système S4) :**
   $$ \Box A \to \Box\Box A $$
- ### Les Logiques Temporelles
  Les logiques temporelles raffinent les opérateurs modaux pour formaliser l'évolution d'un système au cours du temps.
  * **Logique Temporelle Linéaire (LTL) :** Modélise un temps discret et déterministe via l'opérateur d'instant suivant \circ et l'opérateur de permanence \Box.
   $$ \circ(\neg A) \leftrightarrow \neg \circ A $$
   $$ \Box A \leftrightarrow (A \land \circ \Box A) $$
  * **Induction Temporelle :** Formule le principe de récurrence sur l'axe du temps.
   $$ \text{Si } \vdash A \to \circ A, \quad \text{alors } \vdash A \to \Box A $$
  * **Computation Tree Logic (CTL) :** Introduit des quantificateurs sur des arbres de calcul pour les structures de temps arborescentes, associant un quantificateur de chemin (A pour tout, E pour il existe) à un opérateur temporel (X pour suivant, G pour global).
   $$ \neg AX , A \leftrightarrow EX , \neg A $$
   $$ AG , A \leftrightarrow A \land AX , AG , A $$
- ## 4. Synthèse des Systèmes Informatiques et Logiques
  | Système Logique | Structure du Séquent | Règle Restreinte / Ajoutée | Champ d'Application |
  |---|---|---|---|
  | **Classique** | \Gamma \vdash \Delta | Aucune restriction | Mathématiques générales |
  | **Intuitionniste** | \Gamma \vdash A | Cardinalité du membre droit \le 1 | Calculabilité, Typage (Curry-Howard) |
  | **Linéaire** | \Gamma \vdash \Delta | Suppression de (W) et (C) | Gestion de ressources, Protocoles |
  | **Modale / Temporelle** | \Gamma \vdash \Delta indexés | Insertion d'opérateurs relationnels | Spécification et Vérification de programmes |