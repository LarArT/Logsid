- En logique formelle, l'état des buts (*goals*) dans un assistant de preuve correspond exactement à un séquent \Gamma \vdash A (ou \Gamma \vdash \Delta en logique classique), où \Gamma est le contexte des hypothèses et A est la conclusion à prouver.
  Voici la correspondance exacte entre les règles de structure et de connecteurs du calcul des séquents (type Gentzen/intuitionniste) et les tactiques à utiliser en **Lean 4** et **Rocq** (Coq).
- ### 1. Règles de Structure et Identité
  | Règle du calcul des séquents | Signification | Tactique Lean 4 | Tactique Rocq (Coq) | Commentaire |
  |---|---|---|---|---|
  | **Axiome** : \frac{}{A \vdash A} | La conclusion est dans les hypothèses. | exact h | exact h. / assumption. | -- Initialise ou clôt une branche évidente. |
  | **Coupure (Cut)** : \frac{\Gamma \vdash A \quad \Gamma, A \vdash B}{\Gamma \vdash B} | Utiliser un lemme intermédiaire A. | have h : A := ... | assert (h : A). | -- Crée un sous-but pour prouver A, puis l'ajoute au contexte pour prouver B. |
  | **Affaiblissement gauche** : \frac{\Gamma \vdash B}{\Gamma, A \vdash B} | Ajouter une hypothèse inutile. | Automatique | Automatique | -- On peut simplement ignorer l'hypothèse superflue. |
  | **Contraction gauche** : \frac{\Gamma, A, A \vdash B}{\Gamma, A \vdash B} | Dupliquer une hypothèse. | have h2 := h1 | pose proof h1 as h2. | -- Permet d'utiliser une hypothèse (comme une quantification universelle) plusieurs fois. |
- ### 2. Règles des Connecteurs Logiques
- #### Implication (A \to B)
  * **À Droite (\vdash \to)** : Prouver A \to B revient à supposer A pour prouver B.
   * **Lean 4 :** intro h -- *Soit h l'hypothèse A.*
   * **Rocq :** intro h. -- *Supposons A.*
  * **À Gauche (\to \vdash)** : Utiliser A \to B dans le contexte. Si on a A, on obtient B.
   * **Lean 4 :** apply h_imp ou have hB := h_imp hA -- *Par le modus ponens...*
   * **Rocq :** apply h_imp. ou specialize (h_imp hA). -- *Par application de l'implication.*
- #### Conjonction / Et (A \land B)
  * **À Droite (\vdash \land)** : Prouver A \land B (séparer le but en deux branches).
   * **Lean 4 :** constructor -- *Prouvons d'une part A, et d'autre part B.*
   * **Rocq :** split. -- *Séparons la conjonction en deux sous-buts.*
  * **À Gauche (\land \vdash)** : Décomposer une hypothèse h : A \land B.
   * **Lean 4 :** rcases h with ⟨hA, hB⟩ -- *Soient hA et hB les composants de l'hypothèse.*
   * **Rocq :** destruct h as [hA hB]. -- *Par élimination de la conjonction.*
- #### Disjonction / Ou (A \lor B)
  * **À Droite (\vdash \lor)** : Choisir de prouver le membre de gauche ou de droite.
   * **Lean 4 :** left ou right -- *Il suffit de montrer le membre gauche/droit.*
   * **Rocq :** left. ou right. -- *Choisissons de prouver la partie gauche/droite.*
  * **À Gauche (\lor \vdash)** : Raisonner par cas sur une hypothèse h : A \lor B (crée deux branches).
   * **Lean 4 :** rcases h with hA | hB -- *Raisonnons par cas selon que A ou B est vrai.*
   * **Rocq :** destruct h as [hA | hB]. -- *Disjonction de cas sur l'hypothèse.*
- #### Quantificateur Universel (\forall x, P(x))
  * **À Droite (\vdash \forall)** : Prouver pour un x générique.
   * **Lean 4 :** intro x -- *Soit x un élément quelconque.*
   * **Rocq :** intro x. -- *Soit x arbitraire.*
  * **À Gauche (\forall \vdash)** : Instancier une hypothèse universelle avec un terme spécifique t.
   * **Lean 4 :** have h_inst := h_all t -- *Instancions l'hypothèse générale pour t.*
   * **Rocq :** specialize (h_all t). -- *Appliquons la propriété générale au cas particulier t.*
- #### Quantificateur Existentiel (\exists x, P(x))
  * **À Droite (\vdash \exists)** : Fournir un témoin t pour valider l'existence.
   * **Lean 4 :** use t -- *Montrons que le terme t convient.*
   * **Rocq :** exists t. -- *Sujet témoin donné par t.*
  * **À Gauche (\exists \vdash)** : Extraire le témoin et sa propriété depuis une hypothèse existencielle.
   * **Lean 4 :** rcases h with ⟨x, hx⟩ -- *Soit x le témoin tel que hx est vérifiée.*
   * **Rocq :** destruct h as [x hx]. -- *Supposons l'existence d'un tel x vérifiant la propriété.*
- #### Faux / Absurdité (\perp)
  * **À Gauche (\perp \vdash)** : Utiliser une contradiction dans le contexte (Principe d'explosion).
   * **Lean 4 :** contradiction ou rcases h (si h : \text{False}) -- *L'hypothèse est absurde.*
   * **Rocq :** contradiction. ou destruct h. (si h : \text{False}) -- *Par élimination de la contradiction.*
- ### Exemple de correspondance visuelle
  Si vous effectuez cette règle en calcul des séquents :
  
  * En **Lean 4**, votre écran affiche ⊢ A → B. Vous tapez intro h, l'écran devient :
   ```lean
   h : A
   ⊢ B
   
   ```
  * En **Rocq**, votre écran affiche Goal A -> B. Vous tapez intro h., l'écran devient :
   ```coq
   h : A
   ============================
   B
   
   ```
-