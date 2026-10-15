Alias:: Standard Operating Procedure, SOP

- La **Procédure Opérationnelle Standard (SOP - Standard Operating Procedure)** est le document de référence qui traduit la théorie (votre plan de contingence ou vos modèles ergonomiques) en **actions concrètes, séquencées et répétables**.
  Dans le secteur de la télésurveillance assistée par IA, la SOP est ce qui garantit que deux opérateurs différents réagiront de la même manière face à une alerte identique.
- ## 1. Structure type d'une SOP (Format "Action/Réaction")
  Une SOP efficace doit être rédigée de manière impérative et visuelle. Voici les sections indispensables :
  * **Identifiant :** Code unique (ex: SOP-SURETE-01) et version.
  * **Objectif :** Ce que la procédure doit résoudre (ex: "Levée de doute après détection d'intrusion").
  * **Déclencheur (Trigger) :** L'événement qui lance la procédure (ex: Alerte rouge sur le logiciel VSA).
  * **Étapes de l'action :** Liste numérotée et chronologique.
  * **Logigramme :** Une représentation visuelle (type *Diagrams.net* ou *Mermaid*).
- ## 2. Exemple concret : SOP "Détection de Comportement Suspect par IA"
  Voici comment se décline une SOP moderne intégrant la technologie et l'humain :
- ### Étape 1 : Validation de l'alerte (Filtrage)
  * **L'IA émet une alerte** (encadré jaune sur l'écran).
  * **L'opérateur dispose de 10 secondes** pour confirmer s'il s'agit d'un "Vrai Positif" (humain) ou d'un "Faux Positif" (reflet, animal).
  * *Si Faux Positif :* Acquitter l'alerte et noter le motif pour l'entraînement de l'IA.
- ### Étape 2 : Analyse contextuelle (Ergonomie Cognitive)
  * L'opérateur utilise les caméras adjacentes pour suivre la cible (**tracking**).
  * **Vérification des critères :** La cible porte-t-elle des outils ? Présente-t-elle une posture de guet ? Est-elle dans une zone de haute sensibilité ?
- ### Étape 3 : Action immédiate
  * **Activation de l'interphonie :** "Monsieur, vous êtes dans une zone protégée, veuillez vous identifier."
  * **Déclenchement des mesures actives :** Allumage des projecteurs, sirène ou canon à brouillard si le périmètre est franchi.
- ### Étape 4 : Escalade et Reporting
  * Appel des forces de l'ordre ou de l'agent de patrouille via la ligne prioritaire.
  * Envoi du flux vidéo en temps réel sur la tablette de l'agent de terrain.
  * Clôture de l'incident dans le main courante informatique (MCI).
- ## 3. La SOP dans le cadre de la maintenance de l'IA
  Originalement, dans les métiers de demain, il existera des **SOP de "Correction Algorithmique"** :
  > **SOP-IA-RECALIBRAGE :**
  >  1. Si l'algorithme génère plus de 15% de faux positifs sur une heure.
  >  2. L'opérateur doit basculer en mode "Sensibilité Réduite".
  >  3. Ouvrir un ticket d'incident auprès du Data Scientist de garde.
  >  4. Capturer les séquences erronées pour le "Re-training".
  > 
  ## 4. Outils pour créer et gérer vos SOP
  Pour que vos procédures ne soient pas des documents Word poussiéreux, utilisez :
  * **Logiciels de Workflow :** *Camunda* (comme vu précédemment) pour rendre la SOP "exécutable".
  * **Checklists Dynamiques :** Des outils comme *Manifest.ly* ou *SweetProcess* qui obligent l'opérateur à cocher chaque étape sur sa tablette.
  * **Vidéo-SOP :** Utiliser des tutoriels courts pour montrer le comportement attendu.
  ## 5. Pourquoi la SOP est cruciale pour l'Ergonome ?
  L'ergonome analyse les SOP pour détecter les **"points de friction"**.
  * *Exemple :* Si la SOP demande à l'opérateur de taper 12 caractères pour confirmer une alerte alors qu'il est en situation de stress, l'ergonome simplifiera la procédure (ex: un seul bouton physique "Panic Button").
  **Souhaitez-vous que je génère le code d'un logigramme Mermaid (visuel) pour une SOP spécifique (incendie, intrusion, panne système) que vous pourriez copier-coller dans un éditeur ?**