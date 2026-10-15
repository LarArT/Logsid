# Logique mathématique : Syntaxe vs Sémantique
- ## 1. Distinction fondamentale : Syntaxe vs Sémantique
	- $$ \begin{array}{ccc} \mathbf{Syntaxe} & \text{vs} & \mathbf{Sémantique} \\ \text{(Déduction, symboles, règles)} & & \text{(Modèles, structures, interprétations)} \\ T \vdash \varphi & & \mathcal{M} \models \varphi \quad \text{ou} \quad \models \varphi \\ \text{Démontrable, Contradictoire, Décidable} & & \text{Vrai, Valide} \end{array} $$
- ## 2. Tableau comparatif des notions
	- | Notion | Domaine | Portée / Objet | Définition formelle rapide |
	  | :--- | :--- | :--- | :--- |
	  | **Démontrable** | Syntaxe | Formule $\varphi$ | $T \vdash \varphi$ : Il existe une preuve formelle de $\varphi$ à partir de $T$. |
	  | **Contradictoire** | Syntaxe | Théorie $T$ | $T \vdash \bot$ : On peut démontrer une contradiction ($A \land \neg A$). |
	  | **Non contradictoire** | Syntaxe | Théorie $T$ | $T \nvdash \bot$ : Aucun raisonnement dans $T$ ne produit de contradiction. |
	  | **Décidable** | Calculabilité / Syntaxe | Théorie ou Problème | Il existe un algorithme qui détermine si $T \vdash \varphi$ en un temps fini. |
	  | **Vrai** | Sémantique | Formule dans une structure | $\mathcal{M} \models \varphi$ : La formule $\varphi$ est vérifiée dans le modèle $\mathcal{M}$. |
	  | **Valide** | Sémantique | Formule universelle | $\models \varphi$ : La formule $\varphi$ est vraie dans tous les modèles possibles. |
	  | **Complet** | Méta-théorie | Système ou Théorie | • **Système :** Tout ce qui est valide est démontrable ($\models \varphi \implies \vdash \varphi$).<br>• **Théorie :** Pour toute formule close $\varphi$, $T \vdash \varphi$ ou $T \vdash \neg \varphi$. |
	  | **Compact** | Méta-théorie | Théorie (Sémantique) | $T$ a un modèle $\iff$ Tout sous-ensemble fini $T_0 \subseteq T$ a un modèle. |
- ## 3. Définitions détaillées
	- ### Notion 1 : Démontrable ($\vdash$)
		- Une formule $\varphi$ est démontrable dans une théorie $T$ (noté $T \vdash \varphi$) s'il existe une suite finie de formules constituant une dérivation formelle de $\varphi$ en utilisant uniquement les axiomes de $T$ et les règles de déduction du système (ex. *Modus Ponens*).
	- ### Notion 2 : Contradictoire et Non contradictoire (Consistance)
		- **Contradictoire (Inconsistante) :** Une théorie $T$ est contradictoire si l'on peut y démontrer le faux ($T \vdash \bot$). Par le principe d'explosion en logique classique, une théorie contradictoire permet de démontrer n'importe quelle formule du langage.
		- **Non contradictoire (Consistante) :** $T$ est non contradictoire si $T \nvdash \bot$. Il existe au moins une formule du langage qui n'est pas démontrable dans $T$.
	- ### Notion 3 : Décidable
		- Le terme s'applique à deux niveaux distincts :
			- **D'une théorie $T$ :** $T$ est décidable s'il existe un algorithme (une machine de Turing) capable de déterminer en un nombre fini d'étapes, pour n'importe quelle formule $\varphi$, si $T \vdash \varphi$ est vrai ou faux.
			- **D'une formule $\varphi$ dans $T$ :** $\varphi$ est décidable dans $T$ si $T \vdash \varphi$ ou $T \vdash \neg \varphi$.
	- ### Notion 4 : Vrai ($\models$)
		- La vérité est une notion relative à une structure donnée $\mathcal{M}$ (un univers de discours avec une interprétation des symboles) :
			- $$ \mathcal{M} \models \varphi \quad (\text{"}\varphi\text{ est vraie dans le modèle }\mathcal{M}\text{"}) $$
		- *Exemple :* La formule $\exists x \, (x \cdot x = 2)$ est vraie dans la structure $(\mathbb{R}, \cdot)$ mais fausse dans la structure $(\mathbb{Q}, \cdot)$.
	- ### Notion 5 : Valide ($\models \varphi$)
		- Une formule $\varphi$ est valide (ou universellement valide) si elle est vraie dans toute structure/modèle adapté à son langage :
			- $$ \text{Pour tout modèle }\mathcal{M}, \, \mathcal{M} \models \varphi \implies \models \varphi $$
		- En logique propositionnelle, une formule valide s'appelle une **tautologie** (ex. $A \lor \neg A$).
	- ### Notion 6 : Complet (Complétude)
		- La notion dépend du contexte :
			- **Complétude d'un système logique (Gödel) :** Le pont entre sémantique et syntaxe. Un système déductif est complet si toute formule valide y est démontrable :
				- $$ \text{Si } T \models \varphi \text{ alors } T \vdash \varphi $$
			- **Complétude d'une théorie $T$ :** Une théorie $T$ est complète si elle ne laisse aucune formule close indécidée : pour toute formule close $\varphi$, on a $T \vdash \varphi$ ou $T \vdash \neg \varphi$.
		- **Note :** Le premier théorème d'incomplétude de Gödel énonce que toute théorie arithmétique suffisante, récursivement axiomatisable et non contradictoire est incomplète.
	- ### Notion 7 : Compact (Théorème de compacité)
		- Propriété fondamentale de la logique du premier ordre découlant du théorème de complétude :
			- $$ \text{Un ensemble infini d'axiomes } T \text{ possède au moins un modèle} \iff \text{Tout sous-ensemble fini } T_0 \subseteq T \text{ possède un modèle} $$
		- *Application classique :* Permet de construire des modèles non standards (ex. des modèles de l'arithmétique contenant des entiers infiniment grands).
	- ### ​Notion 5 : Catégorique (Théorie catégorique)
	  
	  ​Une théorie T est **\kappa****-catégorique** (pour un cardinal \kappa) si tous ses modèles de cardinalité \kappa sont isomorphes entre eux (ils ont exactement la même structure).
	- ​*Exemple :* La théorie des corps algébriquement clos de caractéristique 0 est \aleph_1-catégorique.
	- ### ​Notion 6 : Théorème de Löwenheim-Skolem
	  
	  ​Théorème fondamental de la théorie des modèles qui complète le théorème de compacité :
	- ​**Löwenheim-Skolem vers le bas :** Si une théorie dénombrable a un modèle infini, elle a un modèle **dénombrable**.
	- ​**Löwenheim-Skolem vers le haut :** Si une théorie dénombrable a un modèle infini, elle a des modèles de **toutes les cardinalités infinies supérieures**.
- # Notions Fondamentales de Logique et Théorie des Modèles #card #logique #maths
  collapsed:: false
	- ## 1. SYNTAXE #syntaxe
		- **Démontrable** #notion
			- definition:: Une formule $\varphi$ est démontrable dans $T$ s'il existe une preuve formelle (suite finie de règles de déduction).
			- notation:: $T \vdash \varphi$
		- **Cohérent / Consistant** #notion
			- definition:: Une théorie $T$ est cohérente s'il est impossible d'y dériver une contradiction.
			- notation:: $T \nvdash \bot$
			- equivalence-semantique:: $T$ possède au moins un modèle (Théorème de complétude de Gödel).
		- **Contradictoire / Inconsistant** #notion
			- definition:: Une théorie $T$ permettant de démontrer le faux ($\bot$). Par principe d'explosion, elle permet de tout prouver.
			- notation:: $T \vdash \bot$
		- **Indépendant** #notion
			- definition:: Formule qui ne peut être ni prouvée ni réfutée dans $T$.
			- notation:: $T \nvdash \varphi$ et $T \nvdash \neg\varphi$
			- exemple:: L'hypothèse du continu vis-à-vis d'Axiomes de Zermelo-Fraenkel ($ZFC$).
		- **Décidable** #notion #calculabilite
			- d-une-theorie:: Existe-t-il un algorithme déterminant en temps fini si $T \vdash \varphi$ ?
			- d-une-formule:: $T \vdash \varphi$ ou $T \vdash \neg\varphi$.
	- ## 2. SÉMANTIQUE #semantique
		- **Vrai dans un modèle** #notion
			- definition:: La formule $\varphi$ est satisfaite dans une structure donnée $\mathcal{M}$.
			- notation:: $\mathcal{M} \models \varphi$
		- **Valide / Tautologie** #notion
			- definition:: La formule $\varphi$ est vraie dans TOUS les modèles possibles.
			- notation:: $\models \varphi$
		- **Satisfiable / Réalisable** #notion
			- definition:: Il existe au moins une structure $\mathcal{M}$ validant la formule.
			- notation:: $\exists \mathcal{M}, \mathcal{M} \models \varphi$
	- ## 3. MÉTA-THÉORIE & THÉORIE DES MODÈLES #meta-theorie
		- **Correct / Sound** #notion
			- propriete:: $T \vdash \varphi \implies T \models \varphi$ (Pas de fausse preuve).
		- **Complet** #notion
			- dun-systeme:: $T \models \varphi \implies T \vdash \varphi$ (Tout ce qui est valide est démontrable).
			- d-une-theorie:: Pour toute formule close $\varphi$, $T \vdash \varphi$ ou $T \vdash \neg\varphi$.
		- **Compact** #notion
			- theoreme:: $T$ a un modèle $\iff$ tout sous-ensemble fini $T_0 \subseteq T$ a un modèle.
		- **Catégorique** #notion
			- definition:: Une théorie est $\kappa$-catégorique si tous ses modèles de cardinalité $\kappa$ sont isomorphes.