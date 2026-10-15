- Une **fonction à support fini** est une fonction qui s'annule presque partout : elle ne prend des valeurs non nulles que sur un ensemble fini de son domaine de départ.
- ## Definition formelle
  
  Soit X un ensemble et Y un ensemble contenant un élément neutre 0 (comme un groupe, un anneau ou un espace vectoriel).
  
  Une fonction f : X \to Y est dite **à support fini** si l'ensemble :
  
  `\text{supp}(f) = \{ x \in X \mid f(x) \neq 0 \}`
  
  est un **ensemble fini**.
  
  > 
  
  **Remarque :** Si X est lui-même un ensemble fini, toute fonction de X dans Y est trivialement à support fini. La notion prend tout son sens lorsque X est infini (comme \mathbb{N} ou \mathbb{R}).
- ## Notation classique
  
  L'ensemble de ces fonctions est souvent noté Y^{(X)} ou Y_0^X.
  
  Lorsque Y = \mathbb{K} (un corps comme \mathbb{R} ou \mathbb{C}), l'ensemble \mathbb{K}^{(X)} des fonctions à support fini de X dans \mathbb{K} forme un **espace vectoriel**.
- ## Exemples et applications
- **Suites presque nulles :** Si X = \mathbb{N}, une fonction f : \mathbb{N} \to \mathbb{R} est une suite. Dira qu'elle est à support fini signifie qu'il existe un rang N \in \mathbb{N} tel que f(n) = 0 pour tout n \ge N.
- **Polynômes :** Un polynôme P(X) = \sum_{k=0}^n a_k X^k peut être identifié à la suite de ses coefficients (a_k)_{k \in \mathbb{N}}. C'est une suite à support fini.
- **Combinaisons linéaires :** Toute combinaison linéaire dans un espace vectoriel fait intervenir une famille de scalaires à support fini. Cela garantit que la somme comporte un nombre fini de termes non nuls.