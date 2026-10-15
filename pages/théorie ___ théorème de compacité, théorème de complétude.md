- Version Claude
- # Fiche de lecture — Théorie du premier ordre : complétude et compacité
- ## 0. Cadre et vocabulaire
  
  Une **théorie** $T$ dans un langage $\mathcal L$ est un **ensemble d'énoncés clos** de $\mathcal L$ (formules sans variable libre), généralement supposé clos par conséquence syntaxique ($T = \{\varphi : T \vdash \varphi\}$) ou simplement un ensemble d'axiomes engendrant cette clôture — les deux usages coexistent, à préciser selon le contexte.
  
  **Deux notions de conséquence, à ne jamais fusionner sans le dire :**
  
  | Notation | Nom | Définition |
  |---|---|---|
  | $T \vdash \varphi$ | conséquence **syntaxique** (prouvabilité) | il existe une dérivation formelle de $\varphi$ à partir de $T$ dans un système de preuve (axiomes logiques + règles, ex. déduction naturelle, calcul des séquents) |
  | $T \models \varphi$ | conséquence **sémantique** | tout modèle $\mathcal M \models T$ satisfait aussi $\varphi$ |
  
  Ces deux relations sont *a priori* indépendantes : $\vdash$ dépend du système de preuve choisi, $\models$ dépend de la définition de satisfaction (Tarski, cf. fiche précédente). Le théorème de complétude est précisément l'énoncé de leur **coïncidence**.
  
  **Cohérence (consistance).** $T$ est **syntaxiquement cohérente** si $T \not\vdash \bot$ (ne prouve pas de contradiction). $T$ est **satisfiable** s'il existe $\mathcal M \models T$.
- ## 1. Théorème de complétude (Gödel, 1929)
  
  **Énoncé (forme forte).** Pour toute théorie $T$ et tout énoncé $\varphi$ du premier ordre :
  $$T \vdash \varphi \iff T \models \varphi$$
  
  **Corollaire (forme équivalente, souvent nommée elle aussi "théorème de complétude").**
  $$T \text{ cohérente} \iff T \text{ satisfiable}$$
  Les deux formulations sont interchangeables : la forme forte s'obtient de la seconde en appliquant celle-ci à $T \cup \{\neg\varphi\}$ (et réciproquement).
  
  **Point de vigilance n°1.** Le sens facile est $\vdash \Rightarrow \models$ (**correction / soundness**) : chaque règle de preuve préserve la vérité dans tout modèle, se vérifie par récurrence sur la longueur de la dérivation, sans difficulté. Le sens difficile et le véritable contenu du théorème est $\models \Rightarrow \vdash$, ou de façon équivalente **cohérence $\Rightarrow$ satisfiabilité** : *construire un modèle à partir de la seule absence de contradiction syntaxique*.
  
  **Idée de la preuve (méthode de Henkin, 1949 — reformulation de Gödel).**
  1. Étendre $\mathcal L$ en $\mathcal L^+$ par des **constantes de Henkin** $c_\varphi$ pour chaque formule $\exists x\, \varphi(x)$, avec les axiomes de Henkin $\exists x\,\varphi(x) \to \varphi(c_\varphi)$ — assure que les témoins existentiels sont nommés dans le langage.
  2. Étendre $T$ (cohérente) en une théorie **complète** $T^*$ (pour tout $\varphi$, $T^*\vdash\varphi$ ou $T^*\vdash\neg\varphi$) et **maximale cohérente** dans $\mathcal L^+$, par un argument de type Lindenbaum (extension par énumération des énoncés, utilise l'**axiome du choix** / lemme de Zorn en général).
  3. Construire le **modèle terme** (ou modèle de Henkin) : univers = termes clos de $\mathcal L^+$ modulo l'égalité prouvée par $T^*$ ; interprétation directe des symboles.
  4. Vérifier par récurrence sur $\varphi$ que $\mathcal M \models \varphi \iff T^*\vdash\varphi$ — les axiomes de Henkin garantissent que l'étape $\exists$ fonctionne.
  
  **Point de vigilance n°2.** Ce modèle construit est **dénombrable** si $\mathcal L$ est dénombrable — la preuve de complétude usuelle donne donc au passage un résultat de type Löwenheim–Skolem (§3), et non un modèle arbitraire.
- ## 2. Théorème de compacité
  
  **Énoncé.** $T$ est satisfiable $\iff$ **toute partie finie** $T_0 \subseteq T$ est satisfiable.
  
  **Preuve directe à partir de la complétude.** Si $T$ n'est pas satisfiable, par complétude $T \vdash \bot$ ; or une dérivation formelle est de longueur **finie**, donc n'utilise qu'un nombre fini de prémisses de $T$ : il existe $T_0 \subseteq T$ fini avec $T_0 \vdash \bot$, donc $T_0$ non satisfiable (contraposée). C'est *exactement* la finitude syntaxique des preuves qui produit la compacité — le lien logique entre les deux théorèmes n'est pas accessoire, il est constitutif.
  
  **Preuve alternative (ultraproduits, indépendante de la complétude).** Si toute partie finie de $T$ est satisfiable, soit $\mathcal M_{T_0} \models T_0$ pour chaque $T_0$ fini. On forme un ultraproduit $\prod \mathcal M_{T_0} / \mathcal U$ sur un ultrafiltre $\mathcal U$ bien choisi sur l'ensemble des parties finies de $T$ ; par le **théorème de Łoś**, ce produit satisfait $T$ tout entier. Preuve purement sémantique, sans passer par la syntaxe.
  
  **Point de vigilance n°3.** Compacité $\Rightarrow$ complétude n'est **pas** automatique : la compacité seule ne donne pas la coïncidence $\vdash \, = \, \models$ — historiquement d'ailleurs, Gödel prouve d'abord la complétude, et la compacité en est tirée comme corollaire ; ce n'est que via une preuve indépendante (ultraproduits) qu'on peut établir la compacité *sans* passer par la complétude, mais cela ne redonne pas la complétude en retour.
- ## 3. Applications structurantes
- **Löwenheim–Skolem (descendant).** Toute théorie satisfiable dans un langage dénombrable a un modèle dénombrable — se lit directement dans la construction de Henkin (§1 étape 3).
- **Löwenheim–Skolem (ascendant), via compacité.** Si $T$ a des modèles finis arbitrairement grands (ou un modèle infini), $T$ a des modèles de **tout cardinal infini** $\geq |\mathcal L|$ : ajouter des constantes $c_1,c_2,\ldots$ et les axiomes $c_i \neq c_j$ ($i\neq j$) ; toute partie finie n'engage qu'un nombre fini de $c_i$, satisfiable dans un modèle assez grand de $T$ ⇒ par compacité, $T \cup \{c_i\neq c_j\}$ satisfiable ⇒ modèle infini.
- **Existence de modèles non standards de l'arithmétique.** Soit $\mathrm{Th}(\mathbb N)$ la théorie complète de $(\mathbb N,+,\times,<)$. Ajouter une constante $c$ et les axiomes $\{c > \underline n : n\in\mathbb N\}$ ($\underline n$ = numéral). Toute partie finie est satisfiable dans $\mathbb N$ (en interprétant $c$ assez grand) ⇒ par compacité, il existe un modèle $\mathcal M \models \mathrm{Th}(\mathbb N)$ contenant un élément **infiniment grand** — modèle non isomorphe à $\mathbb N$, bien qu'**élémentairement équivalent**. Exemple canonique illustrant que le premier ordre ne peut pas caractériser $\mathbb N$ à isomorphisme près (contrairement au second ordre).
- **Analyse non standard (Robinson).** Même procédé sur $(\mathbb R,+,\times,<)$ : compacité donne un corps ordonné $^*\mathbb R \succeq \mathbb R$ contenant des infinitésimaux, fondant rigoureusement le calcul infinitésimal à la Leibniz.
- ## 4. Ce que ces théorèmes ne disent PAS
  
  **Point de vigilance n°4 — distinction avec Gödel-incomplétude.** « Complétude » ici signifie *complétude du système de preuve* (toute vérité sémantique est prouvable) — à ne **jamais confondre** avec « théorie complète » au sens de **Gödel-incomplétude** (existence d'un énoncé $\varphi$ tel que ni $T\vdash\varphi$ ni $T\vdash\neg\varphi$, pour $T$ récursivement axiomatisable et assez forte, ex. $T\supseteq$ PA). Les deux résultats **ne se contredisent pas** :
- La complétude de Gödel (1929) porte sur le **calcul logique** : toute formule sémantiquement valide est syntaxiquement prouvable — vrai pour **toute** théorie du premier ordre.
- L'incomplétude de Gödel (1931) porte sur des **théories particulières** (assez fortes pour coder l'arithmétique) : il existe des énoncés *indécidables* (ni prouvables ni réfutables) — cela signifie seulement que $T \not\vdash\varphi$ et $T\not\vdash\neg\varphi$, ce qui par la complétude (correcte !) équivaut à dire qu'il existe un modèle de $T\cup\{\varphi\}$ **et** un modèle de $T\cup\{\neg\varphi\}$. Aucune contradiction : la complétude garantit juste que prouvabilité = validité dans *tous* les modèles, pas que toute question ait une réponse déterminée par $T$.
- ## 5. Tableau récapitulatif
  
  | Théorème | Auteur | Énoncé | Preuve typique |
  |---|---|---|---|
  | Correction (soundness) | — | $T\vdash\varphi \Rightarrow T\models\varphi$ | récurrence sur la dérivation |
  | Complétude | Gödel 1929 / Henkin 1949 | $T\models\varphi \Rightarrow T\vdash\varphi$ | construction du modèle terme de Henkin |
  | Compacité | (corollaire de complétude) | satisfiable $\iff$ finiment satisfiable | finitude des preuves, ou ultraproduits (Łoś) |
  | Löwenheim–Skolem ↓ | 1915/1920 | modèle satisfiable $\Rightarrow$ modèle dénombrable | modèle terme (Henkin) |
  | Löwenheim–Skolem ↑ | Tarski | modèle infini $\Rightarrow$ modèles de tout cardinal $\geq |\mathcal L|$ | compacité + constantes fraîches |
- ## 6. Points à ne jamais valider sans vérification
- Ne pas dire "complétude" pour "théorie complète" (Gödel-incomplétude) — deux notions homonymes, contextes disjoints.
- Ne pas dire que la compacité est une conséquence *triviale* : le point clé est la **finitude des dérivations formelles**, propriété syntaxique qu'il faut expliciter, pas juste invoquer.
- Ne pas présenter le modèle de Henkin comme "le" modèle canonique : il dépend du choix de l'extension de Lindenbaum (non canonique en général, utilise le choix).
- Ne pas confondre équivalence élémentaire ($\mathcal M \equiv \mathcal N$) et isomorphisme : l'existence de modèles non standards élémentairement équivalents à $\mathbb N$ mais non isomorphes est précisément ce que montre §3.