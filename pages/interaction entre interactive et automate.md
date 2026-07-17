Tags:: atp, smt, prover, hammer, nekola erc

- L'écosystème de la preuve formelle et de la résolution de problèmes mathématiques de haut niveau vit une convergence majeure entre les approches symboliques traditionnelles (comme la superposition) et l'intelligence artificielle (générative et par renforcement).
- ## ​1. Panorama des technologies similaires (Proving & Solvers)
  
  ​Autour de la superposition et de l'automatisation des assistants de preuve (Lean, Coq/Rocq, Isabelle), on trouve plusieurs familles de technologies complémentaires :
- ### ​A. Les SMT Solvers (Satisfiability Modulo Theories)
  
  ​Contrairement aux prouveurs par superposition (qui excellent sur l'égalité pure et le premier ordre général), les solveurs SMT intègrent des théories mathématiques spécifiques (arithmétique linéaire, tableaux, vecteurs de bits).
- ​**Technologies clés :** **Z3** (Microsoft), **cvc5**.
- ​**Lien avec la superposition :** Ils sont souvent appelés par les assistants de preuve via des *Hammers* pour clore des sous-buts arithmétiques ou logiques complexes.
- ### ​B. Les "Hammers" (Ponts d'automatisation)
  
  ​Ce sont des outils d'intégration qui traduisent le but d'un assistant de preuve (ordre supérieur) vers des formats acceptés par des prouveurs automatiques externes (premier ordre), puis réimportent la preuve validée.
- ​**Technologies clés :** **Sledgehammer** (pour Isabelle/HOL), **CoqHammer** (pour Coq/Rocq), **Duper / LeanHammer** (pour Lean).
- ### ​C. Les Prouveurs ATP de Premier Ordre classiques
  
  ​Ils reposent massivement sur le calcul de superposition classique et la résolution.
- ​**Technologies clés :** **Vampire**, **E Prover** (qui intègre désormais des concepts issus de la \lambda-superposition), **Zipperposition**