- La tactique `rewrite` (souvent abrégée en `rw`) est l'outil fondamental pour utiliser des égalités. Son but est simple : remplacer un terme par un autre équivalent au sein du but ou des hypothèses.
  
  Voici comment fonctionne ce mécanisme en SSReflect (Coq/Rocq) et son équivalent direct dans Lean 4.
- ## 1. En SSReflect (Coq / Rocq) : La puissance de  `rewrite`
  
  En SSReflect, `rewrite` est extrêmement flexible. On l'associe souvent à des symboles directionnels ou à des multiplicateurs.
- ### A. Remplacement de la gauche vers la droite (par défaut)
  
  Si vous disposez d'une hypothèse `h : A = B`, utiliser `rewrite h` va chercher toutes les occurrences de `A` dans le but et les transformer en `B`.
  
  ```
  Lemma exemple_rw_droit (A B : Type) (x y : A) (f : A -> B) (h : x = y) : f x = f y.
  Proof.
  rewrite h.
  -- "En utilisant l'égalité h, nous remplaçons le terme x par y dans l'objectif courant."
  
  by [].
  -- "Le but est maintenant f y = f y, ce qui est trivialement vrai par réflexivité."
  Qed.
  ```
- ### B. Remplacement de la droite vers la gauche ( `<-` )
  
  Si vous voulez faire l'inverse, c'est-à-dire remplacer `B` par `A` à partir de `h : A = B`, on ajoute le symbole `<-`.
  
  ```
  -- rewrite <- h.
  -- "En utilisant l'égalité h de droite à gauche, nous remplaçons le terme y par x dans l'objectif."
  ```
- ### C. Enchaînement et réécriture dans les hypothèses ( `in` )
  
  SSReflect permet de chaîner les réécritures dans une seule commande, ou de cibler une hypothèse précise du contexte à l'aide du mot-clé `in`.
  
  ```
  -- rewrite h1 h2.
  -- "Appliquons successivement les égalités h1 puis h2 dans notre objectif."
  
  -- rewrite h1 in h2.
  -- "Utilisons l'égalité h1 pour modifier le contenu de l'hypothèse h2."
  ```
- ## 2. L'équivalent dans Lean 4 : La tactique  `rw`
  
  En Lean 4, le comportement est conceptuellement identique, mais la syntaxe utilise des flèches textuelles (`←`) et des crochets pour l'enchaînement.
- ### A. Remplacement de la gauche vers la droite
  
  Par défaut, `rw [h]` remplace le membre de gauche par celui de droite.
  
  ```
  lemma exemple_rw_lean (A B : Type) (x y : A) (f : A → B) (h : x = y) : f x = f y := by
  rw [h]
  -- "Utilisons l'hypothèse d'égalité h pour substituer x par y au sein de notre objectif."
  
  rfl
  -- "L'objectif étant devenu f y = f y, la preuve se clôt par réflexivité de l'égalité."
  ```
- ### B. Remplacement de la droite vers la gauche ( `←` )
  
  Pour inverser le sens de l'égalité dans Lean 4, on place le symbole `←` (obtenu en tapant `\l`) devant l'hypothèse à l'intérieur des crochets.
  
  ```
  -- rw [← h]
  -- "Utilisons l'égalité h dans le sens inverse pour remplacer y par x dans l'objectif."
  ```
- ### C. Enchaînement et réécriture dans les hypothèses ( `at` )
  
  Lean 4 utilise des listes entre crochets `[...]` pour enchaîner les modifications et le mot-clé `at` pour cibler le contexte.
  
  ```
  -- rw [h1, h2]
  -- "Réécrivons séquentiellement l'objectif d'abord avec l'égalité h1, puis avec l'égalité h2."
  
  -- rw [h1] at h2
  -- "Appliquons l'égalité h1 pour transformer les termes correspondants à l'intérieur de l'hypothèse h2."
  ```
- ### Tableau de correspondance rapide
  
  | Action de réécriture | Syntaxe SSReflect (Coq) | Syntaxe Lean 4 |
  
  | **Gauche vers droite** | `rewrite h` | `rw [h]` |
  
  | **Droite vers gauche** | `rewrite <- h` | `rw [← h]` |
  
  | **Enchaîner plusieurs égalités** | `rewrite h1 h2` | `rw [h1, h2]` |
  
  | **Réécrire dans une hypothèse `h2`** | `rewrite h1 in h2` | `rw [h1] at h2` |
  
  | **Clôture automatique après rw** | Souvent géré par `by []` | `rw` tente automatiquement `rfl` à la fin |