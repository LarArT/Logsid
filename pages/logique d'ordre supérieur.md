Tags:: hol

- , la logique du premier ordre ne permet de quantifier (\forall, \exists) que sur des **individus/objets**. La logique d'ordre supérieur lève cette restriction.
- ​**Logique du second ordre :** On peut quantifier sur des **propriétés** ou des **ensembles** d'individus.
	- ​*Exemple :* Le principe de récurrence sur les entiers nécessite de dire "Pour toute propriété P, si P(0) est vrai et...". On écrit \forall P, \dots, ce qui est du second ordre.
- ​**Logique d'ordre supérieur (HOA / Higher-Order Logic) :** On peut quantifier sur des fonctions de fonctions, des propriétés de propriétés, etc., sans limite d'ordre.
- ​La HOL est l'extension directe de la logique classique ou intuitionniste. C'est une logique à base de **types simples** (Church).
- ​**Le principe :** On formalise les mathématiques en manipulant des propositions logiques complexes, des ensembles et des fonctions. Comme vu précédemment, on s'autorise à quantifier sur des fonctions ou des prédicats.
- ​**L'égalité :** L'égalité est **extensionnelle** et logique. Deux fonctions sont égales si elles renvoient les mêmes valeurs pour les mêmes arguments. Une fois qu'une égalité a = b est prouvée, elle est considérée comme un simple fait atomique (vrai ou faux).
- ​**Usage moderne :** C'est le fondement logique de systèmes d'aide à la preuve très populaires comme **Isabelle/HOL** ou **HOL Light**
	-