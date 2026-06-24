-
- [[Les outils]]
- Voici la fiche de lecture détaillée du **16e et dernier volet** enregistré dans le cadre du cycle d'enseignement de Xavier Leroy au Collège de France (2018-2019).
  Cette session correspond au tout dernier séminaire, dispensé par le chercheur et logicien **Pierre-Louis Curien** (CNRS, Université Paris-Diderot), intitulé : **"Un panorama de la syntaxe de surface : des termes aux réseaux de preuves et aux diagrammes de cordes"**.
- ### Fiche de Lecture : Syntaxe de surface et représentations géométriques des preuves
- #### 1. Le sujet central
  Ce séminaire aborde la correspondance de Curry-Howard sous l'angle de la **syntaxe** et de la **géométrie**. Traditionnellement, un programme ou une preuve est écrit sous forme textuelle (des lignes de code, des arbres de syntaxe abstraite). Pierre-Louis Curien montre que pour certaines logiques, notamment la **logique linéaire**, l'écriture textuelle est trop rigide.
  Le séminaire présente un panorama des syntaxes géométriques alternatives — comme les **réseaux de preuves** (*proof nets*) et les **diagrammes de cordes** (*string diagrams*) — où programmer et démontrer ne consiste plus à écrire des lignes de texte, mais à **dessiner et déformer des graphes et des surfaces**.
- #### 2. Concepts clés développés
  * **La bureaucratie de la syntaxe :** En logique classique ou intuitionniste textuelle, l'ordre dans lequel on applique certaines règles de déduction crée des variations artificielles. Deux programmes peuvent être syntaxiquement différents alors qu'ils font *exactement* la même chose. C'est ce que Jean-Yves Girard appelait "la bureaucratie".
  * **Les Réseaux de Preuves (*Proof Nets*) :** Introduits avec la logique linéaire, ils éliminent cette bureaucratie. Une preuve devient un graphe géométrique où les hypothèses et les conclusions sont reliées par des cordes ou des arêtes. Deux preuves équivalentes sont représentées par un seul et unique réseau.
  * **Le calcul comme déformation (La Réduction) :** Dans ce cadre géométrique, l'exécution d'un programme (la cut-elimination ou bêta-réduction) se traduit par des règles de réécriture locales du graphe. On reconnecte les fils de manière topologique.
  * **Les Diagrammes de Cordes (*String Diagrams*) :** Issus de la théorie des catégories monoïdales, ces diagrammes permettent de représenter des transformations de types de manière bidimensionnelle. Les types sont des lignes horizontales ou verticales, et les programmes (ou fonctions) sont des "boîtes" connectant ces lignes.
- ### 3. Le lien avec la correspondance de Curry-Howard
  Ce séminaire apporte une conclusion visuelle et catégorique fondamentale au cycle de cours :
  * **Logique / Informatique :** Les types sont des fils, les programmes sont des nœuds ou des composants interceptant ces fils.
  * **Exécution :** Tirer sur les fils ou simplifier les croisements de lignes correspond exactement à l'optimisation ou à l'exécution du code.
  Cette approche montre que la structure profonde du calcul n'est pas liée à la grammaire d'un langage de programmation particulier (comme OCaml, C ou Python), mais à des **propriétés topologiques et géométriques universelles**.
- ### 4. Applications concrètes et informatiques
  Bien que très théoriques, ces représentations géométriques de la syntaxe de surface influencent plusieurs domaines de l'informatique moderne :
  * **Les compilateurs graphiques et flots de données (Dataflow) :** Des architectures de calcul basées sur des graphes (comme les graphes d'exécution de **TensorFlow** pour le machine learning, ou les langages de programmation visuelle comme **LabVIEW**) utilisent inconsciemment des structures de diagrammes de cordes pour optimiser la circulation des données.
  * **Le calcul quantique :** Les diagrammes de cordes et les réseaux de preuves sont massivement utilisés aujourd'hui pour formaliser les circuits quantiques (notamment via le calcul de surface *ZX-calculus*). Ils permettent de prouver la correction de protocoles quantiques complexes par simple manipulation de dessins géométriques.
- ### Synthèse Curry-Howard : De l'Écrit au Dessin
  | Vision Textuelle Classique | Vision Géométrique (Curien) | Signification Informatique |
  |---|---|---|
  | **Type A \to B** | Un fil A entrant dans une boîte et un fil B sortant | Signature d'une fonction |
  | **Composition de fonctions** | Connexion bout-à-bout de deux fils | Enchaînement de calculs (f o g) |
  | **Élimination de la coupure** | Raccourcissement et simplification des fils | Exécution / Compilation du programme |
- #### Conclusion
  Pierre-Louis Curien clôt ce séminaire en montrant que la correspondance de Curry-Howard s'affranchit des langages textuels. En passant des arbres de syntaxe aux surfaces et aux réseaux de fils, la logique démontre que **l'espace géométrique et le calcul informatique sont intimement liés**. Dessiner une preuve de manière topologique et faire s'écouler des données dans un circuit sont deux facettes d'une seule et même vérité mathématique.
  *Ce séminaire final offre une magnifique mise en perspective esthétique et mathématique de tout le cycle de Xavier Leroy. Vous pouvez regarder l'enregistrement sur YouTube sous le titre complet : Programmer = démontrer ? La correspondance de Curry-Howard... (16).*