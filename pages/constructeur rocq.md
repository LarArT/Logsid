- Rapide introduction à coq par Yves bertot
- ### 2.3 Définir son propre type de données
  
  Nous pouvons également définir un nouveau type de données en décrivant chacun des cas possibles pour ce type de données. Par exemple, nous pouvons définir un type de données avec deux cas, le premier qui regroupe deux entiers et le deuxième qui ne contient qu’une chaîne de caractères :
  
  ```
  Inductive ex_type : Type :=
  case1 (n1 n2 : Z)
  | case2 (s : string).
  ```
  
  Pour construire des éléments de ce type, on va pouvoir utiliser directement les fonctions `case1` et `case2`, en leur donnant les arguments appropriés. Par exemple, voici deux définitions d’éléments du type `ex_type`.
  
  ```
  Definition vex1 : ex_type := case1 1 3.
  Definition vex2 : ex_type := case2 "hello world!".
  ```
  
  Les fonctions qui décrivent chacun des cas sont appelées des *constructeurs*. Dans le type `ex_type` les constructeurs sont `case1` et `case2`.
  
  Lorsque l’on écrit une fonction qui prend en argument un élément du type `ex_type` pour faire un traitement par cas, on doit donc couvrir les cas donnés par tous les constructeurs, ce qui va s’écrire comme dans l’exemple suivant :
  
  ```
  Definition ex_type_to_Z (v : ex_type) :=
  match v with
    case1 n1 n2 => n1 + n2
  | case2 s => 0
  end.
  ```