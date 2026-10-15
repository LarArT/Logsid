- Oui, absolument. Le passage d'une représentation textuelle des preuves et des programmes à une représentation géométrique (réseaux de preuves, diagrammes de cordes) a donné naissance à plusieurs logiciels et outils de développement très concrets.
  Ces outils permettent de "coder" ou de "prouver" graphiquement, en manipulant des fils et des boîtes, tout en garantissant une rigueur mathématique absolue en arrière-plan.
  Voici les outils les plus emblématiques développés dans cette optique, classés par domaine d'application :
- ## 1. Calcul quantique : DisCoPy et PyZX
  C'est aujourd'hui le domaine industriel le plus actif pour ces théories. Le calcul quantique se prête parfaitement aux diagrammes de cordes car un circuit quantique est, par nature, un réseau de fils où circulent des qubits à travers des portes logiques.
  * **DisCoPy (Distributional Compositional Python) :** Développé initialement par l'Université d'Oxford, c'est une boîte à outils Python permettant de manipuler directement des diagrammes de cordes. Il est utilisé pour le traitement du langage naturel quantique (Lambeq) et la conception de circuits.
  * **PyZX :** Cet outil implémente le *ZX-calculus*, une extension directe des réseaux de preuves pour la physique quantique. PyZX permet d'entrer un circuit quantique, de le transformer en diagramme géométrique, et d'appliquer des règles de déformation topologique pour **optimiser automatiquement le circuit** (réduire le nombre de portes logiques) avant de l'exécuter sur un véritable ordinateur quantique.
- ## 2. Assistants de preuve visuels : Globular et Homotopy.io
  Pour les mathématiciens et les logiciens qui étudient la théorie des types homotopiques (HoTT) ou les catégories supérieures, taper des lignes de code devient vite impossible en raison de la dimension des espaces.
  * **Globular :** C'est un outil en ligne pionnier qui permet de construire des preuves formelles dans des catégories de dimension supérieure en dessinant et en faisant glisser des surfaces colorées. Une preuve d'égalité est littéralement une animation où l'on voit un diagramme se déformer de manière continue.
  * **Homotopy.io :** Successeur spirituel de Globular, cet assistant de preuve basé sur le web permet de manipuler des diagrammes de cordes en haute dimension. Le chercheur clique et glisse pour connecter des cellules géométriques, et le logiciel vérifie en temps réel que les déformations respectent les lois de la logique linéaire et de l'homotopie.
- ## 3. Preuves de logique linéaire : SeLog (Sequent Calculus Provers)
  Pour la logique linéaire pure, plusieurs prototypes de recherche ont été créés pour visualiser la suppression des coupures (*cut-elimination*) :
  * **Les éditeurs de réseaux de preuves :** Des outils académiques (souvent développés en OCaml ou en Java dans les laboratoires du CNRS) permettent de saisir un séquent logique et de le transformer instantanément en un réseau de fils. L'utilisateur peut cliquer sur une "coupure" (un nœud de calcul) et voir le graphe se réorganiser graphiquement et de manière synchrone pour afficher le résultat simplifié.
- ## 4. Ingénierie système : Actris / Iris
  Bien que textuels à la base, les frameworks modernes de vérification comme **Actris** (construit au-dessus d'Iris dans Coq) utilisent la notion de *Session Types*.
  * **Le principe :** Actris formalise la communication entre différents programmes distribués comme des fils logiques (des canaux) que l'on s'échange. Bien que l'outil s'utilise via du code, la structure sous-jacente du vérificateur de types est calquée sur les réseaux de preuves de Pierre-Louis Curien pour s'assurer qu'aucun message ne soit dupliqué ou perdu dans le réseau (interblocage).
- ### Synthèse des outils
  | Outil | Base Mathématique | Usage Concret |
  |---|---|---|
  | **PyZX / DisCoPy** | Diagrammes de cordes | Optimisation et compilation de **circuits quantiques**. |
  | **Homotopy.io** | Géométrie de dimension N | **Démonstration de théorèmes** topologiques par le dessin. |
  | **Actris (Coq)** | Réseaux de preuves linéaires | Certification de **systèmes distribués** et concurrents. |