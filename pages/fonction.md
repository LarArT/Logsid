## Déclaration de fonction dans lean
- opaque f: Z -> Z
-
- ## définition de fonction dans lean
- def name (params1: type₁)... ): type
	- | $$patterns_1 => result_1$$
	  | $$patterns  _2 => result_2$$
-
- ## rocq
- Dans Rocq (comme dans Coq), pour déclarer un objet ou une fonction sans en fournir la définition (ce qui correspond exactement au mot-clé opaque ou axiom dans Lean), on utilise le mot-clé Parameter ou Axiom.
  Les deux mots-clés sont sémantiquement identiques pour le moteur de preuve, mais l'usage veut que l'on utilise Parameter pour les données/fonctions et Axiom pour les énoncés logiques.