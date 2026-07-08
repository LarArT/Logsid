- En logique intuitionniste, il est plus exact de dire que les lois de De Morgan ne fonctionnent que **partiellement**.
  
  En raison du rejet du principe du tiers exclu (A \lor \neg A) et de la règle de la double négation (\neg\negA \implies A), certaines équivalences de la logique classique se transforment en implications à sens unique.
  
  Voici l'état exact des quatre implications classiques en logique intuitionniste.
- ## 1. La négation de la disjonction (Valide)
  
  Cette loi fonctionne exactement comme en logique classique, dans les deux sens. L'équivalence suivante est **intuitionnistiquement valide** :
  
  $\neg(A \lor B) \iff \neg A \land \neg B$
- **Sens direct (\implies) :** Si on a une preuve que A \lor B mène à une contradiction, alors on peut prouver \neg A (car si A était vrai, A \lor B le serait, ce qui est absurde) et de même pour \neg B.
- **Sens réciproque (\impliedby) :** Si on a à la fois \neg A et \neg B, et que l'on suppose A \lor B, chaque cas de la disjonction mène immédiatement à une contradiction.
- ## 2. La négation de la conjonction (Partielle)
  
  C'est ici que la logique intuitionniste diverge de la logique classique. L'équivalence générale est perdue et seule **une unique implication** est valide :
  
  $\neg A \lor \neg B \implies \neg(A \land B)$
- ### Pourquoi le sens direct est valide ?
  
  Si l'on sait que \neg A est vrai (ou que \neg B est vrai), alors l'hypothèse A \land B (qui fournit à la fois A et B) mène directement à une contradiction.
- ### Pourquoi la réciproque (\neg(A \land B) \implies \neg A \lor \neg B) échoue ?
  
  En logique intuitionniste, pour prouver une disjonction X \lor Y, on doit disposer d'une méthode effective pour déterminer **lequel** des deux membres est vrai.
  
  Savoir que le couple (A, B) ne peut pas être simultanément vrai (\neg(A \land B)) ne donne pas d'information suffisante pour affirmer de manière constructive lequel des deux est faux.
  
  > 
  
  **Exemple classique :** Soit A une proposition mathématique non résolue (par exemple, la conjecture de Goldbach) et B sa négation (\neg A).
- La conjonction A \land \neg A est structurellement contradictoire, donc \neg(A \land \neg A) est trivialement vrai.
- Écrire la conclusion de De Morgan reviendrait à affirmer : \neg A \lor \neg\neg A.
- Or, affirmer cette disjonction exigerait de savoir aujourd'hui soit démontrer \neg A, soit démontrer \neg\neg A (ce qui revient souvent à démontrer A). Tant que le problème n'est pas résolu, le logicien intuitionniste ne peut pas valider cette disjonction.
- ## Résumé des forces logiques
  
  Le tableau suivant synthétise ce qui est démontrable en logique intuitionniste :
  
  | Forme Classique | Statut Intuitionniste | Forme Valide Démontrable |
  
  | \neg(A \lor B) \iff \neg A \land \neg B | **Valide** (Double implication) | \neg(A \lor B) \iff \neg A \land \neg B |
  
  | \neg(A \land B) \iff \neg A \lor \neg B | **Invalide** (Sens réciproque faux) | \neg A \lor \neg B \implies \neg(A \land B) |
  
  On peut toutefois récupérer une version affaiblie de la réciproque manquante en introduisant une double négation devant la disjonction : \neg(A \land B) \implies \neg\neg(\neg A \lor \neg B).