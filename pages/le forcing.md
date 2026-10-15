- Voici la fiche de lecture de la **12e vidéo** de l'enseignement de Xavier Leroy (2018-2019) au Collège de France.
  Il s'agit du **séminaire du 9 janvier 2019** intitulé : **"Le forcing, une transformation de programme comme une autre ?"**, dispensé par le logicien Alexandre Miquel en complément du cours de Xavier Leroy.
- ### Fiche de Lecture : Le Forcing et les Transformations de Programmes
- #### 1. Le sujet central
	- Le forcing est, historiquement, une méthode de logique mathématique inventée par Paul Cohen en 1963 pour démontrer l'indépendance de l'Hypothèse du Continu et de l'Axiome du Choix dans la théorie des ensembles (ZF).
	- L'objectif de ce séminaire est de jeter un pont spectaculaire via la correspondance de Curry-Howard : montrer que **le forcing mathématique n'est rien d'autre qu'une transformation de programme informatique**, s'apparentant à de la compilation ou à une traduction de code (comme le passage en style de transmission de continuations ou *CPS*).
- #### 2. Concepts clés développés
	- **L'extension de modèles par l'informatique :** En mathématiques, le forcing permet d'ajouter des "objets génériques" imaginaires à un modèle logique pour créer un nouveau modèle plus riche. En informatique, cela revient à ajouter de nouvelles fonctionnalités ou constantes à un langage de programmation (par exemple, des canaux de communication ou de la mémoire mutable) tout en préservant la cohérence de son système de types.
	- *La relation de forcing( $p \Vdash A$ ) : En logique, cela signifie qu'une condition ou une information partielle p "force" la proposition A à être vraie. Alexandre Miquel montre que cette condition p se comporte exactement comme un **environnement d'exécution** ou une contrainte de ressources en informatique.
	  * **La traduction de types :** La correspondance montre que transformer une preuve par forcing correspond à transformer le code source d'un programme. Si l'on traduit une proposition mathématique A sous la forme forcée A^*, on définit en réalité un nouveau type de données en programmation qui prend en compte les contextes ou les ressources variables.
- #### 3. L'analogie avec les pratiques de programmation
  Le séminaire explique que le forcing, lorsqu'il est décodé par l'informatique, ressemble à plusieurs outils bien connus des ingénieurs logiciels :
  * **Les Continuations (CPS) :** Le forcing manipule la notion de vérité future ou d'information croissante, ce qui est conceptuellement proche de la monade de continuation ou de l'évaluation différée.
  * **Le passage d'état / d'environnement :** Forcer une formule en fonction d'une condition p revient à passer un paramètre de configuration supplémentaire (comme dans la Monade *Reader* ou *State*) à toutes les fonctions de votre programme.
- ### Synthèse Curry-Howard : Le Forcing décodé
  | Vision Logique / Mathématique | Vision Informatique (Curry-Howard) |
  |---|---|
  | **Extension générique d'un modèle (Cohen)** | Extension d'un langage avec de nouvelles primitives |
  | **Condition ou information partielle p** | Environnement, ressources ou état d'exécution |
  | **La relation de Forcing p \Vdash A** | Une fonction qui prend une ressource p et produit un type A |
  | **Preuve par forcing d'un théorème** | Compilation / Traduction de code d'un langage vers un autre |
- #### Conclusion
  Ce séminaire démontre la puissance bilatérale de la correspondance de Curry-Howard : non seulement l'informatique bénéficie des structures logiques pour sécuriser ses programmes, mais **l'informatique permet de simplifier et d'éclairer des pans entiers des mathématiques pures**. Le forcing, autrefois considéré comme une technique de logique pure extrêmement complexe et abstraite, trouve sa contrepartie naturelle dans les techniques d'ingénierie logicielle et de transformation de code.
  Cette vidéo est essentielle si vous souhaitez comprendre comment l'informatique moderne parvient à donner une sémantique de calcul à des théories mathématiques très abstraites. Pour visionner cette session, vous pouvez consulter la vidéo Programmer = démontrer ? La correspondance de Curry-Howard... (12). Elle montre avec brio l'imbrication des mathématiques fondamentales du XXe siècle et de la compilation.