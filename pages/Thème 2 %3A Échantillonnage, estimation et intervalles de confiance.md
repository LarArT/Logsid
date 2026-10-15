- Voici la transposition complète et structurée de votre document au format Markdown, respectant scrupuleusement les informations et les formules fournies.
- # FICHE DE LECTURE
  **Statistique pour ingénieur — Thème 2 : Échantillonnage, estimation et intervalles de confiance** *F. Delacroix, M. Lecomte & R. Schwartz | Institut Mines-Télécom | 18 mai 2026*
- ## 1. Informations générales
  |  |  |
  |---|---|
  | **Discipline** | Statistique pour ingénieur |
  | **Thème** | Thème 2 – Échantillonnage, estimation, estimateurs et intervalles de confiance |
  | **Auteurs** | F. Delacroix, M. Lecomte & R. Schwartz |
  | **Institution** | Institut Mines-Télécom |
  | **Date** | 18 mai 2026 |
  | **Prérequis** | Thème 0 (statistique descriptive), Thème 1 (probabilités, TCL, loi des grands nombres) |
- ## 2. Objectifs du document
  Ce thème introduit la statistique inférentielle : comment tirer des conclusions sur une population entière à partir d'un simple échantillon. Il vise à :
  * Définir les notions de population, échantillon, statistique et inférence statistique.
  * Étudier les distributions d'échantillonnage des moyennes et des variances.
  * Construire et évaluer des estimateurs ponctuels (biais, variance, EQM).
  * Présenter la méthode du maximum de vraisemblance.
  * Construire des intervalles de confiance pour \mu, \sigma^2 et une proportion p.
  * Illustrer les applications industrielles via les cartes de contrôle (MSP/SPC).
- ## 3. Plan du document
  | § | Section | Contenu principal |
  |---|---|---|
  | **1** | Vocabulaire et hypothèses | Population, échantillon, taux de sondage, hypothèses i.i.d. de la statistique classique |
  | **2** | Échantillonnage | Statistiques, distribution de \bar{X} (cas général, TCL, gaussien), loi du \chi^2, distribution de S^2 |
  | **3** | Estimation | Estimateurs, biais, EQM, méthode du maximum de vraisemblance |
  | **4** | Intervalles de confiance | IC pour \mu (\sigma connu : loi N ; \sigma inconnu : loi de Student), IC pour \sigma^2 (loi \chi^2), IC pour une proportion p |
  | **5** | Contrôle statistique | Cartes de contrôle p, cartes aux mesures (moyenne et écart-type), courbes d'efficacité |
- ## 4. Notions et définitions clés
- ### 4.1 Vocabulaire de base
  * **Population \Omega** : Ensemble de N individus sur lesquels porte l'étude. La variable d'intérêt X est définie sur \Omega.
  * **Échantillon S** : n-uplet (\omega_1, \dots, \omega_n) prélevé dans \Omega. Taille n (minuscule) à distinguer de N (majuscule).
  * **Taux de sondage** : \tau = \frac{n}{N}. Dans le sondage aléatoire simple (PESR), chaque individu a la même probabilité d'être sélectionné.
  * **Hypothèses classiques** : Les observations (x_1, \dots, x_n) sont des réalisations de n v.a. X_1, \dots, X_n i.i.d. (indépendantes, même loi que X). Valide pour tirages avec remise ou N \gg n.
  * **Statistique T** : Variable aléatoire T = f(X_1, \dots, X_n). Sa loi s'appelle distribution d'échantillonnage.
- ### 4.2 Distribution d'échantillonnage de la moyenne \bar{X}
  | Situation | Résultat |
  |---|---|
  | **Cas général** (X de loi quelconque) | E(\bar{X}) = \mu et V(\bar{X}) = \frac{\sigma^2}{n} — toujours valables. |
  | **n grand** (n \ge 30) | Par le TCL : \bar{X} \sim N\left(\mu ; \frac{\sigma^2}{n}\right) approximativement. |
  | **X \sim N(\mu ; \sigma^2)** (échantillon gaussien) | \bar{X} \sim N\left(\mu ; \frac{\sigma^2}{n}\right) exactement, quelle que soit la taille n. |
- ### 4.3 Variance empirique et loi du \chi^2
  * **Variance empirique S^2** :
   
  * **Variance corrigée S^{*2}** :
   
  * **Loi du \chi^2(\nu)** : Loi de la somme de \nu v.a. N(0;1) indépendantes au carré. E(Z) = \nu. Si X \sim N(\mu;\sigma^2) :
- ### 4.4 Qualités d'un estimateur
  | Critère | Définition | Exemple |
  |---|---|---|
  | **Biais** | E(\hat{\Theta}_n) - \theta | S^2 est biaisé (biais = -\frac{\sigma^2}{n}) ; S^{*2} est sans biais |
  | **Sans biais** | E(\hat{\Theta}_n) = \theta pour tout \theta | \bar{X} est sans biais pour \mu ; F = \frac{K}{n} est sans biais pour p |
  | **Asympt. sans biais** | E(\hat{\Theta}_n) \to \theta quand n \to \infty | S^2 est asymptotiquement sans biais |
  | **Consistant** | \hat{\Theta}_n \xrightarrow{P} \theta (cf. Thème 1) | \bar{X} \xrightarrow{P} \mu par la loi des grands nombres |
  | **EQM** (erreur quadr. moy.) | \text{EQM} = V(\hat{\Theta}_n) + [\text{biais}]^2 | Pour \bar{X} : \text{EQM} = \frac{\sigma^2}{n} (sans biais) |
  > **Théorème clé** : si E(\hat{\Theta}_n) \to \theta et V(\hat{\Theta}_n) \to 0, alors \hat{\Theta}_n est un estimateur de \theta (via l'inégalité de Markov).
  > 
  ### 4.5 Méthode du maximum de vraisemblance (MV)
  * **Fonction de vraisemblance L** : L(x, \theta) = \prod_i f(x_i, \theta) où f est la densité (ou la probabilité) de la loi. Représente la probabilité d'avoir observé l'échantillon pour un \theta donné.
  * **Estimateur MV** : Valeur \hat{\theta} qui maximise L(x, \theta) ou \ln L(x, \theta) (log-vraisemblance). En pratique : résoudre \frac{\partial \ln L}{\partial \theta} = 0.
  **Exemples d'application :**
  * **Poisson P(\lambda)** : \lambda \implies \text{Estimateur MV : } \bar{X} = \frac{1}{n} \sum X_i
  * **Normale N(\mu ; \sigma^2) avec \mu connu** : \sigma \implies \text{Estimateur MV : } \hat{\Sigma} = \sqrt{\frac{1}{n} \sum(X_i - \mu)^2} \quad \text{(biaisé)}
  ### 4.6 Intervalles de confiance (IC)
  Un IC au niveau 1-\alpha est un intervalle aléatoire [T_1, T_2] tel que P(T_1 \le \theta \le T_2) = 1-\alpha. On appelle \alpha le risque et 1-\alpha le niveau de confiance.
  | Paramètre | Hypothèses | Loi utilisée | Formule de l'IC au niveau 1-\alpha |
  |---|---|---|---|
  | **\mu** | \sigma connu, n grand ou X gaussien | N(0;1) \to quantile u_{\alpha/2} | \bar{x} \pm u_{\alpha/2} \cdot \frac{\sigma}{\sqrt{n}} |
  | **\mu** | \sigma inconnu, X \sim N(\mu;\sigma^2) | Student T(n-1) \to quantile t_{\alpha/2} | \bar{x} \pm t_{\alpha/2} \cdot \frac{s}{\sqrt{n-1}} |
  | **\sigma^2** | X \sim N(\mu;\sigma^2) | \chi^2(n-1) \to fractiles \chi^2_{\alpha/2} et \chi^2_{1-\alpha/2} | \left[\frac{nS^2}{\chi^2_{1-\alpha/2}} \; ; \; [span_69](start_span)\frac{nS^2}{\chi^2_{\alpha/2}}\right] |
  | **Proportion p** | n petit (5 \le n \le 100) | Loi binomiale (abaques) | Lecture d'abaques |
  | **Proportion p** | n > 100 et nf(1-f) > 18 | N(0;1) via Moivre-Laplace | f \pm u_{\alpha/2} \cdot \sqrt{\frac{f(1-f)}{n}} |
  > **IC bilatéral** : risque \alpha réparti aux deux extrémités.
  > **IC unilatéral** : risque \alpha concentré d'un seul côté (ex. : vérifier qu'un candidat est favori).
  > 
  ### 4.7 Loi de Student T(\nu)
  * **Définition** : T = \frac{U}{\sqrt{Z/\nu}} où U \sim N(0;1) et Z \sim \chi^2(\nu), indépendants. Densité symétrique, plus évasée que la loi normale.
  * **Lien avec l'IC de \mu** : Si X \sim N(\mu;\sigma^2) et \sigma inconnu : T = \frac{\bar{X} - \mu}{S/\sqrt{n-1}} \sim T(n-1). Pour \nu > 160 : T(\nu) \approx N(0;1).
  ### 4.8 Contrôle statistique des processus (MSP/SPC)
  * **Carte de contrôle p** : Surveille la proportion p_0 de non-conformes. Limites : p_0 \pm 3\sqrt{\frac{p_0(1-p_0)}{n}}. Un point hors limites \implies processus hors contrôle.
  * **Carte de la moyenne** : Surveille le réglage du processus. Limites : \mu \pm 3\frac{\sigma}{\sqrt{n}} (risque \alpha = 0,27\%). Un point hors limites \implies décentrage.
  * **Carte de l'écart-type** : Surveille la dispersion. Limites basées sur les fractiles de \chi^2(n-1) : \sigma\sqrt{\frac{\chi^2_{\alpha/2}}{n}} et \sigma\sqrt{\frac{\chi^2_{1-\alpha/2}}{n}}. **Analyser en premier**.
  * **Courbe d'efficacité** : Représente \beta(k) = risque de ne pas détecter un décentrage de k\sigma. Permet de calibrer la taille n des échantillons. Valeurs admissibles de \beta : 5\% à 20\%.
  ## 5. Formules essentielles à retenir
  * E(\bar{X}) = \mu et V(\bar{X}) = \frac{\sigma^2}{n} (toujours valables, quelle que soit la loi de X).
  * E(S^2) = \frac{n-1}{n} \cdot \sigma^2 (biaisé) \to E(S^{*2}) = \sigma^2 (sans biais, avec diviseur n-1).
  * \text{EQM}(\hat{\Theta}) = V(\hat{\Theta}) + [\text{biais}]^2 = V(\hat{\Theta}) + [E(\hat{\Theta}) - \theta]^2.
  * Si X \sim N(\mu;\sigma^2) : \frac{nS^2}{\sigma^2} \sim \chi^2(n-1) et \frac{\bar{X}-\mu}{S/\sqrt{n-1}} \sim T(n-1).
  * **IC de \mu (\sigma connu)** : \bar{x} \pm 1,96 \cdot \frac{\sigma}{\sqrt{n}} au niveau 95\% (u_{\alpha/2} = 1,96 pour \alpha = 5\%).
  * **IC de \mu (\sigma inconnu, n = 10, \alpha = 5\%)** : \bar{x} \pm 2,262 \cdot \frac{s}{\sqrt{n-1}}.
  * **IC de p (grand n)** : f \pm u_{\alpha/2} \cdot \sqrt{\frac{f(1-f)}{n}} avec condition n \cdot f \cdot (1-f) > 18.
  ## 6. Points de vigilance
  * **S^2 vs S^{*2}** : S^2 (diviseur n) est l'estimateur biaisé ; S^{*2} (diviseur n-1) est sans biais. Préférer S^{*2} surtout pour de petits échantillons.
  * **IC \neq probabilité a posteriori** : une fois l'IC calculé, \mu est soit dedans soit dehors. Le niveau de confiance 95\% signifie que 95\% des IC construits de cette façon contiendront \mu.
  * **Loi de Student vs loi normale** : utiliser T(n-1) quand \sigma est inconnu et n < 30. Pour n \ge 30, on peut approcher T(n-1) par N(0;1).
  * **IC pour \sigma^2 non centré** : l'asymétrie de la loi \chi^2 rend l'IC pour \sigma^2 non centré autour de s^2.
  * **IC pour p** : la condition nf(1-f) > 18 est nécessaire pour l'approximation normale ; sinon utiliser les abaques de la loi binomiale.
  * **Cartes de contrôle** : toujours analyser la carte de l'écart-type **AVANT** la carte de la moyenne. Un déréglage non détecté (risque \beta) peut être coûteux.
  * **Estimateur MV non nécessairement sans biais** : la MV donne de bons estimateurs asymptotiquement, mais peut être biaisée à taille finie (ex. : \hat{\Sigma} pour la loi normale).
  ## 7. Résumé des exercices proposés
  | Exercice | Thématique | Descriptif / Résultat clé |
  |---|---|---|
  | **Ex. 1** | Estimateurs | Loi uniforme sur [0, a] : comparaison de l'estimateur A_n = \max(X_i) et de B_n = 2\bar{X}. Calcul des lois, biais, variances. B_n est sans biais mais a une plus grande variance que A_n pour n grand. |
  | **Ex. 2** | Maximum de vraisemblance | Loi exponentielle de paramètre \lambda. Construction de l'estimateur MV par maximisation de la log-vraisemblance. Résultat : \hat{\lambda} = \frac{1}{\bar{X}}. |
  | **Ex. 3** | Loi de Poisson | Estimation de \lambda par deux méthodes (MV et estimateur de e^{-\lambda} via loi conditionnelle de \sum_n). Comparaison des estimateurs. Met en évidence que l'estimateur sans biais d'une fonction de \theta n'est pas la même chose que l'estimateur sans biais de \theta lui-même. |
  | **Ex. 4** | IC pour \mu et \sigma^2 | Billes pour roulements : \mu et \sigma inconnus, X \sim N(\mu;\sigma^2). Calcul de l'IC de \mu (loi de Student) et de l'IC de \sigma^2 (loi \chi^2) à partir de données numériques. |
  | **Ex. 5** | IC pour une proportion | Proportion de billes défectueuses. Deux sous-cas : n = 100 (loi binomiale) et n = 500 (approximation normale). Application du théorème de Moivre-Laplace. |
  | **Ex. 6** | Publicité mensongère ? | Durée de vie moyenne annoncée 200\text{h} vs \bar{x} = 185\text{h} observée sur 25 piles. Construction d'un IC unilatéral pour tester si la publicité est mensongère. |
  | **Ex. 7** | Paramètre d'une loi continue | Loi de densité e^{\theta-x} (x \ge \theta). Comparaison d'un IC via TCL et d'un IC via inégalité de Bienaymé-Tchebychev. L'IC TCL est plus serré ; illustre le gain d'efficacité lorsqu'on dispose d'une information sur la loi. |
  | **Ex. 8** | Cartes de Shewhart | Construction des limites de contrôle pour les cartes (\bar{X}, S^*) et (\bar{X}, R). Détermination des coefficients c_4 (correction pour S^*) et d_2, d_3 (estimation de \sigma par l'étendue R). Bases théoriques des tables ISO/SPC. |
  ## 8. Contexte dans le cours global
  Ce thème 2 constitue le cœur applicatif de la statistique inférentielle :
  * **Thème 0 – Statistique descriptive** : fournit le vocabulaire (moyenne, variance, fréquence) utilisé pour définir les statistiques.
  * **Thème 1 – Probabilités** : TCL et loi des grands normes justifient la distribution de \bar{X} ; loi normale, \chi^2 et Student sont les outils des IC.
  * **Thème 2 – Estimation (présent document)** : estimation ponctuelle et par intervalle, cartes de contrôle.
  * **Thème 3 – Tests statistiques** : prolongement direct — un test revient souvent à vérifier si une valeur cible appartient à un IC.
  * **Thème 4 – Régression linéaire** : utilise les IC pour tester la significativité des coefficients du modèle.
-