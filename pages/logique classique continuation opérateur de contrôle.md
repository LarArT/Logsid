- [[continuation aborder plus simplement]]
- [[implémentation dans différents langages de programmation]]
- Voici une fiche de lecture détaillée et pédagogique de la conférence de Xavier Leroy intitulée **"Programmer = démontrer ? La correspondance de Curry-Howard... (5)"** dispensée au Collège de France.
- # Fiche de Lecture : Logique Classique, Continuations et Opérateurs de Contrôle
- ## 1. Informations Générales
- **Conférencier :** Xavier Leroy
- **Institution :** Collège de France (Chaire Sciences logicielles)
- **Série :** Programmer = démontrer ? La correspondance de Curry-Howard
- **Date de publication :** 12 septembre 2022 (Cours de l'année 2018-2019)
- **Thématique :** Informatique théorique, logique mathématique, sémantique des langages de programmation.
- **Vidéo :** [Visionner sur YouTube](http://www.youtube.com/watch?v=riY9sDgzjNk)
- ## 2. Problématique et Objectif du Cours
  
  Le cours s'articule autour d'une question centrale : **Si la logique intuitionniste correspond parfaitement au lambda-calcul simplement typé, à quel paradigme de programmation correspond la logique classique ?**
  
  L'objectif est de formaliser la contrepartie calculatoire des principes classiques (comme le tiers exclu ou le raisonnement par l'absurde) en établissant un pont avec les **continuations** et les **opérateurs de contrôle non local** (comme le `call/cc` de Scheme).
- ## 3. Structure et Contenu Scientifique
- ### Étape 1 : Comprendre la Logique Classique via la Logique Intuitionniste [ [01:12](https://www.youtube.com/watch?v=riY9sDgzjNk&t=72) ]
  
  En logique intuitionniste, on rejette le principe du **tiers exclu** (P \lor \neg P) et l'**élimination de la double négation** (\neg \neg P \implies P). Xavier Leroy rappelle que ce rejet a historiquement provoqué de vifs débats, notamment l'opposition d'indignation de David Hilbert [[02:17](https://www.youtube.com/watch?v=riY9sDgzjNk&t=137)].
  
  Le cours prend le contre-pied historique : utiliser la logique intuitionniste comme base stable pour coder et injecter la logique classique via les **traductions négatives (par double négation)** :
- **Approche de Glivenko (1929) :** Pour les formules propositionnelles, P est prouvable classiquement si et seulement si \neg \neg P est prouvable intuitionnistement [[08:12](https://www.youtube.com/watch?v=riY9sDgzjNk&t=492)].
- **Traductions de Kolmogorov (1925), Gödel (1933) et Gentzen (1936) :** Permettent d'étendre ce principe aux quantificateurs (\forall, \exists) en insérant rigoureusement des doubles négations devant chaque connecteur [[09:22](https://www.youtube.com/watch?v=riY9sDgzjNk&t=562)].
- **Théorème de Friedman (1970) :** Introduction d'une négation relative à une formule cible R (au lieu de l'absurdité \bot). Il démontre que toute formule \Pi_0^2 prouvable en arithmétique classique l'est aussi en arithmétique intuitionniste [[11:40](https://www.youtube.com/watch?v=riY9sDgzjNk&t=700)].
- ### Étape 2 : Théorie des Continuations et Transformation CPS [ [16:54](https://www.youtube.com/watch?v=riY9sDgzjNk&t=1014) ]
  
  Une **continuation** représente "le reste du calcul à effectuer" une fois qu'une sous-expression est évaluée [[17:11](https://www.youtube.com/watch?v=riY9sDgzjNk&t=1031)]. Elle peut être modélisée comme une fonction prenant le résultat intermédiaire pour produire le résultat final.
  
  Le cours détaille la **transformation CPS (*Continuation-Passing Style*)**, un outil sémantique traduisant un programme pour expliciter sa stratégie d'évaluation [[18:58](https://www.youtube.com/watch?v=riY9sDgzjNk&t=1138)] :
- **Appel par nom (*Call-by-name*) :** L'argument d'une fonction est passé sans évaluation préalable [[19:57](https://www.youtube.com/watch?v=riY9sDgzjNk&t=1197)].
- **Appel par valeur (*Call-by-value*) :** L'argument est d'abord réduit à une valeur avant d'être lié [[19:34](https://www.youtube.com/watch?v=riY9sDgzjNk&t=1174)].
- ### Étape 3 : Opérateurs de Contrôle et Effets "Faustiens" [ [25:09](https://www.youtube.com/watch?v=riY9sDgzjNk&t=1509) ]
  
  Les opérateurs de contrôle permettent de capturer la continuation courante sous forme de fonction de première classe. Le plus célèbre est **call/cc** (*call-with-current-continuation*) [[26:38](https://www.youtube.com/watch?v=riY9sDgzjNk&t=1598)].
- Xavier Leroy illustre son utilité pratique pour implémenter des mécanismes complexes comme le *backtracking* (retour en arrière) dans l'exploration de listes [[29:54](https://www.youtube.com/watch?v=riY9sDgzjNk&t=1794)].
  
  **Le cœur de la correspondance (Griffin, 1990) :** [[42:26](https://www.youtube.com/watch?v=riY9sDgzjNk&t=2546)] Timothy Griffin a découvert que les opérateurs de contrôle reçoivent des types qui correspondent exactement aux lois de la logique classique :
- Le type de `call/cc` correspond à la **loi de Clavius** (ou *mirabile elegantia*) : (\neg P \implies P) \implies P [[43:51](https://www.youtube.com/watch?v=riY9sDgzjNk&t=2631)].
- Le type de l'opérateur `C` (Felleisen) correspond à l'**élimination de la double négation** [[44:44](https://www.youtube.com/watch?v=riY9sDgzjNk&t=2684)].
  
  Pour expliquer de manière pédagogue comment `call/cc` permet de "prouver" le tiers exclu, l'orateur utilise une allégorie théâtrale : le **pacte faustien avec le Diable** [[47:21](https://www.youtube.com/watch?v=riY9sDgzjNk&t=2841)]. Le programme triche avec le temps et le contexte : il formule une promesse (l'un des côtés de l'alternative) et, si le contexte le contredit plus tard, il utilise la continuation pour remonter le temps et changer son choix initial [[49:12](https://www.youtube.com/watch?v=riY9sDgzjNk&t=2952)].
- ### Étape 4 : Le Calcul des Séquents Classique et Dualité Symétrique [ [51:41](https://www.youtube.com/watch?v=riY9sDgzjNk&t=3101) ]
  
  La dernière partie introduit le **calcul des séquents classique** de Gentzen (1934), qui manipule des séquents à plusieurs conclusions (A_1, ... A_n \vdash B_1, ... B_m), restaurant une parfaite symétrie et dualité (Lois de De Morgan) [[53:13](https://www.youtube.com/watch?v=riY9sDgzjNk&t=3193)].
  
  La contrepartie informatique de cette symétrie se retrouve dans les travaux de Philip Wadler (2003) et le **calcul dual** [[58:13](https://www.youtube.com/watch?v=riY9sDgzjNk&t=3493)] :
- Un programme n'est plus un terme isolé, mais l'**interaction en parallèle entre un terme (le calcul) et un co-terme (le contexte / la pile)** [[56:54](https://www.youtube.com/watch?v=riY9sDgzjNk&t=3414)].
- ## 4. Synthèse et Conclusion Logique [ [01:04:52](https://www.youtube.com/watch?v=riY9sDgzjNk&t=3892) ]
  
  La réponse à la question "la logique classique a-t-elle un contenu calculatoire ?" est nuancée :
- **Le problème de la confluence :** Des logiciens comme Jean-Yves Girard ont soutenu que non, car l'élimination des coupures en logique classique pure souffre d'un manque de confluence (non-déterminisme, plusieurs réductions possibles pour une même preuve) [[01:05:12](https://www.youtube.com/watch?v=riY9sDgzjNk&t=3912)].
- **La solution informatique :** L'informatique théorique valide pourtant ce contenu calculatoire, à condition d'**accepter de briser la symétrie pure en fixant une stratégie d'évaluation** (appel par valeur ou appel par nom) [[01:06:35](https://www.youtube.com/watch?v=riY9sDgzjNk&t=3995)].
  
  **Conclusion majeure :** Les preuves classiques ne correspondent pas à des fonctions pures (lambda-calcul pur), mais à des **programmes avec effets de bord** (manipulation de pile, sauts non locaux, gestion du contrôle) [[01:07:03](https://www.youtube.com/watch?v=riY9sDgzjNk&t=4023)].
  
  *Les vues de vidéos YouTube seront stockées dans votre historique YouTube, et vos données seront stockées et utilisées par YouTube conformément à ses [Conditions d'utilisation](https://www.youtube.com/static?template=terms)*
  
  *Les vues de vidéos YouTube seront stockées dans votre historique YouTube, et vos données seront stockées et utilisées par YouTube conformément à ses [Conditions d'utilisation](https://www.youtube.com/static?template=terms)*