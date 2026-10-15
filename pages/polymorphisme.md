- Voici une fiche de lecture synthétique du **cours numéro 6** de Xavier Leroy (année 2018-2019) au Collège de France, intitulé : *"Theorems for free: parametricity and logical relations"*.
- ### Fiche de Lecture : Théorèmes "gratuits" et Paramétricité
- #### 1. Le sujet central
  Le cours explore comment le **polymorphisme** (le fait de pouvoir écrire du code qui fonctionne pour tout type de données) permet de déduire des propriétés mathématiques sur un programme sans même avoir à lire son code. C'est ce qu'on appelle les "Théorèmes pour rien" (*Theorems for free*).
- #### 2. Concepts clés
  * **La Paramétricité :** C'est l'idée qu'une fonction polymorphe se comporte de manière uniforme sur tous les types. Si une fonction f prend un type générique 'a, elle ne peut pas "regarder" à l'intérieur de la valeur de type 'a pour décider quoi faire, car elle ne connaît pas la nature de ce type. Elle ne peut que déplacer, dupliquer ou appliquer d'autres fonctions génériques.
  * **Les Relations Logiques :** Pour prouver des propriétés sur ces fonctions, on utilise des "relations" entre les données. On ne compare pas seulement deux valeurs, mais on montre comment une relation entre deux entrées est préservée par la fonction pour produire une relation entre deux sorties.
  * **Théorèmes "gratuits" (*Free Theorems*) :** La signature de type d'une fonction (par exemple : f : (a -> a) -> List a -> List a) impose des contraintes si strictes que l'on peut prédire le comportement de la fonction (ex: la fonction ne peut pas inventer de nouveaux éléments dans la liste) simplement en regardant son type.
- #### 3. L'enjeu majeur
  Xavier Leroy démontre que **le typage n'est pas seulement un filet de sécurité** pour éviter les erreurs d'exécution. C'est un outil d'abstraction puissant :
  * En imposant des types génériques, on limite les actions possibles du programmeur.
  * Cette limitation est une force : elle garantit que le programme respecte certaines propriétés logiques (ex: l'immutabilité, le non-effacement de données, l'ordre des éléments) de manière automatique, sans besoin de tests ou de preuves supplémentaires.
- #### 4. Conclusion pédagogique
  Ce cours illustre parfaitement la philosophie de la chaire de Xavier Leroy : plus le système de types d'un langage est expressif (polymorphisme, types paramétrés), plus il permet d'extraire des preuves logiques du code source. Le typage devient une forme de **spécification formelle** qui accompagne le développement.
  > *"Le polymorphisme est un puissant moyen d'abstraction qui contraint le comportement des programmes de telle sorte que les types seuls suffisent à garantir des propriétés de correction."*
  > 
  Pour approfondir ce sujet, vous pouvez visionner la vidéo originale : Théorèmes pour rien : paramétricité et relations logiques.
  Cette vidéo est particulièrement pertinente car elle explique comment les signatures de types dans des langages comme OCaml ou Haskell agissent comme des théorèmes mathématiques garantissant le comportement du logiciel.