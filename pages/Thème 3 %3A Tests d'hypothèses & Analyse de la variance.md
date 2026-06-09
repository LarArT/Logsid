# Fiche de lecture — Thème 3 : Tests d'hypothèses & Analyse de la variance
**Institut Mines-Télécom** | Verdel, Kosior & Sauceau | Mai 2026

---
- ## 🎯 Objectif général
  
  À partir d'échantillons, **tirer des conclusions sur des populations** via un raisonnement probabiliste structuré (introduit par Student/Gosset, théorisé par Neyman & Pearson).
  
  ---
- ## 1. Principe des tests d'hypothèses
  
  **Deux hypothèses** : H₀ (nulle) vs H₁ (alternative)
  
  | | H₀ vraie | H₁ vraie |
  |---|---|---|
  | Décision H₀ | ✅ correct (1−α) | ❌ erreur 2ᵉ espèce (β) |
  | Décision H₁ | ❌ erreur 1ʳᵉ espèce (α) | ✅ correct (1−β) |
- **α** = risque de rejeter H₀ à tort → fixé a priori (souvent 5%)
- **β** = risque d'accepter H₀ à tort
- **Puissance du test** = 1−β
  
  **Démarche en 6 étapes :**
  1. Formuler H₀ et H₁
  2. Choisir la variable de décision
  3. Fixer α → déterminer la région critique
  4. Calculer la puissance (optionnel)
  5. Calculer la valeur expérimentale
  6. Conclure (rejeter ou non H₀)
  
  > ⚠️ Ne pas rejeter H₀ ≠ H₀ est vraie
  
  **Types de tests :**
- **Unilatéral gauche/droit** : H₁ orientée (< ou >)
- **Bilatéral** : H₁ : θ ≠ θ₀ → risque α/2 de chaque côté
  
  ---
- ## 2. Tests de conformité (lois outils)
  
  | Situation | Variable de décision | Loi |
  |---|---|---|
  | Moyenne, variance **connue** | U = (X̄ − µ₀)/(σ/√n) | N(0,1) |
  | Moyenne, variance **inconnue** | T = (X̄ − µ₀)/(S/√n−1) | T(n−1) |
  | Variance | Z = nS²/σ₀² | χ²(n−1) |
  | Données **appariées** | T sur les différences dᵢ = yᵢ − xᵢ | T(n−1) |
  
  ---
- ## 3. Comparaison de 2 populations normales
  
  **Ordre obligatoire :** variances d'abord, moyennes ensuite.
  
  | Étape | Test | Variable | Loi |
  |---|---|---|---|
  | 1. Variances | Fisher | F = S*²₁/S*²₂ | F(n₁−1, n₂−1) |
  | 2. Moyennes | Student | T = (X̄₁−X̄₂)/(S*·√1/n₁+1/n₂) | T(n₁+n₂−2) |
  
  > Le **test des appariements est plus puissant** que la comparaison indépendante quand il est applicable.
  
  ---
- ## 4. Tests d'ajustement (χ²)
  
  Tester si une distribution observée suit une loi L.
  
  $$D^2 = \sum_{i=1}^k \frac{(N_i - np_i)^2}{np_i} \sim \chi^2(k-1-\ell)$$
- ℓ = nombre de paramètres estimés
- Effectifs théoriques nᵢpᵢ ≥ 5 (regrouper sinon)
- Test **unilatéral à droite**
  
  ---
- ## 5. Test d'indépendance (χ²)
  
  Tester si deux variables qualitatives sont indépendantes.
  
  $$D^2 = \sum_{i,j} \frac{(n_{ij} - t_{ij})^2}{t_{ij}} \sim \chi^2((r-1)(s-1))$$
  
  avec effectifs théoriques : tᵢⱼ = nᵢ· × n·ⱼ / n
  
  ---
- ## 6. Analyse de la variance (ANOVA)
- ### À 1 facteur
  
  **Décomposition :** SCT = SCA + SCR
  
  | Source | SC | DL | F calculé |
  |---|---|---|---|
  | Facteur A | SCA | p−1 | SCA/(p−1) ÷ SCR/(n−p) |
  | Résiduelle | SCR | n−p | — |
  | Totale | SCT | n−1 | — |
  
  → F suit une loi **F(p−1 ; n−p)** sous H₀
- ### À 2 facteurs (avec répétitions)
  
  **Décomposition :** SCT = SCA + SCB + SCAB + SCR
  
  | Source | DL | Test |
  |---|---|---|
  | Facteur A | p−1 | FA = [SCA/(p−1)] / [SCR/pq(r−1)] |
  | Facteur B | q−1 | FB = [SCB/(q−1)] / [SCR/pq(r−1)] |
  | Interaction AB | (p−1)(q−1) | FAB similaire |
  | Résiduelle | pq(r−1) | — |
  
  > Sans répétitions (r=1) : impossible de tester l'interaction → on l'suppose nulle et SCAB sert de référence.
  
  ---
- ## 🗝️ Points clés à retenir
- **Rejeter H₀** est une conclusion forte ; **ne pas rejeter** ne prouve rien
- Toujours vérifier les **hypothèses du modèle** (normalité, homoscédasticité)
- Les tests **non paramétriques** (médiane, signes, χ²) s'utilisent sans hypothèse de loi
- L'**interaction** entre facteurs signifie que l'effet de l'un dépend des modalités de l'autre