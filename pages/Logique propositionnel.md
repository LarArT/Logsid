Tags:: calcul propositionnel

- Si les seuls symboles de relation du langage sont des relations d'arité 0 (même le symbole = est absent), les quantificateurs sont alors inutiles (puisqu'une formule ne peut pas contenir de variables). On obtient alors le calcul propositionnel défini ci- dessous.
  title:: Logique propositionnel
- Définition 1.2.21
	- L'ensemble $\mathcal{C}_P$ des formules du calcul propositionnel est défini par la grammaire (où $\mathcal{V}_P$ est l'ensemble des relations d'arité $0$) :
	  \[
	  \mathcal{C}_P = \mathcal{V}_P \mid \bot \mid \neg \mathcal{C}_P \mid \mathcal{C}_P \vee \mathcal{C}_P \mid \mathcal{C}_P \wedge \mathcal{C}_P \mid \mathcal{C}_P \rightarrow \mathcal{C}_P
	  \]
- C'est le niveau le plus basique de la logique formelle. Elle manipule des blocs d'énoncés entiers (des variables propositionnelles comme A, B, C) sans regarder ce qu'il y a à l'intérieur de ces énoncés.
- ​**Composants :** Des variables (A, B), des connecteurs logiques (\land, \lor, \neg, \implies, \iff).
- ​**Exemple :** * Soit A : "Il pleut".
	- ​Soit B : "Le sol est mouillé".
	- ​Formule : A \implies B ("S'il pleut, alors le sol est mouillé").
- ​**Limite :** Elle est incapable d'exprimer des notions de quantité ("tous", "certains") ou de lier des objets à des propriétés.
-