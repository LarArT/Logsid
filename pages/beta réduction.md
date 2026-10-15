-
- Définitions de la $\beta$ -réduction
	- On appelle **redex** (pour *reducible expression*) toute expression de la forme (λ x.s) t.
	- On dit que s[t/x] est le **réduit** de (λ x.s) t, et on note :
	  $(\lambda x.s) t \rightarrow_{\beta_0} s[t/x]$
	- La $\beta-réduction$ $\rightarrow_\beta$ est la plus petite relation *compatible avec la syntaxe* sur $\Lambda$ contenant $\rightarrow_{\beta_0}$ .
-
- # exemple
- Source:: https://lsv.ens-paris-saclay.fr/~goubault/Lambda/lambda-agreg-1-short-step-by-step_compressed.pdf
- [[exemple de bêta réduction]]
- # Un exemple de réductions
  
  Au départ, le terme initial comporte **2 rédexes** :
  $$\underline{(\lambda y . \ \underline{(\lambda x . yxx)(\lambda z . z(xy))})(\lambda z' . z')}$$
  
  ---
- ### 1. Chemin de gauche (Réduction du rédexe interne en premier)
  
  * **Étape 1 :**
  $$(\lambda y . y(\lambda z . z(xy))(\lambda z . z(xy)))(\lambda z' . z')$$
  * **Étape 2 :**
  $$(\lambda z' . z')(\lambda z . z(x(\lambda z' . z')))(\lambda z . z(x(\lambda z' . z')))$$
  * **Étape 3 (Convergence) :**
  $$(\lambda z . z(x(\lambda z' . z')))(\lambda z . z(x(\lambda z' . z')))$$
  
  ---
- ### 2. Chemin de droite (Réduction du rédexe externe en premier)
  
  * **Étape 1 :**
  $$(\lambda x . (\lambda z' . z')xx)(\lambda z . z(x(\lambda z' . z')))$$
  * **Étape 2 (Bifurcation) :**
  * *Option A (Directe) :* Rejoint directement l'**Étape 3** de convergence :
    $$(\lambda z . z(x(\lambda z' . z')))(\lambda z . z(x(\lambda z' . z')))$$
  * *Option B (Intermédiaire) :* Réduit d'abord le sous-terme interne :
    $$(\lambda x . xx)(\lambda z . z(x(\lambda z' . z')))$$
    Puis rejoint l'**Étape 3** de convergence.
  
  ---
- ### 3. Cheminement commun vers la forme normale
  
  À partir de l'**Étape 3**, les réductions se poursuivent de manière linéaire :
  
  * **Étape 4 :**
  $$(\lambda z . z(x(\lambda z' . z')))(x(\lambda z' . z'))$$
  * **Étape 5 (Forme normale) :**
  $$x(\lambda z' . z')(x(\lambda z' . z'))$$
  
  ---
  
  > ### Forme normale (= sans rédexe)
  > Les réductions **confluent**, et la forme normale est **unique**.