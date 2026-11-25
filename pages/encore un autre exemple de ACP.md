- Voici un cas concret d'**Analyse en Composantes Principales (ACP)** résolu pas à pas, avec des calculs exacts.
- ### Image mentale de l'ACP
  
  Imaginez un nuage de points allongé en forme de ballon de rugby dans l'espace. Faire une ACP revient à trouver **le grand axe du ballon** : c'est la direction où les points sont les plus dispersés. Projeter les points sur cet axe, c'est comme éclairer le ballon perpendiculairement à cet axe et regarder l'ombre portée : on perd un peu d'information (l'épaisseur du ballon), mais on garde l'essentiel de sa structure.
- ### 1. Données initiales
  
  Considérons n = 4 sites observés selon p = 2 variables quantitatives :
- X_1 : indice de fréquentation du site (échelle de 1 à 5).
- X_2 : indice d'intensité opérationnelle (échelle de 1 à 5).
  
  | Site | X_1 | X_2 |
  
  | **Site A** | 1 | 2 |
  
  | **Site B** | 2 | 1 |
  
  | **Site C** | 4 | 5 |
  
  | **Site D** | 5 | 4 |
- ### 2. Centrage des données
  
  On calcule d'abord la moyenne de chaque variable :
  
  `\bar{x}_1 = \frac{1 + 2 + 4 + 5}{4} = \frac{12}{4} = 3`
  `\bar{x}_2 = \frac{2 + 1 + 5 + 4}{4} = \frac{12}{4} = 3`
  
  On centre ensuite chaque observation en soustrayant la moyenne de sa colonne (\tilde{x}_{ij} = x_{ij} - \bar{x}_j). Le nuage de points est ainsi ramené à l'origine (0, 0) :
  
  | Site | \tilde{X}_1 = X_1 - 3 | \tilde{X}_2 = X_2 - 3 |
  
  | **Site A** | -2 | -1 |
  
  | **Site B** | -1 | -2 |
  
  | **Site C** | +1 | +2 |
  
  | **Site D** | +2 | +1 |
  
  *(Note : dans ce cas, les deux variables ont la même échelle et une dispersion comparable ; on travaille donc sur les données centrées sans standardisation supplémentaire.)*
- ### 3. Matrice de variance-covariance
  
  Pour simplifier les fractions tout en conservant les mêmes directions propres, utilisons le diviseur n = 4 (la logique reste identique avec n - 1 = 3, les valeurs propres étant simplement multipliées par \frac{4}{3}) :
  
  `\text{Var}(X_1) = \frac{(-2)^2 + (-1)^2 + 1^2 + 2^2}{4} = \frac{4 + 1 + 1 + 4}{4} = 2{,}5`
  `\text{Var}(X_2) = \frac{(-1)^2 + (-2)^2 + 2^2 + 1^2}{4} = \frac{1 + 4 + 4 + 1}{4} = 2{,}5`
  `\text{Cov}(X_1, X_2) = \frac{(-2)(-1) + (-1)(-2) + (1)(2) + (2)(1)}{4} = \frac{2 + 2 + 2 + 2}{4} = 2{,}0`
  
  La matrice de variance-covariance \Sigma vaut donc :
  
  `\Sigma = \begin{pmatrix} 2{,}5 & 2{,}0 \\ 2{,}0 & 2{,}5 \end{pmatrix}`
  
  La trace de \Sigma, qui représente l'**inertie totale** (somme des variances), est :
  
  `\text{tr}(\Sigma) = 2{,}5 + 2{,}5 = 5{,}0`
- ### 4. Valeurs propres et part de variance expliquée
  
  On résout l'équation caractéristique \det(\Sigma - \lambda I) = 0 :
  
  `(2{,}5 - \lambda)^2 - 2{,}0^2 = 0`
  
  En factorisant cette différence de deux carrés :
  
  `\bigl((2{,}5 - \lambda) - 2{,}0\bigr)\bigl((2{,}5 - \lambda) + 2{,}0\bigr) = (0{,}5 - \lambda)(4{,}5 - \lambda) = 0`
  
  On obtient deux valeurs propres :
- `\lambda_1 = 4{,}5`
- `\lambda_2 = 0{,}5`
  
  On vérifie bien \lambda_1 + \lambda_2 = 5{,}0. La part d'inertie expliquée par chaque axe principal est :
- **Axe 1** : \frac{4{,}5}{5{,}0} = 0{,}90, soit **90\ \%** de la variance totale.
- **Axe 2** : \frac{0{,}5}{5{,}0} = 0{,}10, soit **10\ \%** de la variance totale.
- ### 5. Vecteurs propres (axes principaux)
  
  Chaque vecteur propre u_k de norme unitaire (\Vert{}u_k\Vert{}_2 = 1) donne la direction d'un axe principal.
- #### Premier axe (\lambda_1 = 4{,}5)
  
  On résout (\Sigma - 4{,}5 I) u_1 = 0 :
  
  `\begin{pmatrix} -2{,}0 & 2{,}0 \\ 2{,}0 & -2{,}0 \end{pmatrix} \begin{pmatrix} a \\ b \end{pmatrix} = \begin{pmatrix} 0 \\ 0 \end{pmatrix} \implies a = b`
  
  En normalisant pour avoir a^2 + b^2 = 1 :
  
  `u_1 = \begin{pmatrix} \frac{1}{\sqrt{2}} \\ \frac{1}{\sqrt{2}} \end{pmatrix} \approx \begin{pmatrix} 0{,}707 \\ 0{,}707 \end{pmatrix}`
- #### Deuxième axe (\lambda_2 = 0{,}5)
  
  On résout (\Sigma - 0{,}5 I) u_2 = 0 :
  
  `\begin{pmatrix} 2{,}0 & 2{,}0 \\ 2{,}0 & 2{,}0 \end{pmatrix} \begin{pmatrix} c \\ d \end{pmatrix} = \begin{pmatrix} 0 \\ 0 \end{pmatrix} \implies d = -c`
  
  En normalisant pour avoir c^2 + d^2 = 1 :
  
  `u_2 = \begin{pmatrix} \frac{1}{\sqrt{2}} \\ -\frac{1}{\sqrt{2}} \end{pmatrix} \approx \begin{pmatrix} 0{,}707 \\ -0{,}707 \end{pmatrix}`
  
  Les deux vecteurs sont orthogonaux (u_1^\top u_2 = 0), ce qui garantit des composantes non corrélées.
- ### 6. Coordonnées des individus sur les axes (scores)
  
  Pour chaque site i, on projette le vecteur centré \tilde{x}_i = (\tilde{x}_{i1}, \tilde{x}_{i2}) sur u_1 et u_2 :
- **Site A** (-2, -1) :
	- `F_{1,A} = -2 \cdot \frac{1}{\sqrt{2}} - 1 \cdot \frac{1}{\sqrt{2}} = -\frac{3}{\sqrt{2}} \approx -2{,}12`
	- `F_{2,A} = -2 \cdot \frac{1}{\sqrt{2}} - 1 \cdot \left(-\frac{1}{\sqrt{2}}\right) = -\frac{1}{\sqrt{2}} \approx -0{,}71`
- **Site B** (-1, -2) :
	- `F_{1,B} = -1 \cdot \frac{1}{\sqrt{2}} - 2 \cdot \frac{1}{\sqrt{2}} = -\frac{3}{\sqrt{2}} \approx -2{,}12`
	- `F_{2,B} = -1 \cdot \frac{1}{\sqrt{2}} - 2 \cdot \left(-\frac{1}{\sqrt{2}}\right) = +\frac{1}{\sqrt{2}} \approx +0{,}71`
- **Site C** (+1, +2) :
	- `F_{1,C} = 1 \cdot \frac{1}{\sqrt{2}} + 2 \cdot \frac{1}{\sqrt{2}} = +\frac{3}{\sqrt{2}} \approx +2{,}12`
	- `F_{2,C} = 1 \cdot \frac{1}{\sqrt{2}} + 2 \cdot \left(-\frac{1}{\sqrt{2}}\right) = -\frac{1}{\sqrt{2}} \approx -0{,}71`
- **Site D** (+2, +1) :
	- `F_{1,D} = 2 \cdot \frac{1}{\sqrt{2}} + 1 \cdot \frac{1}{\sqrt{2}} = +\frac{3}{\sqrt{2}} \approx +2{,}12`
	- `F_{2,D} = 2 \cdot \frac{1}{\sqrt{2}} + 1 \cdot \left(-\frac{1}{\sqrt{2}}\right) = +\frac{1}{\sqrt{2}} \approx +0{,}71`
	  
	  Récapitulatif des coordonnées factorielles :
	  
	  | Site | Composante F_1 (90\ \%) | Composante F_2 (10\ \%) |
	  
	  | **Site A** | -2{,}12 | -0{,}71 |
	  
	  | **Site B** | -2{,}12 | +0{,}71 |
	  
	  | **Site C** | +2{,}12 | -0{,}71 |
	  
	  | **Site D** | +2{,}12 | +0{,}71 |
- ### 7. Interprétation concrète
- **Axe 1 (90\ \% de l'inertie) — Niveau global d'activité** : les deux composantes de u_1 ont le même signe positif. Cet axe oppose les sites à faible activité globale (**A** et **B**, à -2{,}12) aux sites à forte activité globale (**C** et **D**, à +2{,}12). Si l'on ne conserve qu'une seule dimension, 90\ \% de la dispersion initiale est préservée.
- **Axe 2 (10\ \% de l'inertie) — Contraste entre X_1 et X_2** : les composantes de u_2 sont de signes opposés (+0{,}707 pour X_1 et -0{,}707 pour X_2). Cet axe capte la différence relative entre les deux variables : **B** et **D** (+0{,}71) ont un léger avantage de X_1 sur X_2, tandis que **A** et **C** (-0{,}71) ont un léger avantage de X_2 sur X_1.