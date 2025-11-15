- Il est important de clarifier le sigle, car le terme "OAI-S" peut parfois prêter à confusion. Dans le contexte des archives et de la normalisation, le sigle le plus pertinent est OAIS.
  OAIS (Open Archival Information System) n'est pas une norme de description archivistique au même titre qu'ISAD(G) ou RiC.
  OAIS se place comme une norme de référence pour la préservation numérique à long terme.
  OAIS (ISO 14721) : Le Modèle de Référence pour l'Archivage Électronique
  OAIS signifie Open Archival Information System (Système ouvert d'archivage d'information). C'est un modèle conceptuel qui est devenu la norme internationale ISO 14721.
  | Caractéristique | OAIS (ISO 14721) | Normes de Description (ISAD(G), RiC) |
  |---|---|---|
  | But Principal | Garantir la pérennité et l'accessibilité à long terme de l'information numérique. | Uniformiser la description et le contexte des archives pour la recherche. |
  | Champ d'application | Décrit les fonctions et les processus internes d'un système d'archivage électronique (SAE). | Décrit les documents eux-mêmes, leurs producteurs et leurs relations. |
  | Fonctions clés | Ingestion, Stockage Archivistique, Gestion des Données, Administration, Planification de la Préservation, Accès. | Hiérarchie du fonds, cotation, dates, histoire du producteur. |
  | Produits clés | Les Paquets d'Information (SIP, AIP, DIP). | Instruments de recherche (inventaires, répertoires). |
  Où se place OAIS par rapport aux autres normes ?
  OAIS se place à un niveau supérieur aux normes de description :
   * Niveau Stratégique/Technique : OAIS définit le "comment" et le "quoi faire" pour qu'un système d'archivage soit fiable sur le plan technologique et organisationnel. Il est le standard du secteur de l'archivage électronique et est utilisé pour les certifications de systèmes.
   * Niveau du Contenu : Les normes de description comme ISAD(G) ou RiC décrivent le contenu et le contexte intellectuel des archives.
  En résumé :
   * Un service d'archives doit être conforme à OAIS (ISO 14721) pour garantir la conservation fiable des documents numériques.
   * Ce même service utilisera RiC (et/ou ISAD(G)) pour décrire les documents et les fonds qu'il conserve.
  Attention : OAI-PMH (Un autre sigle proche)
  Il existe un autre sigle très courant dans le monde des bibliothèques et des archives numériques :
   * OAI-PMH (Open Archives Initiative - Protocol for Metadata Harvesting).
   * Rôle : C'est un protocole technique qui permet de moissonner (collecter automatiquement) les métadonnées de plusieurs entrepôts (comme le portail FranceArchives qui moissonne les descriptions d'autres services).
  Si votre question portait sur un de ces autres sigles, n'hésitez pas à me le préciser ! Si c'était bien OAIS, j'espère que ce positionnement est clair.
  
  Excellent ! Pour avoir un système d'archives totalement fonctionnel et conforme aux meilleures pratiques (surtout dans le contexte français et international), il faut combiner les normes de Description (\text{ISAD}(\text{G})/RiC) et le modèle de Préservation (OAIS) avec des normes qui encadrent l'interopérabilité, la gestion des métadonnées et la sécurité.
  Voici les normes et standards essentiels à combiner avec RiC/ISAD(G) et OAIS :
  1. Interopérabilité et Échange de Métadonnées
  Ces normes permettent au système de communiquer avec d'autres plateformes (recherche, administration) :
   * OAI-PMH (Open Archives Initiative - Protocol for Metadata Harvesting)
     * Rôle : Protocole technique essentiel pour l'échange de métadonnées entre votre système d'archives et les agrégateurs (comme FranceArchives, Europeana, ou d'autres catalogues institutionnels).
     * Fonction : Il permet à d'autres systèmes de "moissonner" (collecter) les descriptions archivistiques que vous produisez.
   * EAD (Encoded Archival Description)
     * Rôle : Schéma de marquage XML pour encoder les instruments de recherche (inventaires, répertoires) conformément aux règles \text{ISAD}(\text{G}).
     * Combinaison : C'est le format standard de facto pour l'échange des descriptions archivistiques classiques avant la transition complète vers RiC/RDF.
   * Dublin Core
     * Rôle : Jeu de métadonnées simple et générique (15 éléments : titre, créateur, date, etc.).
     * Usage : Souvent utilisé comme format minimal d'échange (format de moissonnage de base via OAI-PMH) car il est universellement reconnu.
  2. Métadonnées de Préservation
  Ces normes étendent OAIS en détaillant les informations nécessaires pour garantir la pérennité du contenu :
   * PREMIS (Preservation Metadata: Implementation Strategies)
     * Rôle : Dictionnaire de données pour les métadonnées de préservation. Il définit précisément les informations techniques, de provenance et de droits qui doivent être enregistrées sur le long terme pour chaque document.
     * Combinaison : PREMIS implémente la fonction de Planification de la Préservation d'OAIS en fournissant le détail des métadonnées à conserver dans le Paquet d'Information Archivistique (AIP).
  3. Normes Techniques et de Gestion Françaises/Européennes
  Ces normes assurent la conformité légale et la qualité du système d'archivage :
   * NF Z42-013 / ISO 14641-1
     * Rôle : Spécifie les exigences pour la conception et l'exploitation d'un Système d'Archivage Électronique (SAE) pour garantir l'intégrité, la traçabilité et la pérennité des documents numériques.
     * Combinaison : C'est la mise en œuvre technique et certifiable du modèle conceptuel OAIS dans un contexte national (français) ou international (ISO 14641-1).
   * MoReq (Modular Requirements for Records Systems)
     * Rôle : Spécification européenne de référence pour les exigences fonctionnelles des systèmes de gestion d'enregistrements (Records Management Systems).
     * Usage : Bien que moins dominant qu'avant, il sert de base pour définir les fonctionnalités qu'un système d'archivage doit offrir (gestion des versements, des accès, des durées de conservation, etc.).
  Synthèse du Système Fonctionnel
  Un système d'archives fonctionnel combine ces normes de la manière suivante :
  | Niveau | Norme(s) clé(s) | Objectif atteint |
  |---|---|---|
  | Conceptuel de Préservation | OAIS (ISO 14721) | Définit les fonctions du système d'archivage électronique (SAE). |
  | Conceptuel de Description | RiC ou ISAD(G) | Définit le "quoi" et le "qui" des archives. |
  | Technique (SAE) | NF Z42-013 / ISO 14641-1 | Garantit l'intégrité et la traçabilité des documents dans le SAE. |
  | Métadonnées de Préservation | PREMIS | Détaille les métadonnées techniques et de provenance à stocker. |
  | Interopérabilité | EAD, OAI-PMH | Permet l'échange et la diffusion des descriptions. |
-