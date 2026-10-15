- Voici la fiche de lecture détaillée et structurée du **cours numéro 8** de la série de Xavier Leroy au Collège de France (2018-2019), intitulé : **"Step carefully: step-indexing techniques"** (Avancer prudemment : les techniques d'indexation par les étapes).
- ### Fiche de Lecture : L'indexation par les étapes (*Step-indexing*)
- #### 1. Le problème de fond : L'effondrement des types face aux références circulaires
  Jusqu'à présent, la correspondance de Curry-Howard fonctionnait sur des structures bien fondées (où l'on peut garantir qu'un calcul se termine ou qu'un type ne tourne pas en boucle).
  Cependant, l'informatique réelle utilise des **références stockées en mémoire qui peuvent contenir des fonctions, qui elles-mêmes manipulent ces références**.
  Cette circularité (ou réflexivité) crée un problème mathématique majeur : le système de types risque de devenir incohérent (paradoxes logiques), empêchant toute démonstration de correction ou de sécurité du programme.
- #### 2. La solution : L'indexation par les étapes (*Step-indexing*)
  Introduite par Andrew Appel et David McAllester au début des années 2000, la technique du *step-indexing* consiste à **introduire la notion de temps (découpé en étapes de calcul) directement au cœur de la définition des types**.
  Au lieu de dire de manière absolue :
  > « Cette valeur possède le type T »
  > 
  On dit de manière relative :
  > « Cette valeur se comporte comme le type T pendant au moins n étapes de calcul. »
  > 
  #### 3. Concepts clés développés par Xavier Leroy
  * **La sémantique opérationnelle chronométrée :** Chaque réduction ou pas de calcul consomme un "crédit" ou une unité de temps (n \to n-1).
  * **L'approximation des types :** Un type est vu comme une suite d'approximations. Plus l'indice n est grand, plus la précision sur le comportement du programme est élevée. Si un programme est sûr pour un nombre infini d'étapes, il est fondamentalement sûr.
  * **Résolution des paradoxes :** En limitant la validité d'une propriété à n étapes, on brise les cercles vicieux des définitions récursives infinies. On peut ainsi typer des fonctions stockées en mémoire sans que les équations mathématiques sous-jacentes ne s'effondrent.
  #### 4. Exemples et applications pratiques
  Cette technique mathématique abstraite est indispensable pour modéliser et valider le code dans plusieurs situations réelles :
  ##### A. Les pointeurs de fonctions en C / C++ et Rust
  Lorsqu'un langage permet de stocker une fonction dans une structure de données, elle-même modifiable en mémoire, le compilateur doit garantir qu'il n'y aura pas de violation d'accès.
  * **En Rust :** Le framework **Iris** (développé au-dessus de l'assistant de preuve Coq) utilise massivement le *step-indexing* pour prouver logiquement la validité du code concurrent et la sûreté de la mémoire, notamment pour valider les blocs de code marqués unsafe.
  ##### B. Les types récursifs et objets
  Dans des langages orientés objets ou fonctionnels avancés (comme **OCaml** ou **Scala**), les types peuvent faire référence à eux-mêmes de manière très complexe. L'indexation par étapes permet au système de types de valider la correction de ces structures sans boucler à l'infini lors de la phase de compilation.
  ### Synthèse logico-informatique
  | Concept classique | Extension via le *Step-indexing* |
  |---|---|
  | **Validité d'un type** | Validité restreinte à un horizon de n étapes de calcul |
  | **Équivalence logique** | Équivalence "jusqu'à l'étape n" |
  | **Garantie de sécurité** | Induction mathématique sur le nombre d'étapes restant |
  #### Conclusion
  Xavier Leroy montre dans ce cours que pour étendre la correspondance de Curry-Howard aux langages de programmation les plus complexes (ceux manipulant des états mutables avancés et de la concurrence), les mathématiciens ont dû accepter de faire descendre la notion de "temps machine" au niveau de la logique pure. Le *step-indexing* est le pont qui permet de raisonner mathématiquement sur l'exécution pas-à-pas d'un logiciel.
  *Pour aller plus loin, vous pouvez consulter la vidéo originale : La correspondance de Curry-Howard aujourd'hui (8) - Xavier Leroy. Ce cours démontre de manière limpide comment une idée technique (compter les étapes) résout un problème logique profond.*