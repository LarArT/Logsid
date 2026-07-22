-
- Les **méthodes formelles** désignent un ensemble de techniques rigoureuses fondées sur les **mathématiques** (logique, théorie des ensembles, théories des types, théorie des automates) utilisées pour spécifier, concevoir, analyser et vérifier des systèmes matériels ou logiciels.
  
  Voici une cartographie détaillée de tout ce que recouvre ce domaine :
- ## 1. La Spécification Formelle (Exprimer le « Quoi »)
  
  Avant de pouvoir vérifier un système, il faut décrire son comportement attendu à l'aide d'un langage mathématique non ambigu.
- **[[Spécifications fondées sur les états et le raffinage]] :**
- [[Assistant de preuve ITP]]
- [[Langages de contrat]]
- [[méthodes fondées sur les modèles et le Model Checking]]
- ## 2. La Vérification Formelle (Prouver le « Comment »)
  
  Il existe deux grands paradigmes pour vérifier qu'un système satisfait sa spécification :
- ### A. La vérification algorithmique (Automatique / Model Checking)
  
  Le système est modélisé comme un automate à états finis, et un outil parcourt de façon exhaustive tous les états possibles.
- **Model Checking énumératif & symbolique :** Exploration de l'espace d'états (ex. via BDDs — *Binary Decision Diagrams*).
- **Bounded Model Checking (BMC) :** Utilisation de solveurs SAT/SMT pour vérifier le système jusqu'à une profondeur maximale fixée.
- **Logiques temporelles associées :**
	- LTL (*Linear Temporal Logic*) : Logique temporelle linéaire (propriétés sur des traces).
	- CTL (*Computation Tree Logic*) : Logique temporelle arborescente (propriétés sur des arborescences d'exécutions).
- **Outils représentatifs :** SPIN, UPPAAL, NuSMV, TLC (pour TLA+).
- ### B. La vérification déductive (Démonstration de théorèmes)
  
  On transforme le problème en un ensemble de théorèmes mathématiques à prouver.
- **Calcul des conditions de vérification (Weakest Precondition / Logic de Hoare) :**
	- Génération automatique de propositions mathématiques (VCs - *Verification Conditions*) transmises à des solveurs SMT (Z3, CVC5) ou des assistants de preuve.
	- *Outils :* Frama-C (WP), Why3, Dafny.
- [[Assistant de preuve ITP]]
- ## 3. L'Analyse Statistique & Interprétation Abstraite
  
  Méthodes automatiques permettant de garantir des propriétés globales du code sans exécuter le programme ni écrire de preuves complètes.
- **Interprétation Abstraite :** Sur-approximation du comportement du programme sur un domaine abstrait (ex. intervalles, polyèdres) pour prouver l'absence d'erreurs à l'exécution (division par zéro, dépassement de tableau, débordement de mémoire).
	- *Outils :* Astrée, Polyspace.
- **Analyse de flux de données & Slicing :** Analyse du parcours de l'information pour détecter les failles de sécurité ou supprimer du code mort.
- ## 4. La Synthèse et la Génération Certifiées
  
  Les méthodes formelles ne se limitent pas à vérifier du code existant, elles permettent aussi de le construire :
- **Raffinage :** Passage progressif d'une spécification abstraite vers un code exécutable en garantissant la préservation des propriétés à chaque étape (ex. Génération de code C/Ada depuis la méthode B).
- **Extraction de code :** Traduction automatique d'une fonction prouvée dans un assistant de preuve vers un langage de programmation (ex. extraction de Rocq/Coq vers OCaml, Haskell ou C).
- **Compilation certifiée :** Garantie que le compilateur ne modifie pas la sémantique du programme source (ex. le compilateur *CompCert*).
- **Synthèse de programmes / de contrôleurs :** Génération automatique d'un algorithme ou d'un automate à partir de sa spécification logique.
- ## 5. Fondements Mathématiques Subjacents
  
  L'ensemble de ces méthodes repose sur un socle théorique strict :
  
  | Domaine théorique | Application principale |
  
  | **Logique mathématique** | Logique du 1er ordre, Logique de Hoare, Logiques temporelles (LTL, CTL) |
  
  | **Théorie des types** | Calcul des Constructions Inductives (CIC), Théorie des types dépendants, Correspondance de Curry-Howard |
  
  | **Théorie des automates** | Automates à états finis, Automates à mots infinis (\omega-automates), Automates temporisés |
  
  | **Sémantique des langages** | Sémantique opérationnelle, dénotationnelle et axiomatique |
  
  | **Théorie des treillis & Point fixe** | Fondements de l'interprétation abstraite (Théorème de Knaster-Tarski) |
- ## Synthèse du périmètre
  
  Pour résumer, l'écosystème des méthodes formelles couvre :
- **Comment on exprime les exigences :** Spécifications (B, TLA+, ACSL).
- **Comment on vérifie automatiquement :** Model Checking (SPIN) & Analyse statique (Astrée).
- **Comment on prouve mathématiquement :** Preuve déductive (Frama-C) & Assistants de preuve (Rocq, Lean 4).
- **Comment on produit du logiciel sûr :** Compilation certifiée (CompCert) & Génération par raffinage.
-
-