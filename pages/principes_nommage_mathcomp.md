Voici les principes généraux régissant le nommage des lemmes dans la bibliothèque Mathematical Components :

* **Généralités**
    * La plupart du temps, le nom d'un lemme peut être deviné à partir de son énoncé : un lemme nommé `fee_fie_foe` dira quelque chose sur `(fee .. (fie .. (foe ..) ..) ..)`, par exemple le lemme `size_cat` dans `seq.v`.
    * Nous utilisons souvent un suffixe d'une seule lettre pour résoudre les surcharges de notation, par exemple `addn`, `addb` et `addr` désignent respectivement l'addition sur les entiers naturels (`nat`), les booléens (`boolean`) et les anneaux (`ring`).
    * Enfin, une poignée de théorèmes possèdent des noms historiques, par exemple `Cayley_Hamilton` ou `factor_theorem`.

* **Structures et Enregistrements (Records)**
    * Chaque type de structure commence par une lettre minuscule, et son constructeur porte le même nom mais avec une première lettre majuscule.
    * Chaque instance d'un type de structure a un nom formé avec le nom du type support (carrier type), suivi d'un caractère de soulignement (`_`) et de celui du type de structure, comme dans `seq_sub_subType`, la structure de `subType` définie sur `seq_sub` (voir `fintype.v`). Les exceptions notables à cette règle sont les constructions canoniques qui tirent parti des espaces de noms modulaires, comme dans `ssralg.v`.

* **Suffixes**
    * Si la conclusion d'un lemme est un prédicat ou une égalité pour un prédicat, alors ce prédicat est un suffixe du nom du lemme, comme dans `addn_eq0` ou `rev_uniq`.
    * Si la conclusion d'un lemme est une propriété standard telle que `\char`, `<|`, etc. : la propriété doit être indiquée par un suffixe (comme `_char`, `_normal`, etc.), de sorte que le nom du lemme commence par une description de l'argument de la propriété, comme sa propriété clé ou sa constante de tête. Ainsi, nous avons `quotient_normal`, et non `normal_quotient`, etc. Cette convention ne s'applique pas aux règles de monotonie, pour lesquelles nous utilisons soit le nom de la propriété avec le suffixe pour l'opérateur (par exemple, `groupM`), soit le nom de l'opérateur avec le suffixe `S` pour la monotonie des sous-ensembles (par exemple, `mulgS`).
    * Nous essayons d'utiliser et de maintenir l'ensemble suivant de suffixes de lemmes :
        * `0` : zéro, ou l'ensemble vide
        * `1` : unité, ou le singleton (utiliser `_set1` pour ce dernier afin de lever les ambiguïtés)
        * `2` : deux, doublant, paires (doubletons)
        * `3` etc., de manière similaire
        * `A` : associativité
        * `C` : commutativité, ou complémentaire d'un ensemble (utiliser `Cr` pour le complémentaire en fin de nom)
        * `D` : différence d'ensembles, addition
        * `E` : élimination de définition (souvent des lemmes de conversion)
        * `F` : faux booléen (false), variante de type fini (comme dans `canF_eq`), ou foncteur de groupe
        * `G` : argument de groupe
        * `I` : intersection d'ensembles, injectivité pour les opérateurs binaires
        * `J` : conjugaison de groupe
        * `K` : lemmes de simplification / d'annulation (cancellation lemmas)
        * `L` : membre de gauche / côté gauche (left hand side, comme dans `canLR`)
        * `M` : multiplication de groupe
        * `N` : négation booléenne, opposé pour l'addition
        * `P` : propriétés caractéristiques (souvent des lemmes de réflexion)
        * `R` : commutateur de groupe, ou membre de droite / côté droit (right hand side, comme dans `canRL`)
        * `S` : argument de sous-ensemble, ou successeur d'un entier
        * `T` : vérité booléenne (true) et ensembles à l'échelle du Type (Type-wide sets)
        * `U` : union d'ensembles
        * `V` : inverse multiplicatif de groupe ou d'anneau
        * `W` : affaiblissement (weakening)
        * `X` : exponentiation, ou produit cartésien d'ensembles
        * `Y` : jointure de groupes (group join)
        * `Z` : homothétie / mise à l'échelle de module ou d'espace vectoriel (scaling)
