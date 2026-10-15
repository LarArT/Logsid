- Étude générale des structures mathématiques : espace vectorial espace normé anneaux corps exetera
- **Définition 2.4.3** Soient $\mathcal{M}$ et $\mathcal{N}$ deux interprétations d'un langage $\mathcal{L}$.
	- 1. Un *$\mathcal{L}$-morphisme* de $\mathcal{M}$ dans $\mathcal{N}$ est une fonction $\phi : |\mathcal{M}| \rightarrow |\mathcal{N}|$ telle que :
		- Pour chaque symbole de constante $c$ on a : $\phi(c_{\mathcal{M}}) = c_{\mathcal{N}}$.
		- Pour chaque symbole de fonction $n$-aire $f$ et pour $a_1, \dots, a_n \in |\mathcal{M}|$ on a : $\phi(f_{\mathcal{M}}(a_1, \dots, a_n)) = f_{\mathcal{N}}(\phi(a_1), \dots, \phi(a_n))$.
		- Pour chaque symbole de relation $n$-aire $R$ (autre que $=$) et pour $a_1, \dots, a_n \in |\mathcal{M}|$ on a : $(a_1, \dots, a_n) \in R_{\mathcal{M}}$ ssi $(\phi(a_1), \dots, \phi(a_n)) \in R_{\mathcal{N}}$.
	- 2. Un *$\mathcal{L}$-isomorphisme* est un $\mathcal{L}$-morphisme bijectif.
	- 3. $\mathcal{M}$ et $\mathcal{N}$ sont *$\mathcal{L}$-isomorphes* s'il existe un $\mathcal{L}$-isomorphisme de $\mathcal{M}$ dans $\mathcal{N}$.
-
- **Définition 2.4.11** — Extension et sous-interprétation #[[Logique du premier ordre]] #Définition
  id:: def-extension-interpretation
	- **Énoncé** :: Soient $\mathcal{L}$ un langage, $\mathcal{M}$ et $\mathcal{N}$ deux interprétations de $\mathcal{L}$. On dit que $\mathcal{M}$ est une **extension** de $\mathcal{N}$ (ou que $\mathcal{N}$ est une **sous-interprétation** de $\mathcal{M}$) si et seulement si les conditions suivantes sont satisfaites :
		- `1.` **Inclusion des domaines**
			- $|\mathcal{N}| \subset |\mathcal{M}|$
		- `2.` **Conservation des constantes**
			- Pour tout symbole de constante $c$ de $\mathcal{L}$ on a :
			  $$c_\mathcal{N} = c_\mathcal{M}$$
		- `3.` **Restriction des fonctions**
			- Pour tout symbole de fonction $n$-aire $f$ de $\mathcal{L}$ on a :
			  $$f_\mathcal{N} = f_\mathcal{M} \restriction |\mathcal{N}|^n$$
			- > **Remarque :** Puisque $f_\mathcal{N}$ est une fonction de $|\mathcal{N}|^n$ dans $|\mathcal{N}|$, cela implique que $f_\mathcal{M}(|\mathcal{N}|^n)$ est inclus dans $|\mathcal{N}|$.
		- `4.` **Restriction des relations**
			- Pour tout symbole de relation $n$-aire $R$ de $\mathcal{L}$ on a :
			  $$R_\mathcal{N} = R_\mathcal{M} \cap |\mathcal{N}|^n$$