- Voici la transposition complète et structurée de votre document au format Markdown, respectant scrupuleusement les informations et les formules fournies.
- # FICHE DE LECTURE
  **Statistique pour ingénieur — Thème 1 : Notions de probabilités** *D. Pastor, F.-X. Socheleau & C. Garnier | Institut Mines-Télécom | 6 mai 2026*
- ## 1. Informations générales
  |  |  |
  |---|---|
  | **Discipline** | Statistique pour ingénieur |
  | **Thème** | Thème 1 – Notions de probabilités |
  | **Auteurs** | D. Pastor, F.-X. Socheleau & C. Garnier |
  | **Institution** | Institut Mines-Télécom |
  | **Date** | 6 mai 2026 |
  | **Niveau** | Formation d'ingénieur (niveau licence/master) |
  | **Prérequis** | Thème 0 – Statistique descriptive |
- ## 2. Objectifs du document
  Ce thème pose les fondements mathématiques de la théorie des probabilités nécessaires à la statistique inférentielle. Il vise à :
  * Formaliser la notion d'expérience aléatoire et de mesure de probabilité (axiomatique de Kolmogorov).
  * Définir la variable aléatoire, sa loi, sa fonction de répartition et sa densité.
  * Introduire les moments (espérance, variance) et les lois usuelles (Bernoulli, binomiale, Poisson, uniforme, normale).
  * Étudier les couples de variables aléatoires : loi conjointe, lois marginales, lois conditionnelles, indépendance, covariance.
  * Établir les modes de convergence de suites de variables aléatoires, en particulier la loi des grands nombres et le théorème central-limite.
- ## 3. Plan du document
  | § | Section | Contenu principal |
  |---|---|---|
  | **1** | Introduction | Motivation historique, modélisation du hasard |
  | **2** | Modèles probabilistes | Axiomatique de Kolmogorov, probabilité conditionnelle, formule de Bayes, indépendance |
  | **3** | Variables aléatoires | Définitions, fonction de répartition, densité, changements de variables, moments, lois usuelles |
  | **4** | Couples de variables aléatoires | Loi conjointe, lois marginales, lois conditionnelles, indépendance, covariance, corrélation |
  | **5** | Convergences | Convergence en loi (TCL), en probabilité (loi des grands normes), en moyenne quadratique, presque sûre |
  | **6** | Exercices | 5 exercices applicatifs (spams, durée de vie, consommation, vecteur gaussien, TCL) |
- ## 4. Notions et définitions clés
- ### 4.1 Espace probabilisé (Axiomatique de Kolmogorov)
  * **Univers \Omega** : Ensemble de tous les résultats possibles d'une expérience aléatoire (espace des états).
  * **Tribu \mathcal{T}** : Ensemble de parties de \Omega stable par complémentaire et par union dénombrable, contenant \Omega. Ses éléments sont les événements.
  * **Espace probabilisé** : Triplet (\Omega, \mathcal{T}, P) avec P : \mathcal{T} \to [0,1] vérifiant P(\Omega) = 1 et la \sigma-additivité (P d'une union d'événements disjoints = somme des probabilités).
  * **Probabilité conditionnelle** : P(B|A) = \frac{P(A \cap B)}{P(A)} (Axiome de Bayes). Requiert P(A) \neq 0.
  * **Formule de Bayes** : Calcul des probabilités a posteriori:
   
  * **Indépendance d'événements** : A et B indépendants \iff P(A \cap B) = P(A) \cdot P(B) \iff P(A|B) = P(A) (si P(B) \neq 0).
- ### 4.2 Variables aléatoires
  * **Variable aléatoire (v.a.)** : Application mesurable X : \Omega \to \mathbb{R}. L'image réciproque de tout intervalle borélien appartient à \mathcal{T}.
  * **Loi de probabilité P_X** : Probabilité image de P par X : P_X(B) = P(X \in B) pour tout borélien B.
  * **Fonction de répartition F_X** : F_X(x) = P(X \le x). Toujours croissante, continue à droite, limites 0 en -\infty et 1 en +\infty.
  * **Densité de probabilité f_X** : Si elle existe, X est dite absolument continue:
   
  * **V.a. discrète** : X(\Omega) fini ou dénombrable. Entièrement caractérisée par les P(X = x_i).
  * **V.a. absolument continue** : X(\Omega) = \mathbb{R} ou un intervalle, et X admet une densité. P(X = a) = 0 pour tout a.
- ### 4.3 Moments
  * **Moment d'ordre k** : \mathbb{E}(X^k) = \sum_i x_i^k P(X=x_i) (discret) ou \int_{-\infty}^{+\infty} x^k f_X(x) \, dx (continu). Existe si \mathbb{E}(|X^k|) < +\infty.
  * **Espérance \mathbb{E}(X)** : Moment d'ordre 1 — paramètre de centralité. Linéaire : \mathbb{E}(aX+b) = a\mathbb{E}(X)+b.
  * **Variance \mathbb{V}(X)** : \mathbb{V}(X) = \mathbb{E}((X-\mathbb{E}(X))^2) = \mathbb{E}(X^2) - \mathbb{E}^2(X). Transformation affine : \mathbb{V}(aX+b) = a^2\mathbb{V}(X).
  * **Théorème de transfert** : \mathbb{E}(g(X)) = \sum_i g(x_i)P(X=x_i) ou \int_{-\infty}^{+\infty} g(x)f_X(x) \, dx. Permet de calculer l'espérance d'une fonction de X sans connaître la loi de g(X).
- ### 4.4 Lois usuelles
  | Loi | Notation | P(X=k) ou f_X(x) | \mathbb{E}(X) | \mathbb{V}(X) |
  |---|---|---|---|---|
  | **Bernoulli** | \mathcal{B}(1;p) | P(X=1)=p, \quad P(X=0)=1-p | p | p(1-p) |
  | **Géométrique** | \mathcal{G}(p) | P(X=k) = (1-p)^{k-1} p | \frac{1}{p} | \frac{1-p}{p^2} |
  | **Binomiale** | \mathcal{B}(n;p) | P(X=k) = C(n,k) p^k(1-p)^{n-k} | np | np(1-p) |
  | **Poisson** | \mathcal{P}(\lambda) | P(X=k) = \frac{e^{-\lambda} \lambda^k}{k!} | \lambda | \lambda |
  | **Uniforme** | \mathcal{U}([a,b]) | f_X(x) = \frac{1}{b-a} sur [a,b] | \frac{a+b}{2} | \frac{(b-a)^2}{12} |
  | **Normale** | \mathcal{N}(\mu;\sigma^2) | f_X(x) = \frac{1}{\sqrt{2\pi\sigma^2}} \exp\left(-\frac{(x-\mu)^2}{2\sigma^2}\right) | \mu | \sigma^2 |
- ### 4.5 Couples de variables aléatoires
  * **Loi conjointe P_{X,Y}** : P_{X,Y}(C) = P((X,Y) \in C). Caractérisée par F_{X,Y}(x,y) = P(X \le x, Y \le y).
  * **Densité conjointe f_{X,Y}** : Si (X,Y) absolument continu : F_{X,Y}(x,y) = \int_{-\infty}^{x}\int_{-\infty}^{y} f_{X,Y}(u,v) \, du \, dv.
  * **Lois marginales** : f_X(x) = \int_{-\infty}^{+\infty} f_{X,Y}(x,y) \, dy et f_Y(y) = \int_{-\infty}^{+\infty} f_{X,Y}(x,y) \, dx. Les lois marginales ne suffisent **PAS** à retrouver la loi conjointe.
  * **Densité conditionnelle** : f_{Y|X=x}(y) = \frac{f_{X,Y}(x,y)}{f_X(x)} (si f_X(x) \neq 0).
  * **Espérance conditionnelle** : \mathbb{E}(Y|X=x) = \int_{-\infty}^{+\infty} y f_{Y|X=x}(y) \, dy. Règle des espérances itérées : \mathbb{E}(Y) = \int_{-\infty}^{+\infty} \mathbb{E}(Y|X=x) f_X(x) \, dx.
  * **Indépendance de v.a.** : X et Y indépendantes \iff F_{X,Y}(x,y) = F_X(x) \cdot F_Y(y) \iff f_{X,Y} = f_X \cdot f_Y (cas continu).
  * **Covariance \text{Cov}(X,Y)** : \text{Cov}(X,Y) = \mathbb{E}(XY) - \mathbb{E}(X)\mathbb{E}(Y). Propriétés : symétrie, \text{Cov}(X,X)=\mathbb{V}(X), transformation affine : \text{Cov}(aX+b, cY+d) = ac \cdot \text{Cov}(X,Y).
  * **Coefficient de corrélation \rho** : \rho(X,Y) = \frac{\text{Cov}(X,Y)}{\sqrt{\mathbb{V}(X)\mathbb{V}(Y)}} \in [-1,1]. |\rho|=1 \iff relation affine p.s. entre X et Y.
- ### 4.6 Modes de convergence
  | Mode | Définition | Résultat clé |
  |---|---|---|
  | **En loi** (\xrightarrow{\mathcal{L}}) | F_{X_n}(x) \to F_X(x) en tout point de continuité de F_X | Théorème central-limite (TCL) |
  | **En probabilité** (\xrightarrow{\mathcal{P}}) | $\forall \varepsilon>0 : P( | X_n-X |
  | **En moy. quadratique** (\xrightarrow{\text{m.q.}}) | \mathbb{E}((X_n-X)^2) \to 0 | \bar{X} \xrightarrow{\text{m.q.}} \mu (car \mathbb{V}(\bar{X})=\frac{\sigma^2}{n} \to 0) |
  | **Presque sûre** (\xrightarrow{\text{p.s.}}) | P(\lim_n X_n = X) = 1 | Loi forte des grands nombres |
  > **Relations d'implication** :
  > \xrightarrow{\text{m.q.}} \implies \xrightarrow{\mathcal{P}} \implies \xrightarrow{\mathcal{L}}
  > \xrightarrow{\text{p.s.}} \implies \xrightarrow{\mathcal{P}} \implies \xrightarrow{\mathcal{L}}
  > 
  ## 5. Théorèmes fondamentaux
  ### 5.1 Théorème central-limite (TCL)
  Si (X_n) est une suite de v.a. i.i.d. d'espérance \mu et d'écart-type \sigma > 0, alors:
  
  
  Autrement dit, pour n suffisamment grand:
  * \bar{X} = \frac{1}{n} \sum X_i suit approximativement \mathcal{N}\left(\mu ; \frac{\sigma^2}{n}\right)
  * S_n = \sum X_i suit approximativement \mathcal{N}(n\mu ; n\sigma^2)
  *Importance : Justifie l'omniprésence de la loi normale en statistique, quelle que soit la loi d'origine des X_i.*
- ### 5.2 Loi faible des grands nombres
  Sous les mêmes hypothèses que le TCL:
  
  
  *Importance : Justifie l'utilisation de la moyenne empirique comme estimateur de l'espérance, et établit le lien probabilité \leftrightarrow fréquence.*
- ### 5.3 Inégalité de Bienaymé-Tchebychev
  Pour toute v.a. X d'espérance \mu et de variance \sigma^2, et tout \alpha > 0:
  
  
  *Importance : Utilisée pour déduire la convergence en probabilité depuis la convergence en moyenne quadratique.*
- ## 6. Points de vigilance
  * **Indépendance \neq décorrélation** : L'indépendance entraîne \text{Cov} = 0, mais la réciproque est fausse (la décorrélation ne suffit pas à prouver l'indépendance).
  * **Les lois marginales ne déterminent pas la loi conjointe** : Deux couples de variables distincts peuvent avoir les mêmes lois marginales tout en présentant des lois conjointes différentes.
  * **Probabilité en un point** : Pour une v.a. absolument continue, P(X = a) = 0 pour tout réel a. Les probabilités en un point isolé sont nulles.
  * **Non-unicité de la densité** : Deux densités qui diffèrent sur un ensemble dénombrable définissent la même loi de probabilité.
  * **Interprétation de la convergence en loi** : \vphantom{X}X_n \xrightarrow{\mathcal{L}} X n'indique pas que les valeurs numériques de X_n sont proches de celles de X.
  * **Conditions du TCL** : Requiert dans sa forme de base des variables i.i.d. et des variances finies. Le seuil de validité de l'approximation dépend fortement de la loi des X_i.
  * **Formule de Bayes** : Elle permet de « retourner » une probabilité conditionnelle en inversant le conditionnement pour obtenir des probabilités a posteriori.
- ## 7. Résumé des exercices proposés
  | Exercice | Thématique | Descriptif / Résultat clé |
  |---|---|---|
  | **Ex. 1** | Spams | Probabilités conditionnelles et formule des probabilités totales. Application à la détection de spam par mots-clés. Calcul de P(\text{spam} \| \text{mot « order »}. |
  | **Ex. 2** | Durée de vie | Loi exponentielle (densité \lambda e^{-\lambda x}). Propriété de loi sans mémoire, durée de vie moyenne, et comparaison entre la moyenne et la médiane pour détecter un discours trompeur. |
  | **Ex. 3** | Consommation | Couple de v.a. indépendantes. Calcul de P(X_1 > X_2) par intégration à l'aide des fonctions de répartition et des densités marginales. |
  | **Ex. 4** | Vecteur gaussien | Transformation linéaire d'un vecteur gaussien centré. Calcul de variances, covariances, densités marginales de Y_1 et Y_2, et vérification de leur indépendance. |
  | **Ex. 5** | TCL (Poisson) | Application non probabiliste du TCL. Somme de v.a. de Poisson, convergence en loi vers \mathcal{N}(0;1), et déduction d'une limite analytique : \lim_n e^{-n} \sum_k \frac{n^k}{k!} = \frac{1}{2}. |
- ## 8. Contexte dans le cours global
  Ce thème 1 est le socle théorique indispensable pour les thèmes suivants du cours global:
  * **Thème 0 – Statistique descriptive** *(Prérequis)* : Fournit le vocabulaire de base, l'étude de la distribution empirique et de la corrélation.
  * **Thème 1 – Probabilités** *(Présent document)* : Offre les outils nécessaires pour modéliser l'aléatoire.
  * **Thème 2 – Estimation** : Mobilise l'espérance, la variance, le TCL et la loi des grands nombres pour la construction d'estimateurs.
  * **Thème 3 – Tests statistiques** : S'appuie sur ces lois de probabilité et les différents modes de convergence pour concevoir des tests d'hypothèses.
  * **Thème 4 – Régression linéaire** : Met en application les couples de variables aléatoires, la covariance et le coefficient de corrélation.
-
-