# Modèles Homotopiques : Théories Cubiques vs Simpliciaux
- **Auteur** : Clarification rigoureuse basée sur Coquand, Lurie, Riehl, Shulman
- **Date** : Août 2026
- **Domaine** : Théorie des types homotopiques, topologie synthétique, ∞-catégories

## ⚠️ ATTENTION — Imprécisions du texte original
- Les tableaux LaTeX sont mal rendus/incomplets
- La notation "⇄ Quillen ∼" est non-standard et source de confusion
- Certaines affirmations ne distinguent pas clairement les niveaux (modèles vs syntaxe)
- Manque de précision sur le statut sémantique des équivalences

## 1. Les trois niveaux fondamentaux
- **Niveau 1 : Géométrie combinatoire (Modèles classiques)**
  - Objets : Ensembles simpliciaux (sSet) et ensembles cubiques (cSet)
  - Statut : Structures mathématiques concrètes
  - Lien : Liés par une équivalence de Quillen
  - Importance : Outils calculatoires pour manipuler les espaces
- **Niveau 2 : Structures algébriques abstraites**
  - ∞-Groupoïdes : Espaces où toutes les flèches sont inversibles (chemins symétriques)
  - ∞-Catégories : Structures où les morphismes a → b ne sont pas nécessairement réversibles
  - Statut : Objets mathématiques idéaux (peuvent être modélisés par sSet ou cSet)
- **Niveau 3 : Théorie des types formelle**
  - Statut : Syntaxe informatique/logique de programmation
  - Fonction : Formaliser les concepts du niveau 2 dans un langage prouvable
  - Exécution : Implémentées dans des prouveurs assistés par ordinateur

## 2. L'équivalence de Quillen (Fondation du pont classique)
- **Énoncé mathématique rigoureux**
  - Il existe un couple de foncteurs adjoints : sSet ⇄ cSet
  - Ces foncteurs induisent une équivalence de catégories dérivées
  - L'équivalence préserve les structures homotopiques (fibrations de Kan)
- **Notation correcte**
  - sSet ≃ cSet (équivalence de catégories dans Qcat)
  - NON : "⇄ Quillen ∼" (trop vague et non-standard)
  - Précision : Les adjoints sont des **équivalences de Quillen** en théorie des modèles
- **Ce qu'elle transporte**
  - Tout calcul en simplicial se transpose en cubique
  - Les homotopies sont préservées dans les deux directions
  - Les fibrations de Kan (notion cruciale pour HoTT) existent dans les deux cadres
- **Implication ontologique**
  - Les simplexes et cubes sont deux représentations équivalentes de la même réalité topologique
  - Le choix entre eux est une question de commodité computationnelle, pas de différence fondamentale

## 3. Filiation I : Coquand & Voevodsky (Univers des espaces)
- **Axiomatisation : Homotopy Type Theory (Vladimir Voevodsky)**
  - Année : Années 2000-2010
  - Objectif : Réconcilier théorie des types constructive et topologie algébrique
  - Axiome clé : Univalence (isomorphisme ≡ égalité de types)
  - Univers ontologique : ∞-Groupoïdes
  - Statut : Théorie des types abstraite (sans implémentation spécifiée)
- **Implémentation concrète : Théorie des Types Cubiques**
  - Auteurs principaux : Thierry Coquand, Marc Bezem, Cubical Type Theory (2015+)
  - Géométrie primitive : Ensembles cubiques I^n (cubes standards)
  - Avantage clé : Rend l'axiome d'univalence **calculable** (pas seulement postulé)
  - Nature des chemins : Symétriques — tout chemin γ : a ↔ b peut se parcourir avant ou arrière
  - Modèle mathématique : cSet muni des fibrations de Kan
- **Prouveurs implémentant cette théorie**
  - Cubical Agda (Mora Steenkamp et al., 2016+)
    - Langage : Extension d'Agda avec primitives cubiques
    - Exécutabilité : Oui, programs computationally terminate
  - RedTT (Sterling & Angiuli)
    - Fokus : Théorie observationnelle pour les cubes
  - XTT (Angiuli et al.)
    - Extension pour les structures linéaires
- **Priorité mathématique**
  - Calculabilité de l'univalence (pas juste postulat non-computé)
  - Constructivité (preuve = programme)
  - Applicabilité algorithmique
- **Propriété clé : Égalité propositionnelle calculable**
  - En théorie cubique, a = b peut être décidé par un algorithme
  - Cela contraste avec HoTT classique où l'égalité peut être indécidable
  - Avantage : Les prouveurs peuvent faire de la vérification de type plus efficace

## 4. Filiation II : Lurie & Riehl (Univers des catégories)
- **Théorie fondatrice : Jacob Lurie (∞-Catégories)**
  - Œuvre majeure : *Higher Topos Theory* (2009), *Higher Algebra* (2016)
  - Objectif : Développer la théorie des catégories pour la topologie algébrique moderne
  - Univers : ∞-Catégories avec morphismes **orientés** et non-inversibles
  - Géométrie : Ensembles simpliciaux (simplexes Δⁿ)
  - Modèle privilégié : Quasi-catégories (ensembles simpliciaux satisfaisant certaines conditions de corned)
  - Statut : Théorie classique (utilise la logique classique, pas constructive)
  - Impact : Révolutionné la théorie des catégories, dérivée, géométrie algébrique supérieure
- **Extension formelle : Simplicial Type Theory (Emily Riehl & Michael Shulman)**
  - Objectif principal : Axiomatiser les ∞-catégories de Lurie dans une théorie des types
  - Fondement : Extension de HoTT (pas remplacement)
  - Innovation clé : Ajout d'un intervalle **orienté** I (vs intervalle non-orienté en HoTT)
  - Conséquence : Permet de distinguer a → b et b → a formellement
  - Statut des morphismes : Non-inversibles par défaut
  - Langage : Synthétique (sur papier, pas d'exécution computationnelle prévue)
  - Utilité : Rendre les arguments de Lurie plus directs et formalisables
- **Relation entre Lurie et Riehl : Sémantique exacte**
  - Les quasi-catégories de Lurie = **modèles géométriques** de Simplicial Type Theory
  - Riehl construit une interprétation sémantique dans les quasi-catégories
  - Conséquence : Tout théorème en Simplicial Type Theory peut être interprété géométriquement chez Lurie
  - Impact philosophique : La théorie de Riehl est une "synthétisation" du programme de Lurie
- **Prouveurs et formalisations**
  - Rzk language (Favonia et al.)
    - Implémente Simplicial Type Theory
    - Accent : Formalisation explicite des ∞-catégories
    - Status : Expérimental mais fonctionnel
  - Lean 4 (en développement)
    - Extension vers les types simpliciaux
    - Ambitieux : Formaliser des théorèmes de Higher Algebra de Lurie

## 5. Tableau comparatif détaillé (CORRIGÉ ET AUGMENTÉ)
- **Langage formel**
  - Cubique : Cubical Type Theory (Coquand et al.)
  - Simplicial : Simplicial Type Theory (Riehl & Shulman)
- **Géométrie primitive**
  - Cubique : Ensembles cubiques I^n (cubes standards)
  - Simplicial : Ensembles simpliciaux Δⁿ (simplexes)
- **Pont mathématique**
  - Cubique : Équivalence de Quillen (préserve Kan fibrations)
  - Simplicial : Équivalence de Quillen (même pont)
- **Structure ontologique**
  - Cubique : ∞-Groupoïdes (toutes flèches inversibles)
  - Simplicial : ∞-Catégories (morphismes potentiellement non-inversibles)
- **Nature des chemins/morphismes**
  - Cubique : Symétriques (a ↔ b, bidirectionnel)
  - Simplicial : Orientés (a → b, unidirectionnel)
- **Univers sémantique mathematique**
  - Cubique : HoTT de Voevodsky (topologie synthétique)
  - Simplicial : ∞-Catégories de Lurie (géométrie algébrique supérieure)
- **Implémentation informatique**
  - Cubique : Cubical Agda, RedTT (exécutable, constructif)
  - Simplicial : Rzk, Lean 4 (synthétique, logique classique)
- **Priorité mathématique**
  - Cubique : Calculabilité, constructivité, décidabilité de l'égalité
  - Simplicial : Géométrie synthetique formelle, axiomatisation rigoureuse des catégories
- **Filiation philosophique**
  - Cubique : Voevodsky (HoTT) → Coquand (implémentation cubique calculable)
  - Simplicial : Lurie (quasi-catégories) → Riehl (formalisation synthétique)

## 6. DISTINCTION CRUCIALE : Espaces vs Catégories
- **Topologie synthétique (Univers Cubique)**
  - Objet type : ∞-Groupoïde (espace)
  - Propriété définissante : Tous les chemins sont réversibles
  - Formalisation : Une boucle γ : * → * et son inverse γ⁻¹ sont **égaux** dans le type
  - Exemple concret : La sphère S¹ est un espaces homotopique où π₁(S¹) = ℤ
  - Géométrie : Topologie usuelle (continue, sans direction privilégiée)
- **Algèbre catégorique (Univers Simplicial)**
  - Objet type : ∞-Catégorie
  - Propriété définissante : Les morphismes a → b et b → a sont **distincts**
  - Formalisation : f : a → b et g : b → a ne s'égalisent pas sans composition explicite
  - Exemple concret : La catégorie Set⁰ᵖ des ensemble (cotangente) : f et f⁻¹ sont formellement différentes
  - Géométrie : Catégorique (les flèches ont une source et une cible orientées)
- **Implication pour la théorie des types**
  - Cubique = Langage pour décrire les espaces (topologie synthétique)
  - Simplicial = Langage pour décrire les structures algébriques orientées (théorie de Lurie)
- **À ne pas confondre**
  - HoTT (Voevodsky) postule seulement l'univalence abstraitement
  - Cubical Type Theory rend cette univalence concrètement calculable
  - Simplicial Type Theory ne calcule pas l'univalence, mais axiomatise les morphismes orientés

## 7. Architecture globale et flux sémantique
- **Strate classique (Catégories de modèles)**
  - sSet (ensembles simpliciaux)
    - Modèles géométriques des quasi-catégories (Lurie)
    - Reliés par fibrations de Kan
  - cSet (ensembles cubiques)
    - Modèles géométriques des espaces homotopiques (Voevodsky)
    - Reliés par fibrations de Kan cubiques
  - Pont : Équivalence de Quillen sSet ≃ cSet
- **Strate intermédiaire (Structures abstraites)**
  - ∞-Catégories (Jacob Lurie)
    - Objets idéaux sans implémentation directe
    - Modélisés par quasi-catégories dans sSet
  - ∞-Groupoïdes (Vladimir Voevodsky)
    - Objets idéaux correspondant aux espaces
    - Modélisés par objets fibrants dans cSet
- **Strate formelle (Théories des types)**
  - Cubical Type Theory (Coquand)
    - Formalisation synthétique des ∞-groupoïdes
    - Interprétée sémantiquement dans cSet
    - Modèles : Cubical Agda, RedTT
  - Simplicial Type Theory (Riehl & Shulman)
    - Formalisation synthétique des ∞-catégories
    - Interprétée sémantiquement dans sSet et quasi-catégories
    - Modèles : Rzk, Lean 4

## 8. Erreurs courantes à éviter
- **Erreur 1 : Confondre HoTT avec théorie cubique**
  - HoTT = théorie abstraite des types
  - Théorie cubique = implémentation calculable de HoTT
  - Distinction : HoTT n'engage pas sur la calculabilité
- **Erreur 2 : Penser que Riehl "améliore" Lurie**
  - Faux : Riehl formalise synthétiquement ce que Lurie décrit géométriquement
  - Relation : Complémentarité, non hiérarchie
- **Erreur 3 : Équivalence de Quillen = identité**
  - Faux : C'est une équivalence, pas une égalité
  - Conséquence : sSet et cSet sont **isomorphes à équivalence** près, pas identiques
- **Erreur 4 : Croire que simplicial = mieux que cubique**
  - Faux : Simplement des choix de représentation différents
  - Réalité : Cubique = meilleur pour la calculabilité, simplicial = meilleur pour la géométrie
- **Erreur 5 : Confondre univalence et équivalence de Quillen**
  - Univalence : Axiome de HoTT (isomorphisme = égalité de types)
  - Équivalence de Quillen : Pont entre deux catégories de modèles
  - Lien : L'univalence est un principe qui s'implémente grâce aux modèles via l'équivalence de Quillen

## 9. Points critiques non clarifiés dans l'original (À mémoriser)
- **Point 1 : L'équivalence de Quillen ne transpose pas juste les objets**
  - Elle transporte aussi les **morphismes** et les **structures homotopiques**
  - Les fibrations de Kan sont préservées rigoureusement
  - Conséquence : Tout calcul en simplicial reste valide en cubique (et vice-versa)
- **Point 2 : HoTT ≠ Théorie cubique**
  - HoTT est l'axiomatisation abstraite
  - La théorie cubique en est **une implémentation** parmi d'autres possibles
  - Importance : Cette distinction permet de séparer les "vraies" propriétés de HoTT de ses réalisations techniques
- **Point 3 : Riehl n'étend pas HoTT pour le "dépasser", mais pour capturer les ∞-catégories**
  - Extension de HoTT : Ajout d'un intervalle orienté
  - Focalisation : Spécifiquement sur les morphismes non-réversibles
  - Utilité : Formaliser synthétiquement le programme de Lurie
- **Point 4 : Les prouveurs implémentent ces théories, pas l'inverse**
  - Cubical Agda implémente Cubical Type Theory (pas l'inverse)
  - Rzk implémente Simplicial Type Theory (pas l'inverse)
  - Conséquence : Les limitations du prouveur ne reflètent pas les limitations de la théorie
- **Point 5 : Évaluation vs Vérification**
  - Théorie cubique : Exécution complète (evaluation)
  - Théorie simpliciale : Vérification formelle seulement (pas d'execution a priori)
  - Implication : Cubique = plus constructif, simplicial = plus "abstrait synthétiquement"

## 10. Bibliographie et références rigoureuses
- **Fondations : HoTT**
  - Voevodsky, V. "A very short note on the homotopy λ-calculus" (2006)
  - HoTT Book (Institute for Advanced Study, Princeton, 2013)
- **Théorie cubique**
  - Coquand, T., Huber, M., Mörtberg, A. "Cubical type theory: a constructive interpretation of the univalence axiom" (2018)
  - Mörtberg, A. "Cubical Type Theory" (PhD Thesis, 2017)
- **Théorie simpliciale & ∞-catégories**
  - Lurie, J. "Higher Topos Theory" (Princeton University Press, 2009)
  - Lurie, J. "Higher Algebra" (2016, freely available online)
  - Riehl, E., Shulman, M. "A type theory for synthetic ∞-categories" (2017)
- **Formalisations**
  - Cubical Agda : https://agda.readthedocs.io/en/latest/language/cubical.html
  - Rzk language : https://rzk-lang.github.io/

## 11. Questions ouvertes et recherche active
- **Q1 : Peut-on calculer efficacement dans la théorie simpliciale?**
  - État : Recherche en cours par Riehl, Shulman, et collaborateurs
  - Enjeu : Implémenter Rzk de manière efficace
- **Q2 : L'univalence en théorie cubique capture-t-elle toute la géométrie simpliciale?**
  - État : Oui, via l'équivalence de Quillen, mais les détails restent à clarifier
  - Enjeu : Comprendre le rapport exact entre modèles cubiques et simpliciaux
- **Q3 : Peut-on fusionner cubique et simplicial en une théorie unique?**
  - État : Pas de consensus, plusieurs approches exploratoires
  - Enjeu : Avoir un seul formalisme pour espaces et catégories

## 12. SIMPLEXES VS CUBES — Différences géométriques et computationnelles
- **Deux briques de base concurrentes**
  - Simpliciale : Simplexes Δ^n (points, segments, triangles, tétraèdres, ...)
  - Cubique : Cubes/Hypercubes I^n (points, segments, carrés, cubes, ...)
  - Question : Pourquoi deux approches si l'équivalence de Quillen les rend mathématiquement équivalentes?
  - Réponse : **Raisons géométriques**, **informatiques** et **de calculabilité**

### 12.1 Différences géométriques et combinatoires
- **Approche Simpliciale (Ensemble Simplicial sSet)**
  - Briques élémentaires : Simplexes standards Δ^n
    - Δ^0 = un point
    - Δ^1 = un segment [0,1]
    - Δ^2 = un triangle (trois points et trois arêtes, une face)
    - Δ^3 = un tétraèdre (quatre points, six arêtes, quatre faces, une région 3D)
    - Δ^n = ensemble convexe standard de dimension n dans ℝ^(n+1)
  - Composition : Collage par faces communes (facettes)
    - Exemple : Deux triangles Δ^2 peuvent être collés sur une arête commune
    - Abstraction : Notion de *horn filling* (remplissage de cornets)
    - Définition précise : Un horn Λ^n_k ⊂ Δ^n est un simplexe avec une face manquante
  - **Problème combinatoire : Produits non-fermés**
    - Δ^a × Δ^b ≠ Δ^(a+b) (**ce n'est pas fermé pour le produit**)
    - Exemple concret : Δ^2 × Δ^2 (triangle × triangle) n'est pas un 4-simplexe, mais une réunion complexe de plusieurs 4-simplexes
    - Conséquence : Exprimer un produit d'espaces simpliciaux demande une décomposition en de nombreux simplexes
    - Impact combinatoire : Croissance exponentielle de la complexité structurelle
- **Approche Cubique (Ensemble Cubique cSet)**
  - Briques élémentaires : Hypercubes I^n
    - I = [0,1] (intervalle unitaire standard)
    - I^0 = un point
    - I^1 = un segment (1D)
    - I^2 = un carré (2D) avec coordonnées (x, y) où x, y ∈ [0,1]
    - I^3 = un cube (3D) avec coordonnées (x, y, z)
    - I^n = hypercube n-dimensionnel = {(x₁, ..., xₙ) ∈ ℝⁿ : 0 ≤ xᵢ ≤ 1 pour tout i}
  - Composition : Gérée par une **algèbre d'intervalle**
    - Toute structure se décrit par des variables i, j, k ∈ {0, 1}
    - Exemple : Un point intérieur au carré I² est défini par ses deux coordonnées
    - Opérations : Produit tensoriel (⊗), faces (en fixant une variable à 0 ou 1)
  - **Propriété cruciale : Fermeture multiplicative**
    - **I^a × I^b ≅ I^(a+b)** (isomorphisme canonique, NON égalité naïve)
    - Démonstration : (x₁,...,xₐ, y₁,...,yᵦ) ∈ [0,1]^(a+b)
    - Conséquence : Produit de deux cubes = direct hypercube de dimension supérieure
    - Impact combinatoire : Structure très régulière, gestion algébrique simple
  - **Algèbre sous-jacente**
    - Les opérations géométriques se traduisent en manipulations symboliques d'intervalles
    - Exemple : Face d'un cube en fixant x = 0 est juste une substitution formelle
    - Utilité : Très naturel pour l'implémentation informatique et les calculs

### 12.2 Comparaison tabulaire : Géométrie
| Aspect | Simplexes Δ^n | Cubes I^n |
|--------|---|---|
| **Briques élémentaires** | Points, segments, triangles, tétraèdres | Points, segments, carrés, cubes |
| **Dimention N** | Simplexe convexe standard à N+1 sommets | Hypercube [0,1]^N |
| **Produit** | Δ^a × Δ^b ≠ Δ^(a+b) — extrêmement complexe | I^a × I^b ≅ I^(a+b) — direct et algébrique |
| **Composition** | Collage par faces (horn filling) | Algèbre d'intervalles et substitutions |
| **Régularité** | Combinatoire exponentielle — vite complexe | Très régulière — gestion simple |
| **Codification géométrique** | Coordonnées barycentriques | Coordonnées cartésiennes [0,1]^n |

### 12.3 Comment on compose : Le défi algorithmique

#### Approche Simpliciale — Remplissage de cornets (Horn Filling)
- **Opération fondamentale**
  - On colle des triangles par leurs côtés ou sommets communs
  - **Notion centrale : Horn Λⁿₖ (corne)** = un simplexe auquel on a enlevé une face maximale
    - Exemple : Λ²₁ est un triangle privé d'une de ses trois faces
    - Le problème : Peut-on toujours remplir cette corne? (La condition d'horn-filling)
  
- **Inconvénient pour le produit d'espaces**
  - Le produit de deux triangles Δ² × Δ² n'est **pas** un simplexe
  - Il faut le décomposer en plusieurs simplexes de dimensions variées
  - Résultat : La combinatoire explose quand on essaie de manipuler des produits
  - Impact pratique : Très difficile à implémenter efficacement

#### Approche Cubique — Algèbre des intervalles
- **Opération fondamentale**
  - Tout est géré par des **variables d'intervalle** i, j ∈ [0,1]
  - Un carré I² a des coordonnées (i, j)
  - Composition = substitution algébrique simple
  
- **Avantage pour le produit d'espaces**
  - Le produit de deux cubes Iᵃ × Iᵇ = I^(a+b) — directement un cube de dimension supérieure
  - **Exemple concret** :
    ```
    Carré 1 : (i, j) où i, j ∈ [0,1]
    Carré 2 : (k, l) où k, l ∈ [0,1]
    Produit : (i, j, k, l) où tous ∈ [0,1]
    Résultat : Un hypercube 4D I⁴ — pas de décomposition complexe nécessaire
    ```
  
- **Propriété clé**
  - La géométrie algébrique y est **beaucoup plus régulière**
  - Les opérations suivent des lois homogènes et prévisibles
  - Très naturel pour une implémentation informatique

### 12.3.1 Tableau synthétique : Mode de composition

| Aspect | Simplexes (Horn Filling) | Cubes (Algèbre d'intervalle) |
|--------|---|---|
| **Composition de base** | Collage par faces communes | Substitution de variables |
| **Produit de deux objets** | Décomposition complexe (non fermé) | Produit direct fermé |
| **Exemple : triangle × triangle** | Assemblage de plusieurs tétraèdres | Un hypercube 4D simple |
| **Gestion algorithmique** | Cas par cas, horn filling complexe | Uniforme et régulière |
| **Décidabilité des opérations** | Difficile (horn filling = problème dur) | Triviale (substitution syntaxique) |
| **Implantation informatique** | Très complexe | Directe et efficace |

---

### 12.4 Le **vrai** enjeu informatique : Calculabilité de l'univalence
- **Contexte : Théorie des types homotopiques (HoTT) de Voevodsky**
  - Axiome central : Univalence
    - Énoncé : Deux types X et Y sont égaux si et seulement si il existe une équivalence f : X ≃ Y
    - Formalisme : (X = Y) ≃ (X ≃ Y)
  - Statut dans HoTT classique : Axiome postulé (non-provable)
  - Conséquence logique : Théorie cohérente ✓
  - Conséquence informatique : **Non-calculable ✗**
  
- **Le problème computationnel avec l'approche simpliciale**
  - Implémentation classique : HoTT + univalence comme axiome
  - Exemple : Prouveur Rocq (ex-Coq) avec HoTT
  - Scénario : Vous écrivez une preuve p : X = Y qui utilise l'univalence
    - ```coq
      definition p : Type := ... univalence ... 
      #eval compute_something_with p  -- ERREUR : Axiom encountered
      ```
  - Problème exact : L'univalence est une "boîte noire"
    - Le prouveur peut vérifier que p est une preuve correcte (vérification de type ✓)
    - Mais l'ordinateur **ne peut pas exécuter** le contenu de p car aucune règle de calcul n'est fournie
  - Impact pratique :
    - Extraction de termes : Impossible pour les preuves utilisant univalence
    - Vérification de type : Slow (doit traiter les axiomes symboliquement)
    - Exécution de programmes : Bloquée
    
- **La solution cubique de Coquand : Rendre l'univalence calculable**
  - Idée clé : Utiliser la structure algébrique des cubes pour implémenter directement la déformation d'équivalence
  - Approche cubique :
    - L'intervalle I = [0,1] devient primitif dans le langage
    - Les chemins entre X et Y deviennent des applications p : I → Universe
    - L'équivalence n'est pas un axiome, mais une définition constructive explicite
    - Résultat : On peut calculer comment transformer X en Y
  - Formalisme :
    - Univalence cubique = une fonction calculable
    - Quand on appelle cette fonction (par exemple dans Cubical Agda), elle exécute réellement la déformation d'équivalence
    - ```cubical
      equiv-to-path : {X Y : Type} (f : X ≃ Y) → X = Y
      equiv-to-path f = <λ i -> ...> -- Ceci s'exécute réellement!
      ```
  - Avantage majeur :
    - L'univalence n'est plus un postulat, c'est une **fonction exécutable**
    - Extraction de termes : Fonctionne complètement
    - Type-checking : Plus rapide (règles algorithmiques, pas axiomatiques)
  
- **Comparaison directe**
  | Propriété | HoTT simplicial classique | HoTT cubique (Coquand) |
  |-----------|---|---|
  | **Univalence** | Axiome postulé | Théorème constructif et calculable |
  | **Statut formel** | Axiomatique (non-provable) | Synthétique (embedded dans la théorie des types) |
  | **Exécution** | Impossible (axiomes = boîtes noires) | Complètement exécutable (Cubical Agda, RedTT) |
  | **Extraction de termes** | Partielle (bloquée sur axiomes) | Totale |
  | **Complexité combinatoire** | Énorme (produits simpliciaux) | Maîtrisée (produits cubiques réguliers) |
  | **Vérification de type** | Lente (traitement symbolique des axiomes) | Rapide (calcul direct) |

### 12.4.1 Tableau synthétique global : Toute la distinction

| Dimension | Simplexes (Δⁿ) | Cubes (Iⁿ) |
|-----------|---|---|
| **Géométrie** | Triangles, tétraèdres (orientés) | Carrés, cubes (symétriques) |
| **Composition** | Remplissage de cornets (horn filling) | Algèbre des intervalles et substitution |
| **Produit de deux objets** | Complexe (Δᵃ × Δᵇ ≠ Δ^(a+b)) | Fermé (I^a × I^b = I^(a+b)) |
| **Régularité** | Combinatoire exponentielle | Algèbre régulière |
| **Univalence** | Axiome non-calculable (boîte noire) | Théorème calculable (transparent) |
| **Extraction de termes** | Impossible (bloquée par axiomes) | Totale (fonctionnelle complète) |
| **Rôle théorique** | ∞-Catégories de Lurie (morphismes orientés) | ∞-Groupoïdes de Voevodsky (chemins réversibles) |
| **Implémentation** | Rzk, Lean 4 (synthétique, sur papier) | Cubical Agda, RedTT (exécutable) |

---

### 12.5 Pourquoi Thierry Coquand a choisi les cubes
- **Raison 1 : Structure algébrique fermée**
  - Les cubes forment un produit catégorique régulier
  - Les substitutions et les opérations géométriques se codent directement en algèbre
  - Les simplexes ne jouissent pas de cette propriété (produit exponentiel)
  
- **Raison 2 : Décidabilité de l'égalité**
  - Égalité entre deux cubes : Décidable (comparaison structurelle)
  - Égalité entre deux simplexes : Plus complexe (nécessite l'algorithme de remplissage de cornet)
  
- **Raison 3 : Calculabilité constructive**
  - L'axiome d'univalence peut être rendu transparent (voir sa preuve complètement)
  - Les opérations de transport et de déformation sont codées explicitement
  - Les simplexes ne permettent pas cette implémentation directe (nécessitent l'axiome)
  
- **Raison 4 : Implémentation informatique**
  - Les intervalles [0,1] et les variables formelles sont très naturels pour la programmation
  - Exemple : Cubical Agda peut utiliser une syntaxe proche de la théorie:
    ```cubical
    transport : {A : I → Type} {x : A 0} {y : A 1} → x = y → ...
    ```
  - Les simplexes demandent une théorie plus complexe et moins algorithmique

### 12.6 Pourquoi Emily Riehl reste avec les simplexes (pour les ∞-catégories)
- **Raison 1 : Les ∞-catégories ne sont pas des espaces**
  - ∞-Catégories = structures où les morphismes a → b ne sont pas réversibles
  - Cubes = naturellement symétriques (x ∈ I = [0,1] est "réversible" dans les deux sens)
  - Simplexes = orientés par nature (orientation du simplexe Δ^n)
  
- **Raison 2 : Quasi-catégories de Lurie**
  - Les quasi-catégories sont définies sur les simplexes et ont des propriétés spéciales
  - Exemple : Horn filling condition = propriété de quasi-catégorie
  - Transposer cela en cubique changerait les structures fondamentales
  
- **Raison 3 : Fidelité au programme de Lurie**
  - Riehl formalise synthétiquement ce que Lurie a écrit en géométrie simpliciale
  - Changer de géométrie changerait les théorèmes
  
- **Raison 4 : Notion de direction**
  - Simplexes = notion intuitive d'ordre et de direction (sommet "initial", faces successives)
  - Cubes = structure additive symétrique (pas d'ordre naturel)
  - Pour capturer les ∞-catégories dirigées, les simplexes sont plus naturels

### 12.7 Synthèse : Quand utiliser quoi?
- **Utiliser les CUBES si vous voulez :**
  - Calculabilité de l'égalité
  - Exécution sur machine
  - Implémentation informatique d'équivalences
  - Théorie constructive avec univalence calculable
  - **Prouveurs : Cubical Agda, RedTT**
  
- **Utiliser les SIMPLEXES si vous voulez :**
  - Formaliser les ∞-catégories avec morphismes orientés
  - Travailler dans l'univers de Jacob Lurie
  - Théorie synthétique "sur papier" sans visée computationnelle
  - Capturer les structures dirigées
  - **Prouveurs : Rzk, Lean 4 (en développement)**

### 12.8 Mise en garde : Équivalence de Quillen ne résout pas tout
- **Ce que l'équivalence de Quillen **fait**:**
  - Garantit que sSet et cSet modélisent la même topologie abstraite
  - Transporte les structures homotopiques
  - Permet de passer mathématiquement de l'un à l'autre
  
- **Ce que l'équivalence de Quillen **ne fait pas**:**
  - Ne rend pas les cubes calculables pour les ∞-catégories (car les cubes sont symétriques)
  - Ne résout pas le problème de l'univalence axiomatique (c'est une question informatique, pas juste mathématique)
  - N'unifie pas les deux théories des types (cubique vs simpliciale) — elles restent syntaxiquement distinctes
  
- **Point critique :**
  - L'équivalence de Quillen est un théorème **classique** de théorie des catégories
  - La calculabilité est un problème **informatique** — l'équivalence ne garantit pas que deux représentations mathématiquement équivalentes sont également calculatoirement équivalentes
  - Conclusion : Même si sSet ≃ cSet, la théorie cubique est plus efficace informatiquement pour implémenter HoTT

### 12.9 Erreurs courantes à corriger
- **Erreur : "Les cubes et simplexes sont identiques grâce à l'équivalence de Quillen"**
  - Nuance : Mathématiquement équivalents, mais différents computationnellement
  - Réalité : L'équivalence est un isomorphisme de catégories, pas une égalité d'objets
  
- **Erreur : "La théorie cubique est un remplacement de la théorie simpliciale"**
  - Nuance : Pas un remplacement, un choix complémentaire
  - Réalité : Cubique = pour HoTT constructif; Simplicial = pour ∞-catégories de Lurie
  
- **Erreur : "L'axiome d'univalence s'exécute en théorie cubique"**
  - Précision : Ce n'est pas qu'on exécute l'axiome (axiomes ne s'exécutent pas)
  - Réalité : On dispose d'une implémentation computatoire de la notion d'équivalence, qui rend l'univalence **provable** (pas axiomatique)
  
- **Erreur : "Simplexes = meilleur que cubes" ou vice-versa**
  - Réalité : Choix contextuels différents selon l'objectif (calculabilité vs géométrie)

## Tags
- #typeTheory #homotopy #cubical #simplicial #Coquand #Lurie #Riehl #HoTT #categoryTheory #formalMathematics #geometry #computation #univalence #quasiCategories