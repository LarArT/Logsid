- Voici une fiche de lecture détaillée du cours de Xavier Leroy au Collège de France, intitulé **« Polymorphisme à tous les étages ! Du système F au calcul des constructions »** (série *« Programmer = démontrer ? La correspondance de Curry-Howard aujourd'hui »*).
- # Fiche de lecture : Polymorphisme à tous les étages !
- ## 1. Informations générales
  * **Auteur / Conférencier :** Xavier Leroy (Chaire Sciences du logiciel, Collège de France)
  * **Date du cours :** 21 novembre 2018
  * **Thématique principale :** L'extension du lambda-calcul et de la logique propositionnelle via le polymorphisme, les constructeurs de types et les types dépendants.
- ## 2. Objectif du cours
  L'objectif est de dépasser les limites du lambda-calcul simplement typé (en informatique) et de la logique intuitionniste propositionnelle (en logique). Le cours démontre comment la convergence des besoins en programmation (généricité, réutilisation de code) et en logique (arithmétique du second ordre, assistants de preuve) a mené à des systèmes unifiés extrêmement puissants.
- ## 3. Structure et concepts clés
- ### Axe 1 : Le polymorphisme du second ordre (Système F)
  * **Le problème en programmation :** Avec les types simples, on fait du "copier-coller" de code pour adapter une même logique (ex. un algorithme de tri) à différents types (entiers, chaînes).
  * **La solution (John Reynolds, 1974) :** Permettre de passer des types comme paramètres à des fonctions. Introduction du quantificateur universel (\forall X. T) et du grand lambda (\Lambda).
  * **La convergence logique (Jean-Yves Girard, 1970) :** Girard invente le même système (baptisé **Système F**) pour étudier l'arithmétique du second ordre (qui permet de quantifier sur des ensembles d'entiers, modélisant ainsi les réels).
  * **Propriété majeure :** **Normalisation forte**. Tout programme du Système F termine toujours. La preuve est complexe car le système est *imprédicatif* (un type abstrait peut être instancié par lui-même).
- ### Axe 2 : Les constructeurs de types (F^\omega)
  * **Concept :** Passage à un niveau supérieur où l'on manipule des fonctions de types vers des types (ex. le constructeur Liste qui prend un type T et renvoie le type Liste de T).
  * **Les Sortes (Kinds) :** Pour éviter les types mal formés, on introduit un système de types pour les types, appelé "sortes" (noté \star pour les types de base, et \star \rightarrow \star pour les constructeurs).
- ### Axe 3 : Les types dépendants (Logique LF)
  * **Concept :** Un type qui dépend d'un terme (une valeur).
   * *En logique :* C'est un prédicat (ex. le type des preuves que n est pair dépend de l'entier n).
   * *En programmation :* C'est par exemple un tableau dont la taille fait partie du type (ex. un tableau de taille n+m).
  * **Problème de la conversion :** Vérifier l'égalité de deux types dépendants (ex. est-ce que le type Tableau(5+1) est égal à Tableau(6)) implique de faire sémantiquement des calculs ou des preuves mathématiques lors du typage, ce qui peut devenir indécidable.
  * **Origine historique :** Le système *Automath* de Nicolaas de Bruijn (1968), ancêtre des assistants de preuve modernes.
- ## 4. La grande synthèse : Le Cube de Barendregt et les PTS
  Le logicien Henk Barendregt a formalisé ces extensions sous la forme d'un cube à trois dimensions à partir des types simples :
  1. **Axe X :** Le polymorphisme (Termes dépendants de Types \rightarrow Système F).
  2. **Axe Y :** Les constructeurs (Types dépendants de Types \rightarrow F^\omega).
  3. **Axe Z :** Les types dépendants (Types dépendants de Termes \rightarrow \lambda P ou LF).
  Le sommet combinant les trois dimensions est le **Calcul des Constructions (CoC)**, développé par Thierry Coquand et Gérard Huet (1986), qui sert de fondement au logiciel **Coq**. Les **Systèmes de Types Purs (PTS)** unifient cette syntaxe en fusionnant termes, types et sortes dans une grammaire unique régie par des *univers*.
- ## 5. Les pièges logiques : "Type:Type" et le paradoxe de Girard
  Vouloir simplifier à l'extrême en posant qu'un univers contient sa propre sorte (introduire l'axiome Type : Type) mène à des incohérences. Per Martin-Löf a proposé cette approche en 1971, mais Jean-Yves Girard a démontré qu'elle permettait de reproduire une variante du paradoxe de Russell (le paradoxe de Burali-Forti sur les ordinaux). Par conséquent, la logique s'effondre (on peut tout démontrer, même le faux). C'est pourquoi les systèmes comme Coq ou Agda utilisent une stratification stricte d'univers infinis (Type 0, Type 1, etc.).
- ## 6. Conclusion et perspectives
  Le cours montre le succès total de la correspondance de Curry-Howard. La convergence entre logiciens et informaticiens a permis de concevoir des systèmes où **écrire un programme hautement générique équivaut à formaliser une théorie mathématique profonde**. Xavier Leroy conclut en ouvrant sur le cours suivant, qui quittera le seul monde des fonctions pour introduire les types inductifs et les structures de données.
- Le **Cube de Barendregt** (ou cube des lambda-calculs) est un outil visuel extraordinaire inventé par le logicien Henk Barendregt. Son but est de classer et de cartographier la puissance des langages de programmation et des systèmes logiques.
  Pour comprendre simplement, imaginez que vous partez du langage informatique le plus basique possible (le lambda-calcul simplement typé) et que vous pouvez lui ajouter **trois super-pouvoirs** différents. Chaque super-pouvoir correspond à une dimension (un axe) du cube.
- ## Les 3 Axes du Cube (Les 3 Super-Pouvoirs)
  Pour construire le cube, on part du coin inférieur gauche (le niveau 0) et on ajoute des axes :
- ### 1. L'axe du Polymorphisme (Axe X) : Les fonctions qui acceptent des types
  Dans un langage basique, si vous écrivez une fonction pour trier une liste d'entiers, elle ne marche *que* pour les entiers. Si vous voulez trier des chaînes de caractères, il faut réécrire la fonction.
  * **Le super-pouvoir :** On permet aux fonctions de prendre un **type en paramètre** (par exemple : "Donne-moi un type X et une liste de X, et je te la trie"). C'est ce qu'on appelle les *generics* en Java/C# ou le **Système F**.
- ### 2. L'axe des Constructeurs de types (Axe Y) : Les types qui créent des types
  Au niveau basique, les types sont figés (comme Entier, Booléen).
  * **Le super-pouvoir :** On crée des "machines à fabriquer des types". Par exemple, Liste n'est pas un type en soi, c'est une fonction de type. Si on lui donne Entier, elle fabrique le type Liste d'Entiers. C'est l'extension appelée **F^\omega** (F-oméga).
- ### 3. L'axe des Types Dépendants (Axe Z) : Les types qui dépendent de valeurs
  C'est le pouvoir le plus difficile et le plus mathématique. Habituellement, le monde des programmes (les valeurs comme 3, "bonjour") et le monde des types (Entier, Chaîne) sont totalement séparés.
  * **Le super-pouvoir :** On permet à un type de dépendre d'une valeur concrète. Par exemple, au lieu d'avoir juste le type Tableau, on peut créer le type Tableau de taille 5. Si vous essayez d'y ajouter un 6ème élément, le compilateur voit une erreur avant même que le programme ne s'exécute. C'est le système **LF** (Logical Framework).
- ## Le Sommet du Cube : Le Calcul des Constructions
  Si vous activez ces trois super-pouvoirs en même temps, vous atteignez le sommet opposé du cube : le **Calcul des Constructions (CoC)**.
  C'est un système d'une puissance logicielle et mathématique absolue. C'est la base de logiciels appelés **assistants de preuve** (comme le célèbre logiciel français **Coq** ou le langage **Agda**). Dans ces systèmes, grâce à la correspondance de Curry-Howard :
  * Écrire un programme informatique équivaut à écrire une démonstration mathématique.
  * Vérifier que le programme ne bugge pas équivaut à vérifier que le théorème est vrai.
- ## En résumé
  Le Cube de Barendregt n'est rien d'autre qu'un **menu de restaurant pour concepteurs de langages de programmation** : vous pouvez choisir de concevoir un langage simple, d'y ajouter un seul ingrédient (comme le polymorphisme dans les langages modernes), ou de tout prendre (les types dépendants) pour fabriquer une machine à prouver des théorèmes mathématiques.
  Souhaitez-vous que l'on zoome sur l'un de ces trois axes pour voir concrètement à quoi ressemble le code associé ?
- Le deuxième axe du Cube de Barendregt concerne les **constructeurs de types** (souvent associé au système nommé **F^\omega**).
  Pour comprendre cet axe simplement, il faut d'abord comprendre un concept fondamental : **les fonctions**.
- ## 1. L'analogie : Des fonctions à tous les étages
  * **Une fonction classique (au niveau du code) :** C'est une machine qui prend une *valeur* et renvoie une *valeur*.
   * *Exemple :* La fonction double(x) prend l'entier 3 et renvoie l'entier 6.
  * **Un constructeur de types (au niveau des types) :** C'est une machine qui prend un *type* et renvoie un *type*.
   * *Exemple :* Le constructeur Liste prend le type Entier et renvoie le type Liste d'Entiers.
  Sur cet axe, on s'autorise à manipuler ces "machines à fabriquer des types" exactement comme s'il s'agissait de types normaux. On peut les passer en paramètre, les combiner et créer des structures de données extrêmement abstraites.
- ## 2. Un exemple concret : L'abstraction de conteneur
  Imaginez que vous développez une application et que vous voulez définir ce qu'est une **Collection** (un conteneur qui peut stocker des éléments, comme une Liste, un Arbre binaire ou un Vecteur).
  Sans le deuxième axe, vous pouvez définir une Liste d'éléments, mais vous ne pouvez pas écrire une fonction générique qui fonctionne pour *n'importe quel type de conteneur*.
  Avec le deuxième axe, vous pouvez écrire un type qui dit :
  > « Je prends en paramètre une machine à fabriquer des types (appelons-la C), et je vais l'appliquer à un type d'élément (appelons-le X). »
  > 
  En pseudo-code, cela ressemble à ceci :
  ```text
  // C est un constructeur de type (ex: Liste, Arbre, Vecteur)
  // X est un type de base (ex: Entier, Chaîne)
  type Collection[C, X] = C[X]
  
  ```
  Si vous passez Liste et Entier, le système calcule automatiquement le type final : Liste[Entier].
- ## 3. Le besoin de flicage : Les "Sortes" (Kinds)
  Dès que l'on commence à manipuler des fonctions qui créent des types, un problème surgit : comment s'assurer qu'on ne fait pas n'importe quoi ?
  Dans un langage classique, les types servent à empêcher les erreurs (comme essayer de multiplier une chaîne de caractères par un booléen). Au niveau supérieur, il faut un système pour empêcher les erreurs de types... dans les types ! C'est ce qu'on appelle les **Sortes** (ou *Kinds* en anglais). On peut voir cela comme **le type d'un type**.
  * \star (prononcé "Étoile") : C'est la sorte de tous les types simples, ceux qui décrivent des valeurs directes (comme Entier, Booléen, Chaîne).
  * \star \rightarrow \star : C'est la sorte d'un constructeur de type simple (comme Liste). Cela signifie : *"Donne-moi un type simple (\star), et je te renverrai un type simple (\star)"*.
  Grâce aux sortes, le compilateur peut interdire des absurdités syntaxiques. Par exemple, si vous essayez d'écrire Liste[Liste], le compilateur va regarder les sortes :
  * Liste attend un type de sorte \star.
  * Or, la seconde Liste est de sorte \star \rightarrow \star.
  * **Erreur de sorte !** Le type est rejeté avant même que le programme ne tourne.
- ## En résumé
  Le deuxième axe apporte la puissance de la **programmation fonctionnelle appliquée aux types eux-mêmes**. C'est cet axe qui permet, dans les langages modernes (comme Haskell, Scala ou via des patterns avancés en TypeScript), de manipuler ce que les développeurs appellent des *Higher-Kinded Types* (des types paramétrés par d'autres constructeurs de types), offrant un niveau d'abstraction maximal pour les bibliothèques et les frameworks.
- Le troisième axe du Cube de Barendregt est sans doute le plus fascinant et le plus révolutionnaire. Il introduit le concept de **types dépendants**.
  Pour le comprendre simplement, il faut d'abord réaliser qu'en programmation traditionnelle, il y a une frontière étanche entre deux mondes :
   1. **Le monde des types :** Ce sont les étiquettes statiques que le compilateur vérifie (ex: Entier, Chaîne, Booléen).
   2. **Le monde des valeurs (les termes) :** Ce sont les données concrètes qui bougent et changent pendant que le programme s'exécute (ex: 4, "bonjour", true).
  Le troisième axe fait sauter cette frontière : **il permet à un type de dépendre d'une valeur dynamique**.
- ## 1. Un exemple concret : Les tableaux sécurisés
  Dans un langage classique comme Java ou C, si vous créez un tableau, son type est simplement Tableau d'Entiers.
  * Si le tableau a une taille de 3 éléments et que votre programme essaie de lire le 4ème élément, le compilateur ne dit rien.
  * L'erreur se produit **pendant l'exécution**, provoquant un crash du programme (le fameux *IndexOutOfBoundsException*).
  Avec les types dépendants, la taille du tableau s'invite directement *dans* le type. Le type n'est plus juste Tableau, mais Vecteur(X, n) où X est le type des éléments et n est la **valeur** représentant sa taille.
- ### L'avantage magique pour le code
  Imaginez une fonction de concaténation qui prend deux tableaux et les met bout à bout. Avec les types dépendants, on peut écrire son type de manière ultra-précise :
  ```text
  concatène(Vecteur(Entier, n), Vecteur(Entier, m)) -> Vecteur(Entier, n + m)
  
  ```
  Ici, le compilateur fait des mathématiques. Si vous essayez d'écrire un code qui prend un tableau de taille 3, un tableau de taille 2, et que votre fonction renvoie par erreur un tableau de taille 4 (parce qu'elle a oublié un élément en chemin), **le programme refusera de compiler**. Le compilateur sait que 3 + 2 \neq 4.
- ## 2. La correspondance en logique : Les prédicats
  Le cours de Xavier Leroy s'intitule *"Programmer = démontrer"*. Quel est le rapport entre ces tableaux et les mathématiques ?
  Grâce à la correspondance de Curry-Howard, un type dépendant en informatique correspond exactement à un **prédicat** (ou une propriété) en logique.
  * Un type simple comme Entier est juste un ensemble de données.
  * Un type dépendant comme Premier(n) est une proposition logique qui dépend de la valeur de n (*"L'entier n est un nombre premier"*).
  Si vous arrivez à écrire une fonction qui renvoie un objet de type Premier(7), le simple fait que votre programme compile prouve mathématiquement que 7 est un nombre premier. La valeur de la preuve est vérifiée par le compilateur.
- ## 3. Pourquoi tous nos langages n'ont-ils pas ce super-pouvoir ?
  Si c'est si génial pour éviter les bugs, pourquoi Python, Java ou C++ n'utilisent-ils pas tous des types dépendants ?
  Parce que cela rend le typage **indécidable** ou extrêmement complexe. Si le type d'un tableau dépend d'une variable n, et que cette variable n est calculée par une fonction complexe (par exemple, le résultat d'une suite mathématique ou une entrée tapée par l'utilisateur), comment le compilateur peut-il deviner à l'avance si le type est correct ?
  Pour résoudre cela, le compilateur doit lui-même exécuter des morceaux de code ou demander au développeur d'écrire des **preuves mathématiques** directement au milieu de son code pour lui "expliquer" pourquoi l'égalité est vraie.
- ## En résumé
  Le troisième axe fait passer le compilateur du rôle de "simple vérificateur d'étiquettes" à celui de **mathématicien rigoureux**. C'est cet axe qui transforme un langage de programmation en un outil capable de certifier qu'un logiciel est mathématiquement parfait et sans aucun bug (comme on le fait pour les logiciels de pilotage de fusées ou de métros automatiques via des systèmes comme Coq ou Lean).
- Le troisième axe (les types dépendants) est l'un des domaines les plus pointus de la recherche en informatique. Bien que ce concept soit né dans les années 1970 avec le système **Automath** et la **théorie des types de Martin-Löf**, son implémentation dans de vrais langages de programmation utilisables a pris du temps.
  Voici les principaux langages qui l'implémentent et des exemples concrets de leur application.
- ## 1. Dans quels langages trouve-t-on le troisième axe ?
  On peut diviser ces langages en deux catégories :
- ### Les assistants de preuve (Logique + Programmation)
  Ce sont des outils conçus avant tout pour faire des mathématiques, mais qui sont aussi des langages de programmation fonctionnels complets.
  * **Coq (devenu Rocq) :** Développé en France (Inria), basé directement sur le Calcul des Constructions (le sommet du cube).
  * **Lean :** Développé par Microsoft Research, aujourd'hui massivement utilisé par les mathématiciens pour vérifier des théorèmes complexes.
- ### Les langages de programmation généraux à types dépendants
  Ce sont des langages créés spécifiquement pour écrire des logiciels classiques (applications, serveurs, compilateurs) mais avec la sécurité absolue du troisième axe.
  * **Idris :** Un langage très proche de Haskell, mais avec des types dépendants complets. Il est conçu pour la programmation de tous les jours.
  * **Agda :** À la frontière entre l'assistant de preuve et le langage de programmation.
- ## 2. Exemples concrets d'implémentation
  Pour comprendre comment cela fonctionne, voici deux exemples classiques d'utilisation des types dépendants.
- ### Exemple A : Le vecteur de taille fixe (en Idris)
  L'exemple le plus célèbre est le tableau dont la taille est inscrite dans le type. En Idris, la syntaxe pour déclarer un vecteur ressemble à ceci :
  ```idris
  -- On définit un vecteur de 3 entiers
  monTableau : Vect 3 Integer
  monTableau = [10, 20, 30]
  
  ```
  Si vous essayez d'écrire ceci, le compilateur génère une **erreur de typage** immédiatement, car le type annoncé (Vect 3) ne correspond pas à la valeur fournie (4 éléments) :
  ```idris
  -- ERREUR À LA COMPILATION :
  monTableauErreur : Vect 3 Integer
  monTableauErreur = [10, 20, 30, 40] 
  
  ```
- ### Exemple B : L'accès sécurisé à un élément (en Idris / Agda)
  Dans un langage classique, la fonction pour lire un élément dans un tableau à l'indice i peut planter si i est trop grand.
  Avec les types dépendants, on utilise un type spécial pour l'indice, souvent appelé Fin n (pour "entier fini strictement inférieur à n").
  ```idris
  -- La fonction "index" prend :
  -- 1. Un indice qui est obligatoirement plus petit que n
  -- 2. Un vecteur de taille n
  -- 3. Elle renvoie l'élément trouvé
  index : Fin n -> Vect n a -> a
  
  ```
  Si le vecteur a une taille de 3 (n = 3), le type Fin 3 n'autorise que les valeurs 0, 1 et 2. Essayer de passer 3 comme argument provoquera un refus de compilation. **La fonction ne peut mathématiquement jamais planter à l'exécution.**
- ## 3. Applications réelles d'envergure
  Où utilise-t-on concrètement ce troisième axe aujourd'hui ?
  * **Le projet CompCert (en Coq) :** C'est un compilateur pour le langage C entièrement écrit et vérifié en Coq. Il est utilisé dans l'industrie aéronautique et nucléaire. Parce qu'il utilise les types dépendants et le calcul des constructions, il est mathématiquement prouvé que ce compilateur ne produit **aucun bug** lors de la traduction du code source en code machine.
  * **La cryptographie (Projet Everest / F*) :** Spécifier des protocoles de sécurité (comme TLS/HTTPS) avec des types dépendants permet de prouver qu'aucune faille de type "dépassement de tampon" (buffer overflow) ou fuite de mémoire n'est possible dans le code généré.
  Le troisième axe est donc disponible et utilisé, mais principalement là où le coût d'un bug informatique serait catastrophique (spatial, médical, sécurité d'État, cryptographie monétaire).
-