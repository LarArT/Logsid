# general
-
- En Typst, la mise en page et le style ne se gèrent pas via des "variables" au sens traditionnel, mais à travers des **fonctions de configuration** et leurs **arguments**.
  Voici la liste exhaustive des fonctions clés de mise en page et leurs principaux paramètres :
- ### 1. La page (#set page(...))
  C'est la fonction principale pour configurer le support.
  * **paper** : Le format de la page ("a4", "letter", etc.).
  * **width / height** : Dimensions personnalisées.
  * **flipped** : Mode paysage si true (booléen).
  * **margin** : Les marges. Peut être une valeur unique, ou un dictionnaire ((top: 2cm, bottom: 2cm, left: 3cm, right: 3cm) ou (x: 2cm, y: 1.5cm)).
  * **columns** : Nombre de colonnes sur la page (entier).
  * **flipped** : Active le mode paysage (true ou false).
  * **header / footer** : Le contenu de l'en-tête et du pied de page.
  * **header-ascent / footer-descent** : Distance entre le texte et l'en-tête/pied de page.
  * **background / foreground** : Contenu placé en arrière-plan ou au premier plan (ex: filigrane).
  * **numbering** : Format de la numérotation des pages (ex: "1", "1 / 1", "I").
  * **number-align** : Alignement du numéro de page (center, right, etc.).
  * **binding** : Côté de la reliure (left ou right).
- ### 2. Les paragraphes (#set par(...))
  Contrôle la disposition des blocs de texte.
  * **justify** : Justifie le texte si true (booléen).
  * **leading** : L'interligne (espace entre les lignes d'un même paragraphe).
  * **spacing** : L'espace entre deux paragraphes distincts.
  * **first-line-indent** : Le retrait de la première ligne.
  * **hanging-indent** : Le retrait suspendu (toutes les lignes sauf la première).
  * **linebreaks** : Algorithme de césure ("optimized" ou "simple").
- ### 3. Le texte (#set text(...))
  Gère l'apparence brute des caractères.
  * **font** : Police de caractères (chaîne ou tableau de chaînes).
  * **size** : Taille de la police (ex: 11pt).
  * **weight** : Épaisseur ("regular", "bold", 700, etc.).
  * **style** : Style de police ("normal", "italic", "oblique").
  * **fill** : Couleur du texte (ex: black, rgb("#ff0000")).
  * **tracking** : L'interlettrage (espace entre les lettres).
  * **kerning** : Active ou désactive le crénage (booléen).
  * **lang / region** : Langue du document pour la césure (ex: "fr", "FR").
  * **hyphenate** : Active la césure automatique (true ou false).
- ### 4. L'alignement et le placement (#align(...) / #place(...))
  * **#align(direction, contenu)** : Aligne les blocs. Directions possibles : top, bottom, horizon, left, right, center. On peut les combiner : top + right.
  * **#place(direction, contenu)** : Place un élément de manière absolue par rapport à son conteneur sans occuper d'espace dans le flux de texte (avec options dx et dy).
- ### 5. Les espacements fixes (#v(...) et #h(...))
  * **#v(dimension)** : Espacement vertical (ex: #v(2cm)). Paramètre weak: true pour qu'il disparaisse en haut de page.
  * **#h(dimension)** : Espacement horizontal (ex: #h(10mm)). Paramètre fractional (ex: #h(1fr)) pour créer des espaces élastiques.
- # table et gride
	- En Typst, le choix entre #block et #grid dépend principalement de la structure de votre mise en page :
	- ### Utilisez #block pour le flux vertical (unidimensionnel)
	  Le bloc sert à regrouper du contenu pour lui appliquer des règles globales de mise en forme sans casser le flux naturel du texte.
	  * **Quand l'utiliser :** Pour isoler un paragraphe, insérer un encadré de texte, ajouter une couleur d'arrière-plan à une section, ou forcer des marges/espacements (inset, outset, radius).
	  * **Comportement :** Le contenu s'empile verticalement.
	- ### Utilisez #grid pour les structures en lignes et colonnes (bidimensionnel)
	  La grille est indispensable dès que vous devez aligner précisément des éléments à la fois horizontalement et verticalement.
	  * **Quand l'utiliser :** Pour créer des formulaires, des tableaux complexes sans bordures, des galeries d'images, ou aligner des éléments côte à côte (comme un logo à gauche et du texte à droite dans un en-tête).
	  * **Comportement :** Vous définissez explicitement le nombre et la taille des colonnes (columns: (1fr, 2fr)) et des lignes.
	- La fonction #grid est l'outil fondamental de Typst pour concevoir des mises en page bidimensionnelles rigoureuses. Contrairement aux tableaux (#table), la grille est purement structurelle : elle ne possède aucune bordure par défaut, ce qui la rend idéale pour aligner des éléments graphiques, du texte ou des blocs de code côte à côte.
	  Voici une exploration approfondie de son fonctionnement et de ses paramètres clés.
	- ## 1. Définir la structure : columns et rows
	  Le cœur d'une grille repose sur la définition de ses dimensions. Vous exprimez la taille des colonnes et des lignes sous forme de tableaux (arrays).
	- ### Les unités de dimensionnement
	  Typst propose trois types de tailles indispensables pour vos grilles :
	  * **Absolue (cm, mm, pt, em) :** Une taille fixe qui ne bouge pas.
	  * **Relative (100%) :** Un pourcentage de l'espace disponible (la largeur de la page ou du bloc parent).
	  * **Fractionnaire (fr) :** L'unité la plus puissante. Les fractions se partagent l'espace restant après le calcul des tailles absolues et relatives.
	  ```typst
	  #grid(
	  columns: (100pt, 1fr, 2fr), // 3 colonnes : une fixe, et le reste divisé en 1/3 et 2/3
	  rows: (auto, 40pt),        // 2 lignes : la première s'adapte au contenu, la seconde est fixe
	  [Cellule 1], [Cellule 2], [Cellule 3],
	  [Cellule 4], [Cellule 5], [Cellule 6]
	  )
	  
	  ```
	- ## 2. Gérer l'espacement : gutter
	  Le paramètre gutter (gouttière) définit l'espace vide entre les cellules, évitant que le contenu ne se colle. Vous pouvez le définir globalement ou séparément pour les lignes et les colonnes.
	  * **Global :** gutter: 10pt (applique l'espace horizontalement et verticalement).
	  * **Spécifique :** column-gutter: 1cm et row-gutter: 5mm.
	- ## 3. Placement avancé : Fusion et Positionnement
	  Pour des mises en page complexes (comme un en-tête de CV ou un tableau de bord), vous devez parfois fusionner des cellules ou modifier leur alignement. Pour cela, on utilise la fonction grid.cell à l'intérieur de la grille.
	- ### Fusionner des lignes ou colonnes (colspan / rowspan)
	  ```typst
	  #grid(
	  columns: 3,
	  gutter: 10pt,
	  grid.cell(colspan: 3, fill: blue.lighten(80%))[
	    *Titre de la grille qui prend les 3 colonnes*
	  ],
	  [Col 1], [Col 2], [Col 3]
	  )
	  
	  ```
	- ### Aligner le contenu (align)
	  Par défaut, le contenu est aligné en haut à gauche. Vous pouvez modifier cela globalement ou par cellule :
	  * **Global :** #grid(align: center + horizon, ...) (centre tout le texte verticalement et horizontalement).
	  * **Par cellule :** grid.cell(align: right)[Texte à droite]
	- ## 4. Habillage visuel : fill et stroke
	  Bien que la grille soit invisible par défaut, vous pouvez colorer ses cases ou y ajouter des lignes directrices.
	  * **fill :** Permet de colorer le fond. Vous pouvez passer une couleur unique, ou une fonction pour créer une alternance (pratique pour les listes).
	  * **stroke :** Ajoute des bordures (similaire à un tableau).
	  ```typst
	  #grid(
	  columns: (1fr, 1fr),
	  fill: (x, y) => if calc.even(y) { gray.lighten(80%) } else { white },
	  [Ligne 1, Col 1], [Ligne 1, Col 2],
	  [Ligne 2, Col 1], [Ligne 2, Col 2]
	  )
	  
	  ```
	- ## Cas d'usage typiques de #grid
	  1. **En-têtes de documents / CV :** Placer vos coordonnées à gauche et votre photo ou un résumé à droite, parfaitement alignés sur le plan vertical.
	  2. **Formulaires :** Aligner une colonne de "Labels" (Nom, Prénom) avec une colonne de lignes vides ou de cases à cocher.
	  3. **Mises en page de type "Magazine" :** Insérer une lettrine ou un encadré de citation à côté d'un bloc de texte principal sans utiliser le système de colonnes global du document.
- # fonction avancée
	- En **Typst**, la fonction #style est une fonction de bas niveau qui permet d'accéder aux propriétés de style courantes du document (comme la police, la couleur ou la taille du texte) à un endroit précis de la mise en page.
	  Voici ses caractéristiques principales et son fonctionnement :
	- ### 1. Syntaxe et principe
	  La fonction prend une fermeture (une fonction anonyme) qui reçoit un argument styles et retourne du contenu :
	  ```typst
	  #style(styles => [
	  // Utilisation des styles ici
	  ])
	  
	  ```
	- ### 2. Accès aux propriétés
	  Elle s'utilise généralement avec la fonction .at() pour extraire une valeur spécifique à partir d'un élément de référence.
	  ```typst
	  #style(styles => {
	  // Récupérer la taille de police actuelle
	  let size = text.at("size", default: 11pt, styles)
	  [La taille actuelle est de #size.]
	  })
	  
	  ```
	- ### 3. Cas d'usage principaux
	  * **Calculs géométriques dynamiques** : Mesurer la taille d'un élément (via la fonction measure) en fonction du contexte de style actuel.
	  * **Composants adaptatifs** : Ajuster l'espacement, les bordures ou les marges d'un bloc selon que le texte est en gras, en italique ou configuré avec une police spécifique.
	- ### 4. Alternative moderne (Typst 0.11+)
	  Bien que #style reste disponible, Typst privilégie désormais l'utilisation de la fonction **#context**. Plus large et plus intuitive, elle englobe l'accès aux styles, aux compteurs et aux coordonnées sans nécessiter de syntaxe de rappel (callback) explicite.
	  ```typst
	  // Approche moderne avec context
	  #context [
	  La taille actuelle est de #text.size.
	  ]
	  
	  ```
	- La fonction #context est une innovation majeure de Typst (introduite pour remplacer des fonctions de bas niveau comme #style ou #locate). Elle permet de créer du contenu dynamique en accédant aux informations de mise en page qui ne sont connues qu'au moment de la compilation.
	- ## 1. Principe fondamental
	  En Typst, le code est évalué avant la mise en page (le *layout*). Par conséquent, des valeurs telles que le numéro de page actuel, la taille d'un texte ou l'état d'un compteur ne sont pas figées lors de l'exécution du code.
	  La fonction #context indique au compilateur de retarder l'évaluation du bloc de code associé jusqu'à ce que le contexte de mise en page soit disponible.
	  ```typst
	  // Sans context, ceci génère une erreur ou renvoie une valeur statique
	  // Avec context, la valeur réelle est résolue dynamiquement
	  #context [
	  Le numéro de page actuel est : #counter(page).display()
	  ]
	  
	  ```
	- ## 2. Cas d'usage principaux
	- ### A. Accès aux compteurs et aux pages
	  Le cas d'usage le plus fréquent concerne la manipulation des compteurs pour les pages, les chapitres ou les figures.
	  ```typst
	  #context {
	  let page_num = counter(page).get().first()
	  if page_num == 1 [
	    Ce texte s'affiche uniquement sur la première page.
	  ]
	  }
	  
	  ```
	- ### B. Lecture des styles courants
	  #context remplace avantageusement l'ancienne fonction #style. Elle permet de lire directement les champs des éléments de style (comme text.size, text.lang ou page.margin).
	  ```typst
	  #context [
	  La police actuelle est #text.font et sa taille est #text.size.
	  ]
	  
	  ```
	- ### C. Mesure dynamique d'éléments (measure)
	  Pour calculer les dimensions exactes d'un bloc de texte ou d'une figure selon le style appliqué, l'utilisation de #context est obligatoire.
	  ```typst
	  #context {
	  let dimensions = measure([Mon texte à mesurer])
	  [Le texte mesure #dimensions.width de large.]
	  }
	  
	  ```
	- ## 3. Règles de propagation et limites
	  L'utilisation de #context obéit à des règles strictes en raison du fonctionnement du compilateur :
	  * **Sens unique (Puits de contexte)** : Les informations extraites à l'intérieur d'un bloc #context ne peuvent pas "s'échapper" vers l'extérieur. Un bloc #context renvoie toujours un type content.
	  * **Impossibilité de modifier des variables externes** : Vous ne pouvez pas modifier une variable globale définie hors du bloc avec des données lues dans le contexte.
	  ```typst
	  // ❌ CECI EST INCORRECT et ne fonctionnera pas :
	  let ma_taille = 10pt
	  #context {
	  ma_taille = text.size // Impossible d'affecter à une variable externe
	  }
	  
	  //  CECI EST CORRECT :
	  #context {
	  let ma_taille = text.size // Variable locale au bloc context
	  block(width: ma_taille * 2)[Contenu adapté]
	  }
	  
	  ```
	- ## 4. Comparaison : #style vs #context
	  | Caractéristique | Ancienne méthode (#style) | Nouvelle méthode (#context) |
	  |---|---|---|
	  | **Syntaxe** | Requiert une fonction de rappel (styles => ...) | Bloc de code direct et épuré |
	  | **Portée** | Limitée aux propriétés de style | Styles, compteurs, requêtes et mesures |
	  | **Simplicité** | Lourde pour les expressions complexes | Intégration native dans le flux de code|
- # inclure du texte
	- Oui, il est tout à fait possible d'intégrer du texte provenant d'un autre document ou de générer du contenu dynamiquement avant la compilation dans Typst.
	  Voici les deux méthodes principales pour y parvenir, selon votre besoin exact.
	- ## Méthode 1 : L'inclusion native (Recommandée)
	  Si le texte externe est un fichier au format texte brut (.txt), Markdown (.md) ou un autre fichier Typst (.typ), vous n'avez pas besoin de script externe. Typst possède des fonctions natives pour lire et intégrer ces fichiers directement lors de la compilation.
	- ### Pour un fichier Typst externe (.typ)
	  Utilisez la fonction #include. Elle compile et insère le contenu directement.
	  ```typst
	  #include "chapitre1.typ"
	  
	  ```
	- ### Pour un fichier texte ou Markdown (.txt, .md)
	  Utilisez la fonction #read combinée avec #eval (pour du Typst) ou insérez-le comme du texte brut.
	  ```typst
	  // Pour insérer le texte brut tel quel :
	  #read("source.txt")
	  
	  // Pour évaluer le texte comme du code Typst :
	  #eval(read("source.typ"))
	  
	  ```
	- ## Méthode 2 : L'utilisation d'un script avant la compilation
	  Si votre texte doit être généré par un script (Python, Bash, PowerShell) avant d'être intégré, vous devez orchestrer cela en deux étapes : la génération, puis la compilation.
	- ### Étape 1 : Le script de génération
	  Votre script (par exemple generer_texte.py) crée un fichier appelé texte_genere.typ.
	- ### Étape 2 : L'intégration dans le document principal
	  Dans votre fichier main.typ, vous incluez le fichier qui sera généré :
	  ```typst
	  #include "texte_genere.typ"
	  
	  ```
	- ### Étape 3 : Automatisation via le terminal
	  Pour éviter de lancer les commandes une par une, vous pouvez lier la génération et la compilation dans votre terminal ou via un fichier de script (.sh ou .bat).
	  ```bash
	  # 1. Exécution du script pour créer/mettre à jour le texte
	  python generer_texte.py
	  
	  # 2. Compilation du document Typst
	  typst compile main.typ document.pdf
	  
	  ```
	  > **Note de sécurité :** Typst est conçu pour être un environnement sécurisé. Par conséquent, le compilateur Typst ne peut pas exécuter lui-même de scripts système ou de commandes arbitraires pendant sa compilation. C'est pourquoi le script doit impérativement être exécuté **avant** de lancer la commande typst compile.
	  > 
	  Quelle est la nature du texte que vous souhaitez intégrer (du texte brut, du code, le résultat d'un calcul) et quel type de script utilisez-vous ?
- ## package essentiel
	- https://typst.app/universe/package/babble-bubbles : call out
	- https://typst.app/universe/package/showybox : box à la anssi
-