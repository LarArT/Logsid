# Un exemple de réductions

Au départ, le terme possède **2 rédexes** : $$\underline{(\lambda y . \ \underline{(\lambda x . yxx)(\lambda z . z(xy))})(\lambda z' . z')}$$

---
- ### Chemin de gauche (Réduction du rédexe interne en premier)
- **Premier pas :** $$(\lambda y . y(\lambda z . z(xy))(\lambda z . z(xy)))(\lambda z' . z')$$
- **Deuxième pas :** $$(\lambda z' . z')(\lambda z . z(x(\lambda z' . z')))(\lambda z . z(x(\lambda z' . z')))$$
- **Troisième pas :** $$(\lambda z . z(x(\lambda z' . z')))(\lambda z . z(x(\lambda z' . z')))$$
  
  ---
- ### Chemin de droite (Réduction du rédexe externe en premier)
- **Premier pas :** $$(\lambda x . (\lambda z' . z')xx)(\lambda z . z(x(\lambda z' . z')))$$
- **Deuxième pas (séparation en deux sous-branches possibles) :**
	- *Sous-branche 1 :* Rejoint directement l'étape 3 du chemin de gauche : $$(\lambda z . z(x(\lambda z' . z')))(\lambda z . z(x(\lambda z' . z')))$$
	- *Sous-branche 2 :* Passe par le terme suivant avant de rejoindre l'étape suivante : $$(\lambda x . xx)(\lambda z . z(x(\lambda z' . z')))$$
	  
	  ---
- ### Convergence et Forme Normale
  
  Les deux chemins convergent ensuite vers les mêmes étapes finales :
- **Avant-dernière étape :** $$(\lambda z . z(x(\lambda z' . z')))(x(\lambda z' . z'))$$
- **Forme normale finale :** $$x(\lambda z' . z')(x(\lambda z' . z'))$$
  
  > 
  
  **Forme normale (= sans rédexe)**
  
  Les réductions **confluent**, et la forme normale est **unique**.
-