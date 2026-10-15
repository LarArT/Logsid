Tags:: vampire, E*, satalax

- Le processus d'un démonstrateur de superposition repose sur un algorithme de saturation (généralement la boucle Given-Clause, comme l'algorithme d'Otter ou de Discount). Son but est de déduire systématiquement de nouvelles clauses à partir d'un ensemble initial jusqu'à l'obtention d'une contradiction.
  
  Voici la description minutieuse de ce processus, étape par étape.
  
  Étape 1 : Le prétraitement et la mise sous forme clausale (CNF)
  
  Avant de lancer le moteur de preuve, le problème doit être traduit dans un langage standardisé.
  
   * Négation du théorème : Pour prouver qu'une conjecture G découle d'un ensemble d'axiomes F, le démonstrateur cherche à prouver que l'ensemble F \cup \{\neg G\} est insatisfaisable (incohérent).
  
   * Élimination des connecteurs complexes : Les implications et équivalences sont remplacées par des conjonctions, disjonctions et négations.
  
   * Skolémisation : Les quantificateurs existentiels (\exists) sont éliminés en introduisant de nouvelles constantes ou fonctions symboliques, appelées fonctions de Skolem.
  
   * Mise sous forme normale conjonctive (CNF) : La formule logique est transformée en une conjonction de clauses. Une clause est une disjonction de littéraux (par exemple : A \lor \neg B \lor C = D).
  
  Étape 2 : L'initialisation des ensembles de clauses
  
  Le démonstrateur répartit les clauses obtenues dans deux structures de données distinctes :
  
   * L'ensemble des clauses actives (A) : Cet ensemble est initialement vide. Il contiendra les clauses qui ont déjà été sélectionnées et qui sont prêtes à participer aux inférences.
  
   * L'ensemble des clauses passives ou non traitées (U) : Cet ensemble contient initialement toutes les clauses issues de l'étape 1.
  
  Étape 3 : La sélection de la clause pivot (Given Clause)
  
  Le moteur de preuve entre dans une boucle fermée (la boucle de saturation) :
  
   * Choix heuristique : Le démonstrateur sélectionne une clause spécifique, notée g, dans l'ensemble des clauses non traitées U.
  
   * Critères de sélection : Le choix de g est crucial pour l'efficacité. Il s'appuie sur des heuristiques (par exemple, privilégier les clauses les plus courtes ou celles contenant les termes les plus simples).
  
   * Déplacement : La clause g est retirée de U.
  
  Étape 4 : La simplification de la clause choisie (Simplification directe)
  
  Avant d'utiliser la clause g pour générer de nouvelles preuves, le système tente de la réduire en utilisant les clauses déjà présentes dans l'ensemble actif A.
  
   * Démodulation (Réécriture) : Si A contient une égalité stricte s \approx t et que g contient un terme correspondant à s, le terme est remplacé par t (à condition que s soit strictement plus grand que t selon l'ordre global des termes).
  
   * Subsomption : Si une clause de A est plus générale ou implique directement g, alors g est considérée comme redondante et éliminée.
  
   * Tautologie : Si g contient à la fois un littéral et sa négation, ou une égalité réflexive (x \approx x), elle est immédiatement jetée. Le processus retourne alors à l'étape 3.
  
  Étape 5 : La rétro-simplification de l'ensemble actif
  
  Si la clause g survit à l'étape 4, elle est maintenant considérée comme simplifiée et valide. Elle peut être utilisée pour simplifier les clauses déjà stockées.
  
   * Réécriture de l'actif : Le démonstrateur utilise g pour réécrire et simplifier les clauses de A.
  
   * Mise à jour : Si une clause de A est simplifiée par g, elle perd son statut de clause active. Elle est retirée de A et renvoyée dans l'ensemble U des clauses non traitées pour être réévaluée plus tard.
  
  Étape 6 : La génération d'inférences (Le calcul de superposition)
  
  C'est le cœur mathématique du processus. La clause g est combinée avec chaque clause de l'ensemble actif A pour générer de nouvelles clauses. Les règles d'inférence appliquées sont strictement limitées par un ordre partiel complet sur les termes pour éviter les calculs inutiles :
  
   * Superposition stricte : Si g contient une égalité l \approx r et qu'une clause active contient un terme contenant un sous-terme qui s'unifie avec l, le démonstrateur génère une nouvelle clause en remplaçant ce sous-terme par r. Cette opération n'est effectuée que si l est le terme maximal de l'égalité.
  
   * Résolution d'égalité : Si la clause contient une inégalité de la forme s \not\approx t, le démonstrateur tente d'unifier s et t pour éliminer ce littéral.
  
   * Factorisation d'égalité : Cette règle élimine les redondances d'égalités au sein d'une même clause complexe.
  
  Toutes les nouvelles clauses ainsi générées sont appelées des enfants de g.
  
  Étape 7 : Le traitement et l'intégration des nouvelles clauses
  
  Chaque nouvelle clause enfant subit un nettoyage rigoureux :
  
   * Elle est simplifiée par les clauses de l'ensemble actif A.
  
   * Si elle survit (elle n'est ni une tautologie ni redondante), elle est ajoutée à l'ensemble U des clauses non traitées.
  
   * La clause pivot g est enfin insérée dans l'ensemble actif A.
  
  Étape 8 : Les conditions d'arrêt
  
  Le démonstrateur évalue le statut global à la fin de chaque itération :
  
   * Succès (Preuve trouvée) : Si l'une des étapes de simplification ou d'inférence génère la clause vide (notée \square, représentant une contradiction manifeste comme True \approx False), la preuve est établie. Le théorème initial est valide.
  
   * Échec (Pas de preuve) : Si l'ensemble U devient totalement vide et qu'aucune contradiction n'a été trouvée, l'ensemble des clauses est saturé. La conjecture est fausse, et l'ensemble actif A fournit un contre-modèle.
  
   * Non-terminaison : En logique du premier ordre, le problème étant indécidable, le processus peut tourner indéfiniment si le théorème est faux ou trop complexe, jusqu'à épuisement du temps ou de la mémoire allouée.