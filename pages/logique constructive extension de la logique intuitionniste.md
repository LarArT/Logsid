- La logique constructive et la logique intuitionniste sont deux approches de la logique mathématique étroitement liées, souvent confondues, mais qui présentent des nuances historiques et philosophiques distinctes. Toutes deux se caractérisent par le rejet du principe du tiers exclu (A \lor \neg A) et des preuves par l'absurde classiques.
  
  Voici une analyse comparative de ces deux concepts.
- ## 1. La logique intuitionniste : Les fondements philosophiques
  
  L'**intuitionnisme** est une philosophie des mathématiques formulée au début du XXe siècle par le mathématicien hollandais L.E.J. Brouwer.
- **La thèse centrale :** Les mathématiques sont une création de l'esprit humain. Un énoncé mathématique n'existe pas de manière indépendante dans un monde platonique ; il n'est vrai que si nous l'avons construit mentalement.
- **Le rejet du tiers exclu :** Pour Brouwer, affirmer A \lor \neg A signifie que nous disposons *soit* d'une preuve de A, *soit* d'une preuve de sa réfutation. Tant que nous n'avons ni l'une ni l'autre (comme pour la conjecture de Goldbach), nous ne pouvons pas affirmer la validité de A \lor \neg A.
- **Formalisation :** Bien que Brouwer ait été réticent à l'idée de formaliser sa pensée, c'est son élève Arend Heyting qui a structuré la **logique intuitionniste** sous forme de système formel (l'algèbre de Heyting).
- ## 2. La logique constructive : Une approche pragmatique et algorithmique
  
  La **logique constructive** est une extension et une généralisation technique de la logique intuitionniste. Elle se concentre sur l'effectivité et le contenu informationnel des preuves.
- **La thèse centrale :** Pour prouver l'existence d'un objet mathématique possédant une propriété donnée (\exists x, P(x)), il faut fournir une méthode explicite ou un algorithme permettant de construire cet objet x.
- **Rejet de la double négation :** En logique classique, prouver \neg \neg A (il est impossible que A soit faux) suffit à valider A. En logique constructive, éliminer la double négation (\neg \neg A \implies A) n'est pas admis d'office, car savoir qu'une chose n'est pas fausse ne donne pas l'algorithme pour la construire.
- **Lien avec l'informatique :** La logique constructive trouve son apogée dans l'informatique théorique, notamment via l'**isomorphisme de Curry-Howard**, qui établit qu'une preuve constructive correspond rigoureusement à un programme informatique, et que la proposition prouvée correspond au type de ce programme.
- ## 3. Les nuances entre "Intuitionniste" et "Constructive"
  
  Bien que les systèmes logiques formels sous-jacents soient souvent identiques, l'usage des termes diffère selon le contexte :
  
  | Critère | Logique Intuitionniste | Logique Constructive |
  
  | **Origine** | Philosophique (Brouwer, Heyting). | Technique et computationnelle (Markov, Bishop, Martin-Löf). |
  
  | **Postulat** | Basé sur l'intuition du temps et de l'esprit humain. | Basé sur la calculabilité et l'effectivité des procédures. |
  
  | **Objets d'étude** | Admet parfois des principes spécifiques (ex. les suites de choix libres de Brouwer) incompatibles avec la logique classique. | Reste strictement compatible avec la logique classique (toute preuve constructive est valide en logique classique). |
  
  > 
  
  **En résumé :** On utilise généralement le terme de *logique intuitionniste* lorsqu'on s'inscrit dans la tradition philosophique de Brouwer ou dans l'étude des systèmes formels purs (comme la logique propositionnelle intuitionniste). On préfère le terme de *logique constructive* lorsque l'accent est mis sur la calculabilité, la programmation, et l'implémentation dans des assistants de preuve (tels que Lean, Coq/Rocq ou Agda).
- ## 4. Sémantique de Brouwer-Heyting-Kolmogorov (BHK)
  
  Pour comprendre l'interprétation de ces logiques, la sémantique BHK définit la vérité non pas par des tables de vérité, mais par ce qui constitue une **preuve** :
- Une preuve de A \land B est un couple (p, q) où p est une preuve de A et q une preuve de B.
- Une preuve de A \lor B est une preuve de A ou une preuve de B, accompagnée d'une indication claire du membre choisi.
- Une preuve de A \implies B est une fonction (un algorithme) qui transforme toute preuve de A en une preuve de B.
- Une preuve de \neg A est une fonction qui transforme une preuve de A en une preuve de l'absurde (\bot).
- Une preuve de \exists x, P(x) est un couple (c, p) où c est un objet spécifique (le témoin) et p est une preuve que P(c) est vrai.