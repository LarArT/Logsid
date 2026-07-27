# Fiche de lecture — La théorie ZF du point de vue de la logique
- ## 0. Cadre logique général
  
  ZF (Zermelo–Fraenkel) est une **théorie du premier ordre** dans le langage :
  
  $$\mathcal{L}_{\in} = \{\in\}$$
  
  — un unique symbole de prédicat binaire non logique, l'égalité $=$ étant traitée comme symbole logique (ZF est une théorie *avec égalité*).
  
  **Point de vigilance n°1.** ZF n'a **ni constantes, ni symboles de fonction primitifs**. Tous les objets usuels ($\emptyset$, $\{x,y\}$, $x\cup y$, $\mathcal{P}(x)$, $Sx = x \cup \{x\}$, $\omega$, les ordinaux…) sont introduits par **définitions** — c'est-à-dire des abréviations métalinguistiques pour des formules de $\mathcal{L}_\in$, justifiées à chaque fois par un théorème d'existence-unicité. Ce ne sont pas des symboles primitifs du langage, contrairement à ce que suggère la pratique mathématique courante.
- ## 1. Liste des axiomes (formulés dans $\mathcal{L}_\in$)
  
  | # | Nom | Formule (schéma) | Statut |
  |---|-----|-------------------|--------|
  | 1 | Extensionnalité | $\forall x,y\,[\forall z(z\in x \leftrightarrow z\in y) \rightarrow x=y]$ | axiome unique |
  | 2 | Fondation (Régularité) | $\forall x\,[x\neq\emptyset \rightarrow \exists y\in x\,(y\cap x=\emptyset)]$ | axiome unique |
  | 3 | Paire | $\forall x,y\,\exists z\,\forall t\,(t\in z \leftrightarrow t=x\lor t=y)$ | axiome unique |
  | 4 | Réunion | $\forall x\,\exists z\,\forall t\,(t\in z \leftrightarrow \exists y\in x\, t\in y)$ | axiome unique |
  | 5 | Ensemble des parties | $\forall x\,\exists z\,\forall t\,(t\in z \leftrightarrow t\subseteq x)$ | axiome unique |
  | 6 | Infini | $\exists x\,[\emptyset\in x \land \forall y\in x\,(y\cup\{y\}\in x)]$ | axiome unique |
  | 7 | **Séparation** ([[schéma Compréhension restreinte]]) | $\forall \bar p\,\forall x\,\exists z\,\forall t\,(t\in z \leftrightarrow t\in x \land F(t,\bar p))$ | **schéma**, un axiome par formule $F$ |
  | 8 | **Remplacement** | $\forall \bar p\,[\forall x\in a\,\exists! y\, F(x,y,\bar p) \rightarrow \exists z\,\forall x\in a\,\exists y\in z\, F(x,y,\bar p)]$ | **schéma**, un axiome par formule $F$ |
  | (9) | Choix (si ZFC) | $\forall x\,[\emptyset\notin x \rightarrow \exists f: x \to \bigcup x, \ \forall y\in x\,(f(y)\in y)]$ | axiome unique, souvent formulé avec fonction de choix codée relationnellement |
  
  **PA = ZF sans (9)**, à ne pas confondre avec l'arithmétique de Peano $P_0\cup\mathrm{Rec}$ vue précédemment — attention à la collision de notation "PA" selon les ouvrages.
- ## 2. Le point logique central : pourquoi des *schémas* ?
  
  En logique du **premier ordre**, on ne peut **pas quantifier sur les prédicats** (pas de $\forall F$). Or l'intuition naïve de la « compréhension » voudrait :
  
  $$\forall F\ \exists z\ \forall t\,(t\in z \leftrightarrow F(t))$$
  
  — ceci est une formule du **second ordre**, et de toute façon **contradictoire** en tant que telle (paradoxe de Russell : prendre $F(t) \equiv t\notin t$).
  
  **Solutions logiques apportées par ZF :**
- **Séparation** : on affaiblit la compréhension en l'restreignant à un ensemble $x$ déjà existant ($t\in x \land F(t)$ au lieu de $F(t)$ seul). Comme on ne peut pas quantifier sur $F$, on obtient une **famille infinie d'axiomes**, un par formule $F(t,\bar p)$ du langage — d'où le mot *schéma*.
- **Remplacement** (Fraenkel) : renforce Séparation ; permet de transformer l'image d'un ensemble par une relation *fonctionnelle définissable* en un ensemble. Nécessaire par exemple pour construire $V_{\omega+\omega}$ ou pour l'existence de $\aleph_\omega$.
  
  **Point de vigilance n°2.** Séparation ne donne accès qu'aux **sous-ensembles définissables** (par une formule du premier ordre, à paramètres) d'un ensemble donné — pas à *tous* les sous-ensembles au sens naïf. C'est l'axiome de l'**ensemble des parties** (Powerset) qui, lui, affirme (sans les construire explicitement) l'existence de la totalité de $\mathcal{P}(x)$. La différence entre « ensemble des parties définissables » et « ensemble de toutes les parties » est précisément ce qui rend la notion de sous-ensemble **non absolue** entre modèles (cf. §4).
- ## 3. Conséquences métathéoriques du caractère schématique
- **Non finitude essentielle.** Si ZF est consistante, elle n'est **pas finiment axiomatisable** (théorème de Montague–Levy) : aucune sous-théorie finie de ZF n'est équivalente à ZF. C'est une conséquence de la présence de schémas portant sur une infinité de formules non équivalentes entre elles.
- **NBG comme axiomatisation finie.** Von Neumann–Bernays–Gödel (NBG) introduit des **classes** en plus des ensembles, ce qui permet de remplacer les schémas par des axiomes uniques quantifiant sur les classes ; NBG est finiment axiomatisable et **conservative** sur ZF (mêmes théorèmes sur les ensembles).
- **Théorème de réflexion (Lévy).** Pour toute formule $\varphi$ (ou toute liste finie de formules), ZF prouve qu'il existe un ordinal $\alpha$ tel que $V_\alpha \models \varphi \leftrightarrow \varphi^{V_\alpha}$ (réflexion vers un $V_\alpha$). Ce résultat *remplace* l'axiome unique manquant : on ne peut prouver la réflexion que **schéma par schéma**, jamais uniformément pour toutes les formules à la fois — sans quoi on prouverait $\mathrm{Con}(\mathrm{ZF})$ en interne, ce que le second théorème de Gödel interdit.
- ## 4. Sémantique, absoluité, indépendance
- **Modèle intenté.** Le modèle « intuitif » de ZF est la **hiérarchie cumulative** $V = \bigcup_{\alpha\in\mathrm{Ord}} V_\alpha$, avec $V_0=\emptyset$, $V_{\alpha+1}=\mathcal{P}(V_\alpha)$, $V_\lambda = \bigcup_{\alpha<\lambda}V_\alpha$ pour $\lambda$ limite. $V$ n'est **pas un ensemble** (c'est une classe propre) : ZF parle donc d'un modèle qui n'existe pas *en tant qu'objet* de la théorie — distinction essentielle ensemble / classe propre.
- **Paradoxe de Skolem.** Par Löwenheim–Skolem descendant, si ZF est consistante elle admet un modèle **dénombrable** $M$. Pourtant $M \models$ « il existe un ensemble non dénombrable » (par exemple $\mathcal{P}(\omega)$ dans $M$). Ce n'est pas une contradiction : « être dénombrable » n'est **pas absolu** — la bijection témoin de la dénombrabilité, vue de l'extérieur, n'appartient simplement pas à $M$.
- **Indépendance.** Gödel (1938, modèle $L$ des constructibles) montre $\mathrm{Con}(\mathrm{ZF}) \Rightarrow \mathrm{Con}(\mathrm{ZF}+\mathrm{AC}+\mathrm{GCH})$. Cohen (1963, forcing) montre $\mathrm{Con}(\mathrm{ZF}) \Rightarrow \mathrm{Con}(\mathrm{ZF}+\neg\mathrm{AC})$ et $\mathrm{Con}(\mathrm{ZFC}) \Rightarrow \mathrm{Con}(\mathrm{ZFC}+\neg\mathrm{CH})$. Ensemble : **AC et CH sont indépendants de ZF/ZFC**.
- **Incomplétude.** Par le second théorème de Gödel, si ZF est consistante, **ZF ne prouve pas $\mathrm{Con}(\mathrm{ZF})$**. On ne peut donc jamais établir, à l'intérieur de ZF elle-même, que ZF a un modèle.
- ## 5. Comparaison avec le point de vue « type theory / HOL » déjà vu
  
  | | ZF (premier ordre) | HOL / CIC (types) |
  |---|---|---|
  | Comprehension | restreinte via schéma Séparation | souvent primitive dans le système de types |
  | Objets | tout est un ensemble (relation $\in$ unique) | hiérarchie stratifiée de types/sortes |
  | Univers | classe propre $V$, non formalisable en interne | hiérarchie explicite d'univers (cf. Coq, liée à Grothendieck) |
  | Paradoxes évités par | restriction de compréhension (Séparation) | stratification/typage (pas de $t\in t$ bien typé) |
  
  **Remarque de cohérence avec vos lectures précédentes.** L'échappatoire au paradoxe de Russell en ZF (séparation restreinte, un ensemble « déjà là ») et l'échappatoire en théorie des types (stratification en univers, cf. SGA4/Grothendieck) sont **deux stratégies logiques distinctes** répondant au même problème de comprehension non restreinte — utile à garder en tête pour ne pas confondre les deux solutions.
- ## 6. Points à ne jamais valider sans vérification
- Ne pas dire « ZF a 9 axiomes » sans préciser que 2 d'entre eux (Séparation, Remplacement) sont des **schémas infinis**, pas des axiomes uniques.
- Ne pas confondre **Séparation** (sous-ensemble d'un ensemble donné, cohérente) et **Compréhension naïve** (contradictoire, paradoxe de Russell).
- Ne pas dire que $V \models \mathrm{ZF}$ « prouve » que ZF est consistante : $V$ n'est pas un ensemble, l'énoncé « $V\models\mathrm{ZF}$ » n'est pas formalisable dans ZF elle-même.
- Ne pas confondre l'indépendance de AC/CH (résultats sur ZF) avec l'incomplétude de $\mathrm{Con}(\mathrm{ZF})$ (résultat de Gödel sur toute théorie récursivement axiomatisée assez forte) — deux résultats différents, souvent mélangés à tort.