- Voici la transposition complète et structurée de votre document du **Thème 0 : Statistique descriptive** au format Markdown, respectant fidèlement toutes les informations, formules et tableaux fournis.
- # FICHE DE LECTURE
  **Statistique pour ingénieur — Thème 0 : Statistique descriptive** *F. Delacroix & M. Lecomte | Institut Mines-Télécom | 30 avril 2026*
- ## 1. Informations générales
  |  |  |
  |---|---|
  | **Discipline** | Statistique pour ingénieur |
  | **Thème** | Thème 0 – Statistique descriptive |
  | **Auteurs** | F. Delacroix & M. Lecomte |
  | **Institution** | Institut Mines-Télécom |
  | **Date** | 30 avril 2026 |
  | **Niveau** | Formation d'ingénieur (niveau licence/master) |
- ## 2. Objectifs du document
  Ce poly constitue le premier thème d'un cours de statistique pour ingénieur en cinq parties. Il vise à :
  * Décrire et résumer des données à l'aide de graphiques et de paramètres numériques.
  * Introduire le vocabulaire statistique fondamental.
  * Poser les bases de la statistique descriptive, préalable à la statistique inférentielle et à la régression linéaire.
- ## 3. Plan du document
  | § | Section | Contenu principal |
  |---|---|---|
  | **1** | Vocabulaire de la statistique | Population, individu, fréquence, tableau de contingence |
  | **2** | Statistique et probabilités | Lien avec la modélisation probabiliste, théorème central limite |
  | **3** | Variables ou caractères | Qualitatif, quantitatif discret/continu, histogramme, diagrammes |
  | **4** | Loi et fonction de répartition | Distribution empirique, fonction de répartition F_X |
  | **5** | Grandeurs statistiques usuelles | Moyenne, mode, médiane, quartiles, variance, écart-type, IQ |
  | **6** | Distributions à deux caractères | Tableau de contingence, loi conjointe, loi marginale, indépendance |
  | **7** | Deux variables quantitatives | Nuage de points, covariance, coefficient de corrélation linéaire |
- ## 4. Notions et définitions clés
- ### 4.1 Vocabulaire de base
  * **Population (\Omega)** : Ensemble de référence de l'étude, constitué d'individus (unités statistiques).
  * **Variable / Caractère** : Application qui à chaque individu associe une valeur (qualitative ou quantitative).
  * **Fréquence f(E)** : Rapport \frac{\text{Card}(E)}{\text{Card}(\Omega)} \in [0 \; ; \; [span_20](start_span)1], souvent exprimé en pourcentage.
  * **Distribution empirique** : Donnée des fréquences de chaque classe ou modalité d'une variable.
- ### 4.2 Types de variables
  | Type | Définition | Représentation graphique |
  |---|---|---|
  | **Qualitative** | Appartenance à une catégorie (ex. : défectueux ou non) | Diagramme en bâtons, camembert |
  | **Quantitative discrète** | Valeurs finies ou dénombrables (ex. : nb de défauts) | Diagramme en bâtons |
  | **Quantitative continue** | Valeurs dans un intervalle de \mathbb{R} (ex. : durée de vie, diamètre) | Histogramme, fonction de répartition |
- ### 4.3 Paramètres de position
  * **Moyenne \bar{x}** : \bar{x} = \frac{1}{n} \sum x_i. Elle est sensible aux valeurs aberrantes (peu robuste) et subit les transformations affines.
  * **Mode** : Valeur (ou classe) de fréquence maximale.
  * **Médiane M_e** : Valeur qui partage la distribution en deux moitiés d'effectifs égaux. Elle est plus robuste que la moyenne.
  * **Quartiles Q_1, Q_2, Q_3** : Divisent la population en quatre parts égales de 25%. Q_2 = \text{médiane}. Ils sont obtenus par les médianes des demi-distributions.
  * **Quantiles / Déciles** : Généralisent les quartiles. Les déciles D_1 and D_9 sont les plus utilisés en pratique.
- ### 4.4 Paramètres de dispersion
  * **Étendue w** : w = x_{\max} - x_{\min}. Elle est très sensible aux valeurs extrêmes.
  * **Variance \sigma^2** : \sigma^2 = \frac{1}{n} \sum(x_i - \bar{x})^2 = \text{(moyenne des carrés)} - \text{(carré de la moyenne)}. Transformation affine : \sigma^2_Y = a^2\sigma^2_X si Y = aX + b.
  * **Écart-type \sigma** : \sigma = \sqrt{\sigma^2}. Il possède la même unité que la variable et mesure l'étalement autour de la moyenne.
  * **Distance interquartile IQ** : IQ = |Q_3 - Q_1|. Elle est plus robuste que l'étendue et est représentée par la boîte du boxplot.
- ### 4.5 Distributions à deux caractères
  * **Tableau de contingence** : Tableau à double entrée (n_{ij} individus dans la classe C_i \cap D_j) permettant d'étudier deux variables simultanément.
  * **Loi marginale** : Fréquences d'une seule variable, obtenues par sommation sur les lignes ou les colonnes.
  * **Loi conditionnelle** : f_{j/i} = \frac{n_{ij}}{n_{i\cdot}} — représente les fréquences de Y dans la sous-population \{X \in C_i\}.
  * **Indépendance** : X et Y sont indépendantes si f_{j/i} = f_{\cdot j} pour tout i, j, soit f_{ij} = f_{i\cdot} \times f_{\cdot j}.
- ### 4.6 Corrélation entre deux variables quantitatives
  * **Covariance \text{Cov}(X,Y)** : \text{Cov}(X,Y) = \frac{1}{n} \sum(x_i - \bar{x})(y_i - \bar{y}) = \text{moyenne des produits} - \text{produit des moyennes}. Son signe indique le sens de la liaison. De plus, \text{Cov}(X,X) = \mathbb{V}(X).
  * **Coefficient de corrélation r** : r(X,Y) = \frac{\text{Cov}(X,Y)}{\sigma(X) \cdot \sigma(Y)}. Il est toujours compris dans [-1 \; ; \; 1]. Une valeur |r| \ge 0,8 indique une forte corrélation. |r| [span_42](start_span)= 1 \iff relation affine exacte.
- ## 5. Propriétés essentielles à retenir
  * **Transformation affine** Y = aX + b \implies \bar{y} = a\bar{x} + b \quad \text{et} \quad \sigma^2_Y = a^2\sigma^2_X.
  * **Variance d'une somme** : \mathbb{V}(X + Y) = \mathbb{V}(X) + 2\text{Cov}(X,Y) + \mathbb{V}(Y).
  * **Inégalité de Cauchy-Schwarz** : |\text{Cov}(X,Y)| [span_45](start_span)\le \sigma(X) \cdot \sigma(Y), avec égalité si et seulement si Y = aX + b.
  * **Indépendance vs Décorrélation** : Variables indépendantes \implies décorrélées (r = 0), mais la réciproque est **FAUSSE**.
  * **Causalité** : Une corrélation, même forte, ne prouve pas une relation de cause à effet.
- ## 6. Représentations graphiques
  | Graphique | Usage | Caractéristiques |
  |---|---|---|
  | **Diagramme en bâtons** | Variable discrète / qualitative | Longueur \propto effectif ou fréquence |
  | **Diagramme circulaire** | Variable qualitative | Angle \propto fréquence |
  | **Histogramme** | Variable continue (classes) | Aire \propto effectif de la classe |
  | **Fonction de répartition F_X** | Variable quantitative (continue) | Croissante de 0 à 1, permet de lire les quantiles |
  | **Boîte à moustaches (boxplot)** | Comparaison de distributions | Montre Q_1, M_e, Q_3, D_1, D_9 et les valeurs aberrantes |
  | **Nuage de points** | Deux variables quantitatives | Visualise la forme et l'intensité de la liaison |
- ## 7. Points de vigilance
  * **Robustesse de la moyenne** : La moyenne est peu robuste : une seule valeur extrême peut la déplacer fortement. Il faut lui préférer la médiane pour les distributions asymétriques.
  * **Interprétation de l'histogramme** : L'histogramme représente des **aires** (et non des hauteurs) proportionnelles aux effectifs : attention aux classes de largeur inégale.
  * **Décorrélation vs Indépendance** : Décorrélation \neq indépendance : deux variables peuvent avoir r = 0 sans être indépendantes dans le cas d'une liaison non linéaire.
  * **Statistique inférentielle** : En statistique inférentielle, les comparaisons de lois conditionnelles nécessitent un test d'indépendance (\chi^2, cf. Thème 3).
  * **Composante saisonnière** : La composante saisonnière (exercice 3) est définie à la moyenne près : on la centre en soustrayant la moyenne des coefficients mensuels.
- ## 8. Résumé des exercices proposés
  * **Exercice 1** : Calculs de statistique descriptive sur une répartition salariés/âge/sexe. Détermination de la moyenne, médiane, quartiles, écart-type, et réalisation de boîtes à moustaches comparatives.
  * **Exercice 2** : Étude d'une corrélation taille–poids à partir d'un tableau de contingence. Analyse des lois marginales et conditionnelles, calcul de la covariance, du coefficient de corrélation et tracé de la courbe de régression.
  * **Exercice 3** : Série chronologique (chiffre d'affaires mensuel sur 3 ans). Utilisation des moyennes mobiles, décomposition tendance–saisonnalité–aléatoire, et application de la correction des variations saisonnières (CVS).
- ## 9. Contexte dans le cours global
  Ce thème 0 est le point d'entrée d'un cours structuré en cinq thèmes:
  * **Thème 0 – Statistique descriptive** *(Présent document)*
  * **Thème 1 – Probabilités** : Modélisation des phénomènes aléatoires, théorème central limite.
  * **Thème 2 – Estimation** : Généralisation à la population à partir d'un échantillon.
  * **Thème 3 – Tests statistiques** : Validation de modèles, tests d'indépendance.
  * **Thème 4 – Régression linéaire** : Modélisation de la relation entre deux variables.
-