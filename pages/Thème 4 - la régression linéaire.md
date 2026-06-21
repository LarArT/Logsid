# Fiche de lecture — Thème 4 : Régression linéaire simple

*Source : Statistique pour ingénieur, Institut Mines-Télécom, A. Badea, S. Mussard, F. Seyte, T. Verdel*

---
- Un modèle s'écrit différemment selon la manière dont sont observées les variables du
   modèle:
	- lorsque les observations s'effectuent au cours du temps, les variables sont des séries temporelles et le modèle porte le nom de modèle en **séries temporelles**;
	- - lorsque les observations sont réalisées sur des échantillons d'**individus**, à un instant donné, le modèle porte le nom de modèle en **coupe instantanée**;
	- - lorsque les observations portent sur des échantillons au cours du temps, on parle de **modèle de panels**
- ## 0. Cadre général et hypothèses
  
  **Modèle.** Pour `i ∈ {1,…,n}` :
  
  > Modèle théorique : `Yᵢ = β₀ + β₁xᵢ + εᵢ`
  > Modèle empirique (calculé) : `yᵢ = β̂₀ + β̂₁xᵢ + ε̂ᵢ`
  
  **Hypothèse structurelle souvent passée sous silence mais essentielle :** `x` est supposée **déterministe** (`X = x`, valeur fixée, non aléatoire). Toute la randomness du modèle provient donc exclusivement de `εᵢ`. C'est cette hypothèse qui justifie, par exemple, qu'on puisse écrire `V[Ŷ₀] = σ²(1/n + (x₀-x̄)²/(ns²ₓ))` sans terme de variance sur `x`.
  
  **Hypothèses sur l'aléa (à vérifier, pas à supposer gratuitement) :**
  
  | Hypothèse | Énoncé formel | Nom |
  |---|---|---|
  | (H1) | `εᵢ` i.i.d. | — |
  | (H2) | `εᵢ ∼ 𝒩(0, σ²)` | Normalité |
  | (H2a) | `V(εᵢ) = σ²` constante ∀i | Homoscédasticité |
  | (H2b) | `Cov(εᵢ, εᵢ′) = 0` pour `i ≠ i′` | Non auto-corrélation |
  
  **Point de rigueur n°1.** Ces quatre conditions ne sont **pas équivalentes** et ne jouent pas le même rôle :
- Le **théorème de Gauss-Markov** (BLUE) repose uniquement sur (H2a) et (H2b) — *pas* sur la normalité.
- Les résultats *distributionnels* exacts (loi de Student pour les IC/tests sur `β₀, β₁`, loi du χ² pour `σ²`) reposent eux sur (H2), la normalité, qui est strictement plus forte.
  
  Confondre les deux niveaux conduit à croire, à tort, que la normalité est nécessaire pour que les MCO soient « optimaux » au sens variance minimale — c'est faux : elle est nécessaire pour faire de l'inférence exacte à distance finie, pas pour l'optimalité au sens BLUE.
  
  **Point de rigueur n°2 — distinction `εᵢ` / `ε̂ᵢ`.** Le résidu `ε̂ᵢ = yᵢ - ŷᵢ` est une quantité **observée, calculable**, définie par construction de manière exacte (égalité algébrique, non probabiliste). L'erreur `εᵢ` est, elle, **non observable**, une variable aléatoire théorique. Le document le souligne explicitement (Remarque 1) — c'est une distinction trop souvent gommée dans les présentations pédagogiques.
  
  ---
- ## 1. Estimateurs des Moindres Carrés Ordinaires (MCO)
  
  **Problème de minimisation :**
  ```
  min_{β̂₀,β̂₁} Σᵢ (yᵢ - β̂₀ - β̂₁xᵢ)²  ≡  min φ(β̂₀, β̂₁)
  ```
  
  **Solutions (conditions du premier ordre, hessienne définie positive vérifiée via `r t - s² = 4n²s²ₓ > 0`) :**
  
  ```
  β̂₀ = ȳ - x̄ β̂₁          β̂₁ = Cov(x,y) / s²ₓ
  ```
  
  **Point de rigueur n°3 — notation `Cov(x,y)` et `s²ₓ`.** Ici, `Cov(x,y) = (1/n)Σ(xᵢ-x̄)(yᵢ-ȳ)` et `s²ₓ = (1/n)Σ(xᵢ-x̄)²` sont des quantités **empiriques** (moments calculés sur l'échantillon observé `(xᵢ,yᵢ)`), à ne *pas* confondre avec la covariance **théorique** `Cov(β̂₀,β̂₁)` entre estimateurs (variables aléatoires) introduite section 2.4, ou avec une covariance de population au sens probabiliste. Le document réutilise la même notation `Cov(·,·)` dans deux régimes sémantiques différents (statistique descriptive sur l'échantillon vs. moment d'un couple de variables aléatoires). Ce n'est pas une erreur du document — c'est un usage standard — mais une source réelle de confusion si on ne le note pas explicitement.
  
  **Existence de la solution :** implicite, l'estimateur `β̂₁` n'est défini que si `s²ₓ > 0`, c'est-à-dire si les `xᵢ` ne sont pas tous égaux. Condition rarement explicitée mais nécessaire.
  
  **Estimateur de `σ²` :**
  ```
  σ̂*² = (1/(n-2)) Σᵢ ε̂ᵢ²        E[σ̂*²] = σ²   (sans biais)
  ```
  
  **Point de rigueur n°4 — MCO vs maximum de vraisemblance.** Les estimateurs `β̂₀, β̂₁` du MCO coïncident *exactement* avec ceux du maximum de vraisemblance sous (H2). En revanche, l'EMV de `σ²` est `(1/n)Σε̂ᵢ²` — **biaisé** (diviseur `n` et non `n-2`) — donc strictement différent de `σ̂*²`. Une affirmation du type « MCO = EMV » sans préciser ce point serait imprécise.
  
  ---
- ## 2. Propriétés des estimateurs
  
  **Proposition (linéarité, absence de biais, variance minimale).**
  ```
  E[β̂₀] = β₀,   E[β̂₁] = β₁
  V[β̂₁] = σ²/(n s²ₓ)
  V[β̂₀] = σ²(1/n + x̄²/(n s²ₓ))
  Cov(β̂₀,β̂₁) = -σ² x̄ / (n s²ₓ)
  ```
  
  **Théorème de Gauss-Markov.** Parmi tous les estimateurs **linéaires et sans biais**, les MCO sont de variance minimale : ce sont des estimateurs **BLUE**. À rappeler : ce résultat est de nature comparative (« le meilleur *dans la classe* des estimateurs linéaires sans biais ») — il n'affirme rien sur l'efficacité absolue (borne de Cramér-Rao) hors normalité.
  
  ---
- ## 3. Lois des estimateurs, intervalles de confiance, tests
  
  **Lois exactes (avec `σ²` connu — non utilisables en pratique) :**
  ```
  β̂₀ ∼ 𝒩(β₀ ; σ²[1/n + x̄²/(ns²ₓ)])
  β̂₁ ∼ 𝒩(β₁ ; σ²/(ns²ₓ))
  ```
  
  **Théorème de Fisher (pivot pour `σ²`) :**
  ```
  (n-2) σ̂*²/σ² ∼ χ²(n-2)
  ```
  
  **Statistiques de Student (en remplaçant `σ` par `σ̂*`) :**
  ```
  T_{β̂₁} = (β̂₁-β₁)√(ns²ₓ) / σ̂*     ∼ T(n-2)
  T_{β̂₀} = (β̂₀-β₀) / [σ̂*√(1/n + x̄²/(ns²ₓ))]   ∼ T(n-2)
  ```
  
  **Intervalles de confiance bilatéraux symétriques (niveau `1-α`) :**
  
  | Paramètre | IC |
  |---|---|
  | `β₁` | `β̂₁ ± t_{α/2}·σ̂*/√(ns²ₓ)` |
  | `β₀` | `β̂₀ ± t_{α/2}·σ̂*√(1/n + x̄²/(ns²ₓ))` |
  | `σ²` | `[(n-2)σ̂*²/χ²₂ ; (n-2)σ̂*²/χ²₁]` (asymétrique, car `χ²` n'est pas symétrique) |
  
  **Point de rigueur n°5.** L'IC de `σ²` n'est **pas** symétrique en `σ̂*²`, contrairement aux IC de `β₀` et `β₁` qui le sont en `β̂₀, β̂₁` — conséquence directe de l'asymétrie de la loi du χ². Une lecture rapide pourrait laisser croire, par analogie avec les deux cas précédents, à une construction symétrique : ce n'est pas le cas ici.
  
  **Test de validité du modèle (`H₀: β₁ = 0` contre `H₁: β₁ ≠ 0`).** Rejeter `H₀` ⟺ relation linéaire significative entre `y` et `x`. Règle : rejet si `|T_{β̂₁}| > t_{α/2}` ou, de façon équivalente, si `pval ≤ α` avec `pval = P_{H₀}(|T_{β̂₁}| > |t_{β̂₁}|)`.
  
  ---
- ## 4. Corrélation et analyse de la variance (ANOVA)
  
  **Coefficient de corrélation empirique :**
  ```
  r_{y/x} = Cov(x,y) / (sy·sx) ∈ [-1,1]
  ```
  Propriétés : symétrie (`r_{y/x}=r_{x/y}`), sans dimension, invariance par changement d'échelle (`r_{ky/k'x}=r_{y/x}`), invariance par centrage.
  
  **Lien avec `β̂₁` :**
  ```
  r_{y/x} = β̂₁ · (sx/sy)
  ```
  
  **Décomposition ANOVA (égalité algébrique exacte, conséquence de `Σε̂ᵢŷᵢᶜ = 0`) :**
  ```
  SCT = SCE + SCR
  Σ(yᵢ-ȳ)² = Σ(ŷᵢ-ȳ)² + Σε̂ᵢ²
  ```
  
  **Coefficient de détermination :**
  ```
  R² = SCE/SCT = 1 - SCR/SCT ∈ [0,1]      et      R² = r²_{y/x}   (régression simple uniquement)
  ```
  
  **Point de rigueur n°6.** L'égalité `R² = r²_{y/x}` n'est valable **que dans le cas de la régression linéaire simple à une variable explicative**. Elle ne se généralise pas telle quelle à la régression multiple, où `R²` (coefficient de détermination multiple) n'est plus le carré d'un unique coefficient de corrélation bivarié.
  
  **Test du coefficient de détermination — équivalence avec le test de Student :**
  ```
  F = [R²/(1-R²)]·(n-2) ∼ F(1,n-2)         et       F = T²_{β̂₁}   (sous H₀: β₁=0)
  ```
  Ceci découle de la relation générale : si `T ∼ T(d)` alors `T² ∼ F(1,d)`. Le test F et le test T sur `β₁` sont donc **rigoureusement équivalents** en régression simple (même décision, mêmes p-valeurs) — ce n'est qu'une reformulation, pas un test indépendant.
  
  ---
- ## 5. Utilisation en prévision
  
  Deux problèmes **distincts**, à ne pas confondre :
  
  **(a) IC de la valeur moyenne `E[Y₀|x₀] = β₀+β₁x₀`** (incertitude *uniquement* sur l'estimation de la droite) :
  ```
  Ŷ₀ ∼ 𝒩(β₀+β₁x₀ ; σ²[1/n + (x₀-x̄)²/(ns²ₓ)])
  Ic_{1-α}(E[Y₀|x₀]) = Ŷ₀ ± t_{α/2}·σ̂*·√(1/n + (x₀-x̄)²/(ns²ₓ))
  ```
  
  **(b) Intervalle de prévision d'une *nouvelle observation* `Y₀`** (incertitude sur la droite **+** variabilité propre de `ε₀`, en supposant `Y₀` et `Ŷ₀` indépendants) :
  ```
  Y₀ - Ŷ₀ ∼ 𝒩(0 ; σ²[1 + 1/n + (x₀-x̄)²/(ns²ₓ)])
  Ic_{1-α}(y₀) = ŷ₀ ± t_{α/2}·σ̂*·√(1 + 1/n + (x₀-x̄)²/(ns²ₓ))
  ```
  
  **Point de rigueur n°7 — le « +1 » n'est pas cosmétique.** La différence entre (a) et (b) est exactement ce terme « 1 » sous la racine, qui traduit la variance résiduelle propre à une *future réalisation individuelle* de `Y`, en plus de l'incertitude d'estimation des paramètres. L'intervalle de prévision (b) est donc **systématiquement plus large** que l'intervalle de confiance (a), et cet écart ne se résorbe pas asymptotiquement (`n → ∞`) : le terme « 1 » reste, contrairement à `1/n` et `(x₀-x̄)²/(ns²ₓ)` qui s'annulent.
  
  ---
- ## 6. Récapitulatif des objets et de leur statut
  
  | Objet | Statut |
  |---|---|
  | `β₀, β₁, σ²` | Paramètres théoriques, inconnus, non aléatoires |
  | `β̂₀, β̂₁, σ̂*²` | Estimateurs — variables aléatoires (avant observation) |
  | `εᵢ` | Variable aléatoire, non observable |
  | `ε̂ᵢ` | Résidu, observable, calculé exactement |
  | `x` | Déterministe (hypothèse du cours) |
  | `Y₀` | Variable aléatoire (nouvelle observation à venir) |
  | `Ŷ₀` | Estimateur/prédicteur, variable aléatoire |
  
  ---
- ## Synthèse des sept points de vigilance
  
  1. Gauss-Markov (BLUE) ⊥ normalité ; les résultats distributionnels (Student, χ²) requièrent (H2).
  2. `εᵢ` (théorique, inconnu) ≠ `ε̂ᵢ` (résidu, observé, défini par égalité exacte).
  3. `Cov(x,y)`, `s²ₓ` dans `β̂₁` = moments **empiriques** sur l'échantillon, à distinguer de `Cov(β̂₀,β̂₁)` qui est un moment théorique entre estimateurs.
  4. MCO ≡ EMV pour `β₀,β₁` sous normalité, mais **pas** pour `σ²` (EMV biaisé, diviseur `n`).
  5. IC de `σ²` non symétrique (asymétrie du χ²), contrairement aux IC de `β₀,β₁`.
  6. `R² = r²_{y/x}` : vrai en régression simple uniquement.
  7. IC de la moyenne conditionnelle vs intervalle de prévision individuelle : écart structurel (`+1`) qui ne disparaît pas quand `n → ∞`.
  
  ---
  
  *Document de travail personnel — fiche de synthèse, à compléter par la pratique des exercices 1 à 5.*