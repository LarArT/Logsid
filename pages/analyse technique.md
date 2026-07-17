- Voici une analyse technique approfondie du fonctionnement interne de **Catala** et de l'approche d'**AVoCat**, ainsi que les liens vers leurs dépôts et codes sources.
- ## 1. Analyse technique du langage Catala
  
  Le langage Catala a été pensé pour résoudre un problème fondamental : le droit est souvent écrit sous forme de règles générales suivies d’exceptions, de sous-exceptions, et de cas particuliers. Les langages de programmation classiques (comme Python, Java, ou C) gèrent très mal cette structure sans devenir un enchevêtrement illisible de conditions complexes (`if/else`).
- ### L'architecture du compilateur et les choix techniques
- **La programmation littéraire (*Literate Programming*)**
  Catala est conçu pour la programmation littéraire. Le code source est un document unique (généralement en Markdown) qui mélange le texte brut de la loi (les articles de loi officiels) et le code informatique qui le traduit. Le code est imbriqué dans des blocs spécifiques, garantissant une correspondance exacte (1 pour 1) entre un paragraphe de loi et sa traduction logique.
- **La logique par défaut priorisée (*Prioritized Default Logic*)**
  Sous le capot, Catala est l'un des rares langages fondés directement sur la logique par défaut priorisée de Raymond Reiter. Au lieu de définir des priorités d'exécution temporelles (comme l'impératif), le programmeur déclare des règles et des exceptions. Le compilateur de Catala résout lui-même l'ordre logique d'application des règles, ce qui colle parfaitement à la structure du droit.
- **La chaîne de compilation (*Compilation Pipeline*)**
  Le compilateur est écrit en **OCaml** (un langage fonctionnel réputé pour la création de compilateurs robustes). Il traduit le code Catala en plusieurs étapes :
	- **Analyse et désucrage** : Transformation de la syntaxe de haut niveau (très proche de la langue naturelle, disponible en français et en anglais) en représentations intermédiaires.
	- **Typage formel** : Un système de types strict garantit qu'on ne mélange pas, par exemple, des durées, des montants en euros ou des profils familiaux.
	- **Représentation intermédiaire (Calcul λ à typage simple)** : Le code est compilé vers un langage fonctionnel minimal intermédiaire.
	- **Génération de code (*Backends*)** : Cette étape finale compile le code intermédiaire vers une multitude d'autres langages cibles pour s'intégrer aux infrastructures existantes de l'administration : **Python, OCaml, JavaScript (via API REST), C, ou même JSON**.
- ## 2. Analyse technique d'AVoCat : La vérification formelle
  
  **AVoCat** n'est pas un langage de programmation à proprement parler, mais une *action exploratoire* d'Inria dédiée à la recherche sur les méthodes formelles appliquées à Catala.
- ### Approche et outils de preuve
- **Vérification automatique et SMT-solving**
  Pour s'assurer que les lois traduites en Catala ne contiennent pas de contradictions internes ou de cas d'indétermination, AVoCat exploite des solveurs de contraintes et des outils de vérification automatique. Le compilateur Catala inclut un moteur d'analyse statique capable de traduire le programme Catala en formules logiques exploitables par des solveurs SMT (comme **Z3**).
- **Preuve formelle de la sémantique de Catala**
  Afin de prouver que le compilateur lui-même ne déforme pas le sens des règles lors de la traduction (par exemple, de Catala vers Python), l'équipe utilise des assistants de preuve formelle comme **F★ (F-star)** ou **Rocq (ex-Coq)**. Le schéma de compilation du langage a ainsi été entièrement formalisé et mathématiquement validé.
- **Arithmétique des dates**
  Un des enjeux critiques de la vérification réside dans le calcul des dates et des délais d'éligibilité (très complexes en droit social). Les chercheurs d'AVoCat ont par exemple conçu la bibliothèque spécifique **dates-calc** dotée d'une sémantique formelle stricte pour éliminer toute ambiguïté sur les fenêtres temporelles (ex: "le mois suivant", "pendant 3 mois", etc.).
- ## 3. Où trouver leur code source ?
  
  Les deux projets s'inscrivent pleinement dans une démarche d'**open source** et d'ouverture des codes publics encouragée par l'État français.
- ### Le dépôt officiel de Catala
  
  Tout le développement du langage (compilateur, syntaxe, exemples de législation encodée comme les aides au logement ou l'impôt sur le revenu) est centralisé sur GitHub au sein de l'organisation **CatalaLang** :
- **Dépôt principal du compilateur Catala** : [github.com/CatalaLang/catala](https://github.com/CatalaLang/catala)
	- *Langage principal :* OCaml
	- *Licence :* Apache 2.0 (permettant une réutilisation et un audit libres).
- **Dépôt de la bibliothèque de dates (dates-calc)** : [github.com/CatalaLang/dates-calc](https://github.com/CatalaLang/dates-calc)
- ### Le code source lié à AVoCat
  
  Les développements de recherche d'AVoCat sont souvent directement fusionnés dans le compilateur Catala principal (dans les sous-dossiers dédiés aux modules d'analyse statique ou aux outils d'interprétation symbolique). D'autres outils formels ou prototypes de recherche associés à l'équipe-projet SYCOMORES ou PROSECCO peuvent être consultés sur l'instance GitLab d'Inria :
- **GitLab Inria (SYCOMORES / PROSECCO)** : [gitlab.inria.fr](https://gitlab.inria.fr/) *(certains prototypes spécifiques sont hébergés sous les namespaces des chercheurs associés comme Raphaël Monat ou Aymeric Fromherz).*