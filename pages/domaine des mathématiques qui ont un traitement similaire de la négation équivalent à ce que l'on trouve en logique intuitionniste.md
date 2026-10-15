- En logique intuitionniste, la négation \neg A est définie comme l'implication A \to \bot (une preuve d'absurdité), ce qui invalide le tiers exclu (\neg \neg A \implies A). Ce traitement particulier de la négation se retrouve de manière analogue dans plusieurs grands domaines des mathématiques :
- ## 1. Théorie des Topos et Géométrie Algébrique
  
  Dans un topos (une catégorie qui généralise la théorie des ensembles) :
- **Algèbres de Heyting interne :** Les sous-objets d'un objet forment une algèbre de Heyting et non une algèbre de Boole.
- **Pseudocomplément :** Le complémentaire d'un sous-espace ou ouvert n'est pas son complément absolu, mais l'intérieur de son complément (U^* = \text{Int}(U^c)). En général, U \vee U^* \neq 1.
- ## 2. Topologie Générale
  
  Les ouverts d'un espace topologique partagent la même structure algébrique :
- La négation d'un ouvert U correspond à l'intérieur de son complémentaire (\text{Int}(X \setminus U)).
- La propriété U \cup \text{Int}(U^c) = X n'est pas vérifiée en général (par exemple, pour U = \mathbb{R} \setminus \{0\} dans \mathbb{R}).
- ## 3. Informatique Théorique et Correspondance de Curry-Howard
  
  Dans le calcul de types et le L-calcul :
- **Types de fonctions et type vide :** La négation d'un type A est représentée par le type fonctionnel A \to \text{Void}.
- **Absence de refutation directe :** Une preuve de \neg A est une fonction qui transforme n'importe quel élément de type A en une contradiction, sans fournir d'algorithme direct pour « invalider » A de manière classique.
- ## 4. Algèbres de Heyting et Lattices
  
  En algèbre abstraite :
- Un treillis (*lattice*) distribuif et borné muni d'un pseudo-complément vérifie a \wedge b = 0 \iff a \le b^*.
- On n'a pas systématiquement a^{* *} = a, ce qui reflète exactement le comportement de la double négation en logique intuitionniste.
- ## 5. Logiques Modalités et Paraconsistantes (Domaines connexes)
- **Logique modale S4 :** Via la traduction de Gödel-McKinsey-Tarski, la négation intuitionniste \neg A équivaut à la formule modale \Box \sim \Box A.
- **Analyse constructive et Réalisabilité :** En analyse constructive (ex. école de Bishop), la négation est strictement liée à l'existence d'un contre-exemple effectif ou d'un algorithme d'incompatibilité.