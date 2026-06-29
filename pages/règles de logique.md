-
- Voici la retranscription des règles de déduction présentées dans le document, formatée en Markdown et optimisée pour votre système de gestion des connaissances **Logseq**.
  Chaque règle est présentée avec son nom, sa formule au format LaTeX (parfaitement interprétée par Logseq), et une explication synthétique orientée vers la recherche de preuve (de bas en haut) ou l'application (de haut en bas).
- ## 1. Règles Structurelles et Égalité
  * **Axiome (ax)**
   
   * *Sens :* Si la conclusion du séquent fait partie des hypothèses, le séquent est immédiatement prouvé (c'est une feuille terminale de l'arbre).
  * **Affaiblissement (af)**
   
   * *Sens :* Si on démontre A sous un ensemble d'hypothèses, ajouter une hypothèse supplémentaire B ne remet pas en cause la démonstration.
  * **Introduction de l'égalité ($=_i$)**
   
   * *Sens :* On peut toujours affirmer qu'un terme est égal à lui-même (réflexivité de l'égalité).
  * **Élimination de l'égalité ($=_e$)**
   
   * *Sens :* Si deux objets sont égaux (t=u), alors toute propriété vérifiée par t est également vérifiée par u.
- ## 2. Connecteurs Logiques (Calcul Propositionnel)
  * **Élimination de l'implication ($\rightarrow e$) / Modus Ponens**
   
   * *Sens :* Pour démontrer B, il suffit de trouver ou de démontrer un lemme A \rightarrow B, puis de démontrer A.
  * **Introduction de l'implication ($\rightarrow i$)**
   
   * *Sens :* Pour montrer que A \rightarrow B, on ajoute A aux hypothèses et on cherche à démontrer B.
  * **Introduction de la conjonction ($\wedge_i$)**
   
   * *Sens :* Pour prouver A \wedge B, il faut prouver séparément A d'une part, et B d'autre part.
  * **Élimination de la conjonction ($\wedge_e$)**
   
   * *Sens :* D'une hypothèse A \wedge B, on peut extraire librement soit A (élimination gauche), soit B (élimination droite).
  * **Introduction de la disjonction ($\vee_i$)**
   
   * *Sens :* Pour démontrer A \vee B, il suffit de démontrer l'un des deux membres (A ou B).
  * **Élimination de la disjonction ($\vee_e$) / Raisonnement par cas**
   
   * *Sens :* Si on sait que A \vee B est vrai, pour démontrer un objectif C, on traite le problème en deux cas distincts : en supposant A vrai, puis en supposant B vrai.
- ## 3. Négation et Absurde
  * **Introduction de la négation ($\neg_i$)**
   
   * *Sens :* Pour démontrer \neg A, on suppose A et on cherche à aboutir à une contradiction (\perp).
  * **Élimination de la négation ($\neg_e$)**
   
   * *Sens :* Si on a prouvé à la fois A et sa négation \neg A, on a mis en évidence une contradiction (\perp).
  * **Absurdité classique ($\perp_c$) / Raisonnement par l'absurde**
   
   * *Sens :* Pour démontrer A, on suppose sa négation (\neg A) et on cherche à obtenir une contradiction (\perp). *Note : Cette règle est spécifique à la logique classique.*
- ## 4. Quantificateurs (Logique du Premier Ordre)
  * **Introduction du quantificateur universel ($\forall_i$)**
   
   * *Sens :* Pour démontrer qu'une propriété est vraie pour tout x, on la démontre pour un x quelconque, ce qui impose que x n'apparaisse pas dans les hypothèses courantes.
  * **Élimination du quantificateur universel ($\forall_e$)**
   
   * *Sens :* Si une propriété est vraie pour tout x, on peut l'instancier en remplaçant x par n'importe quel terme spécifique t.
  * **Introduction du quantificateur existentiel ($\exists_i$)**
   
   * *Sens :* Pour prouver qu'il existe un x vérifiant la propriété A, il suffit de fournir un exemple de terme t (un témoin) qui la vérifie.
  * **Élimination du quantificateur existentiel ($\exists_e$)**
   
   * *Sens :* Si on sait qu'il existe un x vérifiant A, on peut utiliser cette hypothèse en introduisant un nouveau nom pour cet objet, à condition que ce nom n'intervienne pas déjà dans les hypothèses ou dans la conclusion finale C.
- **14:33** [[quick capture]]: