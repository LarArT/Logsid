Source:: [1] R. David, K. Nour, and C. Raffalli, Introduction à la logique : Théorie de la démonstration, 3rd ed., Dunod, Paris, 2023.

- [[langage]]
- [[termes]]
- [[variable libre variable lié]]
- [[formule close]]
- ### 1. Formule close
  
  Une **formule close** (ou *proposition*, *sentence*) est une formule du calcul des prédicats qui ne contient **aucune variable libre**.
- Toutes les variables qui y apparaissent sont liées par un quantificateur (\forall ou \exists).
- Sa valeur de vérité est absolue dans une structure donnée (elle ne dépend d'aucune assignation des variables).
- *Exemple :* \forall x \, \exists y \, (x < y) est close, alors que x < y ne l'est pas (x et y y sont libres).
- ### 2. Formule prenex  *(ou sous forme prenex)*
  
  Une formule est sous **forme prenex** si tous ses quantificateurs sont regroupés au début de la formule (le *préfixe*), suivis d'une formule sans aucun quantificateur (la *matrice*).
- Structure générale : $Q_1 x_1 \, Q_2 x_2 \dots Q_n x_n \, \phi(x_1, \dots, x_n)$ , où chaque $Q_i \in \{\forall, \exists\} et \phi$ ne contient aucun quantificateur.
- Toute formule du calcul des prédicats est logiquement équivalente à une formule sous forme prenex.
- ### 3. Formule $\Sigma_1^0$
  
  Dans la hiérarchie arithmétique (hiérarchie de Kleene), une **formule \Sigma_1^0** est une formule arithmétique écrite sous forme prenex qui commence par un bloc de quantificateurs existentiels (\exists), suivi uniquement de quantificateurs bornés (ou d'une matrice sans quantificateur).
- Structure générale : \exists x_1 \dots \exists x_k \, \phi, où tous les quantificateurs dans \phi sont de la forme \forall y \le z ou \exists y \le z.
- Ces formules expriment les propriétés **semi-décidables** (ou récursivement énumérables) : si la propriété est vraie, il existe un certificat fini x_1, \dots, x_k vérifiable par calcul direct.
- ### 4. Formule $\Pi_2^0$
  
  Une **formule \Pi_2^0** est une formule de la hiérarchie arithmétique possédant deux alternances de quantificateurs non bornés, en commençant par un bloc de quantificateurs universels (\forall).
- Structure générale : \forall x_1 \dots \forall x_k \, \exists y_1 \dots \exists y_m \, \phi, où \phi ne contient que des quantificateurs bornés.
- Ces formules permettent d'exprimer des propriétés fondamentales comme la totalité d'une fonction calculable ou la présence d'une infinité d'éléments vérifiant une propriété \Sigma_1^0.