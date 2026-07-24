- Dans son cours, Gilles Dowek structure la déduction naturelle classique autour de **18 règles de déduction**.
  
  Le système est construit de manière très symétrique : pour la structure de base (l'axiome de départ) et pour chaque connecteur ou quantificateur logiques (\Rightarrow, \wedge, \vee, \neg, \top, \bot, \forall, \exists), il existe généralement **une règle d'introduction** (qui permet de fabriquer une formule contenant ce connecteur) et **une ou plusieurs règles d'élimination** (qui permettent d'utiliser une formule contenant ce connecteur). À cela s'ajoute une règle spécifique pour la logique classique.
  
  Voici l'énumération complète de ces 18 règles classées par catégorie :
- ### I. La règle de structure (1 règle)
- **1. Axiome (ou Règle de l'hypothèse) :** Si une proposition A fait partie de l'ensemble de nos hypothèses \Gamma, alors on peut immédiatement conclure A.
  `\frac{}{\Gamma, A \vdash A}`
- ### II. Les connecteurs propositionnels (12 règles)
  
  Chaque connecteur dispose de règles pour être introduit (créé) ou éliminé (utilisé).
- #### L'Implication (\Rightarrow)
- **2. Introduction de l'implication (\Rightarrow I) :** Pour prouver A \Rightarrow B, on suppose A et on cherche à prouver B.
- **3. Élimination de l'implication (\Rightarrow E) :** Si on a A \Rightarrow B et que l'on a A, alors on obtient B (appelé aussi *Modus Ponens*).
- #### La Conjonction (\wedge)
- **4. Introduction de la conjonction (\wedge I) :** Si on a prouvé A et qu'on a prouvé $B, alors on obtient A \wedge B.
- **5. Élimination gauche de la conjonction (\wedge E_1) :** Si on a A \wedge B, on peut en déduire A.
- **6. Élimination droite de la conjonction (\wedge E_2) :** Si on a A \wedge B, on peut en déduire B.
- #### La Disjonction (\vee)
- **7. Introduction gauche de la disjonction (\vee I_1) :** Si on a prouvé A, on peut en déduire A \vee B (peu importe ce qu'est B).
- **8. Introduction droite de la disjonction (\vee I_2) :** Si on a prouvé B, on peut en déduire A \vee B.
- **9. Élimination de la disjonction (\vee E) :** Si on a A \vee B, qu'en supposant A on prouve C, et qu'en supposant B on prouve également C, alors on obtient définitivement C (appelé aussi *raisonnement par cas*).
- #### La Négation (\neg) et les Constantes (\top, \bot)
- **10. Introduction de la négation (\neg I) :** Si en supposant A on aboutit à une contradiction (\bot), alors on a prouvé \neg A.
- **11. Élimination de la négation (\neg E) :** Si on a A et \neg A, on obtient le faux/la contradiction (\bot).
- **12. Élimination du Faux (\bot E) :** Du faux, on peut déduire n'importe quelle proposition A (principe d'explosion : *ex falso sequitur quodlibet*).
- **13. Introduction du Vrai (\top I) :** La proposition toujours vraie (\top) peut être démontrée à partir de n'importe quel contexte, sans hypothèse particulière.
- ### III. Les quantificateurs du premier ordre (4 règles)
  
  Ces règles régissent la manipulation des variables logiques.
- #### Le Quantificateur Universel (\forall)
- **14. Introduction du quantificateur universel (\forall I) :** Si on démontre A pour une variable arbitraire x (qui n'est libre dans aucune hypothèse), alors on a prouvé \forall x \, A.
- **15. Élimination du quantificateur universel (\forall E) :** Si on sait que \forall x \, A est vrai, on peut remplacer x par n'importe quel terme t pour obtenir A[x \leftarrow t].
- #### Le Quantificateur Existentiel (\exists)
- **16. Introduction du quantificateur existentiel (\exists I) :** Si on a prouvé qu'une propriété est vraie pour un objet ou un terme précis t (c'est-à-dire A[x \leftarrow t]), alors on peut affirmer qu'il existe au moins un élément qui la vérifie : \exists x \, A.
- **17. Élimination du quantificateur existentiel (\exists E) :** Si on sait qu'il existe un élément tel que \exists x \, A, et qu'en supposant A[x \leftarrow y] (pour un y inconnu et totalement neuf) on arrive à prouver une conclusion B, alors on peut valider B.
- ### IV. La règle de la logique classique (1 règle)
- **18. Règle du Raisonnement par l'Absurde (Abs) :** Pour démontrer A, on peut supposer sa négation \neg A et chercher une contradiction (\bot).
  
  > 
  
  **Note sémantique :** C'est précisément cette 18ème règle qui fait basculer la logique de l'approche *intuitionniste* (où l'on construit explicitement les preuves) à l'approche *classique*. Sans elle, le système ne comporterait que 17 règles.