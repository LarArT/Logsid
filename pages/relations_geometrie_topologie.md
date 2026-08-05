## 1. Objets et relations d'équivalence — le tableau de référence

Le point de méthode central : deux domaines ne sont comparables proprement que si l'on précise **sur quels objets** ils opèrent et **à quelle relation d'équivalence** ils classent ces objets. C'est l'omission de cette précision qui a produit les confusions des échanges précédents.

| Domaine | Objet de base | Classe à isomorphisme/équivalence près | Structure ajoutée par rapport au domaine « plus pauvre » dont il dépend |
|---|---|---|---|
| Topologie différentielle | Variété lisse | Difféomorphisme | Structure différentiable (sur un espace topologique) |
| Topologie algébrique | Espace topologique général | Équivalence d'homotopie (plus grossière que l'homéomorphisme) | — (outil algébrique, pas structure ajoutée) |
| Géométrie différentielle | Variété lisse + métrique *g* | Isométrie | Tenseur métrique (sur une variété lisse) |
| Géométrie euclidienne | ℝⁿ + métrique plate | Isométrie | Cas particulier : courbure ≡ 0 |
| Géométrie hyperbolique | ℍⁿ + métrique à courbure −1 | Isométrie | Cas particulier : courbure constante −1 |
| Géométrie des surfaces | Variété lisse de dimension 2 + métrique | Isométrie | Cas particulier : dimension = 2 |
| Géométrie algébrique | Variété algébrique (zéros d'un système de polynômes, sur un corps quelconque) | Isomorphisme de schémas | Topologie de Zariski (bien plus grossière que la topologie usuelle) sur un ensemble de solutions polynomiales |

---
- ## 2. Relations par paires, typées explicitement
- ### Dépendance (construction par ajout de structure — pas de déduction)
- **Topologie différentielle → Géométrie différentielle.** On part d'une variété lisse (objet de topologie différentielle) et on lui ajoute un tenseur métrique. Le foncteur d'oubli va de la géométrie différentielle vers la topologie différentielle (on peut toujours « oublier » la métrique), jamais l'inverse.
- ### Inclusion stricte (cas particulier au sein d'un domaine plus général)
- **Géométrie différentielle ⊃ Géométrie euclidienne.** ℝⁿ muni de la métrique plate est une variété riemannienne particulière (courbure identiquement nulle).
- **Géométrie différentielle ⊃ Géométrie hyperbolique.** ℍⁿ est une variété riemannienne particulière (courbure constante −1), définie en toute dimension n, pas seulement n = 2.
- **Géométrie différentielle ⊃ Géométrie des surfaces.** La géométrie des surfaces est la restriction de la géométrie riemannienne au cas dimension 2 — c'est historiquement le cas que Gauss a traité *avant* que Riemann ne généralise à toute dimension en 1854.
- ### Appartenance partielle (intersection, pas inclusion totale)
- **Géométrie des surfaces ∩ Géométrie euclidienne = le plan euclidien ℝ².** Le plan appartient à la géométrie des surfaces (dimension 2, courbure 0), mais la géométrie euclidienne existe aussi en dimension quelconque (ℝ³, ℝⁿ) — donc **géométrie euclidienne ⊄ géométrie des surfaces** en général ; seule sa restriction au plan y appartient.
- **Géométrie des surfaces ∩ Géométrie hyperbolique = ℍ² seulement.** Même raisonnement : ℍⁿ pour n > 2 n'appartient pas à la géométrie des surfaces.
- Résultat notable qui unifie ces trois cas : le **théorème d'uniformisation** (Poincaré-Koebe) affirme que toute surface de Riemann simplement connexe est conforme à l'une exactement de ces trois géométries modèles — sphère (courbure +1), plan (courbure 0), disque hyperbolique (courbure −1). C'est le théorème qui structure réellement la « trichotomie » que vos questions précédentes cherchaient à cerner.
- ### Exclusion (incompatibilité au sein d'un même objet)
- **Géométrie euclidienne et géométrie hyperbolique s'excluent mutuellement pour une métrique donnée.** Une même variété lisse peut porter successivement une métrique plate *et* une métrique hyperbolique (ce sont deux objets de géométrie différentielle distincts sur le même support topologique — le disque ouvert est difféomorphe à ℝ², l'un pouvant recevoir la métrique plate, l'autre la métrique de Poincaré) — mais une **métrique donnée** ne peut pas être simultanément à courbure 0 et à courbure constante −1. L'exclusion porte sur la métrique, pas sur la variété support.
- **Topologie algébrique et topologie différentielle utilisent des relations de classement incompatibles entre elles, sur des domaines qui se recouvrent partiellement.** Ce point a été établi dans un échange précédent : l'équivalence d'homotopie (topologie algébrique) est strictement plus grossière que le difféomorphisme (topologie différentielle) — un disque et un point sont homotopiquement équivalents sans être difféomorphes. Ce n'est donc ni une inclusion ni une dépendance, mais deux méthodes de classification différentes appliquées à des objets qui se recoupent (toute variété lisse est en particulier un espace topologique).
	- Pont entre les deux : le **théorème de de Rham** (déjà mentionné) montre que, pour les variétés lisses spécifiquement, les invariants différentiels (cohomologie de de Rham) et les invariants purement topologiques (cohomologie singulière) coïncident — sans quoi les deux domaines resteraient sans lien démontré.
- ### Recouvrement partiel sous condition (ni inclusion, ni exclusion générale)
- **Géométrie algébrique ∩ Géométrie différentielle : non vide seulement sur ℂ, et seulement pour les variétés lisses.** Une variété algébrique lisse sur ℂ est aussi, via ses points complexes munis de la topologie usuelle, une variété complexe donc une variété différentiable réelle — c'est le contenu du théorème de comparaison GAGA (Serre, 1956), qui identifie cohomologie algébrique cohérente et cohomologie analytique complexe pour les variétés projectives.
	- **Mais cette intersection est vide en dehors de ℂ.** Une variété algébrique sur un corps fini 𝔽_p ou sur un corps p-adique n'a *aucune* structure de variété différentiable réelle sous-jacente — la notion même n'a pas de sens dans ce contexte. Sur ces objets, la géométrie algébrique et la géométrie différentielle sont en **exclusion totale de domaine**, pas en recouvrement partiel.
- **Géométrie algébrique ∩ Topologie algébrique : recouvrement par emprunt d'outils, pas par les objets eux-mêmes.** La topologie de Zariski des variétés algébriques est si grossière (les fermés sont les seuls lieux d'annulation de polynômes) qu'elle interdit l'usage direct des outils classiques de la topologie algébrique (par exemple, elle n'a essentiellement pas de chemins continus non constants). Grothendieck a donc dû **reconstruire** un analogue — la cohomologie étale — plutôt que d'appliquer directement la topologie algébrique classique. La relation ici n'est ni une inclusion ni une simple dépendance : c'est un transfert méthodologique motivé par une analogie, nécessitant une reconstruction complète des outils.
  
  ---
- ## 3. Diagramme de synthèse
  
  ```
                    Topologie différentielle
                    (variétés lisses, à difféomorphisme près)
                              |
                    [ajout d'une métrique — dépendance, pas déduction]
                              |
                    Géométrie différentielle
                    (variétés riemanniennes, à isométrie près)
                    /         |          \
              [dim=2]     [courbure≡0]   [courbure≡ -1, dim n quelconque]
                /              |                \
    Géométrie des surfaces   Géométrie          Géométrie hyperbolique
    (dim 2, toute courbure)  euclidienne        (toute dimension)
                \              |                /
                 \             |               /
              [intersection : les 3 géométries modèles en dim 2,
               unifiées par le théorème d'uniformisation]
  
  
    Topologie algébrique                    Géométrie algébrique
    (espaces topo. généraux,                (variétés algébriques,
     à homotopie près)                       topologie de Zariski)
              \                                    /
               \ [pont partiel et reconstruit,     /
                  pas d'inclusion directe :        /
                  de Rham d'un côté, GAGA          /
                  et cohomologie étale             /
                  de l'autre]                     /
                \___________________________/
                  recouvrement conditionnel
                  (sur ℂ, variétés lisses seulement)
  ```
  
  ---
- ## 4. Erreurs à ne pas reproduire (résumé des points déjà corrigés)
  
  1. « Découle de » suggère une déduction logique — c'est presque toujours, ici, un **ajout de structure**, pas un théorème qui en implique un autre.
  2. « Plongé dans » a un sens précis (un objet ⊂ un espace ambiant plus grand de même nature) — on ne plonge pas une géométrie dans une topologie, ni une théorie dans une autre.
  3. Une **signature algébrique** (comme (2,1)) et un **trou topologique** (comme dans « ℝ² privé d'un point ») appartiennent à deux grammaires différentes — algèbre bilinéaire contre topologie algébrique — et ne se traduisent pas l'une dans l'autre.
  4. « Raffinement » implique classer plus finement — la topologie algébrique classe *plus grossièrement* que la topologie différentielle (homotopie plus grossière que difféomorphisme), donc l'inverse de « raffinement » est plus proche de la vérité pour cette paire précise.