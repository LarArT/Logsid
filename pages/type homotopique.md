- Voici la fiche de lecture détaillée et structurée du **cours numéro 10** de la série de Xavier Leroy au Collège de France (2018-2019), intitulé : **"What is equality? From Leibniz to homotopy type theory"** (Qu'est-ce que l'égalité ? De Leibniz à la théorie des types homotopiques).
- ### Fiche de Lecture : La nature de l'égalité et la théorie des types homotopiques
- #### 1. Le problème de fond : L'insaisissable définition de l'égalité
  En informatique et en logique, l'égalité semble être une notion simple (ex: x == y). Pourtant, dès que l'on manipule des structures mathématiques complexes ou des types dépendants, définir précisément quand deux objets sont "égaux" devient un casse-tête fondamental.
  * **L'égalité syntaxique ou définitionnelle :** Deux choses sont égales parce qu'elles se calculent de la même façon (ex: 2+2 et 4).
  * **L'égalité propositionnelle :** Deux choses sont égales parce qu'on peut prouver qu'elles partagent les mêmes propriétés, même si leur code ou leur forme diffère (ex: deux fonctions qui renvoient les mêmes résultats pour les mêmes entrées, mais écrites différemment).
  Le grand problème de la correspondance de Curry-Howard traditionnelle est qu'elle gère mal l'égalité de fonctions ou de types entre eux, bloquant le développement d'une structure mathématique globale unifiée.
- #### 2. La solution historique : De Leibniz à Martin-Löf
  Xavier Leroy retrace le parcours de cette notion :
  * **Leibniz :** L'identité des indiscernables. Deux objets sont égaux s'ils partagent absolument toutes leurs propriétés.
  * **Martin-Löf (Théorie des types dépendants) :** Pour prouver que x = y, il faut fournir une *preuve* d'égalité. Cette preuve est elle-même un objet (un terme). Par conséquent, il peut exister *plusieurs manières différentes* de prouver que deux choses sont égales. L'égalité n'est plus un simple fait binaire (vrai/faux), elle possède sa propre structure.
- #### 3. Le saut conceptuel : La théorie des types homotopiques (HoTT)
  La grande révolution abordée dans ce 10e cours est la **Théorie des Types Homotopiques (HoTT)**, popularisée par Vladimir Voevodsky.
  * **L'analogie géométrique (Homotopie) :** En topologie, on étudie les déformations continues des espaces. HoTT applique cela à la logique :
   * Un **Type** est vu comme un **Espace géométrique**.
   * Une **Valeur** (un élément du type) est un **Point** dans cet espace.
   * Une **Preuve d'égalité** entre deux valeurs est un **Chemin** (un tracé) reliant ces deux points.
   * Une **Preuve d'égalité entre deux preuves d'égalité** devient une déformation de chemin (une homotopie), c'est-à-dire une surface reliant deux chemins !
  * **L'axiome d'univalence :** C'est le cœur de la leçon. Cet axiome affirme que **l'isomorphisme équivaut à l'identité**. Si deux structures (ou types de données) sont isomorphes (c'est-à-dire qu'on peut passer de l'une à l'autre sans perte d'information), alors elles sont mathématiquement *égales*.
- #### 4. Applications concrètes en informatique et langages
  Bien que très abstrait, ce concept révolutionne la programmation et les assistants de preuve :
  * **Le transfert de théorèmes gratuit :** Imaginons que vous écriviez une bibliothèque logicielle en utilisant une structure de données (comme les listes) et que vous prouviez qu'elle est correcte. Plus tard, vous décidez d'utiliser une structure beaucoup plus performante (comme les arbres rouges-noirs). Si les deux structures sont isomorphes, l'axiome d'univalence vous permet de transférer instantanément toutes vos preuves logiques de la structure lente à la structure rapide, sans avoir à réécrire la moindre démonstration.
  * **Nouveaux assistants de preuves (Cubical Agda / Arend) :** Des langages de programmation expérimentaux basés sur la théorie des types dépendants intègrent nativement ces concepts géométriques pour permettre aux développeurs de raisonner sur l'équivalence de programmes de manière bien plus intuitive.
- ### Synthèse logico-informatique de HoTT
  | Concept Logique/Informatique | Interprétation Géométrique (HoTT) |
  |---|---|
  | **Type** (ex: Int, List) | **Espace** (Ensemble de points interconnectés) |
  | **Élément / Valeur** (ex: 42) | **Point** dans l'espace |
  | **Preuve d'égalité** (x = y) | **Chemin** continu entre le point x et le point y |
  | **Axiome d'Univalence** | **Équivalence topologique** (Deux espaces de même forme sont identiques) |
- #### Conclusion
  Xavier Leroy referme cette série de cours en montrant que la correspondance de Curry-Howard a fini par unifier trois grands piliers de la pensée humaine : la **Logique** (les propositions), l'**Informatique** (les programmes) et la **Géométrie** (les espaces topologiques). Définir l'égalité non plus comme une rigidité syntaxique, mais comme un chemin dans un espace, ouvre la voie à une informatique où la réutilisation et la certification globale du code deviennent enfin fluides.
  Si vous souhaitez explorer visuellement ces notions d'espaces et de chemins appliquées aux programmes, vous pouvez consulter le Cours 10 de Xavier Leroy sur le Collège de France. Cette vidéo illustre parfaitement comment les concepts géométriques les plus abstraits viennent au secours de la sécurité et de la flexibilité de nos systèmes logiciels.