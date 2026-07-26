title:: Règles du Calcul des Constructions (CoC)
collapsed:: false

- 1. Univers et Axiomatisation
	- Le CoC manipule deux sortes d'univers $\mathcal{S} = \{\text{Prop}, \text{Set}\}$.
	- Axiome de formation (Ax)
	  $$\text{Ax} : \frac{}{\Gamma \vdash \text{Prop} : \text{Set}}$$
	  (ou selon la variante : $\text{Prop} : \text{Type}_1$, $\text{Set} : \text{Type}_1$)
- 2. Règles de Contexte et de Structure
	- Contexte Vide (Wf-Empty)
	  $$\frac{}{\emptyset \vdash \text{wf}}$$
	- Extension de Contexte (Wf-Var)
	  $$\frac{\Gamma \vdash A : s \quad x \notin \text{dom}(\Gamma)}{\Gamma, x : A \vdash \text{wf}}$$
	- Variable (Var)
	  $$\frac{\Gamma \vdash \text{wf} \quad (x : A) \in \Gamma}{\Gamma \vdash x : A}$$
- 3. Règle Pure du Produit Dépendant ($\Pi$)
	- En CoC, toute la puissance logique repose sur la règle de formation des produits $\Pi(x : A). B$. Les deux sortes $s_1, s_2 \in \{\text{Prop}, \text{Set}\}$ régissent la combinaison :
	- Formation du Produit ($\Pi$-Form)
	  $$\frac{\Gamma \vdash A : s_1 \quad \Gamma, x : A \vdash B : s_2}{\Gamma \vdash \Pi(x : A). B : s_2}$$
	- Les 4 Combinaisons de $s_1 \rightarrow s_2$ :
		- $(\text{Set}, \text{Set})$ : Fonctions ordinaires et fonctions dépendantes (ex: $n : \mathbb{N} \to \text{Vec}(n)$).
		- $(\text{Set}, \text{Prop})$ : Prédicats et propriétés dépendant d'un objet (ex: $n : \mathbb{N} \to (n > 0)$).
		- $(\text{Prop}, \text{Prop})$ : Implication et quantification sur des preuves (ex: $P \to Q$).
		- $(\text{Prop}, \text{Set})$ : Imprédicativité / Polymorphisme d'ordre supérieur (ex: abstractions sur toutes les propositions $\Pi(P : \text{Prop}). A$).
- 4. Introduction, Élimination et Calcul
	- Abstraction / Introduction ($\Pi$-Intro)
	  $$\frac{\Gamma, x : A \vdash b : B}{\Gamma \vdash \lambda x : A. b : \Pi(x : A). B}$$
	- Application / Élimination ($\Pi$-Elim)
	  $$\frac{\Gamma \vdash f : \Pi(x : A). B \quad \Gamma \vdash a : A}{\Gamma \vdash f \, a : B[a/x]}$$
	- Réduction / Calcul ($\beta$-réduction)
	  $$(\lambda x : A. b) \, a \longrightarrow_\beta b[a/x]$$
- 5. Égalité et Conversion
	- Conversion (Conv)
	  $$\frac{\Gamma \vdash a : A \quad \Gamma \vdash B : s \quad A \equiv_\beta B}{\Gamma \vdash a : B}$$
	- L'égalité $A \equiv_{\beta} B$ désigne la $\beta$-équivalence réflexive, symétrique et transitive des termes.