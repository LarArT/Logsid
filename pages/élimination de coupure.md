- C'est une nuance importante : la règle **Mix** n'est pas l'élimination de coupure elle-même, mais une **généralisation de la règle de coupure** (*cut rule*). Gerhard Gentzen l'a conçue comme un outil intermédiaire pour pouvoir prouver son théorème d'élimination des coupures (*Hauptsatz*).
- ### Coupure classique vs Règle Mix
  
  Dans le calcul des séquents (systèmes LK ou LJ) :
- **Coupure classique :** Elle élimine une **seule** occurrence de la formule A partagée entre deux séquents :
  $\frac{\Gamma \vdash \Delta, A \quad A, \Sigma \vdash \Pi}{\Gamma, \Sigma \vdash \Delta, \Pi}$
- **Règle Mix :** Elle élimine **toutes** les occurrences de la formule A simultanément dans les deux séquents :
  $\frac{\Gamma \vdash \Delta \quad \Sigma \vdash \Pi}{\Gamma, \Sigma^* \vdash \Delta^*, \Pi}$
  
  (où $\Delta^*$ et \Sigma^* représentent les ensembles ou listes dont toutes les occurrences de A ont été supprimées).*
- ### Pourquoi Gentzen a-t-il utilisé Mix ?
  
  Lorsqu'on cherche à démontrer le théorème d'élimination des coupures par récurrence sur la taille de la preuve et la complexité de la formule, les règles de **contraction** (qui dupliquent une formule) posent un problème majeur. Avec la règle de coupure classique, supprimer une contraction force à multiplier les coupures et fait capoter l'hypothèse de récurrence.
  
  En remplaçant provisoirement la coupure par la règle **Mix** :
- La règle "absorbe" naturellement les contractions.
- La récurrence pour éliminer les règles Mix de la preuve fonctionne parfaitement.
- Comme la coupure classique n'est qu'un cas particulier de la règle Mix, éliminer toutes les règles Mix élimine aussi toutes les coupures.