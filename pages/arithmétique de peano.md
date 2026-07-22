Source:: [DNR14] R. DAVID, K. NOUR, C. RAFFALLI, Introduction à la logique - 3e édition : Théorie de la démonstration, Dunod, Paris, 2014.
Tags:: arithmétique élémentaire,

- # P0: l'arithmétique élémentaire
	- **Définition 3.4.1**
		- On note $P_0$ l'ensemble des sept formules suivantes :
		- $A_1$ : $\forall x \{Sx \neq 0\}$
		- $A_2$ : $\forall x \{x = 0 \lor \exists y (x = Sy)\}$
		- $A_3$ : $\forall x, y \{Sx = Sy \rightarrow x = y\}$
		- $A_4$ : $\forall x \{x + 0 = x\}$
		- $A_5$ : $\forall x, y \{x + Sy = S(x+y)\}$
		- $A_6$ : $\forall x \{x \times 0 = 0\}$
		- $A_7$ : $\forall x, y \{x \times Sy = x \times y + x\}$
		- $P_0$ est souvent appelé l'*arithmétique élémentaire*.
		- Il décrit les propriétés de base de $0$, $S$ (la fonction successeur), $+$ et $\times$.
		-
	- **Définition 3.4.3**
		- On note $\text{PA} = P_0 \cup \text{Rec}$. La théorie PA s'appelle l'*arithmétique de Peano*.
- # **Définition 3.4.2** : Rec clôture universelle
	- 1. Soit $F$ une formule. On note $\text{Rec}_{F,x}$ la clôture universelle de la formule :
	- $$\{F[x := 0] \land \forall y\, (F[x := y] \rightarrow F[x := Sy])\} \rightarrow \forall x\, F$$
	- 2. On note Rec l'ensemble $\{\text{Rec}_{F,x} \mid F \text{ formule}\}$..
	-
- # Définition 3.4.3 arithmétique de peano
- On note PA = Po U Rec. La théorie PA s'appelle l'arithmétique de Peano.
- Une théorie non contradictoire
- Les modèles de PA sont infinis
- Il existe des modèles non isomorphe de PA