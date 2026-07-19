- En logique combinatoire et en $\lambda$-calcul, le terme « **réécriture de Curry** » fait référence aux règles d'évaluation d'un système formel inventé par Haskell Curry : la **Logique Combinatoire** ($\text{LC}$).
  
  Contrairement au $\lambda$-calcul d'Alonzo Church qui utilise des variables et un mécanisme complexe de substitution (la $\beta$-réduction), le système de réécriture de Curry s'en passe totalement. Il utilise à la place des **combinateurs** (des fonctions de base sans variables libres) appliqués à des termes, agissant comme un pur **système de réécriture de termes** ($\text{TRS}$).
- ## 1. Les Briques de Base : Les Combinateurs S, K, et I
  
  Dans le système de Curry, toute la logique et le calcul sont codés à l'aide de seulement trois constantes fondamentales (appelées les combinateurs de base) et d'une opération d'application. Les règles de réécriture associées sont les suivantes :
- **Identité (I) :** $I \, x \to x$
  
  *(Renvoie simplement son argument).*
- **Constante (K) :** $K \, x \, y \to x$
  
  *(Prend deux arguments et élimine le second pour ne garder que le premier).*
- **Substitution / Distribution (S) :** $S \, x \, y \, z \to (x \, z) \, (y \, z)$
  
  *(Distribue l'argument z à la fois sur x et sur y, puis applique le résultat de l'un à l'autre).*  
  
  >   
  
  ⚠️ **Attention aux parenthèses :** L'application dans la logique de Curry associe à gauche. Ainsi, $K \, x \, y$ signifie de manière rigoureuse $((K \, x) \, y)$.
- ## 2. Le Miracle de la Complétude Combinatoire
  
  Le résultat le plus spectaculaire établi par Curry est qu'**on peut se passer complètement des variables**. Les trois règles de réécriture ci-dessus possèdent le même pouvoir d'expression et de calcul qu'une machine de Turing ou que le $\lambda$-calcul pur.  
  
  On peut traduire n'importe quelle abstraction du $\lambda$-calcul ($\lambda x. t$) en une combinaison pure de S, K, et I via un algorithme appelé **l'abstraction fonctionnelle** (noté $[x]t$) :
- $[x]x \equiv I$
- $[x]c \equiv K \, c$ *(où c est une constante ou une variable différente de x)*
- $[x](u \, v) \equiv S \, ([x]u) \, ([x]v)$
- ### Exemple de réécriture
  
  Supposons qu'on veuille appliquer le terme combinatoire $S \, K \, I$ à un élément arbitraire $x$. Suivons les étapes de la réécriture de Curry pas à pas :  
  
  $$
  \begin{aligned}  
  (S \, K \, I) \, x &\to (K \, x) \, (I \, x) && \text{(Par la règle de } S\text{)} \\  
  &\to x \, (I \, x) && \text{(Par la règle de } K\text{)} \\  
  &\to x \, x && \text{(Par la règle de } I\text{)}  
  \end{aligned}
  $$  
  
  Le terme combinatoire $S \, K \, I$ se comporte donc exactement comme le terme $\lambda x. x \, x$ du $\lambda$-calcul.
- ## 3. Propriétés de la Réécriture de Curry
  
  En tant que système de réécriture de termes, le système de Curry possède des propriétés fondamentales identiques au $\lambda$-calcul :
- **La Confluence (Propriété de Church-Rosser) :** Si un terme combinatoire peut être réécrit de deux manières différentes vers des termes A et B, alors il existe toujours un terme C permettant de rejoindre les deux chemins. Les chemins de calcul finissent toujours par converger.
- **Non-Terminaison (Système Non-Typé) :** Tout comme en $\lambda$-calcul pur, on peut construire des boucles infinies de réécriture. Par exemple, le terme $S \, I \, I \, (S \, I \, I)$ se réécrit indéfiniment vers lui-même.
- **Normalisation Forte (Système Typé) :** Si l'on applique le système de types de Curry aux combinateurs (le typage simple), le théorème de normalisation forte s'applique : toute suite de réécritures combinatoires finit par s'arrêter sur une forme irréductible (une forme normale).
  
  Ce système de réécriture est historiquement crucial car il a grandement facilité la création des premières machines virtuelles et architectures matérielles destinées à exécuter les langages de programmation fonctionnels (comme le Lisp ou le compilateur du langage Miranda), en évitant les renommages complexes de variables lors de la substitution.