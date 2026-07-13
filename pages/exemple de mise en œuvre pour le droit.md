- https://www.inria.fr/fr/catala-logiciel-administration-dgfip-cnaf https://www.inria.fr/fr/avocat
- https://ultv.univ-lorraine.fr/video/22354-logique-et-linguistique-de-linformatisation-du-droit/?hl=fr-FR
- Voici un exposé détaillé présentant les projets **Catala** et **AVoCat**, deux initiatives complémentaires d'Inria situées à la frontière du droit et des sciences du numérique.
- # Exposé : La formalisation et la vérification du droit par l'informatique
  
  La traduction des textes législatifs et réglementaires en programmes informatiques est un défi majeur de l'État moderne. Qu'il s'agisse de calculer l'impôt sur le revenu ou de distribuer des prestations sociales, l'administration s'appuie massivement sur des logiciels. Pour garantir que ces systèmes appliquent fidèlement la loi sans approximations ni biais d'interprétation, Inria soutient deux projets scientifiques de premier plan : **Catala** et **AVoCat**.
- ## 1. Catala : Un langage de programmation au service de la loi
- ### Origine et philosophie du projet
  
  L'idée de **Catala** est née du constat que les systèmes informatiques administratifs reposent souvent sur des technologies patrimoniales complexes et vieillissantes (comme le langage *M* utilisé par la Direction générale des Finances publiques).
  
  Initié par **Denis Merigoux** (Inria), le projet Catala part d'une feuille blanche pour concevoir un langage de programmation moderne, spécifiquement adapté aux structures logiques des textes de loi. Catala a reçu en 2026 le prestigieux *Prix de l'interdisciplinarité scientifique*, soulignant l'importance d'une collaboration étroite entre informaticiens, juristes et sociologues.
- ### Une approche interdisciplinaire unique
  
  Pour préserver l'esprit de la loi et éviter les erreurs de traduction, l'équipe associe :
- **Des informaticiens** (concepteurs du langage et des compilateurs).
- **Des juristes** (comme Liane Huttner, maîtresse de conférences en droit, et Sarah Lawsky, professeure de droit fiscal et logique formelle).
- **Des sociologues** (Marie Alauzen, spécialiste de la modernisation de l'État).
  
  Cette méthode permet aux juristes et aux développeurs de travailler ensemble directement sur le code. Le but n'est pas de tout automatiser, mais de modéliser avec précision le droit "algorithmique" déjà exécuté par les machines (impôts, allocations, assurance chômage).
- ### Applications concrètes et preuves de concept (POC)
  
  Catala n'est pas qu'un projet théorique ; il s'implante déjà au cœur de l'État à travers deux expérimentations majeures :
- **La Caisse Nationale des Allocations Familiales (CNAF)** : Des études sont menées pour évaluer Catala comme base du futur système de calcul de l'intégralité des prestations sociales en France.
- **La Direction Générale des Finances Publiques (DGFIP)** : Un POC a été développé pour le calcul de l'impôt sur le revenu afin d'analyser les gains en matière de maintenance, d'efficacité et d'explicabilité par rapport aux solutions historiques.
- ## 2. AVoCat : La vérification automatique pour garantir la confiance
- ### Qu'est-ce que l'action exploratoire AVoCat ?
  
  Si Catala permet d'écrire la loi sous forme de code compréhensible par les juristes, **AVoCat** (pour *Vérification Automatique de Programmes Catala*) intervient pour s'assurer de la rigueur mathématique absolue de ces programmes.
  
  Menée par les équipes-projets **PROSECCO** et **SYCOMORES** d'Inria (sous la responsabilité scientifique de **Raphael Monat** et **Aymeric Fromherz**), cette action exploratoire développe des outils de preuve formelle.
- ### Les objectifs scientifiques de AVoCat
- **Prouver formellement** : S'assurer mathématiquement que les codes de calcul de prestations sociales ou d'impôts respectent les propriétés de correction et de sûreté juridique dictées par les textes d'origine.
- **Garantir l'absence de bugs et d'incohérences** : Le compilateur et les outils de vérification sont capables de détecter automatiquement si des règles se contredisent ou si des cas particuliers ont été oubliés par le législateur.
- **Générer des contre-exemples concrets** : Si le programme détecte une faille ou une faille de sécurité logique, l'outil produit un cas pratique (un profil d'allocataire ou de contribuable fictif) mettant en évidence le problème, permettant aux juristes de corriger la règle ou sa formulation.
- ## 3. Synergie et perspectives d'avenir
  
  Le couple **Catala & AVoCat** incarne une vision moderne de l'administration publique numérique, reposant sur trois piliers fondamentaux :
- **La fidélité au droit** : Le code informatique devient une copie exacte de l'esprit et de la lettre de la loi.
- **La transparence et l'explicabilité** : Les citoyens et les administrations peuvent comprendre précisément comment chaque décision de calcul a été prise.
- **La sécurité juridique** : Grâce aux méthodes formelles d'AVoCat, l'État peut tester l'impact et la cohérence de nouvelles réformes fiscales ou sociales avant même leur adoption définitive, évitant ainsi des erreurs d'application de grande ampleur.