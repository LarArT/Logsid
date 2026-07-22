- Voici la récapitulation complète du système **LJ** avec l'intégralité des règles, en appliquant strictement le formatage avec le signe dollar pour chaque formule mathématique et élément de séquent.
- ## 1. Structure générale et principes
  
  Le système **LJ** (logique intuitionniste) se distingue du système **LK** (logique classique) par une restriction sur la droite des séquents :
- Les séquents sont de la forme $\Gamma \vdash \Delta$, où $\Delta$ contient **au plus une formule**<!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!---->.  <!----><!----><!----><!----><!----><!----><!----><!---->
- La notation $[A]$ ou $[B]$ indique qu'une formule peut être présente ou absente (au plus un élément à droite)<!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!----><!---->.  <!----><!----><!----><!----><!----><!----><!----><!---->
- ## 2. Règles du système LJ
- ### Axiomes
- **Axiome d'identité :**
  
  $$\frac{}{A \vdash A} ax$$
- **Faux (Absurde) à gauche :**
  
  $$\frac{}{\bot \vdash} \bot_g$$
- ### Règles structurelles
- **Affaiblissement à gauche ($aff_g$) :**
  
  $$\frac{\Gamma \vdash [B]}{\Gamma, A \vdash [B]}$$
- **Affaiblissement à droite ($aff_d$) :**
  
  $$\frac{\Gamma \vdash}{\Gamma \vdash A}$$
- **Contraction à gauche ($contr_g$) :**
  
  $$\frac{\Gamma, A, A \vdash [B]}{\Gamma, A \vdash [B]}$$
- ### Règles des connecteurs logiques
- **Conjonction à gauche ($\wedge_g$) :**
  
  $$\frac{\Gamma, A, B \vdash [C]}{\Gamma, A \wedge B \vdash [C]}$$
- **Conjonction à droite ($\wedge_d$) :**
  
  $$\frac{\Gamma \vdash A \quad \Gamma \vdash B}{\Gamma \vdash A \wedge B}$$
- **Disjonction à gauche ($\vee_g$) :**
  
  $$\frac{\Gamma, A \vdash [C] \quad \Gamma, B \vdash [C]}{\Gamma, A \vee B \vdash [C]}$$
- **Disjonction à droite ($\vee_d^1$ et $\vee_d^2$) :**
  
  $$\frac{\Gamma \vdash A}{\Gamma \vdash A \vee B} \vee_d^1 \qquad \frac{\Gamma \vdash B}{\Gamma \vdash A \vee B} \vee_d^2$$
- **Implication à gauche ($\rightarrow_g$) :**
  
  $$\frac{\Gamma \vdash A \quad \Gamma, B \vdash [C]}{\Gamma, A \rightarrow B \vdash [C]}$$
- **Implication à droite ($\rightarrow_d$) :**
  
  $$\frac{\Gamma, A \vdash B}{\Gamma \vdash A \rightarrow B}$$
- **Négation à gauche ($\neg_g$) :**
  
  $$\frac{\Gamma \vdash A}{\Gamma, \neg A \vdash}$$
- **Négation à droite ($\neg_d$) :**
  
  $$\frac{\Gamma, A \vdash}{\Gamma \vdash \neg A}$$
- ### Règles des quantificateurs
- **Quantificateur universel à gauche ($\forall_g$) :**
  
  $$\frac{\Gamma, A[x:=t] \vdash [C]}{\Gamma, \forall x A \vdash [C]}$$
- **Quantificateur universel à droite ($\forall_d$) :** (avec $x$ non libre dans $\Gamma$)
  
  $$\frac{\Gamma \vdash A}{\Gamma \vdash \forall x A}$$
- **Quantificateur existentiel à gauche ($\exists_g$) :** (avec $x$ non libre dans $\Gamma, [C]$)
  
  $$\frac{\Gamma, A \vdash [C]}{\Gamma, \exists x A \vdash [C]}$$
- **Quantificateur existentiel à droite ($\exists_d$) :**
  
  $$\frac{\Gamma \vdash A[x:=t]}{\Gamma \vdash \exists x A}$$
- ### Règle de coupure
- **Coupure :**
  
  $$\frac{\Gamma \vdash A \quad \Gamma, A \vdash [B]}{\Gamma \vdash [B]} coupure$$
- ## 3. Formulations alternatives pour le système LK (mentionnées dans la fiche)
  
  En **LK**, l'absence de restriction sur le nombre de formules à droite permet des présentations alternatives équivalentes grâce aux règles structurelles :
- **Conjonction à droite avec contextes indépendants :**
  
  $$\frac{\Gamma \vdash A, \Delta \quad \Gamma' \vdash B, \Delta'}{\Gamma, \Gamma' \vdash A \wedge B, \Delta, \Delta'}$$
- **Variantes pour la conjonction à gauche ($\wedge_g^1$ et $\wedge_g^2$) :**
  
  $$\frac{\Gamma, A \vdash \Delta}{\Gamma, A \wedge B \vdash \Delta} \wedge_g^1 \qquad \frac{\Gamma, B \vdash \Delta}{\Gamma, A \wedge B \vdash \Delta} \wedge_g^2$$
- **Variantes pour la disjonction à droite en LK ($\vee_d^1$ et $\vee_d^2$) :**
  
  $$\frac{\Gamma \vdash A, \Delta}{\Gamma \vdash A \vee B, \Delta} \vee_d^1 \qquad \frac{\Gamma \vdash B, \Delta}{\Gamma \vdash A \vee B, \Delta} \vee_d^2$$