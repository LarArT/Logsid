Source:: mooc IMT statistiques pour l'ingénieur

- # Fiche de lecture approfondie – Thème 3 : Tests d’hypothèses et analyse de la variance
- ## 1. Objet et structure générale du document
  
  Le document est un support de cours de statistique pour ingénieur consacré au « Thème 3 : Tests d’hypothèses, analyse de la variance », rédigé par T. Verdel, F. Kosior et M. Sauceau à l’Institut Mines‑Télécom.[^1] Il vise à introduire et formaliser le raisonnement par tests statistiques, depuis les tests élémentaires sur une moyenne ou une proportion jusqu’à l’analyse de la variance (ANOVA) à un ou plusieurs facteurs, en incluant des tests non paramétriques usuels.[^1] L’ouvrage est structuré en huit chapitres de cours suivis d’une série d’exercices corrigés, avec une progression logique : principes généraux, tests de conformité, comparaisons de populations, tests d’ajustement, tests d’indépendance, tests non paramétriques, analyse de la variance à un facteur puis à deux facteurs.[^1]
  
  [^1]
- ## 2. Introduction : naissance du raisonnement par test d’hypothèses
  
  L’introduction part d’un exemple historique attribué à William Gosset (« Student ») travaillant pour la brasserie Guinness: il cherche à savoir si l’engrais a une influence sur le rendement de cultures de pomme de terre à partir des différences de rendement entre moitiés de parcelles traitées ou non.[^1] On considère les différences observées comme des réalisations d’une variable aléatoire de différence D et l’on formule l’hypothèse que l’engrais n’a pas d’effet, ce qui revient à supposer que l’espérance (la moyenne théorique) de D est égale à zéro.[^1] Le test consiste alors à vérifier si les valeurs observées peuvent être jugées compatibles avec cette hypothèse de moyenne nulle; si elles paraissent incompatibles, l’hypothèse d’absence d’effet est remise en cause et l’on conclut à l’influence de l’engrais.[^1]
  
  Cette démarche est décrite comme un raisonnement proche du raisonnement par l’absurde: on suppose une hypothèse de départ, puis on examine si les observations sont plausibles sous cette hypothèse; si ce n’est pas le cas, on rejette l’hypothèse initiale au profit d’une alternative.[^1] Les auteurs rappellent que ce cadre a été formalisé par Neyman et Pearson et qu’il constitue ce que l’on appelle un test d’hypothèses, approche aujourd’hui centrale en statistique inférentielle.[^1]
  
  [^1]
- ## 3. Chapitre 1 – Principe des tests d’hypothèses
- ### 3.1 Hypothèses simples et composites, erreurs de première et seconde espèce
  
  Le chapitre 1 introduit une variable aléatoire X dont la loi de probabilité dépend d’hypothèses que l’on souhaite tester, notées H0, H1, …, qui sont supposées définies précisément.[^1] Une hypothèse est dite simple lorsqu’elle détermine complètement la loi de X (par exemple « la proportion de pièces défectueuses est exactement 5% »); elle est dite composite lorsqu’elle ne la fixe pas entièrement, comme « la proportion de pièces défectueuses est au plus 5% ».[^1] On se place d’abord dans le cas de deux hypothèses simples H0 et H1 couvrant toutes les possibilités et l’on note que toute décision se ramène à affirmer H0 ou à affirmer H1.[^1]
  
  Les auteurs introduisent alors le tableau croisant « état réel du monde » (H0 vraie ou H1 vraie) et « décision prise » (accepter H0 ou accepter H1). On distingue deux types d’erreur : l’erreur de première espèce est le fait de rejeter H0 alors qu’elle est vraie; l’erreur de seconde espèce est le fait d’accepter H0 alors que c’est H1 qui est vraie.[^1] Dans la pratique, ces erreurs n’ont pas la même gravité, ce qui justifie de traiter H0 et H1 de manière asymétrique: on fixe d’abord une borne acceptable pour la probabilité d’erreur de première espèce, notée α, et l’on cherche ensuite à rendre aussi petite que possible la probabilité d’erreur de seconde espèce, notée β.[^1]
  
  [^1]
- ### 3.2 Région d’acceptation, région critique et puissance
  
  Pour relier la décision à l’observation de X, on définit : la région d’acceptation de H0 comme l’ensemble des valeurs observées pour lesquelles on décide que H0 est vraie, et la région critique (ou région de rejet) comme le complémentaire, où l’on décide en faveur de H1.[^1] La région d’acceptation est construite de façon que la probabilité, sous H0, de tomber dans la région critique soit égale à α : c’est le risque de première espèce choisi a priori; la probabilité, sous H1, de rester à tort dans la région d’acceptation est β, dont on souhaite minimiser la valeur.[^1]
  
  La puissance du test est définie comme 1 moins β: c’est la probabilité, en supposant H1 vraie, de rejeter effectivement H0 et donc de détecter la différence que l’on cherche à mettre en évidence.[^1] Un test est d’autant plus puissant, pour un niveau de risque de première espèce donné, que son risque de seconde espèce est faible.[^1]
  
  [^1]
- ### 3.3 Théorème de Neyman–Pearson (cas de deux hypothèses simples)
  
  Les auteurs exposent le cadre théorique dans lequel les densités de probabilité sous H0 et H1 sont notées f0(x) et f1(x) et la région d’acceptation recherchée doit satisfaire deux conditions: d’une part, la probabilité sous H0 d’être dans cette région vaut 1 moins α; d’autre part, la probabilité sous H1 d’y être est minimale.[^1] Le théorème de Neyman–Pearson affirme qu’un test optimal au sens de cette minimisation existe et qu’il correspond à comparer le rapport de vraisemblances f1(x) sur f0(x) à une constante seuil: la région critique est alors définie par les valeurs de x pour lesquelles ce rapport dépasse ce seuil.[^1]
  
  Ce principe est ensuite appliqué à des cas concrets comme le test sur une proportion, où la variable observée est le nombre d’unités défectueuses dans un échantillon, et le test sur une moyenne d’une variable normale, où la variable de décision est la moyenne empirique de l’échantillon.[^1] Dans ces exemples, les auteurs montrent comment, après simplification, la condition sur le rapport de vraisemblances se traduit par une condition de la forme « le nombre d’éléments défectueux est inférieur à une certaine valeur seuil » ou « la moyenne empirique est inférieure à une valeur seuil », les seuils étant fixés pour garantir le niveau α choisi.[^1]
  
  [^1]
- ### 3.4 Hypothèses composites et tests unilatéraux ou bilatéraux
  
  Dans de nombreux problèmes pratiques, la comparaison ne porte pas sur deux hypothèses simples mais sur une hypothèse nulle relativement précise H0 et une famille entière d’hypothèses alternatives H regroupées, par exemple, autour de l’idée que « le paramètre est supérieur à la valeur sous H0 » ou « différent de cette valeur ».[^1] Il est alors possible de construire, pour chaque hypothèse alternative ponctuelle de cette famille, une région d’acceptation par la méthode précédente, mais on cherche surtout des tests qui restent optimaux de manière uniforme sur l’ensemble des alternatives, ce qui conduit à la notion de test uniformément le plus puissant.[^1]
  
  Les auteurs expliquent que, dans de nombreux cas usuels, l’exigence d’uniformité conduit à concentrer le risque α dans une seule extrémité de la distribution de la variable de décision lorsque l’on teste une hypothèse du type « paramètre égal à une valeur de référence » contre « paramètre plus grand que cette valeur », ce qui définit un test unilatéral à droite.[^1] De même, pour une alternative du type « paramètre plus petit que la valeur de référence », on construit un test unilatéral à gauche, tandis que pour une alternative « paramètre différent », on répartit le risque α sur les deux extrémités de la distribution et l’on obtient un test bilatéral, parfois qualifié de symétrique.[^1]
  
  [^1]
- ### 3.5 Démarche générale d’un test
  
  La fin du chapitre résume la démarche standard d’un test d’hypothèses en six étapes: formuler les hypothèses nulle et alternative, choisir la variable de décision calculée à partir de l’échantillon, fixer le risque α et en déduire la région d’acceptation ou la région critique, éventuellement calculer la puissance du test, calculer la valeur observée de la variable de décision, puis comparer cette valeur à la région critique pour décider de rejeter ou non H0.[^1] Les auteurs insistent sur le fait que le rejet d’H0 est une conclusion plus forte que son non‑rejet: ne pas rejeter ne signifie pas que l’hypothèse est vraie, mais seulement que les données ne sont pas en contradiction flagrante avec elle.[^1]
  
  [^1]
- ## 4. Chapitre 2 – Tests de conformité à un standard
- ### 4.1 Rappel des lois outils : loi normale centrée réduite, loi du khi‑deux, loi de Student
  
  Pour construire des tests de conformité à un standard, le document rappelle trois lois de probabilité fondamentales qui servent d’outils: la loi normale centrée réduite, la loi du khi‑deux, et la loi de Student.[^1] La loi normale centrée réduite modélise la distribution d’une variable normalisée, c’est‑à‑dire la différence entre une variable normale et sa moyenne, divisée par son écart‑type; cette transformation permet d’utiliser des tables universelles.[^1] La loi du khi‑deux est présentée comme la distribution de la somme des carrés d’un certain nombre de variables normales centrées réduites indépendantes; elle intervient notamment pour la variance d’un échantillon prélevé dans une population normale.[^1]
  
  La loi de Student est introduite comme la distribution du quotient entre une variable normale centrée réduite et la racine carrée d’une variable de type khi‑deux divisée par son nombre de degrés de liberté; elle intervient pour les tests sur la moyenne lorsque la variance de la population est inconnue.[^1] Ces rappels s’accompagnent de corollaires reliant la moyenne empirique et la variance empirique d’un échantillon normal à ces lois, ce qui servira de base à la construction des tests.[^1]
  
  [^1]
- ### 4.2 Test de conformité sur la moyenne, variance connue
  
  Dans ce cas, on souhaite vérifier si la moyenne d’une variable aléatoire normale de variance supposée connue est égale à une valeur standard µ0, à partir de la moyenne empirique d’un échantillon.[^1] L’hypothèse nulle énonce que la moyenne théorique est égale à cette valeur de référence; l’hypothèse alternative affirme qu’elle est différente, ce qui conduit généralement à un test bilatéral.[^1] En supposant que l’hypothèse nulle est vraie, la moyenne empirique suit une loi normale de moyenne µ0 et de variance égale à la variance connue divisée par la taille de l’échantillon.
  
  On définit alors une variable de décision qui est la différence entre la moyenne empirique et la moyenne de référence, divisée par l’écart‑type de la moyenne empirique, ce qui produit une variable suivant la loi normale centrée réduite.[^1] Pour un risque α donné, on détermine un intervalle symétrique autour de zéro, dans lequel cette variable a une probabilité de 1 moins α de se situer; les valeurs en dehors de cet intervalle constituent la région critique, et si la valeur calculée à partir des données se situe dans cette région, on rejette l’hypothèse nulle en acceptant un risque α de la rejeter à tort.[^1]
  
  [^1]
- ### 4.3 Test de conformité sur la moyenne, variance inconnue
  
  Lorsque la variance de la population est inconnue, on ne peut plus standardiser la moyenne empirique par un écart‑type connu; on utilise alors conjointement la moyenne et l’écart‑type empiriques, ce qui conduit à une variable de décision suivant une loi de Student avec un nombre de degrés de liberté égal à la taille de l’échantillon moins un.[^1] On construit une variable de décision égale à la différence entre la moyenne empirique et la valeur de référence, divisée par l’écart‑type empirique rapporté à la racine carrée de la taille de l’échantillon diminuée d’une unité, puis on compare cette valeur observée aux quantiles de la loi de Student pour un niveau de risque choisi.[^1]
  
  La procédure de décision est analogue à celle du cas à variance connue: pour un test bilatéral, l’hypothèse nulle est rejetée si la valeur calculée en valeur absolue dépasse une valeur critique lue dans les tables de Student, autrement l’hypothèse nulle n’est pas rejetée.[^1] Les auteurs illustrent cette situation avec des exemples où la connaissance ou non de la variance change la conclusion du test, ce qui montre l’impact de l’incertitude sur l’estimation de la variabilité.[^1]
  
  [^1]
- ### 4.4 Test de conformité sur la variance d’une variable normale
  
  Ici, la question est de savoir si la variance d’une variable à distribution normale correspond à une valeur de référence; on construit pour cela une variable de décision qui est égale à la taille de l’échantillon multipliée par la variance empirique, divisée par la variance hypothétique.[^1] Sous l’hypothèse nulle, cette variable suit une loi du khi‑deux avec un nombre de degrés de liberté égal à la taille de l’échantillon moins un; on détermine donc un intervalle d’acceptation à partir des quantiles de cette loi pour un niveau de risque fixé.[^1]
  
  Si la valeur observée de la variable de décision est en dehors de cet intervalle, on rejette l’hypothèse sur la variance; sinon, on ne peut pas la rejeter, même si cela ne prouve pas qu’elle est exacte.[^1] L’exemple présenté, portant sur l’épaisseur d’un fil d’acier, montre comment un test unilatéral vers la droite permet de vérifier si la dispersion est supérieure à ce que spécifie un fabricant.[^1]
  
  [^1]
- ### 4.5 Test des appariements (données appariées)
  
  Dans ce cas, on observe des couples de mesures liées, par exemple deux méthodes de mesure appliquées au même support ou deux traitements appliqués sur deux moitiés d’une même parcelle; on calcule alors pour chaque couple une différence qui constitue la variable étudiée.[^1] Le test de l’hypothèse nulle selon laquelle l’effet moyen est nul se ramène à un test sur la moyenne d’une variable normale, en appliquant les méthodes précédentes au jeu de différences, éventuellement avec la loi de Student si la variance est inconnue.[^1]
  
  Les auteurs estiment que ce test sur données appariées est souvent plus puissant qu’un test de comparaison de moyennes réalisé sur des échantillons indépendants, car il permet de neutraliser une partie de la variabilité commune aux deux mesures; ils illustrent cette puissance accrue par des exemples où le test apparié met en évidence une différence significative là où le test sur échantillons indépendants ne le permet pas.[^1]
  
  [^1]
- ## 5. Chapitre 3 – Tests de comparaison de deux populations normales
- ### 5.1 Comparaison des variances : test de Fisher–Snedecor
  
  Ce chapitre vise à comparer deux populations normales, en examinant d’abord si leurs variances peuvent être considérées comme égales, avant de comparer leurs moyennes.[^1] On suppose que l’on dispose de deux échantillons indépendants issus de ces populations, avec des tailles éventuellement différentes et des variances empiriques associées; sous l’hypothèse d’égalité des variances théoriques, les estimations non biaisées des variances sont des multiples des variances empiriques.[^1]
  
  Le test consiste à considérer le rapport entre ces deux estimations: si l’hypothèse d’égalité des variances est vraie, ce rapport ne s’écarte de la valeur unitaire que du fait des fluctuations d’échantillonnage et suit une loi de Fisher-Snedecor avec des degrés de liberté liés aux tailles des échantillons.[^1] On compare alors la valeur observée de ce rapport aux quantiles de cette loi pour déterminer si la différence observée est compatible avec l’hypothèse d’égalité des variances ou si elle doit être jugée significative pour un niveau de risque donné.[^1]
  
  [^1]
- ### 5.2 Estimation de la variance commune
  
  Lorsque le test précédent ne conduit pas à rejeter l’hypothèse d’égalité des variances, il est utile d’estimer la valeur commune de cette variance, qui sera ensuite utilisée pour les tests sur les moyennes.[^1] On montre que la somme pondérée des variances empiriques, chaque variance étant pondérée par sa taille d’échantillon moins une unité, fournit un estimateur sans biais de la variance commune.[^1]
  
  Cet estimateur agrège l’information sur la variabilité provenant des deux échantillons et sa variance décroît lorsque la taille totale des observations augmente; il joue un rôle central dans la construction du test t de Student pour la comparaison des moyennes de deux échantillons indépendants.[^1]
  
  [^1]
- ### 5.3 Comparaison des moyennes: test t pour échantillons indépendants
  
  On s’intéresse ensuite à savoir si les moyennes de deux populations normales sont égales; on suppose les variances égales et estimées par la variance commune dérivée ci‑dessus.[^1] Sous l’hypothèse d’égalité des moyennes, la différence entre les moyennes empiriques des deux échantillons suit une loi normale d’espérance nulle et de variance dépendant de la variance commune et des tailles des échantillons.[^1]
  
  On construit alors une variable de décision égale à la différence entre les deux moyennes empiriques divisée par l’écart‑type de cette différence, calculée à partir de la variance commune; cette variable suit une loi de Student avec un nombre de degrés de liberté égal à la somme des tailles des échantillons moins deux.[^1] Le test consiste à comparer la valeur observée de cette variable aux quantiles de la loi de Student pour un niveau de risque α; si la valeur en valeur absolue dépasse le seuil, on conclut que la différence entre moyennes est significative au niveau choisi.[^1]
  
  [^1]
- ### 5.4 Estimation de la différence des moyennes
  
  Lorsque la différence observée entre moyennes est jugée significative, il est intéressant de fournir un intervalle de confiance pour la différence réelle entre les moyennes des populations.[^1] La variable différence entre moyennes empiriques est un estimateur sans biais de la différence des moyennes théoriques; la construction d’un intervalle de confiance repose sur la loi de Student décrite précédemment et fournit un encadrement probabiliste de cette différence.[^1]
  
  L’intervalle de confiance est centré sur la différence observée et s’étend de part et d’autre d’une quantité proportionnelle au quantile de Student et à l’écart‑type estimé de la différence; il traduit l’incertitude résiduelle liée à la variabilité d’échantillonnage.[^1]
  
  [^1]
- ## 6. Chapitre 4 – Tests d’ajustement (ou tests d’adéquation)
- ### 6.1 Choix du type de loi de référence
  
  Le document aborde ensuite la question de vérifier si une distribution observée peut être raisonnablement décrite par une loi de probabilité théorique (loi de référence), par exemple une loi uniforme discrète, une loi binomiale, une loi de Poisson ou une loi normale.[^1] Il est indiqué qu’il n’existe pas de recette systématique pour choisir cette loi de référence: on se laisse guider par la nature de la variable (discrète ou continue), des considérations théoriques et l’allure empirique de la distribution.[^1]
  
  Pour la normalité, les auteurs rappellent des critères empiriques: la symétrie de la distribution, la proportion d’observations dans les intervalles centrés autour de la moyenne (par exemple 68% dans un intervalle d’un écart‑type autour de la moyenne), ou encore des outils graphiques comme la « droite de Henry » ou les diagrammes quantile‑quantile, qui transforment une distribution normale en une droite si l’hypothèse est plausible.[^1]
  
  [^1]
- ### 6.2 Estimation des paramètres de la loi de référence
  
  Une fois le type de loi de référence choisi, il faut en estimer les paramètres à partir des données: par exemple, la probabilité de succès dans une loi binomiale ou la moyenne et l’écart‑type dans une loi normale.[^1] Le document préconise l’usage des estimateurs usuels, tels que la moyenne empirique et la variance empirique pour une loi normale, qui sont des estimateurs sans biais ou convergents selon les cas.[^1]
  
  Ces estimations servent ensuite à calculer les probabilités théoriques associées aux classes ou catégories observées, ce qui permettra de comparer la distribution observée à la distribution théorique via un test de khi‑deux.[^1]
  
  [^1]
- ### 6.3 Test du khi‑deux d’adéquation
  
  Le test d’ajustement retenu est fondé sur une statistique de type khi‑deux qui cumule les écarts entre les effectifs observés et les effectifs théoriques calculés avec la loi de référence.[^1] Pour un échantillon de taille n, réparti en k classes, on note pour chaque classe l’effectif observé et l’effectif théorique égal à n multiplié par la probabilité théorique; on définit alors une statistique qui est la somme, sur toutes les classes, des carrés de la différence entre effectifs observés et théoriques, divisés par l’effectif théorique.[^1]
  
  Sous l’hypothèse nulle d’un bon ajustement et à condition que les effectifs théoriques ne soient pas trop faibles, cette statistique suit approximativement une loi du khi‑deux avec un nombre de degrés de liberté égal au nombre de classes diminué d’une unité et du nombre de paramètres estimés.[^1] On compare sa valeur observée à un seuil lu dans les tables; si la statistique dépasse ce seuil, on considère qu’il est préférable de remettre en cause l’hypothèse d’adéquation, sinon les données ne justifient pas de la rejeter.[^1]
  
  [^1]
- ## 7. Chapitre 5 – Tests d’indépendance
  
  Le chapitre 5 présente un test d’indépendance entre deux variables qualitatives observées sur un même échantillon, utilisé notamment en analyse de tableaux de contingence.[^1] On commence par recenser, dans un tableau à r lignes et s colonnes, les effectifs observés pour chaque combinaison de modalités des deux variables; les totaux en ligne et en colonne sont également calculés.[^1]
  
  Sous l’hypothèse nulle d’indépendance, la probabilité de se trouver dans une case donnée est égale au produit des probabilités marginales en ligne et en colonne; on en déduit un effectif théorique pour chaque case égal au total de la ligne multiplié par le total de la colonne, le tout divisé par l’effectif total.[^1] La statistique de test est alors une somme de termes de type « carré de la différence entre effectif observé et effectif théorique divisé par l’effectif théorique », sur l’ensemble des cases; sous H0 et sous des conditions de taille suffisante des effectifs, elle suit une loi du khi‑deux avec un nombre de degrés de liberté égal au produit du nombre de lignes moins un par le nombre de colonnes moins un.[^1]
  
  [^1]
- ## 8. Chapitre 6 – Autres tests non paramétriques
- ### 8.1 Comparaison de plusieurs populations qualitatives
  
  Les auteurs étendent le cadre du test d’indépendance au cas où l’on souhaite comparer plusieurs populations qualitatives, en les considérant comme un facteur de groupement et en regardant la répartition dans des catégories communes.[^1] La structure du tableau est comparable à celle du test d’indépendance, et la statistique de test est de la même forme, ce qui permet d’évaluer l’hypothèse « les populations ont la même distribution sur les catégories ».[^1]
  
  La conclusion repose sur la comparaison de la statistique observée à la loi du khi‑deux avec un nombre de degrés de liberté adapté aux nombres de populations et de catégories; si la statistique est trop grande, on rejette l’hypothèse d’égalité des distributions.[^1]
  
  [^1]
- ### 8.2 Test de la médiane
  
  Le test de la médiane est proposé pour comparer deux populations sans faire d’hypothèse de normalité, en se focalisant sur la position centrale plutôt que sur la moyenne.[^1] On fusionne les résultats des deux échantillons, on les ordonne et l’on détermine la médiane globale; on compte ensuite, pour chaque échantillon, combien d’observations sont au‑dessus et au‑dessous de cette médiane.[^1]
  
  Sous l’hypothèse d’égalité des populations, la proportion théorique d’observations au‑dessus et au‑dessous de la médiane est d’environ une moitié pour chacune; on construit donc un tableau de fréquence et on applique un test de khi‑deux avec un degré de liberté pour décider si la répartition observée est compatible avec cette hypothèse.[^1]
  
  [^1]
- ### 8.3 Test des signes
  
  Le test des signes s’applique en contexte de données appariées lorsque l’on souhaite tester si une différence systématique existe entre deux méthodes ou deux conditions, sans supposer de distribution particulière pour les différences.[^1] Pour chaque couple de mesures, on calcule la différence et l’on ne retient que le signe (positif ou négatif), en ignorant les valeurs exactes.[^1]
  
  Sous l’hypothèse nulle d’absence de différence systématique, la probabilité qu’une différence soit positive est égale à celle qu’elle soit négative, soit une moitié; le nombre de différences positives suit alors une loi binomiale de paramètres la taille de l’échantillon et une moitié, ce qui permet de construire une région critique à partir de cette loi ou, pour des tailles plus grandes, d’utiliser une approximation par une loi du khi‑deux.[^1] Le test consiste à déterminer si le nombre observé de signes d’un type est compatible avec cette loi, auquel cas on ne rejette pas H0, ou s’il est trop extrême pour le niveau de risque choisi, ce qui conduit à rejeter H0.[^1]
  
  [^1]
- ## 9. Chapitre 7 – Analyse de la variance à un facteur (ANOVA à un facteur)
- ### 9.1 Problématique et dispositif expérimental
  
  L’analyse de la variance est introduite via un exemple industriel: un fabricant d’ampoules électriques souhaite étudier l’influence de la nature du filament (facteur qualitatif à plusieurs modalités) sur la durée de vie des ampoules (variable quantitative).[^1] Pour ce faire, il réalise plusieurs séries d’ampoules, identiques en tous points sauf pour le type de filament, et mesure la durée de vie de plusieurs ampoules dans chaque série, ce qui fournit des colonnes de données correspondant aux différentes modalités du facteur.[^1]
  
  Plus généralement, le document présente l’ANOVA à un facteur comme la comparaison de plus de deux populations normales, où chaque colonne du tableau de données représente un échantillon d’une population différente et où l’on se demande si les différences observées entre moyennes de colonnes sont significatives ou uniquement dues aux fluctuations aléatoires.[^1]
  
  [^1]
- ### 9.2 Relation d’analyse de la variance (décomposition en sommes de carrés)
  
  La relation centrale de l’ANOVA décompose la somme totale des carrés des écarts des observations à la moyenne générale en deux composants: une somme de carrés due au facteur (variabilité entre colonnes) et une somme de carrés résiduelle (variabilité à l’intérieur des colonnes).[^1] Formellement, chaque observation est écrite comme la moyenne générale plus un effet de colonne plus un résidu; en élevant au carré et en sommant, le terme de produit croisé s’annule, ce qui donne l’égalité entre la somme totale des carrés, la somme de carrés expliquée par le facteur, et la somme de carrés résiduelle.[^1]
  
  À chaque somme de carrés est associé un nombre de degrés de liberté: la somme de carrés totale a un degré de liberté égal au nombre total d’observations moins un, la somme de carrés due au facteur a un degré de liberté égal au nombre de modalités moins un, et la somme de carrés résiduelle a un degré de liberté égal à la différence entre les deux précédents.[^1]
  
  [^1]
- ### 9.3 Modèle statistique et hypothèses
  
  Pour permettre l’inférence, le document suppose un modèle additif dans lequel chaque observation est égale à une constante globale, plus un effet fixe associé à la modalité du facteur, plus une erreur aléatoire.[^1] Les effets de facteur sont des quantités inconnues mais non aléatoires dont la somme pondérée par le nombre d’observations par modalité est nulle, ce qui fixe une origine; les erreurs aléatoires ont une espérance nulle, une variance commune et suivent des lois normales indépendantes.[^1]
  
  Une hypothèse clé est donc l’homoscédasticité: la variance de l’erreur est supposée identique pour toutes les modalités du facteur; cette hypothèse peut être testée par des tests de type Bartlett, bien que ceux‑ci soient sensibles à l’hypothèse de normalité.[^1]
  
  [^1]
- ### 9.4 Test F d’ANOVA à un facteur
  
  Sous l’hypothèse nulle selon laquelle le facteur n’a pas d’influence, tous les effets de facteur sont nuls et la variabilité entre moyennes de colonnes ne reflète que des fluctuations aléatoires; la somme de carrés due au facteur, divisée par son nombre de degrés de liberté, fournit alors un estimateur de la variance de l’erreur.[^1] De même, la somme de carrés résiduelle, divisée par son nombre de degrés de liberté, est aussi un estimateur de cette variance; le quotient entre ces deux estimateurs suit sous H0 une loi de Fisher-Snedecor avec un nombre de degrés de liberté égal à ceux du numérateur et du dénominateur.[^1]
  
  On obtient ainsi une statistique de test F qui, si elle est nettement supérieure à 1 et dépasse un seuil critique déterminé pour un niveau de risque α, conduit à rejeter l’hypothèse d’absence d’effet du facteur; dans le cas contraire, on ne peut pas conclure à une influence significative.[^1] Le document insiste sur le fait qu’il s’agit d’un test unilatéral à droite, car ce sont des valeurs élevées de la statistic F qui signalent une variabilité entre groupes supérieure à ce que l’on attendrait sous H0.[^1]
  
  [^1]
- ### 9.5 Mise en œuvre pratique et exemple numérique
  
  Pour la mise en œuvre pratique, les auteurs donnent des formules explicites de calcul des différentes sommes de carrés en fonction des observations, des moyennes par groupe et de la moyenne générale; ils résument ces informations dans un tableau d’ANOVA standard qui contient pour chaque source de variabilité la somme de carrés, le nombre de degrés de liberté, la moyenne de carrés et la statistique F correspondante.[^1] Un exemple détaillé portant sur des durées de vie d’ampoules de trois marques montre comment les calculs conduisent à une valeur de F significativement supérieure au seuil critique, ce qui permet de conclure à une différence significative de durée de vie entre les marques.[^1]
  
  [^1]
- ## 10. Chapitre 8 – Analyse de la variance à deux facteurs (plans factoriels)
- ### 10.1 Plan factoriel, effets principaux et interaction
  
  Le chapitre 8 généralise l’ANOVA au cas où deux facteurs sont étudiés simultanément, par exemple le genre et le niveau d’expertise dans un test de connaissances, avec une variable quantitative comme le score obtenu.[^1] Les modalités du premier facteur sont disposées en lignes et celles du second en colonnes, et pour chaque combinaison de modalités, on dispose d’un certain nombre de répétitions de la variable mesurée.[^1]
  
  Le modèle additif de base est étendu pour inclure non seulement les effets principaux de chaque facteur (effet moyen de passer d’une modalité du premier facteur à une autre, indépendamment du second, et réciproquement), mais aussi un terme d’interaction qui capture les effets spécifiques à chaque combinaison de modalités.[^1] L’interaction permet de modéliser le fait que l’effet d’un facteur puisse dépendre du niveau de l’autre facteur.[^1]
  
  [^1]
- ### 10.2 Décomposition en sommes de carrés et tests F
  
  La somme totale des carrés est décomposée en quatre composantes: une somme de carrés due au facteur A, une somme de carrés due au facteur B, une somme de carrés d’interaction entre A et B, et une somme de carrés résiduelle.[^1] À chacune de ces composantes sont associés des degrés de liberté, et l’on calcule les moyennes de carrés correspondantes; en divisant chaque moyenne de carrés par la moyenne de carrés résiduelle, on obtient trois statistiques F distinctes pour tester respectivement l’effet du facteur A, l’effet du facteur B, et l’existence d’une interaction.[^1]
  
  Pour chaque facteur ou interaction, on compare la valeur observée de la statistique F au quantile de la loi de Fisher-Snedecor appropriée; si la valeur dépasse le seuil critique pour un niveau α donné, on conclut à un effet significatif du facteur ou de l’interaction; sinon, on ne rejette pas l’hypothèse d’absence d’effet.[^1] Un exemple chiffré portant sur un test de connaissances conclut à un effet significatif du genre et de l’expertise, mais pas à une interaction significative entre ces deux facteurs.[^1]
  
  [^1]
- ### 10.3 Cas sans répétitions et modèle additif
  
  Dans certains cas, une seule observation est disponible pour chaque combinaison de modalités des deux facteurs, ce qui empêche d’estimer séparément une variabilité résiduelle pour l’interaction.[^1] Le document indique alors qu’il devient impossible de tester l’interaction de manière empirique et que l’on doit faire une hypothèse forte d’absence d’interaction, ce qui revient à adopter un modèle purement additif.[^1]
  
  Sous cette hypothèse, la somme de carrés d’interaction sert de référence pour estimer la variance résiduelle, et l’on construit des tests F pour les effets principaux en divisant les moyennes de carrés associées aux facteurs par la moyenne de carrés de l’interaction, interprétée comme une estimation de la variance de l’erreur.[^1] Les auteurs illustrent cette situation avec un exemple sur des compilateurs et des programmes, où l’on conclut à une influence significative du type de programme mais pas du compilateur sur le temps de compilation.[^1]
  
  [^1]
- ## 11. Chapitre 9 – Exercices
  
  La dernière partie du document regroupe une série d’exercices permettant de mettre en pratique les concepts et méthodes développés dans les chapitres précédents.[^1] Les exercices couvrent un large éventail de situations: rappel de tests sur une variance ou une moyenne, tests sur données appariées, comparaisons de deux populations, tests sur des variances, tests d’ajustement à une loi uniforme discrète ou à une loi de Poisson, tests d’ajustement à une loi normale, tests d’indépendance, ANOVA à un facteur, et ANOVA à deux facteurs.[^1]
  
  Ces exercices fournissent au lecteur l’occasion de consolider sa compréhension du formalisme des tests d’hypothèses, de la mise en œuvre des statistiques de test et de l’interprétation des résultats en termes de risque de se tromper et de signification pratique.[^1]
  
  [^1]
- ## 12. Appréciation critique et intérêt pour un profil « sécurité / gestion de projet »
  
  Pour un professionnel de la sécurité, de l’audit ou de la gestion de projet, ce document constitue une base solide pour comprendre et appliquer les tests statistiques dans des contextes de contrôle qualité, d’analyse de performance ou d’évaluation de mesures de sécurité.[^1] La rigueur de la démarche (formulation claire des hypothèses, maîtrise des risques de première et de seconde espèce, interprétation prudente des non‑rejets) est directement transposable aux revues de conformité, aux essais pilotes ou aux comparaisons de procédures.[^1]
  
  L’accent mis sur l’ANOVA et sur les plans factoriels est particulièrement pertinent pour analyser l’effet simultané de plusieurs facteurs sur une métrique de performance (par exemple, différents paramètres de configuration d’un système et différents scénarios de charge), tout en contrôlant statistiquement le risque de conclure à tort à un effet.[^1] Les tests non paramétriques complètent utilement l’outillage quand les hypothèses de normalité sont douteuses, situation fréquente dans les données opérationnelles ou de sécurité.[^1]
  
  ---
- ## References
  
  1. [T3_Final__1__copie.pdf](https://ppl-ai-file-upload.s3.amazonaws.com/web/direct-files/attachments/52474944/c1108cde-c9d9-4cf3-bcf3-eb41f1c656e5/T3_Final__1__copie.pdf?AWSAccessKeyId=ASIA2F3EMEYEX3NJG2US&Signature=CHO31kbQCg6RfxZNE%2FEhuzZDkUI%3D&x-amz-security-token=IQoJb3JpZ2luX2VjEBwaCXVzLWVhc3QtMSJGMEQCIDy3FFVeA3QUsazgazktL9r%2Br%2FiwLMWsehSfr3O1zdMjAiAenGYR5JduRCurvTnP7YqtPwffa2Dv%2FAMR0lQoZq%2FmTSr8BAjk%2F%2F%2F%2F%2F%2F%2F%2F%2F%2F8BEAEaDDY5OTc1MzMwOTcwNSIM6%2B5lkMFT7bm40dmUKtAEfXWh1w%2FYBz1WL2bboxSTe%2FJmCH9Ofn19zA82X7dBLwuAojcXRJgfyn%2FQPQdnqvZBh8iUdVbhvjdfrHx3%2BSR9JpTcxD0rA1LNJaptLnjjbnaTrkw%2F8GDrezwwWzGm6KyTH9bRA9blzJFldNpI1oGBFRW1kJyjvQRq1FAIkIoftO0uN6Ayw9IJXP07fGS5nAu0OzNhnLuejShFvOj9WBVqZhiIceN9lFKdDFwGcMzdQMK71Bq4l2cVk864ccXz4yXcMlI3OB771gZsTHskeMJTDqgWgG%2Bsf3OIi4qrw7LtvVlyCBDEdzc6fK55OUYgSgTHG9%2B7Ca7CQIsJuL6OPCrZWzyF1B1ur8am%2Bv8JGVVAaClqNTV8cBOQsu9apFzKvgk%2BojOChPhQ8RByhfRhbd3WJhx%2Bk2UP9km%2BEnO6IbSW1typ3809h7YBmzwSMLaGmr5qJYk2y8QGquN6si%2FQARdSAU0IQirNy9KI3WtCW3uNzxyPjFkH7GAMMhmB9hVNpumtOFXKW2fZIUYw0kIHWwmA%2FUGH7oDW1DrWrYQDNNqzMJUyrlRVD%2BdtYJD38yRTr94RIzyZCzUwq3I08KcjiVEpGQacqX0bBnvTesi6kFDsFaUZxlPKwkhmLvIaOY38IbDBJv%2FHNZbJUGY%2FTbRJFg%2FaPWHWq6x83dyAUe6i7goDFZxAtc%2F0e5HHBmyMKBVMO4b80X0rs6VcaxudrgCS3wEcmbXqhu%2BXytg3%2BCtHqYG0II8JI5mkvOtuVSf%2BvtzvURU%2FuKmlTe7EQM9Cysft8H88XjDSrN3RBjqZAbWSd3rwS7qwEMVWPYa8LXSOPQ4iI65L7hZpR2F41cSVEaNrmhL1lSx71oUa4k4%2BdsSoiXyF2qlIQMTcisEo9w3ZJ1bCrA%2BODb%2BMGIA%2BzJe8ZYMHUICrDt5jgQeRxhV2o37lb%2FXLMZpF6Ue2Ujmfze5ILunML224wHtSvND10%2B%2FxVzVG1QnGhR1pKykibFI%2BOCJLlt8P2wLSTQ%3D%3D&Expires=1782015013) - **page-1**
  Thème3:Testsd’hypothèses,analysedelavarianceStatistiquepouringénieurStatistiquepouringéni...