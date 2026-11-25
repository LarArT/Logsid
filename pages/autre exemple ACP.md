- Dans **Logseq**, le moteur KaTeX rencontre fréquemment des problèmes de rendu avec :
- L'environnement `\begin{pmatrix} ... \end{pmatrix}` (le séparateur de ligne `\\` à l'intérieur d'un bloc est parfois interprété comme un saut de ligne Markdown). Il faut le remplacer par `\begin{bmatrix} ... \end{bmatrix}` ou par une écriture en ligne / vecteur transposé `^\top`, ou encore échapper les doubles antislashs.
- Les espaces fines LaTeX comme `\,` (dans `86,06\,\%`) ou les accents dans `\text{...}` qui font échouer le parseur.
- Les blocs `$$ ... $$` qui doivent impérativement être isolés sur leur propre ligne (avec un saut de ligne à l'intérieur du même bloc Logseq, via `Shift + Entrée`).
  
  Voici la version corrigée, testée pour un affichage KaTeX sans erreur dans Logseq :
- **ACP à la main : recherche du premier axe principal**
	- **Image mentale** : imaginez trois points sur une feuille. On place d'abord l'origine (0,0) au centre de gravité du triangle, puis on fait pivoter la feuille pour aligner l'axe horizontal avec la plus grande longueur du triangle.
	- **Données brutes**
		- Individu 1 : X_1 = 2, X_2 = 3
		- Individu 2 : X_1 = 4, X_2 = 5
		- Individu 3 : X_1 = 6, X_2 = 4
	- **Étape 1 : Centrer les données**
		- Moyennes : \bar{x}_1 = \frac{2+4+6}{3} = 4 et \bar{x}_2 = \frac{3+5+4}{3} = 4.
		- Matrice centrée X :
		  `X = \left[\begin{array}{cc} -2 & -1 \\ 0 & 1 \\ 2 & 0 \end{array}\right]`
	- **Étape 2 : Construire la matrice de variance-covariance S**
		- Pondération uniforme : \frac{1}{n} = \frac{1}{3}.
		- Variances et covariance :
			- `\mathrm{Var}(X_1) = \frac{(-2)^2 + 0^2 + 2^2}{3} = \frac{8}{3}`
			- `\mathrm{Var}(X_2) = \frac{(-1)^2 + 1^2 + 0^2}{3} = \frac{2}{3}`
			- `\mathrm{Cov}(X_1, X_2) = \frac{(-2)(-1) + (0)(1) + (2)(0)}{3} = \frac{2}{3}`
		- Matrice S = \frac{1}{3} X^\top X :
		  `S = \frac{1}{3} \left[\begin{array}{cc} 8 & 2 \\ 2 & 2 \end{array}\right]`
	- **Étape 3 : Calculer les valeurs propres**
		- On pose M = 3S = \left[\begin{array}{cc} 8 & 2 \\ 2 & 2 \end{array}\right] pour travailler sur des entiers, puis on divisera par 3.
		- Trace et déterminant : \mathrm{tr}(M) = 10 et \det(M) = 16 - 4 = 12.
		- Polynôme caractéristique : \mu^2 - 10\mu + 12 = 0.
		- Discriminant : \Delta = 10^2 - 4(1)(12) = 52, soit \sqrt{\Delta} = 2\sqrt{13}.
		- Valeurs propres de M : \mu_1 = 5 + \sqrt{13} \approx 8,606 et \mu_2 = 5 - \sqrt{13} \approx 1,394.
		- Valeurs propres de S :
			- `\lambda_1 = \frac{5 + \sqrt{13}}{3} \approx 2,869`
			- `\lambda_2 = \frac{5 - \sqrt{13}}{3} \approx 0,465`
		- Part d'inertie de l'axe 1 : \frac{\lambda_1}{\lambda_1 + \lambda_2} = \frac{5 + \sqrt{13}}{10} \approx 86,06\%
	- **Étape 4 : Déterminer le premier axe principal normé u_1**
		- Système (M - \mu_1 I) \left[\begin{array}{c} x \\ y \end{array}\right] = \left[\begin{array}{c} 0 \\ 0 \end{array}\right].
		- Première ligne : (3 - \sqrt{13})x + 2y = 0, d'où y = \frac{\sqrt{13} - 3}{2}x.
		- Vecteur directeur pour x = 2 :
		  `v_1 = \left[\begin{array}{c} 2 \\ \sqrt{13} - 3 \end{array}\right] \approx \left[\begin{array}{c} 2 \\ 0,606 \end{array}\right]`
		- Norme euclidienne : \Vert{}v_1\Vert{}_2 = \sqrt{4 + (13 - 6\sqrt{13} + 9)} = \sqrt{26 - 6\sqrt{13}} \approx 2,090.
		- Vecteur unitaire u_1 :
		  `u_1 = \frac{1}{\sqrt{26 - 6\sqrt{13}}} \left[\begin{array}{c} 2 \\ \sqrt{13} - 3 \end{array}\right] \approx \left[\begin{array}{c} 0,957 \\ 0,290 \end{array}\right]`
	- **Étape 5 : Calculer les coordonnées projetées C_1**
		- Projection par C_1 = X u_1 :
		  `C_1 = \left[\begin{array}{cc} -2 & -1 \\ 0 & 1 \\ 2 & 0 \end{array}\right] \left[\begin{array}{c} 0,957 \\ 0,290 \end{array}\right] \approx \left[\begin{array}{c} -2,204 \\ 0,290 \\ 1,914 \end{array}\right]`
		- Vérifications :
			- Somme des coordonnées : -2,204 + 0,290 + 1,914 = 0.
			- Variance projetée : \frac{(-2,204)^2 + 0,290^2 + 1,914^2}{3} \approx 2,868 \approx \lambda_1.