- Voici une retranscription complète de votre tableau récapitulatif structurée pour **Logseq** (format Markdown avec hiérarchie par puces). Cette structure permet d'utiliser les fonctionnalités de "collapse/expand" de Logseq pour une meilleure lisibilité.
- ## Récapitulatif des Tests Statistiques Usuels
- ### Comparaison de Moyennes (Variable réponse numérique)
  * **Comparer une moyenne à une valeur de référence**
   * **Nombre de groupes** : 1
   * **Test paramétrique** : Test de Student (1 échantillon)
   * **Conditions d'application** : Au moins 15 sujets ; normalité des données (Shapiro-Wilk) ; absence de valeurs extrêmes
   * **Test non paramétrique** : Test de Wilcoxon (1 échantillon)
  * **Comparer deux moyennes (Indépendantes)**
   * **Nombre de groupes** : 2
   * **Type de données** : Indépendantes
   * **Test paramétrique** : Test de Student (indépendants)
   * **Conditions d'application** : Au moins 15 sujets dans les deux groupes ; normalité dans chaque groupe (Shapiro-Wilk) ; égalité des variances (test F ou Levene) ; absence d'outliers
   * **Test non paramétrique** : Test de Wilcoxon-Mann-Whitney
  * **Comparer deux moyennes (Appariées)**
   * **Nombre de groupes** : 2
   * **Type de données** : Appariées
   * **Test paramétrique** : Test de Student apparié
   * **Conditions d'application** : Au moins 15 sujets ; normalité des différences appariées ; absence d'outliers
   * **Test non paramétrique** : Test de Wilcoxon apparié
  * **Comparer plusieurs moyennes (>2) (Indépendantes)**
   * **Nombre de groupes** : ≥ 3
   * **Type de données** : Indépendantes
   * **Test paramétrique** : ANOVA à un facteur
   * **Conditions d'application** : Normalité et homogénéité des résidus (Shapiro-Wilk, Levene) ; absence d'outliers
   * **Test non paramétrique** : Test de Kruskal-Wallis
  * **Comparer plusieurs moyennes (>2) (Appariées)**
   * **Nombre de groupes** : ≥ 3
   * **Type de données** : Appariées (mesures répétées)
   * **Test paramétrique** : ANOVA à mesures répétées
   * **Conditions d'application** : Normalité des mesures répétées ; sphéricité (test de Mauchly) ; absence d'outliers
   * **Test non paramétrique** : Test de Friedman
- ### Comparaison de Pourcentages (Variable réponse binaire : oui/non)
  * **Comparer une proportion à une valeur de référence**
   * **Nombre de groupes** : 1
   * **Test paramétrique** : Test binomial
   * **Conditions d'application** : Observations indépendantes ; variable binaire ; probabilité constante entre essais
   * **Test non paramétrique** : —
  * **Comparer deux proportions (Indépendantes)**
   * **Nombre de groupes** : 2
   * **Type de données** : Indépendantes
   * **Test paramétrique** : Test du Chi^2 (2x2)
   * **Conditions d'application** : ≥ 80 % des effectifs théoriques ≥ 5 et aucun < 1 ; observations indépendantes
   * **Test non paramétrique** : Test exact de Fisher (si effectifs faibles)
  * **Comparer deux proportions (Appariées)**
   * **Nombre de groupes** : 2
   * **Type de données** : Appariées
   * **Test paramétrique** : —
   * **Conditions d'application** : Au moins 10 paires discordantes ; observations appariées
   * **Test non paramétrique** : Test de McNemar
  * **Comparer plusieurs proportions (≥3) (Indépendantes)**
   * **Nombre de groupes** : ≥ 3
   * **Type de données** : Indépendantes
   * **Test paramétrique** : Test du Chi^2 (d'homogénéité)
   * **Conditions d'application** : ≥ 80 % des effectifs théoriques ≥ 5 et aucun < 1 ; observations indépendantes
   * **Test non paramétrique** : Test exact de Fisher (si effectifs faibles)
  * **Comparer plusieurs proportions (≥3) (Appariées)**
   * **Nombre de groupes** : ≥ 3
   * **Type de données** : Appariées (mesures répétées)
   * **Test paramétrique** : —
   * **Conditions d'application** : Observations appariées ; chaque sujet observé dans toutes les conditions
   * **Test non paramétrique** : Test Q de Cochran
  © Claire Della Vedova — delladata.fr