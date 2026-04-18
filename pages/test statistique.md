- Voici une retranscription de la carte mentale "Tests Statistiques Usuels" structurée pour **Logseq** (format Markdown avec hiérarchie par puces).
  [[Bien choisir ses tests statistiques]]
  [[Bien choisir ses tests bis]]
- ## Tests Statistiques Usuels
  * **Évaluation des Conditions d'Application**
   * **Normalité**
     * Test de Shapiro-Wilk
     * Test de Kolmogorov Smirnov
     * Test d'Anderson–Darling
     * Test de Jarque–Bera
   * **Homogénéité des variances**
     * **2 groupes**
       * Test F de Fisher
       * Test de Levene
     * **3 groupes et +**
       * Test de Bartlett
       * Test de Levene
   * **Homogénéité des résidus (homoscédasticité)**
     * Test de Breush-Pagan
  * **Comparaison de Moyennes (Réponse quantitative)**
   * **1 groupe**
     * One sample T test (Test de Student pour un échantillon)
     * One sample Wilcoxon Test (Test de Wilcoxon pour un échantillon - Non paramétrique)
   * **2 groupes**
     * **Indépendants**
       * Test de Student
       * Test de Welch
       * Test de Wilcoxon (non paramétrique)
     * **Appariés (Données répétées)**
       * Test de Student apparié
       * Test de Wilcoxon apparié (non paramétrique)
   * **3 groupes et +**
     * **Indépendants**
       * ANOVA paramétrique à 1 facteur
       * Test de Kruskal-Wallis (ANOVA à un facteur non paramétrique)
     * **Appariés (données répétées)**
       * ANOVA à un facteur pour données répétées
       * Test de Friedman (ANOVA non paramétrique sur données répétées)
  * **Comparaisons de Pourcentages (Réponse binaire)**
   * **1 groupe**
     * Test binomial
   * **2 groupes**
     * **Indépendants**
       * Test du Chi2
       * Test exact de Fisher
     * **Appariés**
       * Test de Mac Nemar
   * **3 groupes et +**
     * **Indépendants**
       * Test du Chi2
       * Test exact de Fisher
       * Régression logistique (GLM)
     * **Appariés**
       * Test Q de Cochran
       * Régression logistique mixte (GLMM)
  * **Évaluation de la Liaison Entre 2 Variables**
   * **2 variables quantitatives**
     * Corrélation de Pearson (test égalité à 0 du coefficient de corrélation)
     * Corrélation de Spearman (test égalité à 0 du coefficient de corrélation) : non paramétrique
     * Régression linéaire simple (Test d'égalité à 0 de la pente)
   * **2 variables qualitatives**
     * Test d'indépendance du Chi2
   * **1 variable quantitative et 1 variable qualitative**
     * ANOVA paramétrique à un facteur
     * Test de Kruskal-Wallis (ANOVA non paramétrique à un facteur)