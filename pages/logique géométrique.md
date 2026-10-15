- En logique mathématique et en théorie des topos, une **théorie géométrique** est une théorie du premier ordre formulée dans un fragment spécifique de la logique, appelé **logique géométrique**.
  
  Ce cadre logique possède une propriété remarquable : **ses formules et ses axiomes sont entièrement préservés par les foncteurs de changement de topos** (comme le foncteur image inverse d'un morphisme de topos).
- ## 1. La Logique Géométrique : Grammaire et Syntaxe
  
  Dans une théorie du premier ordre classique, on s'autorise l'usage de tous les connecteurs (\neg, \land, \lor, \implies) et de tous les quantificateurs (\forall, \exists).
  
  La logique géométrique restreint l'usage de certains symboles pour garantir l'invariance topologique/catégorique :
- **Connecteurs autorisés :**
	- La conjonction finie (\land) et le vrai (\top).
	- La disjonction **arbitraire** (éventuellement infinie) (\bigvee) et le faux (\bot).
	- Le quantificateur existentiel (\exists).
- **Connecteurs interdits :**
	- La négation (\neg).
	- L'implication générale (\implies).
	- Le quantificateur universel (\forall).
- ### Formules géométriques
  
  Une **formule géométrique** \phi(\mathbf{x}) (où \mathbf{x} = (x_1, \dots, x_n) est un n-uplet de variables libres) est une formule construite uniquement à l'aide des symboles autorisés à partir d'atomes (égalités ou symboles de relations).
- ### Séquents géométriques (Axiomes)
  
  Même si l'implication \implies n'est pas autorisée *à l'intérieur* d'une formule géométrique, une théorie géométrique s'exprime sous la forme d'un ensemble de **séquents géométriques** (les axiomes de la théorie) :
  
  `\phi(\mathbf{x}) \vdash_{\mathbf{x}} \psi(\mathbf{x})`
  
  où \phi(\mathbf{x}) et \psi(\mathbf{x}) sont deux formules géométriques. Ce séquent se lit intuitivement : *« Pour tout \mathbf{x}, si \phi(\mathbf{x}) est vraie, alors \psi(\mathbf{x}) est vraie. »*
- ## 2. Pourquoi "Géométrique" ? (Origine et Intuition)
  
  Le terme « géométrique » provient de la topologie et de la théorie des faisceaux :
- **Ouverts et intersections :**
	- Dans un espace topologique X, la collection des ouverts \mathcal{O}(X) est stable par **intersections finies** (\land) et par **unions arbitraires** (\bigvee).
	- En revanche, le complémentaire d'un ouvert n'est en général pas un ouvert (d'où l'exclusion de la négation \neg).
- **Prédicats comme ouverts :**
	- Les formules géométriques correspondent à des ensembles ouverts ou à des sous-faisceaux.
- **Images inverses :**
	- Si f : X \to Y est une application continue, l'image inverse f^{-1} préserve les intersections finies et les unions arbitraires d'ouverts. Ainsi, toute vérité exprimée par un séquent géométrique reste vraie après changement de base (pullback).
- ## 3. Logique Cohérente vs Logique Géométrique
  
  Il convient de distinguer la logique géométrique stricte de la **logique cohérente** (souvent manipulée en démonstration automatique) :
  
  | Propriété | Logique Cohérente | Logique Géométrique |
  
  | **Disjonctions** | Finies uniquement (\lor) | Arbitraires/Infinies (\bigvee) |
  
  | **Quantificateurs** | \exists fini | \exists fini |
  
  | **Cadre de calcul** | Fini, constructif, syntaxique | Infini, topologique, toposique |
  
  > 
  
  Une théorie cohérente est une théorie géométrique particulière dont toutes les disjonctions sont finies.
- ## 4. Rôle Majeur : Le Topos Classifiant
  
  Le résultat fondamental établi par Grothendieck, Makkai, Reyes et Joyal est que **toute théorie géométrique \mathbb{T} possède un topos classifiant**, noté \mathcal{E}_{\mathbb{T}}.
  
  ```
  [ Théorie Géométrique T ]
                                 |
                                 v (Construit le topos classifiant)
                    [ Topos Classifiant E_T ]
                                 |
         +-----------------------+-----------------------+
         |                                               |
         v                                               v
  [ Modèle de T dans Set ]                     [ Modèle de T dans un Topos E ]
  = Morphisme de topos                         = Morphisme de topos
    Set -> E_T                                   E -> E_T
  ```
- **Définition :** \mathcal{E}_{\mathbb{T}} est un topos de Grothendieck qui contient un "modèle universel" M_{\mathbb{T}} de la théorie \mathbb{T}.
- **Propriété universelle :** Pour tout autre topos \mathcal{E}, la catégorie des modèles de \mathbb{T} dans \mathcal{E} est équivalente à la catégorie des morphismes de topos (foncteurs géométriques) de \mathcal{E} vers \mathcal{E}_{\mathbb{T}} :
  
  `\mathbf{Mod}(\mathbb{T}, \mathcal{E}) \simeq \mathbf{Hom}_{\mathbf{Topos}}(\mathcal{E}, \mathcal{E}_{\mathbb{T}})`
- ### Conséquence (Équivalence de Morita)
  
  Deux théories géométriques \mathbb{T}_1 et \mathbb{T}_2 qui ont des présentations syntaxiques totalement différentes mais qui partagent le même topos classifiant (à équivalence près, \mathcal{E}_{\mathbb{T}_1} \simeq \mathcal{E}_{\mathbb{T}_2}) sont dites **Morita-équivalentes**. Elles possèdent le même contenu sémantique profond.
- ## 5. Exemples Concrets de Théories Géométriques
- **La théorie des anneaux locaux :**
	- Les axiomes décrivant un anneau commutatif unitaire local (où tout élément x vérifie x inversible ou 1-x inversible) s'expriment sous forme de séquents géométriques/cohérents :
	  `\top \vdash_{x} (\exists y (x \cdot y = 1)) \lor (\exists z ((1 - x) \cdot z = 1))`
- **La théorie des ensembles dénombrables ou des torsions :**
	- Les théories nécessitant des disjonctions infinies (par exemple exprimer qu'un groupe est de torsion : \top \vdash_x \bigvee_{n=1}^{\infty} (x^n = e)).
- **La théorie des filtres / ultrafiltres :**
	- Largement utilisée pour construire des espaces d'états ou de Stone.