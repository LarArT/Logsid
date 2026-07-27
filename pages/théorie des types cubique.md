- Dans le prolongement de la théorie des types dépendants (et en particulier de la **théorie des types homotopiques**, ou *HoTT*), la **théorie des types cubique** (*Cubical Type Theory*) est une avancée majeure qui résout un problème fondamental de la théorie des types synthétique.
- ## 1. Le problème de départ dans HoTT
  
  Dans la théorie des types classique de Martin-Löf ainsi que dans HoTT, l'égalités (ou type d'identité) pose un problème computationnel :
- **L'axiome d'univalence** de Voevodsky affirme que deux types isomorphes sont égaux (A \simeq B \implies A = B). C’est extrêmement puissant sur le plan mathématique.
- **Le problème :** Dans HoTT "standard", l'univalence est ajoutée comme un **axiome opaque**. En conséquence, la théorie perd la **propriété de canonicité** : lorsque vous avez un terme de type entier (\mathbb{N}) construit à l'aide de l'univalence, le système ne sait pas comment le réduire pour obtenir un chiffre concret (ex: 2). On se retrouve "bloqué" par l'axiome.
- ## 2. L'idée clé de la théorie des types cubique
  
  La théorie des types cubique réintroduit le **contenu algorithmique (ou constructif)** de l'univalence et du quotient.
- ### Le cube géométrique (I)
  
  Au lieu de voir l'égalité p : x =_A y comme un type d'identité inductif opaque, la théorie cubique introduit un **intervalle abstrait** noté I (avec deux extrémités 0 et 1).
- Une égalité (un chemin) entre x et y est définie directement comme une **fonction** du type :
  `p : I \to A \quad \text{telle que} \quad p(0) \equiv x \quad \text{et} \quad p(1) \equiv y`
- En ajoutant plusieurs variables dans l'intervalle (i, j : I), on manipule des métaphores géométriques à n dimensions :
	- i : I \implies une ligne / un chemin (1D).
	- i, j : I \implies un carré / une homotopie entre deux chemins (2D).
	- i, j, k : I \implies un cube (3D), d'où le nom **cubique**.
- ## 3. Ce que les  *Cubical Types*  apportent de plus
- ### A. La canonicité restaurée
  
  Grâce à la structure géométrique des opérations d'extension de carré/cube (les opérations de *composition* et de *transport*), l'univalence devint un **théorème calculable** et non plus un axiome passif.
  
  > 
  
  **Résultat :** Tout terme fermé de type \mathbb{N} se réduit effectivement à un nombre entier, même s'il utilise l'univalence ou des types inductifs supérieurs.
- ### B. Types Inductifs Supérieurs ( *Higher Inductive Types*  - HITs)
  
  Dans HoTT classique, la définition de structures topologiques comme le cercle S^1 (défini par un point `base` et un chemin `loop : base = base`) nécessite de passer par des règles ad hoc. En type theory cubique :
- Les HITs deviennent des structures fondamentales faciles à manipuler.
- On peut calculer explicitement les groupes d'homotopie des sphères ou travailler sur des topos synthétiques directement par le calcul.
- ## 4. Implémentations modernes
  
  Les concepts cubiques ont été traduits dans plusieurs assistants de preuve expérimentaux et de production :
- **Cubical Agda :** L'extension cubique d'Agda est sans doute l'environnement le plus mûr pour pratiquer les mathématiques cubiques avec une vérification de type complète et exécutable.
- **redtt / cooltt :** Des assistants de preuve expérimentaux développés pour explorer la théorie des types cubique cartésienne et ses variantes.
- **Arend :** Un assistant développé par JetBrains Research fondé sur la théorie des types cubique.
- ## Synthèse comparative
  
  | Concept | HoTT Standard | Type Theory Cubique |
  
  | **Axiome d'univalence** | Axiome non calculable | Théorème prouvé & calculable |
  
  | **Égalité / Identité** | Type inductif (J-elim) | Fonctions depuis l'intervalle I \to A |
  
  | **Canonicité** | Perdue (bloquée par univalence) | Prervée (tout terme se réduit) |
  
  | **Calculabilité** | Partielle | Totale |