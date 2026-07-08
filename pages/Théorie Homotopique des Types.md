Tags:: hott

- ​La HoTT est une approche beaucoup plus récente (initiée notamment par Vladimir Voevodsky à la fin des années 2000). Elle jette un pont révolutionnaire entre la **logique mathématique** (la théorie des types de Martin-Löf) et la **géométrie/topologie** (la théorie de l'homotopie).
- ​**Le principe (Isomorphisme de Curry-Howard étendu) :** * Un **type** n'est pas juste un ensemble, c'est un **espace topologique**.
	- ​Un **élément** d'un type est un **point** dans cet espace.
	- ​Une **preuve** qu'un objet a est égal à b (a = b) n'est pas un simple drapeau "vrai/faux", c'est un **chemin** (un lacet, une homotopie) reliant le point a au point b.
- ​**L'Univalence (L'Axiome d'Univalence) :** C'est le cœur de la HoTT. Il stipule que **l'équivalence est équivalente à l'égalité**. Si deux structures mathématiques sont isomorphes (par exemple, deux définitions équivalentes des nombres entiers), alors elles sont structurellement *égales*. On peut transférer automatiquement tous les théorèmes de l'une à l'autre sans réécrire la preuve.
- ​**Usage moderne :** C'est un domaine de recherche très actif. Des assistants de preuve comme **Coq / Rocq** ou **Agda** possèdent des extensions ou des modes dédiés à la HoTT.
-