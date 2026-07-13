- La « **réécriture de Hoare** » (ou plus précisément le calcul de la **Logique de Hoare**) est le fondement de la vérification formelle de programmes impératifs. Introduite par Tony Hoare en 1969, elle permet de prouver mathématiquement qu'un programme exécute correctement sa tâche.
  
  Au lieu de réécrire des *termes* (comme chez Curry ou Church), on réécrit ici des **propriétés logiques (des prédicats)** à travers les instructions d'un programme informatique.
- ## 1. La Brique de Base : Le Triplet de Hoare
  
  La logique de Hoare manipule des expressions appelées **triplets de Hoare**, qui s'écrivent sous la forme :
  
  `\{P\} \, c \, \{Q\}`
- P est la **précondition** : la propriété supposée vraie *avant* l'exécution du programme (ex: x > 0).
- c est la **commande** (l'instruction du programme, ex: x := x + 1).
- Q est la **postcondition** : la propriété qui doit être vraie *après* l'exécution (ex: x > 1).
  
  > 
  
  💡 **Signification :** Si la propriété P est vraie avant le programme c, et que c termine son exécution, alors la propriété Q sera vraie à la fin.
- ## 2. Les Règles de Réécriture Logique
  
  Pour prouver un programme, on applique des règles de déduction formelle. Les deux règles de réécriture les plus fondamentales et les plus célèbres sont **l'assignation** et la **séquence**.
- ### A. La règle de l'assignation (Réécriture vers l'arrière)
  
  C'est la règle la plus contre-intuitive au premier abord, car elle se lit **de droite à gauche** (de la postcondition vers la précondition).
  
  `\frac{}{\{Q[e/x]\} \, x := e \, \{Q\}}`
  
  Pour savoir ce qui doit être vrai *avant* l'affectation x := e pour obtenir Q à la fin, il suffit de **réécrire la postcondition Q en remplaçant toutes les occurrences de la variable x par l'expression e**.
- **Exemple :** On veut que x > 5 après l'instruction x := x + 1.
- **Réécriture :** On remplace x par x+1 dans la postcondition.
- **Résultat :** La précondition nécessaire est \{x + 1 > 5\}, ce qui se simplifie algébriquement en \{x > 4\}.
- ### B. La règle de la séquence (Composition)
  
  Pour analyser deux instructions successives c_1 et c_2, on introduit une propriété intermédiaire R qui sert de point de passage :
  
  `\frac{\{P\} \, c_1 \, \{R\} \quad \text{et} \quad \{R\} \, c_2 \, \{Q\}}{\{P\} \, c_1 ; c_2 \, \{Q\}}`
- ## 3. Le Calcul de la Plus Faible Précondition (Dijkstra)
  
  Le concept de réécriture de Hoare a été automatisé par Edsger Dijkstra sous le nom de **Calcul de la plus faible précondition** (\text{wp}, pour *Weakest Precondition*).
  
  Au lieu de deviner les triplets de Hoare, on définit une fonction mathématique \text{wp}(c, Q) qui prend une commande c et une postcondition souhaitée Q, et calcule par réécriture textuelle la précondition minimale exacte pour y parvenir :
- `\text{wp}(x := e, Q) = Q[e/x]`
- `\text{wp}(c_1 ; c_2, Q) = \text{wp}(c_1, \text{wp}(c_2, Q))`
- `\text{wp}(\text{if } b \text{ then } c_1 \text{ else } c_2, Q) = (b \implies \text{wp}(c_1, Q)) \land (\neg b \implies \text{wp}(c_2, Q))`
- ### Le défi de la boucle (\text{while})
  
  La réécriture automatique se heurte à une difficulté majeure avec les boucles \text{while } b \text{ do } c. On ne peut pas calculer directement la précondition sans connaître le nombre d'itérations.
  
  Pour résoudre cela, la logique de Hoare exige l'introduction humaine d'un **invariant de boucle** (I) : une propriété logique qui reste vraie avant, pendant et après chaque itération de la boucle. La réécriture génère alors des obligations de preuve (des formules mathématiques) assurant que :
- L'invariant est vrai à l'entrée de la boucle.
- L'invariant est préservé par le corps c de la boucle.
- L'invariant combiné avec la sortie de la boucle (\neg b) implique la postcondition finale Q.
  
  C'est ce mécanisme exact de réécriture de prédicats (génération d'obligations de preuve) qui est utilisé en coulisses par des outils industriels de méthode formelle comme la **Méthode B** ou le framework **Why3/Frama-C** pour certifier du code logiciel critique.