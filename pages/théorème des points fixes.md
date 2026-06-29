## 2. Définitions Inductives & Théorèmes du Point Fixe
Pour définir des ensembles complexes (comme l'ensemble de toutes les propositions ou des propositions démontrables), on utilise des **définitions inductives** (règles de fermeture). La validité de ces définitions repose sur deux théorèmes de point fixe.
- ### A. Premier Théorème du Point Fixe (Approche Constructive / Continue)
  * **Cadre :** Ensemble muni d'une relation d'ordre, qualifié de *faiblement complet* (toute suite croissante a une borne supérieure).
  * **Condition :** La fonction $f$ opérant sur cet ensemble doit être **croissante et continue** :
    $$\lim_i (f(u_i)) = f(\lim_i u_i)$$
  * **Résultat :** Le plus petit point fixe existe et correspond à la limite constructive obtenue par itérations successives à partir du plus petit élément $m$ :
    $$\lim_i (f^i(m))$$
- ### B. Second Théorème du Point Fixe (Approche Non Constructive / Monotone)
  * **Cadre :** Ensemble *fortement complet* (tout sous-ensemble admet une borne supérieure et une borne inférieure, ex: $\mathcal{P}(A)$ muni de l'inclusion $\subseteq$).
  * **Condition :** La fonction $f$ doit être simplement **croissante** (monotone).
  * **Résultat :** Le plus petit point fixe est défini de manière globale par l'intersection (borne inférieure) de tous les ensembles pré-fixes (clos par $f$) :
    $$\inf \{ c \mid f(c) \le c \}$$
  
  > 💡 **Concept clé : La dérivation** > L'appartenance d'un élément à un ensemble défini inductivement se justifie par une **dérivation**. Structurellement, il s'agit d'un **arbre** dont les nœuds sont étiquetés par les éléments de l'ensemble, et où le passage des enfants au parent correspond à l'application d'une règle (fonction de fermeture).