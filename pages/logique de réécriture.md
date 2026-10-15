Tags:: maude, pi-calcul, CCS, lambda-calcul

	-
- La **logique de réécriture** (*Rewriting Logic*) est un cadre logique et sémantique très puissant introduit au début des années 1990 par **José Meseguer**. Elle a été conçue pour unifier de manière naturelle le calcul, le parallélisme, la logique et la spécification formelle.
  
  Son idée fondamentale est aussi simple que profonde : **revoir la réécriture de termes non pas seulement comme un outil de simplification algébrique, mais comme un modèle général de changement et de transition d'état.**
- ## 1. L'Intuition Fondamentale
  
  Pour bien comprendre la logique de réécriture, il convient de la comparer aux approches logiques traditionnelles.
- ### Dans la logique classique ou le \lambda-calcul
  
  L'égalité est symétrique : si t = u, alors u = t. On utilise la réécriture de termes de façon orientée t \to u uniquement pour trouver des formes normales (simplification). Les termes représentent des **valeurs** ou des **expressions mathématiques**.
- ### Dans la logique de réécriture
  
  La réécriture n'est plus une simple étape de calcul intermédiaire : **la règle de réécriture est le concept central**.
- Un **terme** t représente un **état** du système.
- Une **règle de réécriture** t \to u représente une **transition d'état** ou un **changement local**.
- Les transitions ne sont **pas** nécessairement réversibles ni déterministes.
  
  > 
  
  **Slogan de Meseguer :**
  *State space = Term algebra* (L'espace d'états est une algèbre de termes)
  *State transitions = Rewriting steps* (Les transitions d'état sont des étapes de réécriture)
- ## 2. Définition Formelle
  
  Un système en logique de réécriture est formalisé par une **théorie de réécriture** (\mathcal{R}), définie par le quadruplet :
  
  `\mathcal{R} = (\Sigma, E, L, R)`
- **\Sigma (La signature) :** Définit les sortes (types) et les symboles de fonction (opérateurs) permettant de construire les termes.
- **E (Les équations) :** Un ensemble d'équations (comme la commutativité ou l'associativité) sur les termes. L'égalité dans E définit la structure statique des états. On travaille modulo ces équations (par exemple : \text{état}_1 =_E \text{état}_2).
- **L (Les étiquettes) :** Un ensemble de noms pour identifier les règles de réécriture.
- **R (Les règles de réécriture) :** Un ensemble de règles orientées de la forme :
  
  `r : [t] \to [u] \quad \text{ou de façon conditionnelle} \quad r : t \to u \Leftarrow \bigwedge_i p_i \to q_i \land \bigwedge_j u_j = v_j`
  
  Chaque règle indique qu'un sous-état correspondant au motif t peut évoluer vers u, indépendamment du reste du système.
- ## 3. Déduction et Preuves comme Réécritures
  
  La logique de réécriture est une vraie **logique formelle**. On dit qu'une séquent de réécriture :
  
  `\mathcal{R} \vdash t \to u`
  
  est valide s'il existe une déduction permettant d'atteindre l'état u à partir de l'état t. Les règles d'inférence de cette logique sont :
- **Reflexivité :** Tout état se réécrit en lui-même sans changement (t \to t).
- **Congruence (Parallélisme) :** Si t_i \to u_i, alors f(t_1, \dots, t_n) \to f(u_1, \dots, u_n). Cela exprime que des sous-systèmes indépendants peuvent évoluer en parallèle.
- **Transitivité (Chaining) :** Si t \to u et u \to v, alors t \to v.
- **Remplacement (Application de règle) :** Appliquer une règle de R en substituant des termes aux variables.
  
  Une preuve dans cette logique n'est pas une simple démonstration statique : c'est la **trace d'une exécution** ou un **graphe de transition**.
- ## 4. Propriétés Clés : Concurrence et Non-déterminisme
  
  La logique de réécriture résout naturellement deux grands défis de l'informatique théorique :
- ### La concurrence locale
  
  Si deux règles de réécriture s'appliquent à des sous-termes disjoints d'un même terme, elles peuvent être exécutées **en même temps** (par la règle de Congruence). Le parallélisme est donc une propriété intrinsèque, et non un ajout *ad hoc*.
- ### Le non-déterminisme
  
  Plusieurs règles peuvent s'appliquer sur un même sous-terme (conflit d'accès). La logique de réécriture ne force pas le choix : elle décrit **l'ensemble des comportements possibles** du système.
- ## 5. Un Métamodèle Universel
  
  L'un des plus grands succès théoriques de la logique de réécriture est sa capacité à **assimiler d'autres modèles de calcul**. On peut coder de manière très directe :
- **Les Réseaux de Petri :** Un état est un multi-ensemble de jetons, les transitions sont des règles de réécriture.
- **Le \lambda-calcul :** La \beta-réduction est directement une règle de réécriture.
- **Le Calcul de Processus (\pi-calcul, CCS) :** La communication entre canaux s'exprime sous forme de réécriture.
- **Les Automates à états finis et Systèmes de transition :** Les états sont des termes et les transitions des règles.
- **La Sémantique Exécutable des Langages de Programmation :** Permet de spécifier formellement la syntaxe et la sémantique de langages complexes (comme C, Java ou Python).
- ## 6. L'Écosystème Logique : L'Exemple de  **Maude**
  
  Le langage de programmation et de spécification le plus célèbre basé sur la logique de réécriture est **Maude**.
  
  Dans Maude, l'utilisateur écrit sa théorie \mathcal{R}, puis dispose d'outils puissants :
- **Moteur d'exécution (Rewriting) :** Simule le système en appliquant les règles.
- **Recherche d'états (Reachability Analysis) :** Explore l'espace d'états pour vérifier si un état critique u peut être atteint depuis t (t \to^* u).
- **Model Checking LTL :** Permet de vérifier des propriétés logiques temporelles (ex: "le système ne tombe jamais en deadlock").
- ## En Résumé
  
  | Aspect | Logique Classique | Logique de Réécriture |
  
  | **Égalité t = u** | Identité / Équivalence statique | Même état de référence |
  
  | **Flèche t \to u** | Implication logique | Transition d'état / Évolution |
  
  | **Terme** | Concept mathématique / Valeur | État d'un système |
  
  | **Calcul** | Évaluation vers une valeur | Simulation / Parcours d'un espace d'états |