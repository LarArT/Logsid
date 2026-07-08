Tags:: logique intuitionniste, logique classique, logique du premier ordre, logique du second ordre, logique d'ordre supérieur, HOTT

- Pour comprendre l'organisation, il faut distinguer deux concepts clés :
- **L'expressivité du langage (Le "Quoi") :** Les objets que l'on a le droit de manipuler (propositions, objets, fonctions, types).
- **La philosophie de la vérité (Le "Comment") :** Les règles du jeu que l'on s'impose pour valider un raisonnement (accepte-t-on le tiers exclu ou non ?).
  
  La **logique classique** et la **logique intuitionniste** ne sont pas des embranchements ou des extensions comme la logique du premier ordre ou d'ordre supérieur. Ce sont des **systèmes de vérité (ou sémantiques)**. Ils peuvent s'appliquer à *tous* les niveaux d'expressivité que nous avons évoqués.
  
  Voici leur classification exacte sous forme de cartographie croisée.
- ## La matrice des logiques
  
  Pour savoir exactement où elles se situent, imaginez un tableau à double entrée. Le langage donne la structure, la philosophie (classique ou intuitionniste) donne les règles de preuve :
  
  | Niveau d'expressivité (Le Langage) | Déclinaison **Classique** 
  *(Avec Tiers Exclu & Double Négation)* | Déclinaison **Intuitionniste / Constructive** 
  *(Sans Tiers Exclu direct)* |
  
  | **Propositionnel** 
  *(Variables A, B sans quantificateurs)* | **Logique propositionnelle classique** 
  (Celle des tables de vérité standards) | **Logique propositionnelle intuitionniste** 
  (C'est là que \neg(A \land B) \not\implies \neg A \lor \neg B) |
  
  | **Premier Ordre** 
  *(Prédicats P(x) et quantificateurs \forall, \exists sur les objets)* | **Logique des prédicats classique** 
  (Utilisée en théorie des ensembles standard ZFC) | **Logique des prédicats intuitionniste** 
  (C'est là que \neg(\forall x, P(x)) \not\implies \exists x, \neg P(x)) |
  
  | **Ordre Supérieur / Types** 
  *(Quantifications sur les fonctions, prédicats de prédicats)* | **HOL classique** 
  (Le fondement logique par défaut de systèmes comme *Isabelle/HOL*) | **Théorie des Types de Martin-Löf / HoTT** 
  (Le cœur constructif de *Lean 4*, *Rocq/Coq*, *Agda*) |
- ## Ce qui les sépare fondamentalement à chaque niveau
- **Le camp Classique :** La vérité est *ontologique* (les choses sont vraies ou fausses dans l'absolu, indépendamment de notre esprit). Si une proposition n'est pas fausse, elle est obligatoirement vraie. Le principe du tiers exclu (A \lor \neg A) est un axiome universel.
- **Le camp Intuitionniste (Constructif) :** La vérité est *épistémique* (une proposition n'est vraie que si l'on possède une preuve ou une méthode effective pour la construire). Ne pas pouvoir prouver qu'une chose est vraie ne signifie pas qu'elle est fausse. Le tiers exclu est rejeté comme règle générale, car on ne peut pas affirmer d'emblée qu'un problème non résolu est résolu ou réfuté.
- ## Et le calcul des séquences ?
  
  Pour rappel, le **calcul des séquences** (ainsi que la *déduction naturelle*) est un outil de formalisation des preuves graphiques. Il s'adapte lui aussi aux deux camps :
- Si on autorise plusieurs formules à droite du tourniquet (\Gamma \vdash A, B), on obtient naturellement un calcul des séquences **classique**.
- Si on restreint le système à une seule formule au plus à droite (\Gamma \vdash A), on bloque structurellement la possibilité de prouver le tiers exclu, et on obtient un calcul des séquences **intuitionniste**.