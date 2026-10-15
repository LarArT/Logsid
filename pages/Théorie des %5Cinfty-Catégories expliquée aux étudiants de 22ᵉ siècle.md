- Voici une fiche de lecture issue de la conférence dispensée par **Emily Riehl** intitulée *« \infty-Category Theory for Undergraduates »* (mai 2020) [[00:03](https://www.youtube.com/watch?v=A6hXn6QCu0k&t=3)].
- # Fiche de lecture : La Théorie des \infty-Catégories expliquée aux étudiants de 22ᵉ siècle
- **Conférencière :** Emily Riehl (Johns Hopkins University) [[00:03](https://www.youtube.com/watch?v=A6hXn6QCu0k&t=3)]
- **Thématique :** Homotopy Type Theory (HoTT), Théorie des Types Simpliciaux, \infty-catégories [[02:05](https://www.youtube.com/watch?v=A6hXn6QCu0k&t=125)], [[01:52:13](https://www.youtube.com/watch?v=A6hXn6QCu0k&t=6733)]
- **Source :** [Visionner la vidéo sur YouTube](https://youtu.be/A6hXn6QCu0k?si=Kh_mIpdUZWqj36_C)
- ## 1. La vision et l'expérience de pensée
- ### L'idée directrice
  
  Actuellement, la théorie des \infty-catégories est réputée extrêmement ardue et abstraite, réservée aux spécialistes [[01:43](https://www.youtube.com/watch?v=A6hXn6QCu0k&t=103)]. Emily Riehl pose une question : **Et si, dans un siècle, ce sujet devenait un cours standard de licence ?** [[01:51](https://www.youtube.com/watch?v=A6hXn6QCu0k&t=111)]
- ### L'analogie du changement de socle
- **Hier / Aujourd'hui :** Les mathématiques s'appuient sur la théorie des ensembles (ZFC) et la logique classique des propositions. Pour définir une catégorie supérieure, il faut manipuler des échafaudages complexes (complexes simpliciaux, espaces de Rezk complets, quasi-catégories) [[01:06](https://www.youtube.com/watch?v=A6hXn6QCu0k&t=66)], [[01:52:41](https://www.youtube.com/watch?v=A6hXn6QCu0k&t=6761)].
- **Demain :** Si les étudiants assimilent naturellement la **Théorie des Types Homotopiques (HoTT)** comme fondement intuitif, la définition d'une \infty-catégorie devient presque triviale et se fait en quelques lignes [[02:05](https://www.youtube.com/watch?v=A6hXn6QCu0k&t=125)], [[02:51](https://www.youtube.com/watch?v=A6hXn6QCu0k&t=171)].
- ## 2. Les concepts clés vulgarisés et imagés
  
  Pour comprendre cette intuition, la conférence découpe les briques fondamentales à l'aide d'images simples :
- ### A. Types vs Termes (La métaphore des Moules et des Objets)
- **Les Types (en rouge) :** Représentent des *moules* ou des *catégories d'objets* (ex: le type \text{Pomme}, le type \mathbb{N}) [[07:49](https://www.youtube.com/watch?v=A6hXn6QCu0k&t=469)].
- **Les Termes (en orange) :** Ce sont les *objets concrets* qui sortent de ces moules (ex: a : \text{Pomme} signifie que a est une instance du moule \text{Pomme}) [[07:49](https://www.youtube.com/watch?v=A6hXn6QCu0k&t=469)].
- ### B. L'Égalité devient un Chemin (L'intuition Homotopique)
  
  C'est le saut conceptuel majeur entre la théorie des types classique et HoTT :
- **Ensemble classique :** Deux éléments x et y sont soit égaux, soit différents (un bit 0 ou 1). C'est un monde rigide de points isolés.
- **Vision Synthétique / Homotopique :** Un type est un **espace géométrique** [[01:49:14](https://www.youtube.com/watch?v=A6hXn6QCu0k&t=6554)].
	- Les points du type sont les termes [[01:49:14](https://www.youtube.com/watch?v=A6hXn6QCu0k&t=6554)].
	- L'égalité entre deux termes x =_A y n'est pas un simple fait booléen, mais un **type à part entière** : le type des **chemins (ou cordes)** reliant le point x au point y [[01:49:14](https://www.youtube.com/watch?v=A6hXn6QCu0k&t=6554)].
	- Si deux chemins reliant x à y peuvent être déformés continûment l'un dans l'autre, on a une égalité de niveau supérieur (une surface/homotopie entre chemins).
	  
	  > 
	  
	  **Image intuitive :** Imaginez un paysage. Deux villes A et B ne sont pas seulement "égales ou non" ; elles sont reliées par des routes (les égalités de niveau 1). Les routes peuvent être reliées par des plaines défrichées (les égalités de niveau 2 entre chemins), et ainsi de suite à l'infini (\infty).
	  
	  ```
	  [Point x]  ---- Chemin p ---->  [Point y]
	          ---- Chemin q ---->  
	                ||
	           (Surface / Homotopie entre p et q)
	  ```
- ### C. Le principe d'Univalence
  
  Proposé par Vladimir Voevodsky, ce principe s'énonce simplement : **« Les objets isomorphes sont égaux. »** Dans le monde usuel des ensembles, deux ensembles de même cardinal (ex: \{0, 1\} et \{\text{Vrai}, \text{Faux}\}) ne sont pas strictement égaux. En HoTT, l'équivalence entre deux structures fournit directement un *chemin* d'égalité entre elles.
- ### D. La Théorie des Types Simpliciaux pour les \infty-Catégories
  
  Pour passer à une \infty-catégorie, on ajoute à la théorie des types la notion de **formes géométriques de référence** (les simplexes) [[01:52:13](https://www.youtube.com/watch?v=A6hXn6QCu0k&t=6733)] :
- Un point est un 0-simplexe.
- Une flèche dirigée x \to y est un 1-simplexe (un segment orienté).
- Un triangle rempli caractérise la composition de deux flèches : f : x \to y et g : y \to z composent en h : x \to z.
  
  Dans ce cadre synthétique, une **\infty-catégorie** est tout simplement un type dans lequel tout "cornet" (deux flèches consécutives x \to y \to z) possède un remplissage intérieur (un triangle qui assure l'existence et l'unicité à homotopie près de leur composée).
- ## 3. Synthèse des apports de la conférence
- **Révolution pédagogique :** L'usage de la logique synthétique (HoTT / Types simpliciaux) permet de faire sauter le formalisme combinatoire extrêmement lourd des quasi-catégories pour raisonner directement "sur le papier" (*informal type theory*) [[04:10](https://www.youtube.com/watch?v=A6hXn6QCu0k&t=250)], [[01:52:41](https://www.youtube.com/watch?v=A6hXn6QCu0k&t=6761)].
- **Dualité Calcul / Géométrie :** La théorie des types possède une double nature : c'est à la fois un langage géométrique pour la topologie et un langage de programmation exécutable (adapté aux assistants de preuve comme Coq/Rocq ou Agda) [[03:52](https://www.youtube.com/watch?v=A6hXn6QCu0k&t=232)], [[01:52:13](https://www.youtube.com/watch?v=A6hXn6QCu0k&t=6733)].
- **Perspectives :** L'approche permet de formaliser et de vérifier mécaniquement des théorèmes complexes de topologie et de théorie des catégories supérieures sans être noyé sous la gestion des cohérences de dimensions infinies [[02:51](https://www.youtube.com/watch?v=A6hXn6QCu0k&t=171)], [[01:52:13](https://www.youtube.com/watch?v=A6hXn6QCu0k&t=6733)].
  
  *Les vues de vidéos YouTube seront stockées dans votre historique YouTube, et vos données seront stockées et utilisées par YouTube conformément à ses [Conditions d'utilisation](https://www.youtube.com/static?template=terms)*
  
  *Les vues de vidéos YouTube seront stockées dans votre historique YouTube, et vos données seront stockées et utilisées par YouTube conformément à ses [Conditions d'utilisation](https://www.youtube.com/static?template=terms)*