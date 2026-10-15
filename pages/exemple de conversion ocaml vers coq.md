Source:: https://lsv.ens-paris-saclay.fr/~fthire/teaching/2018-2019/projet-logique/cours/introduction.pdf

- ### Définition du type des entiers naturels ( `nat` )
- #### OCaml
  
  ```
  type nat = Z | S of nat
  ```
  
  *Figure 2: OCaml*
- #### Coq
  
  ```
  Inductive nat : Set :=
  | 0 : nat
  | S : nat -> nat.
  ```
  
  *Figure 3: Coq*
- ### Fonctions Récursives (1/2)
- #### OCaml
  
  ```
  let rec add n m =
  match n with
  | Z -> m
  | S n -> S (add n m)
  ```
  
  *Figure 4: OCaml*
- #### Coq
  
  ```
  Fixpoint add (n m : nat) : nat :=
  match n with
  | 0 => m
  | S n => S (add n m)
  end.
  ```
  
  *Figure 5: Coq*