- Voici une fiche de lecture détaillée du cours de **Xavier Leroy** au Collège de France (chaire de Sciences logicielles), intitulé **« Programmer = démontrer ? La correspondance de Curry-Howard (3) : Types inductifs et prédicats inductifs »**.
- # Fiche de Lecture : Types inductifs et prédicats inductifs
- ## 1. Informations générales
- **Auteur / Conférencier :** Xavier Leroy
- **Institution :** Collège de France (Année académique 2018-2019)
- **Thématique :** Prolongement de la correspondance de Curry-Howard
- **Durée du support vidéo :** ~1 heure et 8 minutes
- **Source :** [Vidéo du Collège de France](https://youtu.be/cUCdMS8c3kE)
- ## 2. Problématique et objectif du cours
  
  Dans les cours précédents, l'accent avait été mis sur le fragment minimal de la correspondance de Curry-Howard (fonctions polymorphes d'un côté, implication et quantification universelle de l'autre).
  
  L'objectif de cette séance `[00:01:00]` est d'étendre cette correspondance au **reste des structures de données** (au-delà des fonctions) et aux **autres connecteurs logiques** (conjonction, disjonction, négation, absurdité, quantification existentielle). La réponse unifiée à ces deux besoins réside dans l'utilisation de deux concepts clés : **les types inductifs** et **les prédicats inductifs** `[00:00:44]`.
- ## 3. Synthèse historique et conceptuelle
- ### L'évolution des structures de données   `[00:01:45]`
  
  Xavier Leroy retrace la généalogie des structures en informatique pour montrer comment on a abouti aux types modernes :
- **Fortran (1957) :** Types de base et tableaux multi-dimensionnels `[00:01:58]`.
- **Cobol (1959) :** Introduction des enregistrements (*records*), collections de champs nommés et hétérogènes `[00:02:57]`.
- **Algol W / C / Pascal (1966+) :** Références et pointeurs (et la fameuse "erreur à un milliard de dollars" du pointeur nul selon Tony Hoare) `[00:03:47]`.
- **Algol 68 / Pascal / C :** Unions discriminées ou variantes (types sommes rudimentaires) `[00:04:42]`.
- **Lisp (1960) & Prolog (1972) :** Approche par type universel (S-expressions ou algèbres de termes) `[00:06:03]`.
- **LCF ML (1978) :** Typage statique avec types produits (\times) et sommes (+) prédéfinis (qui correspondent par Curry-Howard au *ET* et au *OU* logiques) `[00:07:16]`.
- **Hope, Caml, Haskell (1980+) :** **Types algébriques de données**, combinant sommes, produits et récursion via le mécanisme de filtrage de motifs (*pattern matching*) `[00:09:21]`.
- ## 4. Les Types Inductifs (La vision "Théorie des Types")
  
  Les types inductifs sont essentiellement l'équivalent des types algébriques de données, mais adaptés à la théorie des types dépendants (systèmes comme Coq ou Agda) `[00:11:19]`.
- **Principe :** Un type inductif définit le plus petit ensemble de valeurs engendré et saturé par un ensemble de règles initiales appelées **constructeurs** `[00:13:27]`.
- **Exemples fondamentaux décrits :**
	- Le type vide (`False` en logique) : possède 0 constructeur `[00:14:11]`.
	- Le type unité (`True` ou `unit`) : possède 1 seul constructeur sans argument `[00:14:03]`.
	- Les booléens : 2 constructeurs (`true` et `false`) `[00:13:57]`.
	- Les entiers naturels de Peano : une constante `O` et un constructeur de successeur `S : nat -> nat` `[00:14:25]`.
- ### Propriété cruciale : Finitude en profondeur
  
  Un objet inductif peut être infini en largeur (par exemple, les ordinaux de Brouwer utilisant des fonctions indexées sur les entiers) `[00:15:00]`, mais il est **toujours fini en profondeur** `[00:16:14]`. C'est cette absence de branche infinie descendante qui garantit la validité des raisonnements par récurrence.
- ## 5. Élimination, Récursion et la Condition de Garde
  
  Pour exploiter un type inductif, on utilise son principe d'élimination : le **filtrage** (*pattern matching*) `[00:25:12]`. Par Curry-Howard, le filtrage sur une structure équivaut directement à une **démonstration par cas** en logique `[00:25:46]`.
- ### La préservation de la cohérence logique
  
  Dans un assistant de preuve, toutes les fonctions doivent obligatoirement terminer (normalisation forte) `[00:11:57]`. Si la récursion générale (infinie) était autorisée, on pourrait définir un terme qui boucle et lui donner le type vide (`False`), ce qui effondrerait la logique en permettant de prouver n'importe quoi (paradoxe de l'absurdité) `[00:31:33]`.
- ### La récursion structurelle   `[00:30:52]`
  
  Pour assurer la terminaison, Coq impose une **condition de garde syntaxique** : les appels récursifs doivent impérativement être faits sur des **sous-termes stricts** de l'argument initial (ex: passer de `S n` à `n`).
- *Limites :* Ce critère purement syntaxique rejette des fonctions pourtant tout à fait légitimes (comme la division euclidienne par soustractions successives) `[01:01:25]`.
- *Piste de recherche :* L'utilisation de types calibrés par la taille (*sized types*), implémentés partiellement dans Agda `[01:02:13]`.
- ## 6. La Condition de Positivité Strict
  
  Pour éviter des incohérences logiques massives, le type en cours de définition ne doit apparaître qu'en **position strictement positive** dans le type de ses constructeurs `[00:32:33]`.
- Une occurrence positive se situe à droite des flèches (\to). Passer à gauche d'une flèche inverse la polarité `[00:32:45]`.
- **Le danger des occurrences négatives :** Permet d'injecter la négation de soi-même dans soi-même, menant immédiatement à des paradoxes logiques de type auto-référence (Paradoxe de Russell ou codage du lambda-calcul pur qui boucle à l'infini) `[00:33:28]`.
- ## 7. Familles inductives et Prédicats inductifs
  
  Au-delà des types paramétrés classiques (comme les listes polymorphes), la théorie permet de définir des **familles inductives** où les paramètres varient lors des appels récursifs `[00:36:08]`.
- ### Les Prédicats Inductifs   `[00:39:21]`
  
  Ils permettent de modéliser des propriétés mathématiques logées dans l'univers `Prop` sous forme de **règles d'inférence** (Axiomes \to constructeurs constants ; Règles \to constructeurs avec arguments) `[00:39:54]`.
- *Exemple :* Le prédicat `even` (parité d'un entier) avec un cas de base pour 0 et une règle inductive pour n+2 `[00:40:41]`.
- Faire une récursion sur la preuve d'un prédicat inductif revient exactement à faire une **récurrence sur la structure de la dérivation (la preuve)** `[00:40:21]`.
- ### Deux cas spectaculaires : L'accessibilité et L'Égalité
- **L'accessibilité (Ordres bien fondés) :** Un ordre est bien fondé si tout élément est "accessible", c'est-à-dire inductitivement défini par le fait que tous ses prédécesseurs le sont. Cela formalise la récurrence noethérienne `[00:43:08]`.
- **L'égalité de Martin-Löf :** L'égalité mathématique elle-même peut être définie de façon purement inductive comme une relation n'ayant qu'un unique constructeur : la **réflexivité** (`eq_refl : forall x, x = x`) `[00:44:56]`. L'élimination de cette preuve d'égalité n'est rien d'autre qu'une analyse par cas permettant de substituer un terme par un autre `[00:45:51]`.
- ## 8. Concepts Avancés et Limites Actuelles   `[00:54:01]`
  
  Le cours se termine sur l'ouverture vers des notions avancées et des ponts jetés vers la programmation :
- **GADT (Types Algébriques de Données Généralisés) :** L'importation du concept de familles inductives dans les langages de programmation (Haskell en 2007, OCaml en 2012) pour typer plus finement des objets (comme le `printf` statiquement typé) `[00:46:51]`.
- **Types Quotients :** Un problème ouvert majeur en théorie des types. En mathématiques, on passe souvent au quotient par une relation d'équivalence (ex: définir les rationnels \mathbb{Q} à partir de \mathbb{Z} \times \mathbb{Z}^*). En théorie des types standards, il n'y a pas de construction native satisfaisante pour cela `[01:05:28]`.
- **Types Inductifs Supérieurs (HIT) :** Une solution issue de la *Théorie Homotopique des Types (HoTT)* consistant à définir des types inductifs non seulement par des constructeurs de points, mais aussi par des constructeurs d'égalités (de chemins), ouvrant la voie au traitement natif des quotients `[01:06:31]`.
- ## Conclusion / Portée du cours
  
  Ce cours démontre avec brio que le concept d'**induction** est le véritable pivot unifiant le calcul et la logique. Définir un type de données (informatique) ou définir un prédicat/une relation (mathématiques) procède exactement du même formalisme sous Curry-Howard. La robustesse de ce système repose sur des garde-fous stricts (positivité et structures de garde) garantissant que tout calcul se termine et que toute preuve reste cohérente.
-