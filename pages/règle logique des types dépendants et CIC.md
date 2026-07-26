# Système de types dépendants
- ## Structure d'un système de types dépendants
- ### Jugements sous contexte ($\Gamma$)
- Formation de contexte : $\Gamma \vdash \text{wf}$ ($\Gamma$ est un contexte bien formé)
- Formation de type : $\Gamma \vdash A \text{ type}$ ($A$ est un type valide dans $\Gamma$)
- Typage de terme : $\Gamma \vdash a : A$ ($a$ est un terme valide de type $A$)
- Égalité définitionnelle / Conversion : $\Gamma \vdash A \equiv B$ ou $\Gamma \vdash a \equiv b : A$
- ## Règles structurelles principales
- **Règle de la Variable (Ax)**
  $$\frac{\Gamma \vdash \text{wf} \quad (x : A) \in \Gamma}{\Gamma \vdash x : A}$$
- **Règle d'Affaiblissement (Weakening)**
  $$\frac{\Gamma \vdash a : A \quad \Gamma \vdash B \text{ type}}{\Gamma, x : B \vdash a : A}$$
- **Règle de Substitution**
  $$\frac{\Gamma, x : B \vdash a : A \quad \Gamma \vdash b : B}{\Gamma \vdash a[b/x] : A[b/x]}$$
- **Règle de Conversion (Congruence par égalité)**
  $$\frac{\Gamma \vdash a : A \quad \Gamma \vdash A \equiv B}{\Gamma \vdash a : B}$$
- ## Règles générales de la conversion ($\equiv$)
- **Réflexivité** : $\Gamma \vdash a \equiv a : A$
- **Symétrie**
  $$\frac{\Gamma \vdash a \equiv b : A}{\Gamma \vdash b \equiv a : A}$$
- **Transitivité**
  $$\frac{\Gamma \vdash a \equiv b : A \quad \Gamma \vdash b \equiv c : A}{\Gamma \vdash a \equiv c : A}$$
- **Congruence** : Si deux expressions sont composées d'éléments définitionnellement égaux, elles sont égales.
- ## Règles par formeur de type (Quadruplette canonique)
- ### Produit dépendant : Type $\Pi$ (ou $\forall$)
- **Formation ($\Pi$-Form)**
  $$\frac{\Gamma \vdash A \text{ type} \quad \Gamma, x : A \vdash B \text{ type}}{\Gamma \vdash \Pi(x : A). B \text{ type}}$$
- **Introduction ($\Pi$-Intro / $\lambda$-abstraction)**
  $$\frac{\Gamma, x : A \vdash b : B}{\Gamma \vdash \lambda x. b : \Pi(x : A). B}$$
- **Élimination ($\Pi$-Elim / Application)**
  $$\frac{\Gamma \vdash f : \Pi(x : A). B \quad \Gamma \vdash a : A}{\Gamma \vdash f \, a : B[a/x]}$$
- **Calcul ($\Pi$-Comp / $\beta$-réduction)**
  $$\frac{\Gamma, x : A \vdash b : B \quad \Gamma \vdash a : A}{\Gamma \vdash (\lambda x. b) \, a \equiv b[a/x] : B[a/x]}$$
- **Unicité ($\Pi$-Eta / $\eta$-conversion)**
  $$\frac{\Gamma \vdash f : \Pi(x : A). B}{\Gamma \vdash (\lambda x. f \, x) \equiv f : \Pi(x : A). B}$$
- ### Somme dépendante : Type $\Sigma$ (ou $\exists$)
- **Formation ($\Sigma$-Form)**
  $$\frac{\Gamma \vdash A \text{ type} \quad \Gamma, x : A \vdash B \text{ type}}{\Gamma \vdash \Sigma(x : A). B \text{ type}}$$
- **Introduction ($\Sigma$-Intro / Paire)**
  $$\frac{\Gamma \vdash a : A \quad \Gamma \vdash b : B[a/x]}{\Gamma \vdash (a, b) : \Sigma(x : A). B}$$
- **Élimination ($\Sigma$-Elim / Projections ou Pattern Matching)**
  $$\frac{\Gamma \vdash p : \Sigma(x : A). B \quad \Gamma, x : A, y : B \vdash c : C[(x, y)/p]}{\Gamma \vdash \text{match } p \text{ with } (x, y) \Rightarrow c : C[p/p]}$$
	- Forme alternative (projections) : $\pi_1(p) : A$ et $\pi_2(p) : B[\pi_1(p)/x]$
- **Calcul ($\Sigma$-Comp)**
  $$\text{match } (a, b) \text{ with } (x, y) \Rightarrow c \;\equiv\; c[a/x, b/y]$$
	- Forme alternative : $\pi_1(a, b) \equiv a$ et $\pi_2(a, b) \equiv b$
- ### Type d'Égalité / Identité de Martin-Löf ($a =_A b$)
- **Formation (Id-Form)**
  $$\frac{\Gamma \vdash A \text{ type} \quad \Gamma \vdash a : A \quad \Gamma \vdash b : A}{\Gamma \vdash a =_A b \text{ type}}$$
- **Introduction (Id-Intro / Réflexivité)**
  $$\frac{\Gamma \vdash a : A}{\Gamma \vdash \text{refl}_a : a =_A a}$$
- **Élimination (Id-Elim / Règle J ou Transport)**
  $$\frac{\Gamma \vdash p : a =_A b \quad \Gamma, x : A, e : a =_A x \vdash P \text{ type} \quad \Gamma \vdash d : P[a/x, \text{refl}_a/e]}{\Gamma \vdash J(P, d, p) : P[b/x, p/e]}$$
- **Calcul (Id-Comp)**
  $$\Gamma \vdash J(P, d, \text{refl}_a) \equiv d : P[a/x, \text{refl}_a/e]$$
- ### Univers de Types ($\mathcal{U}$)
- **Axiome d'Univers**
  $$\frac{\Gamma \vdash \text{wf}}{\Gamma \vdash \mathcal{U}_i : \mathcal{U}_{i+1}}$$
- **Cumulativité (optionnelle)**
  $$\frac{\Gamma \vdash A : \mathcal{U}_i}{\Gamma \vdash A : \mathcal{U}_{i+1}}$$
- ### Types Inductifs (Exemple : Entiers $\mathbb{N}$)
- **Formation**
  $$\Gamma \vdash \mathbb{N} \text{ type}$$
- **Introduction**
  $$\Gamma \vdash 0 : \mathbb{N}$$
  $$\frac{\Gamma \vdash n : \mathbb{N}}{\Gamma \vdash S(n) : \mathbb{N}}$$
- **Élimination (Récurrence / Induction)**
  $$\frac{\Gamma \vdash n : \mathbb{N} \quad \Gamma, x : \mathbb{N} \vdash P(x) \text{ type} \quad \Gamma \vdash P_0 : P(0) \quad \Gamma, k : \mathbb{N}, h : P(k) \vdash P_S : P(S(k))}{\Gamma \vdash \text{rec}_{\mathbb{N}}(P, P_0, P_S, n) : P(n)}$$
- **Calcul**
  $$\text{rec}_{\mathbb{N}}(P, P_0, P_S, 0) \equiv P_0$$
  $$\text{rec}_{\mathbb{N}}(P, P_0, P_S, S(n)) \equiv P_S[n/k, \text{rec}_{\mathbb{N}}(P, P_0, P_S, n)/h]$$