- Si les seuls symboles de relation du langage sont des relations d'arité 0 (même le symbole = est absent), les quantificateurs sont alors inutiles (puisqu'une formule ne peut pas contenir de variables). On obtient alors le calcul propositionnel défini ci- dessous.
- Définition 1.2.21
	- L'ensemble $\mathcal{C}_P$ des formules du calcul propositionnel est défini par la grammaire (où $\mathcal{V}_P$ est l'ensemble des relations d'arité $0$) :
	  \[
	  \mathcal{C}_P = \mathcal{V}_P \mid \bot \mid \neg \mathcal{C}_P \mid \mathcal{C}_P \vee \mathcal{C}_P \mid \mathcal{C}_P \wedge \mathcal{C}_P \mid \mathcal{C}_P \rightarrow \mathcal{C}_P
	  \]
-