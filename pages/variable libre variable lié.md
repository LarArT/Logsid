- Définition 1.2.16
	- On dit que les formules F et G sont a-équivalentes si elles sont (syntaxiquement) identiques à un renommage près des occurrences liées des variable
- Définition 1.2.19
	- 1. Une formule close est une formule sans variables libres. Les formules de l'exemple 1.2.7 sont toutes closes.
	  2. Soit F une formule dont les variables libres sont 11, , In. La clóture (uni- verselle) de F est la formule close VI1,,In F. Il y a ici formellement un abus : on a fait comme si l'ordre des variables était fixé. Cela n'est pas gê- nant: en choisissant un autre ordre on obtiendrait une formule différente mais équivalente.
-
- # exemple
- | $u$ | $\text{fv}(u)$ == libre | $\text{bv}(u)$ == liée|
  | :--- | :---: | :---: |
  | $\lambda x . x$ | $\varnothing$ | $\{x\}$ |
  | $x(\lambda y . z)$ | $\{x, z\}$ | $\{y\}$ |
  | $x(\lambda x . x)$ | $\{x\}$ | $\{x\}$ |
  | $(\lambda x . xx)(y(\lambda z . yz)x)$ | $\{x, y\}$ | $\{x, z\}$ |