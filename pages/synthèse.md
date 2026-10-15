- Voici un compte rendu complet, structuré et scannable, qui synthétise l'intégralité des sujets théoriques, techniques et applicatifs abordés au cours de nos échanges d'hier (23 juin) et d'aujourd'hui.
  L'ensemble de ces discussions trace une arche parfaite qui part des fondements de la logique textuelle, passe par sa géométrisation spatiale, et aboutit à ses implémentations concrètes dans les logiciels de confiance et l'intelligence artificielle de pointe.
- ## I. Les Fondements : Curry-Howard et les assistants de preuve
  Nos échanges ont pris pour point de départ les cours de **Xavier Leroy au Collège de France** (cycle *"Programmer = démontrer ?"*), qui explorent la correspondance de Curry-Howard.
  * **Le principe central :** Un type de données correspond à une proposition mathématique ; un programme informatique (un terme du lambda-calcul) correspond à la preuve de cette proposition.
  * **Concepts logiques approfondis :**
   * **Types et prédicats :** Comment formaliser des affirmations mathématiques complexes dans le système de types d'un langage.
   * **Coinduction :** La gestion des structures de données infinies (comme les flux de données) et des preuves sur des calculs qui ne s'arrêtent pas, nécessitant des critères de productivité stricts pour éviter les récursions infinies.
   * **Step-indexing :** Une technique technique pour modéliser la sémantique de langages complexes (avec pointeurs ou effets) en indexant les types par un entier représentant le "nombre d'étapes de calcul" restantes.
   * **Effets de bord :** L'intégration logique des actions d'un programme sur son environnement (mémoire, entrées/sorties), notamment à travers les effets algébriques.
  * **Le Calcul des Constructions (CoC) :** Formalisme co-créé par Thierry Coquand en 1985, combinant le lambda-calcul et les types dépendants, qui sert de fondement historique au logiciel Coq.
- ## II. La Géométrisation de la Logique : Proofnets et dimensionnalité
  Pour dépasser la "bureaucratie syntaxique" (le fait que deux textes de codes différents décrivent en réalité le même algorithme), la recherche s'est tournée vers des représentations géométriques.
  * **Les Réseaux de Preuves (Proofnets) :** Issus de la logique linéaire de Jean-Yves Girard et développés par Pierre-Louis Curien. Ils remplacent les lignes de texte par des graphes (fils et nœuds en dimension 1). Deux preuves sont identiques si leurs fils se connectent géométriquement de la même manière.
  * **Les Diagrammes de Cordes (String Diagrams) :** Une extension bidimensionnelle utilisée en théorie des catégories pour modéliser les processus logiques et quantiques.
  * **PyZX :** Un outil logiciel concret (Python) utilisant le calcul ZX pour manipuler et optimiser ces diagrammes de cordes, appliqué notamment à la simplification de circuits informatiques quantiques.
- ## III. La Révolution Cubique et l'Univalence
  Portée par les travaux de Vladimir Voevodsky et les modélisations constructives de Thierry Coquand, cette approche fait grimper la géométrie logique en haute dimension (N-cubes).
  * **L'Axiome d'Univalence :** Énoncé par Voevodsky, il affirme que *"l'équivalence est l'identité"*. Si deux structures mathématiques sont isomorphes, elles sont logiquement égales.
  * **La Théorie des Types Cubiques (Thierry Coquand) :** Pour rendre cet axiome calculable par un ordinateur, Coquand introduit une sémantique topologique. Une preuve d'égalité devient un segment/chemin (1D), l'égalité de deux preuves devient un carré (2D), puis un cube (3D).
  * **Position face aux mathématiques classiques :**
   * **Le Tiers Exclu (LEM) & l'Axiome du Choix (AC) :** En informatique intuitionniste (constructive), le Tiers Exclu pur n'est pas calculable (il résoudrait le problème de l'arrêt). L'Axiome du Choix classique, par le théorème de Diaconescu, introduit le Tiers Exclu et bloque également le calcul.
   * **La Topologie Formelle (*Point-free topology*) :** Développée par Coquand, elle fait de la géométrie sans points, en manipulant uniquement des structures algébriques d'ouverts (approximations finies), rendant les espaces continus (comme les réels) entièrement calculables par une machine.
- ## IV. Implémentations Logicielles et Cartographie de la Recherche
  La transition de ces théories vers le code se fait à travers des langages de programmation fonctionnels avancés et implique des laboratoires de pointe.
- ### 1. Les Langages et leurs choix techniques
  * **Agda (mode Cubical) & Arend (JetBrains) :** Mettent en œuvre l'univalence de manière **constructive**. Le compilateur sait exécuter les calculs géométriques et transférer les programmes à travers les isomorphismes.
  * **Coq (Rocq) :** Utilise historiquement le Calcul des Constructions. L'univalence y est souvent **axiomatique** (via la bibliothèque coq-hott), ce qui permet de faire des preuves mais bloque l'exécution pure (Compute).
  * **Lean 4 :** Préfère exclure l'univalence de son noyau pour optimiser les performances en mathématiques classiques, reléguant l'univalence à un axiome externe.
- ### 2. Le Polymorphisme des Univers Logiques (Recherche 2026)
  Pour éviter le paradoxe de Girard (\text{Type} : \text{Type} qui fait imploser la logique), les langages stratifient les types dans une hiérarchie infinie (\text{Type}_0 : \text{Type}_1 \dots). Actuellement (2026), Thierry Coquand travaille sur l'implémentation de **niveaux d'univers de premier ordre** pour permettre aux programmeurs de manipuler ces variables d'univers directement dans le code sans ralentir les compilateurs.
- ### 3. La recherche en France
  * **Équipe Gallinette (Nantes, LS2N) :** Équipe-projet Inria (rattachée administrativement au centre de l'Université de Rennes) / CNRS / Nantes Université. C'est le pôle phare sur l'univalence constructive dans Coq.
  * **IRMAR (Rennes) :** Impliqué via le séminaire *Pampers* (sur la théorie des types homotopiques en lien avec Inria Rennes) et via son équipe de géométrie pure sur les espaces cubiques CAT(0).
  * **IRIF, LMF (Saclay), LIX (Polytechnique) :** Travaillent sur l'interopérabilité des preuves (Dedukti), la sémantique homotopique et les catégories supérieures.
- ## V. L'Intersection Majeure : L'IA de Confiance chez Google DeepMind
  Le point de convergence industriel le plus spectaculaire de toutes ces théories se trouve chez Google DeepMind, sous l'impulsion de Demis Hassabis (Prix Nobel de Chimie 2024).
  * **AlphaFold 2 (Le Nobel) :** Utilise un module (*Evoformer*) qui abandonne la syntaxe textuelle des acides aminés pour manipuler un **graphe spatial de contraintes géométriques**, faisant écho à la philosophie des diagrammes de cordes et des Proofnets.
  * **AlphaProof & LEAP (2024-2026) :** Pour créer une IA mathématique de confiance sans hallucinations, DeepMind utilise la correspondance de Curry-Howard à grande échelle. L'IA génère des propositions de code, et le compilateur **Lean 4** valide ou rejette la preuve. En mai 2026, cette méthode a permis de résoudre **9 conjectures de Paul Erdős** restées ouvertes.
  * **L'Univalence comme futur de l'IA :** Le but à long terme est d'intégrer l'univalence dans les modèles pour qu'une IA comprenne nativement les invariants mathématiques et soit capable de transférer un raisonnement d'un domaine à un autre (isomorphe) sans devoir réapprendre le problème de zéro.
  > **Actualité de Thierry Coquand en 2026 :** Il synthétise actuellement ces décennies de recherche au **Collège de France** (Chaire *Informatique et sciences numériques* 2025-2026) sur le thème *"La théorie des types, de Russell aux assistants à la démonstration"*, tout en menant des recherches sur l'auto-formalisation de théorèmes complexes (comme celui de Gödel) via des couplages entre LLM et le langage Agda.
  >