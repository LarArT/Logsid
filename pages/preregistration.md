- Pour appliquer concrètement la démarche de préenregistrement, les chercheurs utilisent des plateformes tierces qui font office d'**archives immuables et horodatées**. La plateforme de référence la plus utilisée mondialement est l'**OSF (Open Science Framework)**, gérée par le *Center for Open Science*.
  
  Voici les étapes méthodologiques standard à suivre sur une plateforme d'archivage de ce type pour préenregistrer un protocole avant d'analyser ou de collecter des données.
- ### Étape 1 : Création du projet et structuration
  
  Avant de figer un préenregistrement, vous créez un espace de travail numérique (un "Projet") sur la plateforme.
- **Initialisation :** Vous créez le projet en renseignant le titre de l'étude, la liste des co-auteurs (contributeurs) et une brève description globale.
- **Dépôt des annexes :** C'est le moment d'y téléverser les fichiers de travail qui ne changeront pas, comme le questionnaire exact qui sera diffusé, les scripts de code vides (R, Python) prévus pour les futurs calculs, ou le dictionnaire des variables (*codebook*).
- ### Étape 2 : Sélection et complétion du modèle ( *Template* )
  
  La plateforme ne vous laisse pas face à une page blanche. Pour garantir la rigueur, vous devez choisir un formulaire standardisé adapté à votre discipline. Sur OSF, les modèles les plus courants sont :
- **OSF Preregistration :** Le modèle standard et exhaustif.
- **AsPredicted Preregistration :** Un format très populaire et simplifié en 8 questions précises (idéal pour la psychologie ou l'économie expérimentale).
  
  Vous devez alors répondre de façon extrêmement précise aux sections suivantes :
- #### A. Hypothèses
  
  Vous devez formuler vos hypothèses de manière opérationnelle et testable.
  
  > 
  
  *Exemple vague (à éviter) :* "Le protocole de sécurité améliore la vigilance."
  *Exemple rigoureux (attendu) :* "Les agents ayant suivi le protocole X auront un temps de réaction moyen inférieur de 15 % au test de simulation Y par rapport au groupe témoin."
- #### B. Plan de d'échantillonnage ( *Sampling Plan* )
- Indiquez si les données existent déjà (analyse secondaire) ou s'il s'agit d'une nouvelle collecte.
- Déterminez à l'avance la **taille de l'échantillon** (ex: "Nous recruterons exactement 150 participants") et justifiez-la, souvent par un calcul de puissance statistique.
- Fixez la règle d'arrêt : à quel moment précis s'arrête la collecte (ex: une date butoir ou un nombre précis de réponses).
- #### C. Plan d'analyse ( *Analysis Plan* )
  
  C'est ici que l'on bloque le *p-hacking*. Vous devez spécifier :
- Les variables exactes : Quelle est la variable dépendante ? Quelles sont les variables indépendantes ?
- Les tests statistiques précis qui seront menés (ex: un test t de Student, une régression linéaire).
- **Les critères d'exclusion :** Comment gérerez-vous les données aberrantes ou les participants qui abandonnent en cours de route ? (ex: "Tout participant n'ayant pas répondu à 80 % des questions sera exclu de l'analyse").
- ### Étape 3 : La validation et l'horodatage ( *Timestamp* )
  
  Une fois le formulaire complété, vous cliquez sur "Enregistrer". Le système applique alors un **horodatage cryptographique** et génère un **DOI** (identifiant numérique d'objet) unique.
  
  À partir de cet instant précis :
- Le document devient **strictement non modifiable**. Il est figé dans l'archive.
- **Option d'embargo :** Vous pouvez choisir de rendre ce préenregistrement public immédiatement, ou de le placer sous **embargo** (généralement jusqu'à 4 ans). L'embargo permet de protéger vos idées contre le plagiat pendant que vous réalisez l'étude, tout en prouvant la préexistence de votre protocole. La plateforme permet aussi de générer un lien anonyme pour que les relecteurs du journal (*peer-reviewers*) puissent consulter le protocole caché sans connaître votre identité.
- ### Étape 4 : La phase de publication et confrontation
  
  Une fois l'étude terminée et l'article rédigé, vous devez inclure le lien vers votre préenregistrement archivé dans la section méthodologique de votre article scientifique.
  
  Deux scénarios se présentent alors :
- **Tout s'est passé comme prévu :** Vos analyses confirment ou infirment l'hypothèse. Le relecteur clique sur le lien de l'archive, vérifie que vous avez fait exactement ce qui était écrit, et valide la rigueur statistique.
- **Il y a eu des imprévus (Cas très fréquent) :** Un bug informatique a corrompu une partie des données, ou un modèle statistique prévu s'avère inapplicable.
	- **La règle d'or est la transparence :** Vous avez le droit de dévier du plan initial, mais vous devez l'écrire explicitement dans l'article final (ex: *"Nous avions prévu d'utiliser le test X dans notre préenregistrement [Lien], cependant, la distribution n'étant pas normale, nous avons dû appliquer le test non paramétrique Y. De plus, nous avons réalisé une analyse exploratoire non planifiée pour tester l'effet de..."*).
	  
	  Le préenregistrement n'est donc pas une prison méthodologique, mais une garantie de transparence qui sépare ce qui était prévu de ce qui a été découvert par opportunité.