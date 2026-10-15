Tags:: hott

- Bien que la théorie des types homotopiques — issue du projet des *Fondations Univalentes* initié par Vladimir Voevodsky dans les années 2010 — propose un cadre constructif particulièrement adapté à la formalisation informatique des mathématiques, **ZFC (Zermelo-Fraenkel avec axiome du choix) demeure la référence opérationnelle standard** dans la pratique mathématique contemporaine.
- ### Pourquoi HoTT n'a pas supplanté ZFC dans la pratique globale
- **Pragmatisme des mathématiciens** : ZFC offre un cadre logique classique simple et unifié où « tout est ensemble ». La majorité des mathématiciens travaillent de manière informelle sans ressentir le besoin d'interroger la nature profonde de leurs objets.
- **Courbe d'apprentissage** : L'intuition en théorie des ensembles (des « sacs » contenant des éléments) s'apprend dès le secondaire. L'intuition de HoTT exige de concevoir un type comme un espace topologique, les éléments comme des points, et l'égalité comme un chemin (*path*).
- **Complexité axiomatique** : ZFC repose sur un jeu d'axiomes relativement concis et éprouvé, tandis que HoTT s'appuie sur une théorie des types dépendants intensionnelle complexe enrichie de l'**axiome d'univalence** et des **types inductifs supérieurs** (*Higher Inductive Types*).
- ### La rupture conceptuelle apportée par HoTT
  
  HoTT propose une vision structurelle et homotopique des objets mathématiques :
  
  $\text{Types} \iff \text{Espaces topologiques} \quad \vert{} \quad \text{Termes} \iff \text{Points} \quad \vert{} \quad \text{Égalité } (a = b) \iff \text{Chemin entre } a \text{ et } b$
- **Isomorphisme vs Égalité** : En ZFC, deux structures isomorphes mais construites différemment ne sont rigoureusement pas égales (par exemple, la construction de \mathbb{N} par Von Neumann vs Zermelo). En HoTT, grâce à l'axiome d'univalence de Voevodsky, **l'équivalence est équivalente à l'égalité** (A \simeq B \implies A = B).
- **Hiérarchie de homotopie (h-niveaux)** : Les ensembles ne disparaissent pas dans HoTT ; ils correspondent simplement aux types de niveau homotopique 0 (0-types ou h-sets), c'est-à-dire les espaces dont l'espace des chemins est contractile au-dessus de la première dimension.
- ### Comparaison synthétique des fondations
  
  | Critère | Théorie des Ensembles (ZFC) | Théorie des Types Homotopiques (HoTT) |
  
  | **Nature de la logique** | Logique classique du 1^{\text{er}} ordre | Logique intuitionniste / constructive |
  
  | **Relation d'égalité** | Égalité stricte / matérielle | Égalité intensionnelle (chemins homotopiques) |
  
  | **Théorie des catégories** | Encodée via des classes et ensembles | Naturelle (\infty-catégories, groupoïdes) |
  
  | **Vérification par ordinateur** | Difficile à formaliser directement | Conçue nativement pour les assistants de preuve |
  
  > 
  
  **Pour résumer :** HoTT ne supplante pas ZFC mais constitue un **fondement alternatif structuraliste**. ZFC reste le langage d'usage pour la publication sur papier, tandis que la théorie des types et les fondations univalentes dominent les travaux sur la formalisation des mathématiques par ordinateur (assistants de preuve comme Rocq/Coq, Lean ou Agda).