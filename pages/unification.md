Tags:: unificateur le plus général, mgu

- Voici la feuille récapitulative condensée de l'ensemble du document, au format Markdown strictement compatible avec Logseq (structure en arborescence de puces, indentation tabulée et blocs LaTeX intégrés sans saut de ligne parasite).
- FICHE RÉCAPITULATIVE : ALGORITHME D'UNIFICATION
	- 1. Notions Fondamentales
		- **Langage & Variables :** Termes sur un langage \mathcal{L} et un ensemble de variables \mathcal{V}.
		- **Substitution (\sigma) :** Application associant un terme à chaque variable.
			- **Application :** u[\sigma] désigne le terme u où chaque variable est remplacée par son image.
			- **Composition :** u[\sigma \circ \sigma'] = (u[\sigma])[\sigma'].
		- **Unifiabilité :** Deux termes u et v sont unifiables s'il existe \sigma tel que u[\sigma] = v[\sigma].
			- ⚠️ La relation "être unifiable" est **réflexive et symétrique**, mais **non transitive** (ex: g(x) \sim y et y \sim f(z), mais g(x) \not\sim f(z)).
			- ⚠️ Notion **purement syntaxique** (ex: 2+x et 3 ne sont pas unifiables par x=1 car le terme "2+1" est distinct de "3").
		- **m.g.u. (Most General Unifier) :** Substitution \sigma unifiant u et v telle que tout autre unificateur \sigma' s'écrit \sigma' = \tau \circ \sigma.
	- 2. Algorithme d'Unification
		- **Entrée :** Un système d'équations E = \{ (u_k, v_k) \}_{k \in [1..K]}.
		- **Initialisation :** \sigma \leftarrow id.
		- **Règles de transformation (Tant que E \neq \emptyset, choisir e \in E) :**
			- **Suppression (Cas 1) :** (x, x) \implies E \leftarrow E \setminus \{e\}.
			- **Elimination / Substitution (Cas 2) :** (x, u) avec x \in \mathcal{V} :
				- Si x apparaît dans u \implies Échec (**occur-check**).
				- Sinon \implies E \leftarrow E[x:=u] et \sigma \leftarrow [x:=u] \circ \sigma.
			- **Décomposition / Clash (Cas 3) :** (f(t_1..t_p), g(s_1..s_q)) :
				- Si f \neq g \implies Échec (**clash**).
				- Si f = g \implies E \leftarrow E \setminus \{e\} \cup \{ (t_i, s_i) \}_{i \in [1..p]}.
		- **Sortie :** La substitution \sigma (m.g.u.).
	- 3. Propriétés Majeures (Preuves)
		- **Terminaison :**
			- Repose sur l'ordre lexicographique bien fondé \le = \le_v \times \le_f \times \le_e (v : variables, f : symboles de fonction, e : nombre d'équations).
			- Cas 1 diminue e (e = <), Cas 2 diminue v (v = <), Cas 3 diminue f (f = <).
		- **Correction :**
			- Invariant H_n : « \tau unifie E ssi \exists \tau' unifiant E_n tel que \tau = \tau' \circ \sigma_n ».
			- Si l'algo s'arrête sur E_N = \emptyset, \sigma_N est le m.g.u.
			- Si l'algo s'arrête sur un échec (*clash* ou *occur-check*), E n'a pas de solution.
	- 4. Exemple d'Exécution Pas à Pas
		- **Problème :** Unifier u = f(x, x, y) et v = f(f(y, y, z), f(y, g, z), a).
		- **Déroulement :**
			-
				- **Cas 3 (Décomposition) :** E = \{ (x, f(y, y, z)), (x, f(y, g, z)), (y, a) \}.
			-
				- **Cas 2 (Subst. x) :** E = \{ (f(y, y, z), f(y, g, z)), (y, a) \}, \sigma = [x := f(y, y, z)].
			-
				- **Cas 3 (Décomposition) :** E = \{ (y, y), (y, g, z), (z, z), (y, a) \}.
			-
				- **Cas 1 (Nettoyage) :** Élimination de (y,y), (y, g, z) et (z,z) \implies E = \{ (y, a) \}.
			-
				- **Cas 2 (Subst. y) :** E = \emptyset, \sigma = [y \mapsto a, x \mapsto f(a, a, z)].
		- **Résultat :** m.g.u.(u,v) = \left\{ \begin{array}{l} y \mapsto a \\ x \mapsto f(a, a, z) \end{array} \right..
- Effectivement, au temps pour moi. Dans Logseq, les blocs de mathématiques sur plusieurs lignes avec `$$ ... $$` posent problème s'ils ne sont pas placés sur leurs propres lignes sous le parent ou si des sauts de ligne internes brisent la structure des puces.
  
  Pour garantir une compatibilité totale avec le parser Markdown/Org de Logseq :
- Chaque bloc `$$ ... $$` est placé directement sur sa propre ligne sous le texte parent.
- Les sauts de ligne dans les grands environnements LaTeX (`\begin{array}`) ont été simplifiés ou gardés sur une seule ligne continue pour éviter que Logseq ne découpe le bloc.
- Tous les identifiants et puces utilisent la syntaxe stricte des retraits Logseq.
  
  Voici la version corrigée et testée pour un import sans erreur :
- ALGORITHME D'UNIFICATION
	- On travaille sur des termes écrits dans un langage \mathcal{L} et sur l'ensemble de variables \mathcal{V}.
	- Définitions
		- Une **substitution** est une fonction qui à chaque variable associe un terme.
			- **Exemple :**
			  \mathcal{L} = \{ +, 0 \}
			  \mathcal{V} = \{ x, y, z \}
			  `\sigma = \left\{ \begin{array}{l} x \mapsto x + y \\ y \mapsto y \\ z \mapsto y + 0 \end{array} \right.`
		- Si u est un terme et \sigma une substitution, on note **u[\sigma]** le terme obtenu en remplaçant (simultanément) chaque variable par son image par \sigma.
			- En particulier si x \in \mathcal{V}, x[\sigma] = \sigma(x).
			- ⚠️ u[\sigma \circ \sigma'] = (u[\sigma])[\sigma']
			- **Exemple :**
			  \mathcal{L} = \{ a, +, 0 \}, \mathcal{V} = \{ x, y, z \}
			  `\sigma = \left\{ \begin{array}{l} x \mapsto y \\ y \mapsto a(+)z \\ z \mapsto 0 \end{array} \right. \qquad \sigma' = \left\{ \begin{array}{l} x \mapsto x \\ y \mapsto 1 \\ z \mapsto 0 \end{array} \right.`
			  `\mu = s(x) + y`
			  `\mu[\sigma] = s(y) + s(y) + s(z)`
			  `\mu[\sigma \circ \sigma'] = s(1) + s(0)`
		- **Deux termes u et v sont unifiables** s'il existe une substitution \sigma telle que u[\sigma] = v[\sigma]. On dit alors que \sigma unifie u et v.
			- **Remarque :** Être unifiable est une relation réflexive et symétrique mais non transitive ⚠️. Exemple : g(x) \sim y, y \sim f(z) mais g(x) \not\sim f(z).
			- **Exemples :**
				- s(x+y) et s(z)+x ne sont pas unifiables.
				- s(x+y)+y et s(z)+x sont unifiables : pour \sigma = \left( \begin{array}{l} y \mapsto x \\ z \mapsto x+x \end{array} \right), (s(x+y)+y)[\sigma] = s(x+x)+x = s(z)+x[\sigma].
		- Un **unificateur le plus général (m.g.u. *"most general unifier"*)** de deux termes est une substitution \sigma qui unifie u et v et telle que si \sigma' unifie u et v, alors il existe \tau t.q. \sigma' = \tau \circ \sigma.
			- **Exemple :** u = f(x, x, y) et v = f(f(y,y,z), f(y,g,z), a).
			  `m.g.u.(u,v) = \left\{ \begin{array}{l} x \mapsto f(a,a,z) \\ y \mapsto a \end{array} \right.`
			- ⚠️ Toutes ces notions sont purement syntaxiques. Exemple : 2+x et 3 ne sont pas unifiables par x=1 car "2+1" \neq "3".
	- Proposition
		- Si u et v sont unifiables, alors ils admettent un m.g.u., noté m.g.u.(u,v).
		- La preuve est donnée par l'algorithme suivant qui termine toujours (soit par un échec si non unifiables, soit en fournissant un m.g.u.).
	- Algorithme d'Unification
	  
	  `\text{UNIFICATION}\left( \{ (u_k, v_k) \}_{k \in [1..K]} \right)`
	  `E \leftarrow \{ (u_k, v_k) \mid k \in [1..K] \}`
	  `\sigma \leftarrow id`
	  `\begin{array}{l} \text{Tant que } E \neq \emptyset \\ \quad \text{Choisir } e \in E \\ \quad \text{match } e \text{ with} \\ \quad \begin{array}{\|l} (x,x) \text{ où } x \in \mathcal{V} \rightarrow E \leftarrow E \setminus \{e\} \\ (x,u) \text{ où } x \in \mathcal{V} \rightarrow \begin{array}{\|l} \text{Si } x \text{ apparaît dans } u \text{ alors failwith "occur-check"} \\ \text{sinon } E \leftarrow E[x:=u], \quad \sigma \leftarrow [x:=u] \circ \sigma \end{array} \\ (f(t_1, \dots, t_p), g(s_1, \dots, s_q)) \rightarrow \begin{array}{\|l} \text{Si } f \neq g \text{ alors failwith "clash"} \\ \text{sinon } E \leftarrow E \setminus \{e\} \cup \{ (t_i, s_i) \mid i \in [1..p] \} \end{array} \end{array} \end{array}`
	  `\text{Retourner } \sigma.`
- ## Preuve de Terminaison
- On note v, f, e respectivement le nombre courant de variables, de symboles de fonction, et d'équations dans E.
- On définit l'ordre lexicographique produit \le = \le_v \times \le_f \times \le_e sur les états de E.
- Cet ordre est bien fondé car toute chaîne strictement décroissante est minorée par 0.
- E \le E' signifie :
- E a **strictement moins** de variables que E'
- ou E a **autant** de variables que E' mais **strictement moins** de symboles f
- ou E a **autant** de variables et de symboles f que E', mais **strictement moins** d'équations.
- Analyse des cas de l'algorithme :
- **Cas 1 :** (x,x) \implies le nombre d'équations décroît strictement (e = <).
- **Cas 2 :** (x,u) \implies la variable x disparaît de E (v = <).
- **Cas 3 :** f(t_1..t_p) = f(s_1..s_p) \implies le nombre de symboles de fonction décroît (f = <).
- **Conclusion :** L'algorithme termine systématiquement.
- ## Preuve de Correction
- Soit la propriété récurrente H_n : « \tau unifie E ssi il existe \tau' unifiant E_n tel que \tau = \tau' \circ \sigma_n ».
- **Base (n=0) :** E_0 = E et \sigma_0 = id, trivialement vérifié avec \tau' = \tau.
- **Hérédité (n \to n+1) :**
- **Cas 1 :** E_{n+1} = E_n \setminus \{(x,x)\}. Tout unificateur de E_{n+1} unifie aussi x = x, donc E_n.
- **Cas 2 :** E_{n+1} = E_n[x:=u] et \sigma_{n+1} = [x:=u] \circ \sigma_n. Si \tau' unifie E_n, alors x[\tau'] = u[\tau'], d'où la préservation des solutions.
- **Cas 3 :** Décomposition f(t_1..t_p) = f(s_1..s_p). L'unification du terme principal équivaut à l'unification sous-terme par sous-terme.
- **Conclusion à l'étape finale N :**
- Si E_N = \emptyset, \sigma_N est le m.g.u.
- Si arrêt sur *clash* ou *occur-check*, E n'est pas unifiable.
- **CQFD.**
- ## Exemple pas à pas
- Soient u = f(x, x, y) et v = f(f(y, y, z), f(y, g, z), a).
- Initialisation : E \leftarrow \{ (f(x, x, y), f(f(y, y, z), f(y, g, z), a)) \}, \sigma \leftarrow id.
- **Étape 1 (Cas 3) :** Décomposition de f.
  
  `E \leftarrow \{ (x, f(y, y, z)), (x, f(y, g, z)), (y, a) \}`
- **Étape 2 (Cas 2) :** Substitution x := f(y, y, z).
  
  `E \leftarrow \{ (f(y, y, z), f(y, g, z)), (y, a) \}`
  `\sigma \leftarrow [x := f(y, y, z)]`
- **Étape 3 (Cas 3) :** Décomposition de f.
  
  `E \leftarrow \{ (y, y), (y, g, z), (z, z), (y, a) \}`
- **Étape 4 (Cas 1) :** Suppression de (y,y).
  
  `E \leftarrow \{ (y, g, z), (z, z), (y, a) \}`
- **Étape 5 (Cas 1) :** Traitement/nettoyage.
  
  `E \leftarrow \{ (z, z), (y, a) \}`
- **Étape 6 (Cas 1) :** Suppression de (z,z).
  
  `E \leftarrow \{ (y, a) \}`
- **Étape 7 (Cas 2) :** Substitution y := a.
  
  `E \leftarrow \emptyset`
  `\sigma \leftarrow \left\{ \begin{array}{l} y \mapsto a \\ x \mapsto f(a, a, z) \end{array} \right.`
- **Résultat :** Le m.g.u. obtenu est \sigma = [y \mapsto a, x \mapsto f(a,a,z)].