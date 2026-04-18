- peux-tu me faire un résumé complet des 20 test statistiques les plus utilisés leur caractéristiques un exemple d'interprétation de résultat suivant la plus-value
  
  Voici une fiche synthèse de 20 tests statistiques très courants, avec pour chacun : quand l’utiliser, ses hypothèses essentielles et un exemple d’interprétation qui montre la plus‑value décisionnelle du test.[1][2][3]
  
  ***
- ## Principes généraux à garder en tête
  
  Un test statistique sert à décider si un effet observé (différence, corrélation, etc.) peut raisonnablement s’expliquer par le hasard, ou s’il est trop grand pour être attribué à la seule fluctuation d’échantillonnage.[4][5]
  On pose une hypothèse nulle (H0, « pas de différence / pas d’effet ») et on calcule une p‑valeur ; si $$p < \alpha$$ (souvent 0,05), on rejette H0 et on conclut qu’il existe un effet statistiquement significatif, en gardant à l’esprit les risques d’erreurs de type I et II.[4][6][5]
  
  Plus‑value générale : ces tests permettent de transformer des écarts observés en décisions rationnelles, objectivées par une probabilité d’erreur contrôlée (niveau de signification α).[4][7][5]
  
  ***
- ## Tests paramétriques sur les moyennes
- ### 1. Test t à un échantillon
- **Objectif** : comparer la moyenne d’un échantillon à une valeur de référence (par exemple une norme ou une moyenne théorique).[4][8]
- **Données** : une variable quantitative, distribution approximativement normale, observations indépendantes.[2][7]
- **Hypothèse nulle** : la moyenne de la population étudiée est égale à la valeur de référence (H0 : μ = μ0).[4][8]
  
  **Exemple d’interprétation / plus‑value**  
  On teste si la moyenne de score à un test (échantillon d’élèves) est différente de 10/20 (niveau attendu).[4]
  Si $$p = 0{,}01 < 0{,}05$$, on rejette H0 : la moyenne diffère significativement de 10, ce qui permet de conclure objectivement que le niveau réel est supérieur ou inférieur au standard, avec un risque d’erreur de 1 %.[4][5]
  
  ***
- ### 2. Test t pour deux échantillons indépendants
- **Objectif** : comparer la moyenne de deux groupes indépendants (ex. groupe contrôle vs groupe expérimental).[1][4][3]
- **Données** : variable quantitative, normalité approximative dans chaque groupe, variances homogènes (ou version corrigée).[2][7]
- **H0** : μ1 = μ2 (pas de différence de moyenne entre les groupes).[4][8]
  
  **Exemple / plus‑value**  
  On compare la durée moyenne de session sur un site web avant vs après un nouveau design (deux groupes indépendants d’utilisateurs).[4]
  Si $$p < 0{,}05$$, on conclut que le nouveau design modifie significativement la durée de session, ce qui justifie ou non le déploiement d’un changement coûteux.[4][3]
  
  ***
- ### 3. Test t apparié (paired t‑test)
- **Objectif** : comparer deux mesures faites sur les mêmes unités (avant/après traitement, test/retest).[1][4]
- **Données** : variable quantitative, distribution à peu près normale des différences, observations appariées.[2]
- **H0** : la moyenne des différences est nulle (pas de changement entre les deux temps ou conditions).[4][8]
  
  **Exemple / plus‑value**  
  On mesure la pression artérielle avant et après un médicament sur les mêmes patients.[1]
  Si $$p < 0{,}05$$, on conclut à une baisse significative de la pression, ce qui renforce la preuve d’efficacité du traitement à l’échelle clinique.[1][4]
  
  ***
- ### 4. ANOVA à un facteur (analyse de variance)
- **Objectif** : comparer les moyennes de 3 groupes ou plus sur une variable quantitative à partir d’un facteur catégoriel (ex. 3 régimes alimentaires).[1][4][3]
- **Données** : variable quantitative, normalité approximative, variances homogènes et groupes indépendants.[4][2]
- **H0** : toutes les moyennes sont égales (μ1 = μ2 = … = μk).[4]
  
  **Exemple / plus‑value**  
  Un biologiste teste 4 engrais différents sur la hauteur de plantes.[4]
  Si l’ANOVA donne $$p < 0{,}05$$, on conclut qu’au moins un engrais produit une hauteur moyenne différente, ce qui justifie de poursuivre avec des comparaisons post‑hoc pour choisir le meilleur engrais et optimiser le rendement.[1][4][9]
  
  ***
- ### 5. ANOVA à mesures répétées
- **Objectif** : comparer des moyennes mesurées plusieurs fois sur les mêmes sujets (ex. performance à T1, T2, T3).[2][9]
- **Données** : variable quantitative, normalité des erreurs, sphericité (ou correction), mesures répétées sur les mêmes individus.[2][9]
- **H0** : toutes les moyennes temporelles (ou de conditions) sont égales.[9]
  
  **Exemple / plus‑value**  
  On suit la douleur de patients à 3 temps après une opération avec un même médicament.[9]
  Si $$p < 0{,}05$$, on conclut que l’évolution moyenne diffère au cours du temps, ce qui permet de caractériser précisément la dynamique d’efficacité d’un traitement.[9][10]
  
  ***
- ### 6. Régression linéaire simple
- **Objectif** : modéliser et tester la relation entre une variable dépendante quantitative Y et un prédicteur quantitatif X (pente différente de 0 ?).[1][3][7]
- **Données** : Y quantitative, X quantitatif, relation approximativement linéaire, résidus ~ normaux et indépendants.[2][7]
- **H0** : le coefficient de pente β1 = 0 (pas de relation linéaire).[7]
  
  **Exemple / plus‑value**  
  On étudie l’effet du nombre d’heures de révision sur la note à un examen.[7]
  Si le test sur β1 donne $$p < 0{,}05$$, on conclut qu’augmenter les heures de travail est significativement associé à une meilleure note, ce qui aide à quantifier l’intérêt marginal d’une heure supplémentaire.[3][7]
  
  ***
- ### 7. Régression linéaire multiple
- **Objectif** : tester l’effet simultané de plusieurs prédicteurs sur une variable quantitative (Y), via un F‑test global et des tests t sur chaque coefficient.[3][7]
- **Données** : Y quantitative, plusieurs X quantitatifs/catégoriels, hypothèses similaires à la régression simple.[7]
- **H0 globale** : tous les coefficients de pente sont nuls (modèle sans intérêt).[3]
  
  **Exemple / plus‑value**  
  On modélise le chiffre d’affaires en fonction du budget marketing, du prix, et de la saison.[3]
  Un F‑test significatif montre que le modèle explique une part significative de la variance, et les tests t permettent d’identifier les leviers réellement influents, guidant les décisions d’allocation budgétaire.[3][7]
  
  ***
- ## Tests sur proportions et variables catégorielles
- ### 8. Test z de proportion (une proportion)
- **Objectif** : comparer une proportion observée (succès/échecs) à une proportion théorique p0.[2][7]
- **Données** : variable binaire, échantillon assez grand pour l’approximation normale.[2][7]
- **H0** : p = p0.[2]
  
  **Exemple / plus‑value**  
  On teste si le taux de satisfaction dépasse 80 % dans un échantillon de clients.[7]
  Si $$p < 0{,}05$$, on conclut que le taux réel diffère significativement de 0,80 (par exemple 0,90), ce qui justifie une revendication marketing du type « plus de 9 clients sur 10 satisfaits ».[7]
  
  ***
- ### 9. Test du chi‑deux d’ajustement (goodness‑of‑fit)
- **Objectif** : vérifier si une distribution observée de fréquences suit une distribution théorique (ex. loi de Mendel, distribution uniforme, etc.).[1][2][3]
- **Données** : variable catégorielle, effectifs attendus suffisamment grands.[2][11]
- **H0** : la distribution observée ne diffère pas de la distribution théorique.[1][2]
  
  **Exemple / plus‑value**  
  On vérifie si les naissances garçons/filles suivent une proportion 50/50.[1]
  Si $$p > 0{,}05$$, on ne rejette pas H0 : les écarts sont compatibles avec le hasard, ce qui évite des conclusions hâtives sur un « déséquilibre » inexistant.[1][11]
  
  ***
- ### 10. Test du chi‑deux d’indépendance
- **Objectif** : tester l’association entre deux variables catégorielles (ex. tabagisme oui/non et cancer oui/non).[1][4][3]
- **Données** : tableau de contingence, effectifs attendus raisonnables (règle des 5).[2][11]
- **H0** : les variables sont indépendantes (pas d’association).[1][5]
  
  **Exemple / plus‑value**  
  On examine s’il existe un lien entre statut de fumeur et présence de cancer dans un échantillon hospitalier.[1]
  Si $$p < 0{,}05$$, on conclut à une association statistiquement significative, ce qui conforte un argument de santé publique pour cibler la prévention.[1][3]
  
  ***
- ### 11. Test de McNemar
- **Objectif** : comparer deux proportions binaires appariées (même sujets avant/après ou cas‑témoins appariés), sur une variable dichotomique.[2]
- **Données** : tableau 2×2 avec observations appariées (succès/échec à deux temps).[2]
- **H0** : les proportions de changement dans un sens et dans l’autre sont égales (pas d’effet du traitement).[2]
  
  **Exemple / plus‑value**  
  On mesure l’adhésion à une règle de sécurité avant et après une campagne de sensibilisation sur les mêmes personnes.[2]
  Un test de McNemar significatif montre que la proportion de « non → oui » diffère de « oui → non », ce qui prouve l’efficacité de la campagne sur les comportements déclarés.[2]
  
  ***
- ## Corrélation et association entre variables quantitatives / ordinales
- ### 12. Corrélation de Pearson
- **Objectif** : mesurer et tester la force d’une relation linéaire entre deux variables quantitatives continues.[2][8]
- **Données** : deux variables quantitatives, relation approximativement linéaire, absence de valeurs extrêmes dominantes.[2][8]
- **H0** : ρ = 0 (pas de corrélation linéaire dans la population).[8]
  
  **Exemple / plus‑value**  
  On étudie le lien entre âge et revenu annuel.[8]
  Si r = 0,6 avec $$p < 0{,}01$$, on conclut à une corrélation linéaire positive significative, ce qui permet d’intégrer cet effet dans des modèles prédictifs ou des politiques salariales.[3][8]
  
  ***
- ### 13. Corrélation de Spearman (rho)
- **Objectif** : corrélation non paramétrique basée sur les rangs, adaptée aux données ordinales ou à des distributions non normales.[12][2]
- **Données** : variables ordinales ou quantitatives non normales, relation monotone (pas nécessairement linéaire).[12][10]
- **H0** : aucune corrélation monotone (rho = 0).[12]
  
  **Exemple / plus‑value**  
  On corrèle un score de satisfaction (échelle Likert) avec un rang de priorité donné par les clients.[12]
  Une corrélation de Spearman positive significative montre que, plus un service est jugé prioritaire, plus il est jugé satisfaisant, ce qui aide à hiérarchiser les actions d’amélioration.[12][3]
  
  ***
- ## Tests non paramétriques (alternatives robustes)
- ### 14. Test de Mann‑Whitney U (Wilcoxon rank‑sum)
- **Objectif** : comparer deux groupes indépendants sur une variable ordinale ou quantitative non normale, en testant un décalage de distributions (souvent interprété sur la médiane).[1][12][3]
- **Données** : deux groupes indépendants, au moins niveau ordinal, distributions de forme similaire.[12][13][10]
- **H0** : les deux distributions sont identiques (aucune différence systématique).[12][13][10]
  
  **Exemple / plus‑value**  
  On compare le niveau d’anxiété (échelle 0–10, très asymétrique) entre un groupe traité et un groupe contrôle.[1][12]
  Un $$p < 0{,}05$$ indique que les rangs d’anxiété diffèrent significativement entre groupes, ce qui permet de conclure à un effet du traitement sans exiger la normalité.[12][13][10]
  
  ***
- ### 15. Test de Wilcoxon pour échantillons appariés (signed‑rank)
- **Objectif** : alternative non paramétrique du t‑test apparié, pour comparer deux mesures appariées lorsque les différences ne sont pas normales.[12][9][10]
- **Données** : données au moins ordinales, couples appariés, distribution symétrique des différences.[12][10]
- **H0** : la distribution des différences est centrée sur zéro.[12]
  
  **Exemple / plus‑value**  
  On mesure une échelle de douleur (0–10) avant et après une nouvelle thérapie chez les mêmes patients, avec forte asymétrie.[12][9]
  Un résultat significatif montre que la médiane des différences est non nulle, ce qui fournit une preuve robuste d’amélioration même avec des distributions atypiques.[12][9][10]
  
  ***
- ### 16. Test de Kruskal‑Wallis
- **Objectif** : alternative non paramétrique de l’ANOVA à un facteur, pour comparer 3 groupes ou plus sur des données ordinales ou non normales.[1][12][9]
- **Données** : groupes indépendants, au moins ordinales, variances non forcément homogènes.[12][9][10]
- **H0** : toutes les distributions (ou médianes) sont identiques.[12][9]
  
  **Exemple / plus‑value**  
  On compare des scores de satisfaction (échelles ordinales) pour 4 marques différentes.[1][12]
  Si $$p < 0{,}05$$, on conclut que les marques ne sont pas équivalentes aux yeux des clients, ce qui permet de positionner une marque par rapport aux concurrentes sans imposer la normalité.[12][9][10]
  
  ***
- ### 17. Test de Friedman
- **Objectif** : alternative non paramétrique de l’ANOVA à mesures répétées, pour comparer plusieurs conditions répétées sur les mêmes sujets avec données ordinales ou non normales.[12][9]
- **Données** : mesures répétées sur les mêmes individus, au moins ordinales.[9][10]
- **H0** : les distributions (ou médianes) sont identiques entre conditions.[9]
  
  **Exemple / plus‑value**  
  On compare la satisfaction d’utilisateurs sur 3 versions successives d’une interface, évaluée par les mêmes personnes.[9]
  Un test de Friedman significatif indique que les versions ne sont pas jugées équivalentes, ce qui aide à choisir la version la plus acceptable même avec de petits effectifs et des échelles ordinales.[9][10]
  
  ***
- ## Tests de distribution et de survie
- ### 18. Test de Shapiro‑Wilk (normalité)
- **Objectif** : tester si une variable quantitative suit une distribution normale, ce qui conditionne l’usage de nombreux tests paramétriques.[2][10]
- **Données** : variable quantitative continue, taille d’échantillon petite à moyenne.[10]
- **H0** : la distribution de la population est normale.[2][10]
  
  **Exemple / plus‑value**  
  On teste la normalité des résidus d’un modèle de régression avant de l’interpréter.[10]
  Si $$p < 0{,}05$$, on remet en question l’hypothèse de normalité, ce qui incite à utiliser des méthodes robustes ou non paramétriques, améliorant la validité des conclusions.[2][10]
  
  ***
- ### 19. Test de Kolmogorov‑Smirnov (KS, ajustement de distribution)
- **Objectif** : comparer la distribution empirique d’un échantillon à une distribution théorique donnée (ex. normale, exponentielle) ou comparer deux distributions empiriques.[2][10]
- **Données** : variable continue, échantillons indépendants.[2][10]
- **H0** : les distributions comparées sont identiques.[2]
  
  **Exemple / plus‑value**  
  On vérifie si la distribution des temps d’attente en file suit une loi exponentielle (modèle théorique).  
  Si $$p < 0{,}05$$, on conclut que le modèle théorique ne décrit pas bien les données, ce qui évite de fonder des décisions opérationnelles sur un modèle inadapté (dimensionnement de personnel, etc.).[2][10]
  
  ***
- ### 20. Test du log‑rank (survie)
- **Objectif** : comparer des courbes de survie (temps jusqu’à un événement : décès, panne, échec) entre deux ou plusieurs groupes.[2]
- **Données** : temps de survie, souvent censurés, groupes indépendants.[2]
- **H0** : pas de différence entre les fonctions de survie des groupes.[2]
  
  **Exemple / plus‑value**  
  On compare la survie de patients sous deux traitements anticancéreux.[2]
  Un log‑rank significatif indique que les courbes de survie diffèrent, ce qui peut justifier la préférence pour un traitement offrant une meilleure probabilité de survie à long terme.[2]
  
  ***
- ## Comment utiliser ce panorama dans la pratique
- Commencer par identifier le **type de variable** (quantitative, ordinale, catégorielle) et la **structure des groupes** (indépendants/appariés, nombre de groupes).[2][7]
- Vérifier les **hypothèses** (normalité, homoscédasticité, linéarité) ; si elles ne sont pas plausibles, privilégier les tests non paramétriques.[12][2][10]
- Interpréter toujours un test en termes de **plus‑value décisionnelle** : que change concrètement la conclusion (rejeter ou non H0) pour la décision à prendre (changer de procédure, valider une formation, choisir un traitement, etc.).[4][3][5]
  
  Si tu veux, je peux t’organiser tout cela dans un tableau récapitulatif (test, type de données, hypothèses, alternative non paramétrique, interprétation typique) pour en faire une fiche de révision prête à imprimer.