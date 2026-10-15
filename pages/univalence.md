- Voici la fiche de lecture du **17e enregistrement** de la chaire de Xavier Leroy au Collège de France (2018-2019).
  Cet enregistrement correspond à la deuxième partie du bloc final du **30 janvier 2019**. Il s'agit du séminaire de clôture fondamentale présenté par le mathématicien et logicien **Thierry Coquand** (Université de Göteborg), intitulé : **"Du calcul des constructions à la théorie des types univalents"**.
- ### Fiche de Lecture : Du calcul des constructions à la théorie des types univalents
- #### 1. Le sujet central
  Thierry Coquand est le créateur (avec Gérard Huet) du **Calcul des Constructions (CoC)** en 1985, le formalisme logique qui sert de fondation historique à l'assistant de preuves **Coq**.
  L'objectif de ce séminaire est de retracer l'évolution de ce formalisme sur plus de trente ans, en montrant comment les recherches pour résoudre la question de l'égalité en logique ont naturellement mené à la formulation moderne de la **théorie des types univalents (HoTT)**.
- #### 2. Concepts clés développés
  * **Le Calcul des Constructions (CoC) :** Thierry Coquand rappelle la genèse de ce système, qui unifie le lambda-calcul typé et la logique d'ordre supérieur. C'est l'outil ultime de la correspondance de Curry-Howard où les types représentent des propositions mathématiques arbitrairement complexes.
  * **Le problème de l'identité de Martin-Löf :** Le séminaire revient sur la difficulté historique à caractériser le type identité (x = y). Dans le modèle original, il manquait un aspect calculatoire fort pour manipuler les équivalences de structures complexes (comme l'isomorphisme de types).
  * **Le saut vers l'Univalence (Voevodsky) :** Thierry Coquand explique l'apport fondamental de Vladimir Voevodsky : interpréter les types non plus comme des ensembles statiques, mais comme des espaces topologiques (des types de complexes de Kan). L'axiome d'univalence formalise le fait que deux types isomorphes sont logiquement indiscernables.
  * **Les structures cubiques :** Le cœur technique de la présentation aborde la *théorie des types cubiques*. Coquand détaille comment lui et son équipe ont réussi à redonner un sens constructif (calculatoire) à l'axiome d'univalence de Voevodsky en utilisant des modèles géométriques basés sur des cubes de dimension N.
- ### 3. Le lien avec la correspondance de Curry-Howard
  Ce séminaire réalise la synthèse technique et historique de tout l'enseignement de Xavier Leroy :
  * **Le programme est une construction :** Les objets mathématiques ne sont pas des abstractions inertes, ce sont des programmes que l'on peut exécuter.
  * **L'égalité est un chemin :** En faisant évoluer le Calcul des Constructions vers la théorie univalente, prouver que deux programmes ou deux structures mathématiques sont égales revient à construire un chemin géométrique calculable entre eux.
- ### 4. Applications concrètes et impact
  Les concepts décrits par Thierry Coquand dans cette session ont donné naissance à une toute nouvelle génération de langages de programmation et d'assistants de preuve :
  * **Cubical Agda :** Une extension du langage Agda permettant de calculer explicitement avec l'axiome d'univalence.
  * **Arend :** Un assistant de preuve développé par JetBrains, nativement cubique, conçu pour appliquer ces théories géométriques à la certification logicielle de haut niveau.
- #### Conclusion
  Le séminaire de Thierry Coquand est un jalon historique. Il montre comment les concepts fondamentaux de la programmation fonctionnelle (le lambda-calcul), combinés à la logique formelle la plus stricte, ont fini par réécrire les fondements des mathématiques géométriques.
  Cette vidéo est essentielle pour comprendre la transition historique entre les assistants de preuve traditionnels et les fondations de l'informatique univalente moderne. Vous pouvez la visionner sur YouTube : Programmer = démontrer ? La correspondance de Curry-Howard... (17) - Xavier Leroy (2018-2019). Cet enregistrement offre le privilège rare d'écouter l'un des pères fondateurs de la logique informatique moderne exposer l'évolution de ses propres concepts.
-
- L'univalence (et plus particulièrement la théorie des types univalents) a été implémentée dans plusieurs langages de programmation et assistants de preuve.
  Cependant, il faut distinguer deux grandes étapes dans ces implémentations : l'univalence **axiomatique** (où l'on ajoute l'axiome sans que l'ordinateur sache l'exécuter/le calculer) et l'univalence **constructive** (où l'ordinateur peut réellement exécuter les calculs et les transferts de preuves à travers l'univalence).
  Voici les principaux langages concernés :
- ## 1. L'implémentation reine : Agda (Cubical Agda)
  **Agda** est aujourd'hui le langage de programmation fonctionnel et l'assistant de preuves de référence pour manipuler l'univalence de manière constructive.
  * **Comment c'est implémenté :** Grâce aux travaux de Thierry Coquand sur la théorie des types cubiques, Agda dispose d'un mode spécial appelé Cubical Agda (activable via le drapeau --cubical).
  * **L'avantage :** Dans ce mode, l'axiome d'univalence n'est pas juste une règle théorique. Le compilateur sait *calculer* avec. Si vous prouvez que deux types sont isomorphes, Agda peut exécuter le programme qui transforme automatiquement une fonction conçue pour le premier type en une fonction pour le second type.
- ## 2. Arend : Le langage conçu pour l'univalence
  **Arend** est un assistant de preuves récent et moderne développé par la cellule de recherche de **JetBrains**.
  * **Comment c'est implémenté :** Contrairement à Agda qui a ajouté un mode cubique après coup, Arend a été conçu dès le premier jour autour de la théorie des types homotopiques (HoTT) et de l'univalence cubique.
  * **L'avantage :** Il possède une syntaxe très épurée et s'intègre parfaitement dans les environnements de développement modernes (comme IntelliJ). C'est un langage où l'égalité est, par définition, un chemin géométrique.
- ## 3. Coq (Via des bibliothèques ou HoTT-Coq)
  Coq est le grand frère historique, basé sur le Calcul des Constructions de Thierry Coquand.
  * **L'approche axiomatique (HoTT Coq) :** Par défaut, le cœur de Coq ne sait pas exécuter l'univalence. Cependant, il existe une bibliothèque majeure nommée coq-hott. Elle ajoute l'axiome d'univalence de Voevodsky au système. Le développeur peut l'utiliser pour faire des mathématiques univalentes, mais le code contenant cet axiome "bloque" à l'exécution (il ne peut pas être réduit par la commande Compute).
  * **L'approche constructive (Coq Évolué) :** Des variantes de recherche de Coq, comme *UniMath* ou des prototypes cubiques, tentent d'intégrer nativement le calcul univalent dans le moteur de Coq.
- ## 4. Lean (Lean 3 / Lean 4)
  Dans **Lean**, le choix philosophique a été différent de celui d'Agda.
  * **Le choix de Lean :** Les concepteurs de Lean ont décidé de ne pas intégrer l'axiome d'univalence dans le noyau du langage pour conserver un système de types plus traditionnel et simple à optimiser pour les mathématiques classiques.
  * **Comment on l'utilise quand même :** L'univalence peut être déclarée comme un axiome externe par le programmeur s'il souhaite explorer la théorie des types homotopiques. De plus, la bibliothèque de théorie des catégories de Lean (Mathlib) recrée manuellement les concepts d'isomorphismes et d'équivalences de structures, mais sans la contrepartie géométrique native d'un langage comme Cubical Agda.
- ### Synthèse des implémentations
  | Langage | Type d'implémentation | Statut de l'Univalence |
  |---|---|---|
  | **Agda** (--cubical) | **Constructive (Cubique)** | **Parfaitement calculable**. Le langage de référence pour HoTT. |
  | **Arend** | **Constructive (Cubique)** | Natively univalent, conçu par JetBrains. |
  | **Coq** (coq-hott) | **Axiomatique** | Utilisable pour les preuves, mais bloque le calcul pur. |
  | **Lean 4** | **Non implémentée nativement** | Doit être ajoutée manuellement comme un axiome externe. |