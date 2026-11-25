- L'Analyse Factorielle des Correspondances (AFC) étudie l'association entre deux variables qualitatives croisées dans un tableau de contingence.
- **Image mentale** : Imaginez un mobile suspendu au plafond (le centre de gravité, qui représente l'indépendance parfaite entre les variables). Chaque branche porte des poids proportionnels aux effectifs des modalités. L'AFC cherche les axes d'équilibre principaux (les tiges du mobile) qui résument au mieux l'écart par rapport à cet équilibre neutre.
- Prenons un exemple simple et exact (sans arrondis excessifs) sur N = 100 individus croisant deux variables :
	- **Variable ligne X** : Mode de transport principal (`Vélo`, `Transport en commun`, `Voiture`).
	- **Variable colonne Y** : Type de zone résidentielle (`Centre-ville`, `Périphérie`).
-
- 1. Tableau de contingence (K) et effectifs marginaux
	- Voici les effectifs observés k_{ij} pour N = 100 usagers :
	  
	  | Transport \ Zone | Centre-ville (j=1) | Périphérie (j=2) | Total ligne (k_{i\bullet}) |
	  
	  | **Vélo (i=1)** | 30 | 10 | **40** |
	  
	  | **Transports (i=2)** | 15 | 15 | **30** |
	  
	  | **Voiture (i=3)** | 5 | 25 | **30** |
	  
	  | **Total colonne (k_{\bullet j})** | **50** | **50** | **N = 100** |
-
- 2. Passage aux fréquences (F) et profils
	- On divise chaque case par N = 100 pour obtenir la matrice des fréquences relatives f_{ij} = \frac{k_{ij}}{N} et les poids marginaux f_{i\bullet} et f_{\bullet j}.
	- **Matrice des fréquences F :**
	  
	  | Transport \ Zone | Centre-ville | Périphérie | Masse ligne (f_{i\bullet}) |
	  
	  | **Vélo** | 0.30 | 0.10 | **0.40** |
	  
	  | **Transports** | 0.15 | 0.15 | **0.30** |
	  
	  | **Voiture** | 0.05 | 0.25 | **0.30** |
	  
	  | **Masse colonne (f_{\bullet j})** | **0.50** | **0.50** | **1.00** |
	- **Calcul des profils-lignes (L) :**
		- Chaque ligne est divisée par sa marge f_{i\bullet}. Un profil-ligne donne la répartition conditionnelle P(Y=j \mid X=i).
		- **Vélo** : \left(\frac{0.30}{0.40} ; \frac{0.10}{0.40}\right) = (0.75 ; 0.25)
		- **Transports** : \left(\frac{0.15}{0.30} ; \frac{0.15}{0.30}\right) = (0.50 ; 0.50)
		- **Voiture** : \left(\frac{0.05}{0.30} ; \frac{0.25}{0.30}\right) = \left(\frac{1}{6} ; \frac{5}{6}\right) \approx (0.167 ; 0.833)
		- **Profil moyen (centre de gravité G)** : (f_{\bullet 1} ; f_{\bullet 2}) = (0.50 ; 0.50).
		- *Observation directe* : Le profil des transports en commun est identique au profil moyen (0.50 ; 0.50). Ce point sera exactement sur l'origine du repère factoriel.
-
- 3. Test d'indépendance (\chi^2) et inertie totale (\Phi^2)
	- Avant de projeter les points, on vérifie qu'il existe un lien significatif à l'aide de la distance du \chi^2.
	- **Effectifs théoriques sous indépendance (e_{ij} = \frac{k_{i\bullet} \times k_{\bullet j}}{N}) :**
		- Vélo : \frac{40 \times 50}{100} = 20 (Centre) et 20 (Périphérie).
		- Transports : \frac{30 \times 50}{100} = 15 (Centre) et 15 (Périphérie).
		- Voiture : \frac{30 \times 50}{100} = 15 (Centre) et 15 (Périphérie).
	- **Calcul de la statistique du \chi^2 :**
	  `\chi^2 = \sum_{i,j} \frac{(k_{ij} - e_{ij})^2}{e_{ij}}`
	  `\chi^2 = \frac{(30-20)^2}{20} + \frac{(10-20)^2}{20} + \frac{(15-15)^2}{15} + \frac{(15-15)^2}{15} + \frac{(5-15)^2}{15} + \frac{(25-15)^2}{15}`
	  `\chi^2 = \frac{100}{20} + \frac{100}{20} + 0 + 0 + \frac{100}{15} + \frac{100}{15} = 5 + 5 + 6.67 + 6.67 = 23.33`
	- **Inertie totale du nuage (\Phi^2) :**
	  `\Phi^2 = \frac{\chi^2}{N} = \frac{23.333}{100} = 0.2333`
	- Le nombre maximum d'axes factoriels non triviaux est \min(I - 1, J - 1) = \min(3 - 1, 2 - 1) = 1.
	- **Conclusion dimensionnelle** : Un seul axe factoriel (Axe 1) suffit à expliquer **100 %** de l'inertie totale (\lambda_1 = \Phi^2 = 0.2333).
-
- 4. Diagonalisation et calcul des coordonnées factorielles
	- **Image mentale** : Puisqu'il n'y a que deux colonnes (J=2), tous les profils-lignes sont situés sur une seule droite reliant les deux pôles (Centre-ville et Périphérie). L'AFC consiste simplement à centrer cette droite sur G(0.50 ; 0.50) et à dilater l'échelle selon la métrique du \chi^2.
	- **Matrice des écarts à l'indépendance centrés et pondérés (S) :**
		- Le terme général de la matrice à décomposer en valeurs singulières est :
		  `s_{ij} = \frac{f_{ij} - f_{i\bullet}f_{\bullet j}}{\sqrt{f_{i\bullet} f_{\bullet j}}}`
		- Calculons chaque terme (sachant que \sqrt{f_{\bullet j}} = \sqrt{0.50} = \frac{1}{\sqrt{2}}) :
		- Pour **Vélo** (\sqrt{f_{1\bullet}} = \sqrt{0.40}) :
		  `s_{11} = \frac{0.30 - (0.40 \times 0.50)}{\sqrt{0.40 \times 0.50}} = \frac{0.10}{\sqrt{0.20}} = \frac{0.10}{0.4472} \approx +0.2236`
		  `s_{12} = \frac{0.10 - 0.20}{\sqrt{0.20}} = -0.2236`
		- Pour **Transports** (\sqrt{f_{2\bullet}} = \sqrt{0.30}) :
		  `s_{21} = \frac{0.15 - 0.15}{\sqrt{0.15}} = 0 \quad \text{et} \quad s_{22} = 0`
		- Pour **Voiture** (\sqrt{f_{3\bullet}} = \sqrt{0.30}) :
		  `s_{31} = \frac{0.05 - 0.15}{\sqrt{0.30 \times 0.50}} = \frac{-0.10}{\sqrt{0.15}} = \frac{-0.10}{0.3873} \approx -0.2582`
		  `s_{32} = \frac{0.25 - 0.15}{\sqrt{0.15}} = +0.2582`
	- **Valeur propre (\lambda_1) et vecteurs propres :**
		- On forme la matrice carrée M = S^T S (dimension 2 \times 2) :
		  `M = \begin{pmatrix} 0.2236^2 + 0^2 + (-0.2582)^2 & -0.2236^2 + 0 - 0.2582^2 \\ -0.2236^2 + 0 - 0.2582^2 & (-0.2236)^2 + 0^2 + 0.2582^2 \end{pmatrix} = \begin{pmatrix} 0.1167 & -0.1167 \\ -0.1167 & 0.1167 \end{pmatrix}`
		- La trace de M vaut 0.1167 + 0.1167 = 0.2333 = \lambda_1.
		- Le vecteur propre normé associé à \lambda_1 = 0.2333 est :
		  `u_1 = \begin{pmatrix} \frac{1}{\sqrt{2}} \\ -\frac{1}{\sqrt{2}} \end{pmatrix} \approx \begin{pmatrix} +0.7071 \\ -0.7071 \end{pmatrix}`
	- **Coordonnées factorielles des colonnes (G_1(j)) :**
		- Formule de projection : G_1(j) = \frac{\sqrt{\lambda_1}}{\sqrt{f_{\bullet j}}} u_{1j}.
		- **Centre-ville (j=1)** : G_1(1) = \frac{\sqrt{0.2333}}{\sqrt{0.50}} \times \left(+\frac{1}{\sqrt{2}}\right) = \frac{0.4830}{0.7071} \times 0.7071 = \mathbf{+0.4830}
		- **Périphérie (j=2)** : G_1(2) = \frac{\sqrt{0.2333}}{\sqrt{0.50}} \times \left(-\frac{1}{\sqrt{2}}\right) = \mathbf{-0.4830}
	- **Coordonnées factorielles des lignes (F_1(i)) par relation quasi-barycentrique :**
		- Chaque modalité ligne se place au barycentre des modalités colonnes pondérées par son profil, divisé par \sqrt{\lambda_1} :
		  `F_1(i) = \frac{1}{\sqrt{\lambda_1}} \sum_{j=1}^{2} \frac{f_{ij}}{f_{i\bullet}} G_1(j)`
		- **Vélo (i=1)** :
		  `F_1(1) = \frac{1}{0.4830} \times \left[ (0.75 \times 0.4830) + (0.25 \times (-0.4830)) \right] = 0.75 - 0.25 = \mathbf{+0.5000}`
		- **Transports (i=2)** :
		  `F_1(2) = \frac{1}{0.4830} \times \left[ (0.50 \times 0.4830) + (0.50 \times (-0.4830)) \right] = 0.50 - 0.50 = \mathbf{0.0000}`
		- **Voiture (i=3)** :
		  `F_1(3) = \frac{1}{0.4830} \times \left[ \left(\frac{1}{6} \times 0.4830\right) + \left(\frac{5}{6} \times (-0.4830)\right) \right] = \frac{1}{6} - \frac{5}{6} = -\frac{4}{6} = \mathbf{-0.6667}`
-
- 5. Aides à l'interprétation (CTR et \cos^2)
	- Pour valider la lecture graphique, on calcule deux indicateurs essentiels :
		- **La contribution (CTR_1(i))** : Part de l'inertie de l'axe expliquée par le point i.
		  `CTR_1(i) = \frac{f_{i\bullet} \times F_1(i)^2}{\lambda_1}`
		- **La qualité de représentation (\cos^2_1(i))** : Puisqu'il n'y a qu'un seul axe, toute l'inertie du point est portée par cet axe, donc \cos^2_1(i) = 1 (ou 100\%) pour tous les points non nuls.
	- **Tableau récapitulatif des résultats :**
	  
	  | Modalité | Masse (f) | Coordonnée (F_1 ou G_1) | Contribution (CTR_1) | Qualité (\cos^2_1) |
	  
	  | **Vélo** | 0.40 | +0.5000 | \frac{0.40 \times 0.50^2}{0.2333} = \mathbf{42.9\%} | 1.00 |
	  
	  | **Transports** | 0.30 | 0.0000 | \frac{0.30 \times 0^2}{0.2333} = \mathbf{0.0\%} | — |
	  
	  | **Voiture** | 0.30 | -0.6667 | \frac{0.30 \times (-0.6667)^2}{0.2333} = \mathbf{57.1\%} | 1.00 |
	  
	  | *Centre-ville* | 0.50 | +0.4830 | \frac{0.50 \times 0.4830^2}{0.2333} = \mathbf{50.0\%} | 1.00 |
	  
	  | *Périphérie* | 0.50 | -0.4830 | \frac{0.50 \times (-0.4830)^2}{0.2333} = \mathbf{50.0\%} | 1.00 |
-
- 6. Synthèse et lecture du graphique factoriel
	- **Signification de l'Axe 1 (100 % de l'inertie)** : Il oppose l'usage urbain dense (à droite, coordonnées positives) à l'usage périurbain (à gauche, coordonnées négatives).
	- **Construction de l'axe** : L'opposition est portée à **100 %** par le couple **Voiture** (CTR = 57.1\%) et **Vélo** (CTR = 42.9\%). Bien que le vélo ait une masse plus importante (0.40 contre 0.30), la voiture contribue davantage car son profil est plus fortement excentré par rapport à la moyenne (-0.6667 contre +0.5000).
	- **Proximités et attractions** :
		- **Vélo** (+0.50) et **Centre-ville** (+0.48) sont situés du même côté de l'axe : les cyclistes sont nettement surreprésentés en centre-ville (75\% contre 50\% dans la population globale).
		- **Voiture** (-0.67) et **Périphérie** (-0.48) s'attirent fortement du côté négatif.
		- **Transports en commun** (0.00) se situe au barycentre : sa répartition entre centre-ville et périphérie suit exactement la distribution globale de l'échantillon.
-
- ## retour en détail du calcul calcul du vecteur u1
- Pour obtenir le vecteur propre u_1, on cherche les directions principales de la matrice symétrique M = S^T S (dimension 2 \times 2).
- **Image mentale** : Chercher un vecteur propre d'une matrice 2 \times 2, c'est trouver une direction dans le plan qui n'est pas déviée lorsque la matrice lui est appliquée : le vecteur est simplement étiré ou contracté d'un facteur égal à la valeur propre \lambda.
- ### 1. Rappel de la matrice M
- À partir de la matrice des écarts pondérés S :
  `S = \begin{pmatrix} +0.2236 & -0.2236 \\ 0 & 0 \\ -0.2582 & +0.2582 \end{pmatrix}`
- On calcule M = S^T S (en gardant les fractions exactes pour éviter les erreurs d'arrondi) :
	- `s_{11}^2 = \left(\frac{0.10}{\sqrt{0.20}}\right)^2 = \frac{0.01}{0.20} = 0.05 = \frac{1}{20}`
	- `s_{31}^2 = \left(\frac{-0.10}{\sqrt{0.15}}\right)^2 = \frac{0.01}{0.15} = \frac{1}{15}`
	- Somme des carrés : \frac{1}{20} + 0 + \frac{1}{15} = \frac{3 + 4}{60} = \frac{7}{60} \approx 0.1167
- La matrice M s'écrit donc exactement :
  `M = \begin{pmatrix} \frac{7}{60} & -\frac{7}{60} \\ -\frac{7}{60} & \frac{7}{60} \end{pmatrix} = \frac{7}{60} \begin{pmatrix} 1 & -1 \\ -1 & 1 \end{pmatrix}`
- ### 2. Calcul des valeurs propres (\lambda)
- On résout l'équation caractéristique \det(M - \lambda I) = 0 :
  `\det \begin{pmatrix} \frac{7}{60} - \lambda & -\frac{7}{60} \\ -\frac{7}{60} & \frac{7}{60} - \lambda \end{pmatrix} = 0`
- On développe le déterminant (ad - bc = 0) :
  `\left(\frac{7}{60} - \lambda\right)^2 - \left(-\frac{7}{60}\right)^2 = 0`
- C'est une identité remarquable de la forme A^2 - B^2 = (A - B)(A + B) = 0 :
  `\left(\frac{7}{60} - \lambda - \frac{7}{60}\right) \left(\frac{7}{60} - \lambda + \frac{7}{60}\right) = 0`
  `(-\lambda) \left(\frac{14}{60} - \lambda\right) = 0`
- On obtient deux solutions (les deux valeurs propres) :
	- \lambda_1 = \frac{14}{60} = \frac{7}{30} \approx \mathbf{0.2333} (valeur propre non nulle retenue)
	- \lambda_2 = \mathbf{0} (valeur propre triviale liée à la contrainte de somme des fréquences égale à 1)
- ### 3. Résolution du système pour trouver le vecteur propre v_1
- Un vecteur propre v_1 = \begin{pmatrix} x \\ y \end{pmatrix} associé à \lambda_1 = \frac{7}{30} vérifie la relation :
  `M v_1 = \lambda_1 v_1 \iff (M - \lambda_1 I) v_1 = \begin{pmatrix} 0 \\ 0 \end{pmatrix}`
- On remplace \lambda_1 par \frac{14}{60} dans la matrice :
  `\begin{pmatrix} \frac{7}{60} - \frac{14}{60} & -\frac{7}{60} \\ -\frac{7}{60} & \frac{7}{60} - \frac{14}{60} \end{pmatrix} \begin{pmatrix} x \\ y \end{pmatrix} = \begin{pmatrix} 0 \\ 0 \end{pmatrix}`
  `\begin{pmatrix} -\frac{7}{60} & -\frac{7}{60} \\ -\frac{7}{60} & -\frac{7}{60} \end{pmatrix} \begin{pmatrix} x \\ y \end{pmatrix} = \begin{pmatrix} 0 \\ 0 \end{pmatrix}`
- Les deux lignes donnent la même équation linéaire :
  `-\frac{7}{60} x - \frac{7}{60} y = 0 \iff x + y = 0 \iff \mathbf{y = -x}`
- Tous les vecteurs de la forme \begin{pmatrix} x \\ -x \end{pmatrix} (avec x \neq 0) sont donc des vecteurs propres associés à \lambda_1. Prenons le représentant le plus simple en posant x = 1 :
  `v_1 = \begin{pmatrix} 1 \\ -1 \end{pmatrix}`
- ### 4. Normalisation pour obtenir le vecteur unitaire u_1
- En AFC, les vecteurs propres doivent être **normés** (de longueur euclidienne égale à 1, soit \Vert{}u_1\Vert{} = 1).
- On calcule la norme euclidienne de v_1 :
  `\Vert{}v_1\Vert{} = \sqrt{x^2 + y^2} = \sqrt{1^2 + (-1)^2} = \sqrt{2}`
- On divise chaque composante de v_1 par sa norme \Vert{}v_1\Vert{} :
  `u_1 = \frac{v_1}{\Vert{}v_1\Vert{}} = \frac{1}{\sqrt{2}} \begin{pmatrix} 1 \\ -1 \end{pmatrix} = \begin{pmatrix} +\frac{1}{\sqrt{2}} \\ -\frac{1}{\sqrt{2}} \end{pmatrix} \approx \begin{pmatrix} +0.7071 \\ -0.7071 \end{pmatrix}`
- **Remarque sur le signe** : Si l'on avait choisi x = -1 à l'étape 3, on aurait obtenu u_1 = \begin{pmatrix} -0.7071 \\ +0.7071 \end{pmatrix}, ce qui est tout aussi valide et explique pourquoi R peut inverser l'orientation gauche/droite du graphique.