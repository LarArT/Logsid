- En logique des prédicats (ou logique du premier ordre), une **formule close** (parfois appelée **énoncé** ou *sentence* en anglais) est une formule bien formée qui ne contient **aucune variable libre**.
  
  Toutes les variables qui y apparaissent sont liées par un quantificateur (le quantificateur universel \forall ou le quantificateur existentiel \exists).
- ### Variable libre vs Variable liée
  
  Pour comprendre une formule close, il faut distinguer les deux statuts possibles d'une variable :
- **Variable liée :** Une variable est liée lorsqu'elle se trouve dans le champ d'application d'un quantificateur associé.
- **Variable libre :** Une variable est libre si elle n'est gouvernée par aucun quantificateur. Sa valeur n'est pas spécifiée, elle agit comme une "case vide".
- ### Exemples explicites
- **Formule close :** `\forall x (P(x) \rightarrow Q(x))`
  
  *Ici, la variable x est entièrement liée par le quantificateur \forall. La formule a un sens complet par elle-même.*
- **Formule non close (formule ouverte) :** `P(x) \land \exists y Q(y)`
  
  *Ici, la variable y est liée par \exists, mais la variable x est libre. On ne peut pas déterminer si cette formule est vraie ou fausse sans savoir ce que représente x.*
- ### Propriété fondamentale : La valeur de vérité
  
  La distinction entre formule close et formule ouverte est cruciale pour l'évaluation sémantique (l'interprétation) :
  
  > 
  
  Dans une structure ou un modèle donné, **une formule close possède une valeur de vérité unique et déterminée** (soit elle est vraie, soit elle est fausse).
  
  À l'inverse, une formule ouverte ne possède pas de valeur de vérité fixe ; sa vérité dépend de l'élément du domaine que l'on choisit d'assigner à la variable libre (par exemple, la formule ouverte x > 5 est vraie si x=6, mais fausse si x=3).
- ### Clôture universelle
  
  Il est fréquent en mathématiques de transformer une formule ouverte en formule close en lui appliquant sa **clôture universelle**. Cela consiste à ajouter un quantificateur universel devant la formule pour chaque variable libre présente.
- *Formule ouverte :* x + y = y + x
- *Clôture universelle (formule close) :* \forall x \forall y (x + y = y + x)