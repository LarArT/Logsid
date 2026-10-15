Source:: Rapide introduction à coq par Yves bertot

- Pour simplifier un but, nous pouvons appliquer plusieurs commandes, adaptées pour chaque connecteur logique. Par exemple, si le but commence par une quantification universelle ($forall$) ou une implication $\rightarrow$, il est souvent judicieux de commencer par une commande `intros`. Si une hypothèse est une conjonction, il est souvent judicieux de décomposer cette hypothèse pour récupérer séparément les deux sous-formules qu'elle contient. Si la formule à prouver est une conjonction, il est souvent judicieux de casser cette formule pour prouver séparément les deux sous formules qu'elle contient. Ces différentes commandes, appelées tactiques, sont récapitulées dans le tableau suivant :
- ### Tableau des tactiques
  
  | | $\Rightarrow$ | $\forall$ | $\wedge$ | $\vee$ | $\exists$ |
  | :--- | :---: | :---: | :---: | :---: | :---: |
  | **Hypothesis** | `apply` | `apply` | `elim` | `elim` | `elim` |
  | **goal** | `intros` | `intros` | `split` | `left` or `right` | `exists` $v$ |
  
  | | $\neg$ | $=$ |
  | :--- | :---: | :---: |
  | **Hypothesis** | `elim` | `rewrite`<br>`injection`<br>`discriminate` |
  | **goal** | `intro`<br>`discriminate` | `reflexivity` |
  
  ---
  
  La tactique `discriminate` n'est utilisable pour une négation que lorsque la formule niée est une égalité. La tactique `injection` est utilisable pour une hypothèse lorsque l'égalité dans cette hypothèse est une égalité entre deux formules qui commencent par le même constructeur d'un type inductif. La tactique `discriminate` sur une hypothèse est une égalité entre deux formules qui commence par des constructeurs différents. Il faut parfois faire attention à quelle commande est utilisée, par exemple, lorsque l'on doit prouver une disjonction, appliquer `left` ou `right` est un choix important, car cela permet de choisir celle des deux sous-formules qui est prouvable.
  
  Pour faire avancer une preuve, il peut également être judicieux de faire apparaître une formule logique intermédiaire, que l'on prouve séparément, et que...