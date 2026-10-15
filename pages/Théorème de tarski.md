Tags:: théorème d'élimination des quantificateurs

- Le "théorème de Tarski" ici est le **théorème d'élimination des quantificateurs (QE) pour les corps réels clos (RCF)**, démontré autour de 1930, publié en 1948/1951 (*A Decision Method for Elementary Algebra and Geometry*). Il faut le distinguer nettement du théorème d'indéfinissabilité vu précédemment — c'est un résultat de nature algorithmique/algébrique, pas sémantique.
- ## Cadre précis
  
  Langage $\mathcal L_{OR} = \{+,\times,<,0,1\}$. Un **corps réel clos** (RCF) est un corps ordonné $K$ tel que :
	- tout élément positif a une racine carrée dans $K$,
	- tout polynôme de degré impair sur $K$ a une racine dans $K$.
	  
	  $(\mathbb R, +,\times,<)$ en est l'exemple canonique, mais aussi $\mathbb R_{\mathrm{alg}}$ (réels algébriques) ou des corps de Puiseux.
- ## Énoncé du théorème
  
  **Toute formule** $\varphi(\bar x)$ **de $\mathcal L_{OR}$ est équivalente, modulo la théorie RCF, à une formule sans quantificateurs** $\psi(\bar x)$ (booléenne en $p(\bar x) > 0$, $p(\bar x)=0$, pour $p$ polynôme à coefficients entiers).
  
  **Point de vigilance** : ce n'est pas juste un résultat d'existence — Tarski donne un **algorithme effectif** produisant $\psi$ à partir de $\varphi$ (complexité non élémentaire dans sa version originale ; Collins en 1975 donnera un algorithme praticable, la *décomposition cylindrique algébrique*, CAD).
- ## Ce que QE entraîne immédiatement
- **Complétude de RCF** : tout énoncé clos se réduit (par QE) à une combinaison booléenne de faits sur $0,1$ — décidables dans $\mathbb Q$ — donc RCF tranche tout énoncé. Conséquence : **tous les corps réels clos sont élémentairement équivalents** à $(\mathbb R,+,\times,<)$, notamment $\mathbb R_{\mathrm{alg}} \equiv \mathbb R$.
- **Décidabilité de la théorie du premier ordre de $(\mathbb R,+,\times,<)$** — algorithme concret, à opposer frontalement à l'**indécidabilité de l'arithmétique** $(\mathbb N,+,\times)$ (Church/Turing, via Gödel). C'est le contraste le plus important à retenir : ajouter l'ordre et retirer l'induction fait basculer de l'indécidable au décidable.
- **Model-complétude** : toute injection entre modèles de RCF est une plongement élémentaire (immédiat car toute formule est équivalente sans quantificateurs, donc préservée par sous-structures).
- ## Ce qui vient *après* QE — les applications
  
  1. **Théorème de projection de Tarski–Seidenberg.** Traduction géométrique de QE : la projection d'un **ensemble semi-algébrique** (défini par des égalités/inégalités polynomiales) est encore semi-algébrique. C'est le fait fondateur de la **géométrie algébrique réelle** — sans lui, projeter casserait la semi-algébricité.
  2. **Décidabilité de la géométrie élémentaire.** Tarski axiomatise la géométrie euclidienne dans un langage du premier ordre interprétable dans RCF ⇒ la géométrie élémentaire (à la Euclide, premier ordre) est **décidable** — résultat contre-intuitif souvent mal cité sans préciser "premier ordre" (la géométrie *au sens usuel*, avec quantification sur des ensembles de points arbitraires, ne l'est pas).
  3. **Preuve automatique et calcul formel.** CAD (Collins) est le moteur derrière les logiciels de preuve/résolution de systèmes polynomiaux à contraintes (Mathematica `Reduce`, QEPCAD, Redlog) — utilisé en robotique (espaces de configuration définis par inégalités polynomiales), vérification de systèmes hybrides, synthèse de contrôleurs.
  4. **Positivstellensätze (Krivine, Stengle).** Prolongent la logique de RCF : caractérisations algébriques de la positivité d'un polynôme sur un ensemble semi-algébrique, base théorique de l'**optimisation polynomiale par sommes de carrés (SOS)**.
- « Théorème de Tarski » sans précision est ambigu entre **indéfinissabilité de la vérité** (§ fiche précédente) et **QE pour RCF** (ce théorème-ci) — toujours préciser lequel.
- QE donne un algorithme, mais de complexité **doublement exponentielle** dans le nombre de variables pour l'algorithme original de Tarski ; CAD (Collins) reste exponentiel — ce n'est pas un algorithme praticable en grande dimension, à ne pas présenter comme "efficace" sans nuance.