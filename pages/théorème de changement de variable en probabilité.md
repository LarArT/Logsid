-
- [[exemple dans un restaurant de pizza]]
- Le **théorème de changement de variable** en probabilités permet de déterminer la loi d'une nouvelle variable aléatoire Y obtenue par une transformation déterministe d'une variable aléatoire X dont on connaît déjà la loi (souvent via sa densité f_X).
  Voici la formulation et la méthode pour le cas continu, qui est le plus courant et le plus technique.
- ## 1. Cadre unidimensionnel (Dimmension 1)
  Soit X une variable aléatoire continue de densité f_X définie sur un intervalle I.
  Soit g: I \to J une fonction de classe \mathcal{C}^1 (dérivable et de dérivée continue) et **strictement monotone** (donc bijective de I dans J).
  On pose Y = g(X). La variable Y est aussi une variable aléatoire continue, et sa densité f_Y est donnée pour tout y \in J par :
  Où g^{-1} est la bijection réciproque de g.
- ### Justification par la méthode de la fonction de répartition
  Pour comprendre l'origine du terme de dérivée, on suppose g strictement croissante :
  F_Y(y) = P(Y \le y) = P(g(X) \le y) = P(X \le g^{-1}(y)) = F_X(g^{-1}(y))
  En dérivant par rapport à y, on obtient par la règle de dérivation des fonctions composées :
  f_Y(y) = (g^{-1})'(y) \times f_X(g^{-1}(y))
  Si g est décroissante, la dérivation fait apparaître un signe moins, d'où la présence de la **valeur absolue**.
- ## 2. Cadre multidimensionnel (Généralisation)
  Soit X = (X_1, \dots, X_n) un vecteur aléatoire continu de densité conjointe f_X sur un ouvert U \subset \mathbb{R}^n.
  Soit g: U \to V un **difféomorphisme** de classe \mathcal{C}^1 (une bijection continue, dérivable, dont la réciproque g^{-1} est aussi continue et dérivable).
  On pose Y = g(X). La densité conjointe f_Y du vecteur Y est définie pour tout y \in V par :
  Où J_{g^{-1}}(y) désigne la **matrice jacobienne** de la fonction réciproque g^{-1} évaluée au point y. La valeur absolue du déterminant jacobien joue le même rôle que la valeur absolue de la dérivée en dimension 1 : elle mesure la déformation locale des volumes induite par le changement de coordonnées.
- ## 3. Exemple d'application pratique (Dim 1)
  Soit X une variable suivant une loi exponentielle de paramètre \lambda = 1. Sa densité est f_X(x) = e^{-x} pour x > 0.
  On cherche la loi de Y = X^2.
  1. **Vérification des hypothèses** : La fonction g(x) = x^2 est de classe \mathcal{C}^1 et strictement croissante sur I = ]0, +\infty[. Elle réalise une bijection de I vers J = ]0, +\infty[.
  2. **Détermination de la réciproque** : Pour y > 0, x = g^{-1}(y) = \sqrt{y}.
  3. **Calcul de la dérivée** : \frac{d}{dy} g^{-1}(y) = \frac{1}{2\sqrt{y}}.
  4. **Application de la formule** :
   
  La densité de Y est donc f_Y(y) = \frac{e^{-\sqrt{y}}}{2\sqrt{y}} pour y > 0, et 0 sinon.