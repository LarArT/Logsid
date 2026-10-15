- La correspondance entre la logique (le raisonnement) et la programmation (l'exécution), illustrée par la vidéo, a quitté le domaine purement théorique pour devenir une réalité dans plusieurs langages.
  Voici les implémentations les plus emblématiques et comment elles utilisent ces concepts.
- ### 1. Scheme (et les Lisp)
  C'est le langage "historique" pour manipuler les continuations.
  * **Implémentation :** Il possède la primitive call/cc (*call-with-current-continuation*).
  * **Exemple :** Comme évoqué dans la vidéo, call/cc permet de capturer l'état d'exécution du programme dans une variable. On peut ensuite "revenir" à ce point précis, même si on est sorti de la fonction, ce qui permet de réaliser des recherches avec retour en arrière (*backtracking*) ou de gérer des flux de contrôle complexes sans utiliser de structures classiques.
- ### 2. Haskell (Le roi des langages fonctionnels typés)
  Haskell pousse la logique Curry-Howard à son paroxysme.
  * **Implémentation :** Bien qu'il n'utilise pas de "sauts" comme call/cc, il utilise les **Monades** pour gérer les effets (comme les exceptions, l'état ou l'entrée/sortie) tout en restant dans un cadre purement logique.
  * **Exemple :** La bibliothèque Cont (pour *Continuation Monad*) permet de transformer n'importe quel programme en style CPS (*Continuation Passing Style*). Cela permet de transformer une structure de contrôle complexe en une série de fonctions qui se passent la main, rendant le flux d'exécution explicite.
- ### 3. Coq et Agda (Les assistants de preuves)
  Ce ne sont pas des langages de programmation "généralistes", mais des langages dans lesquels on prouve des théorèmes.
  * **Implémentation :** Ils sont basés sur la logique intuitionniste pure. Chaque programme que vous écrivez dans Coq est mathématiquement prouvé comme étant "correct" vis-à-vis de sa spécification.
  * **Exemple :** Si vous écrivez une fonction de tri dans Coq, vous devez démontrer logiquement que le résultat est bien trié. Le compilateur (l'assistant de preuve) refuse de compiler tant que la preuve logique n'est pas complète. C'est l'application directe de "Programmer = Démontrer".
- ### 4. OCaml et Rust
  Ces langages modernes intègrent des concepts logiques pour garantir la sécurité.
  * **OCaml :** Utilise un système de types très riche issu de la logique. Bien qu'il permette des effets de bord, sa gestion des types aide énormément à structurer le raisonnement logique du programme.
  * **Rust :** Son système de "propriété" (*Ownership*) et d'emprunt (*Borrowing*) est, en réalité, une forme de **logique linéaire** appliquée à la gestion de la mémoire. Le compilateur Rust effectue une "preuve logique" de la validité de l'accès à la mémoire avant même d'exécuter le programme.
- ### Résumé des concepts appliqués
  | Concept Logique | Implémentation informatique | Langage type |
  |---|---|---|
  | **Logique intuitionniste** | Types algébriques / Fonctions pures | Coq, Agda, Haskell |
  | **Contrôle/Saut (Loi de Pierce)** | Continuations (call/cc) | Scheme, Racket |
  | **Gestion de mémoire/Ressources** | Logique linéaire | Rust |
  | **Effets de bord** | Monades | Haskell, OCaml |
  **Pour aller plus loin :**
  Si vous souhaitez expérimenter ces idées, le langage **Racket** (un descendant de Scheme) est le meilleur point d'entrée pour manipuler concrètement les continuations. Pour le côté "Démontrer c'est programmer", je vous recommande d'explorer **Coq**, qui permet de voir en temps réel comment une preuve se transforme en code exécutable.
  Souhaitez-vous que je développe un exemple de code simple (en Scheme ou Haskell) illustrant l'utilisation des continuations ?