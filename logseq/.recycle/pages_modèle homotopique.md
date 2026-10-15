# [[simplex vs cube]]
collapsed:: true
	- [[Le parallèle entre simplex et cube]]
	- Dans l'ensemble, **l'esprit de la proposition est correct**, mais il convient d'apporter quelques **précisions sur les termes techniques** pour éviter une confusion entre la *théorie des modèles* (le cadre mathématique classique) et la *théorie des types* (la syntaxe/logique) :
	- ### 1. Ce qui est tout à fait exact : L'équivalence géométrique
	- **L'équivalence de Quillen** s'applique au niveau des **modèles géométriques sous-jacents**. Il existe une équivalence de Quillen démontrée entre la catégorie des *ensembles simpliciaux* (modèle des quasi-catégories) et la catégorie des *ensembles cubiques*.
	- Sur le plan des objets mathématiques, le cadre cubique de Coquand et le cadre simplicial d'Emily Riehl (avec Michael Shulman) décrivent **exactement le même univers des \infty-catégories**.
	- ### 2. La nuance cruciale : Deux types de théories des types distinctes
	  
	  Sur le plan formel de la théorie des types (la syntaxe informatique), les travaux de Thierry Coquand et d'Emily Riehl ne répondent pas tout à fait au même problème :
	- **La Théorie des Types Cubiques (Thierry Coquand et al.) :**
		- **Objectif :** Rendre l'Axiome d'Univalence **constructif et calculable** pour la topologie générale.
		- **Statut de l'égalité :** Dans cette théorie, **toutes les égalités sont symétriques (non orientées)**. Un type A est un espace (un \infty-groupoïde) où les chemins peuvent toujours être parcourus dans les deux sens.
	- **La Théorie des Types Simpliciaux (Emily Riehl & Michael Shulman) :**
		- **Objectif :** Formaliser la théorie des **\infty-catégories directed (orientées)**.
		- **Statut des flèches :** Elle ajoute à la théorie des types un intervalle orienté I. Cela permet d'avoir des morphismes a \to b qui **ne sont pas inversibles** (des flèches orientées, pas de simples chemins symétriques).
	- ### En résumé
	  
	  | Domaine | Approche Cubique (Coquand) | Approche Simpliciale (Riehl & Shulman) |
	  
	  | **Monde théorique / Modèles** | Ensembles Cubiques | Ensembles Simpliciaux / Espaces de Segal |
	  
	  | **Lien mathématique** | **Équivalents via équivalence de Quillen** |  |
	  
	  | **Structure fondamentale** | Espaces, \infty-groupoïdes (chemins symétriques) | **\infty-catégories** (morphismes orientés a \to b) |
	  
	  | **Objectif principal** | Calculabilité informatique et exécution (ex: *Cubical Agda*) | Géométrie et théorie des catégories synthétiques "sur le papier" (*STT / Rzk*) |
	-
	- Pour bien situer chaque contribution, il faut distinguer la **géométrie des espaces** infinity groupoide  (où toutes les directions sont inversibles) et la **géométrie des catégories** (où les flèches ont un sens unique) (géométrie simplicial)
	- ## 1. Pourquoi Jacob Lurie est du côté d'[[Emily Riehl]] (Simplicial)
	  
	  **Jacob Lurie** est l'auteur des ouvrages de référence (*Higher Topos Theory*, *Higher Algebra*) qui ont fondé la théorie moderne des \infty-catégories.
	- **Son modèle de prédilection :** Les **quasi-catégories**, qui reposent entièrement sur les **ensembles simpliciaux** (les simplexes \Delta^n).
	- **Son objectif :** Étudier des structures orientées où l'on a des flèches non inversibles A \to B.
	- **Le lien avec Emily Riehl :** Les travaux d'Emily Riehl (avec Michael Shulman) constituent précisément une version *synthétique* (en théorie des types) du programme de Jacob Lurie ! Emily Riehl a créé la **Théorie des Types Simpliciaux** pour pouvoir manipuler les quasicategorie qui sont des modeles simpliciaux des \infty-catégories à la Lurie de manière beaucoup plus simple et élégante.
	- ## 2. Ce que fait Thierry Coquand (Cubique & Topologique)
	  
	  La **Théorie des Types Cubiques** de Thierry Coquand se concentre sur une structure géométrique différente :
	- **Son domaine :** La topologie synthétique et la **Théorie des Types Homotopiques (HoTT)** de Vladimir Voevodsky.
	- **La nature des espaces :** Dans le système de Coquand, les chemins sont tous **inversibles (symétriques)**. On n'y étudie pas des catégories orientées, mais des **\infty-groupoïdes** (des espaces topologiques où chaque flèche est un chemin qu'on peut parcourir dans les deux sens).
	- **Son objectif :** Obtenir un système informatique où l'axiome d'univalence de Voevodsky devient un **programme qui s'exécute** (calculabilité).
	- ## Synthèse des filiations
	  
	  Pour résumer clairement les rapprochements :
	  
	  `\begin{array}{ccc} \textbf{Théorie des Types Cubiques} & \longleftrightarrow & \textbf{HoTT (Voevodsky)} \\ \text{(Coquand, Bezem, Huber...)} & & \text{Espaces / $\infty$-groupoïdes (chemins symétriques)} \\ \hline \textbf{Théorie des Types Simpliciaux} & \longleftrightarrow & \textbf{$\infty$-catégories (Jacob Lurie)} \\ \text{(Emily Riehl, Michael Shulman)} & & \text{Structures orientées (morphismes non inversibles)} \end{array}`
	- **Lurie & Riehl** partagent le même univers : la théorie des **\infty-catégories** basée sur la géométrie **simpliciale**.
	- **Coquand & Voevodsky** partagent le même univers : la **théorie des types homotopiques** basée sur la calculabilité des **espaces** (dont l'implémentation la plus efficace s'est révélée être **cubique**).
-
	- il faut distinguer trois niveaux : les **espaces**, les **\infty-catégories**, et la **Théorie des Types (HoTT)**.
	- ## 1. Où s'applique l'équivalence de Quillen ? (Le monde classique)
	  
	  L'équivalence de Quillen est un théorème de la **théorie des catégories de modèles**. Elle établit un pont rigoureux entre deux constructions mathématiques classiques :
	- Au niveau des Espaces (Topologie) : Ensembles Simpliciaux (sSet)} $\quad \mathop{\rightleftarrows}_ Quillen^{\sim} \quad Ensembles Cubiques (cSet)$
	  
	  C'est l'équivalence fondamentale de Kan. Elle dit que pour étudier la topologie des espaces (les \infty-groupoïdes), les simplexes et les cubes sont deux outils parfaitement équivalents.
	- Au niveau des $\infty$-Catégories (Modèle de Jacob Lurie) :
	  `\text{Quasi-catégories simpliciales (Lurie)} \quad \mathop{\rightleftarrows}_{\text{Quillen}}^{\sim} \quad \text{Quasi-catégories cubiques}`
	  
	  L'équivalence de Quillen montre ici que la notion de \infty-catégorie de Jacob Lurie peut être définie indifféremment sur des simplexes ou sur des cubes.
	- ## 2. Quel est le lien avec HoTT (Thierry Coquand & Emily Riehl) ?
	  
	  **HoTT (Théorie des Types Homotopiques)** c'est une **syntaxe / un langage formel**.
	  
	  Le lien **sémantique (les modèles de la théorie des types)** :
		- **La Théorie des Types Cubiques (Coquand) :**
		  Thierry Coquand a construit un *modèle informatique de HoTT* fondé sur les **ensembles cubiques**. Grâce à l'équivalence de Quillen, on sait que ce que Coquand calcule dans son prouveur (Cubical Agda) décrit **la même topologie** que la topologie simpliciale usuelle.
		- **La Théorie des Types Simpliciaux (Emily Riehl) :**
		  Emily Riehl a construit une extension de HoTT adaptée aux **ensembles simpliciaux** pour pouvoir parler directement des \infty-catégories de Jacob Lurie dans la théorie des types.
	- ## Synthèse visuelle
	  
	  ```
	  MONDE DES MODÈLES MATHÉMATIQUES                   LANGAGES FORMELS / PROUVEURS
	  (Catégories de Modèles de Quillen)                    (Théorie des Types / Logiciels)
	  
	    Ensembles Simpliciaux (Lurie)   <=================>   Simplicial Type Theory (Riehl)
	                 ▲                                                    ▲
	                 │ Équivalence                                        │ Interprétation
	                 │ de Quillen                                         │ & Sémantique
	                 ▼                                                    ▼
	    Ensembles Cubiques (Kan)        <=================>   Cubical Type Theory (Coquand)
	  ```
	- ### En résumé :
	- **L'équivalence de Quillen** est le « pont mathématique » garantissant que la géométrie des simplexes (Lurie) et la géométrie des cubes (Kan) décrivent le même univers.
	- **HoTT** est le « langage de programmation / logique » bâti au-dessus pour manipuler ces univers dans un ordinateur ou sur le papier.
	- système d'Emily Riehl (Simplicial Type Theory) est une extension spécifique conçue pour gérer l'orientation des flèches dans les \infty-catégories, tandis que le système cubique de Coquand gère l'exécution calculatoire des égalités symétriques dans les espaces (HoTT).