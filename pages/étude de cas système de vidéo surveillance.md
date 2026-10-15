concevoir et mettre en œuvre un système de vidéosurveillance

Étude du référentiel APSAD R82 : champ d'application, exigences réglementaires, philosophie et concepts de base, approche méthodologique, analyse de risque, conception du système de vidéosurveillance, règles pour la réalisation de l'installation, maintenance, exigences complémentaires, déclaration de conformité - N82, compte rendu de vérification périodique - Q82.


peux-tu rédiger une étude de cas APSAD R82 exhaustif, de classe mondiale

Excellent, j'ai maintenant suffisamment d'informations. Laissez-moi préparer l'étude de cas exhaustive. Je vais créer un document complet.

Créons maintenant une étude de cas détaillée sous forme d'un document structuré.

- # Étude de Cas Exhaustif : Conception et Mise en Œuvre d'un Système de Vidéosurveillance selon le Référentiel APSAD R82
- ## Résumé Exécutif
  
  Le présent document constitue une étude de cas complète et de classe mondiale relative à la conception, l'installation et la maintenance d'un système de vidéosurveillance conforme au référentiel APSAD R82 (édition février 2021). Le référentiel APSAD R82 est un référentiel technique de certification volontaire délivré par le Centre National de Prévention et de Protection (CNPP), destiné à accompagner les utilisateurs, prescripteurs et installateurs dans la conduite d'un projet de vidéosurveillance. Cette étude explore en profondeur tous les éléments constitutifs du référentiel, de son cadre réglementaire jusqu'à l'exploitation opérationnelle du système, en passant par l'analyse des risques, la conception technique précise, la réalisation de l'installation, la réception, la maintenance et la conformité documentaire[1][2][3].
  
  ***
- ## 1. Cadre Réglementaire et Contextuel
- ### 1.1 Fondements Législatifs et Réglementaires
  
  La vidéosurveillance en France s'inscrit dans un cadre réglementaire complexe qui distingue clairement deux catégories : la **vidéoprotection** (systèmes installés dans l'espace public ou lieux ouverts au public) et la **vidéosurveillance** (systèmes privés). Cette distinction revêt une importance capitale car elle détermine le régime d'autorisation et les obligations applicables[4][5].
  
  L'évolution législative a connu plusieurs jalons importants. D'abord, la **loi du 21 janvier 1995** a instauré un cadre réglementaire initial avec un régime d'autorisation préfectorale. Ensuite, la **loi du 26 janvier 2006** a étendu les finalités admissibles en intégrant la lutte contre le terrorisme. Plus récemment, l'**arrêté du 3 août 2007** a défini des normes techniques précises pour les systèmes de vidéoprotection, fixant les spécifications minimales relatives à la résolution, à la fréquence d'enregistrement et aux formats d'image[5][6][7]. Enfin, la **loi du 23 mai 2023** relative aux Jeux Olympiques et Paralympiques de 2024 a reconnu formellement la vidéoprotection comme un traitement de données à caractère personnel, intégrant ainsi pleinement ces systèmes dans le cadre du Règlement général sur la protection des données (RGPD)[5].
- ### 1.2 Conformité au RGPD et à la Protection des Données
  
  Depuis l'entrée en vigueur du RGPD le 25 mai 2018, les systèmes de vidéosurveillance doivent respecter des obligations strictes en matière de protection des données personnelles. Le responsable de traitement doit identifier une **base légale** pour justifier le traitement des images[4]. Pour les dispositifs privés, cela s'effectue généralement sur la base de l'**intérêt légitime** (article 6.1.f du RGPD), qui doit être démontré comme répondant à une nécessité réelle (protection des biens, sécurité des personnes)[4].
  
  Une obligation fondamentale porte sur la **durée de conservation des données**. Selon la CNIL, les images provenant de caméras filmant la voie publique ou un lieu ouvert au public ne doivent pas être conservées plus de **un mois**[8][9]. En pratique, un délai de **7 à 15 jours** est généralement recommandé pour permettre les vérifications nécessaires en cas d'incident, tout en respectant le principe de minimisation des données[8][9][10].
  
  De plus, une **analyse d'impact sur la protection des données (AIPD)** doit être réalisée, notamment lorsque la surveillance est systématique et à grande échelle. Les personnes filmées doivent être **informées** de l'existence du système, du responsable du traitement, de la durée de conservation et de leurs droits (accès, rectification, suppression). La signalisation visuelle des caméras par des panneaux explicites est obligatoire[5].
- ### 1.3 Philosophie et Objectifs du Référentiel APSAD R82
  
  Le référentiel APSAD R82 repose sur une **approche méthodique et structurée** destinée à garantir l'efficacité opérationnelle des installations tout en respectant les exigences réglementaires et les principes de protection des données[1][3]. Le référentiel n'est pas obligatoire, mais son application volontaire offre plusieurs avantages : elle confère une certification reconnue par les assureurs, elle démontre la conformité réglementaire et elle fournit un cadre d'excellence technique[1][11].
  
  Les **principes fondamentaux** du référentiel sont les suivants[12][11]:
  
  1. **Adaptation au contexte** : La solution proposée doit être spécifiquement conçue en fonction des besoins et des risques identifiés, et non pas standardisée de manière générique.
  
  2. **Pluralité des rôles** : Un système de vidéosurveillance peut assumer plusieurs rôles complémentaires, chacun imposant des exigences techniques différentes. Ces rôles doivent être clairement définis avant toute conception.
  
  3. **Sécurité globale** : Au-delà des aspects technologiques, le système doit intégrer une sécurité organisationnelle (accès restreint, traçabilité des opérations) et, depuis l'édition 2021, une **cybersécurité** (conformément au référentiel APSAD D32)[3][13].
  
  4. **Documentation exhaustive** : Le suivi du projet par des documents formalisés (analyse des risques, cahier des charges, déclaration de conformité N82, comptes rendus Q82) garantit la traçabilité et la responsabilité[1][14].
  
  ***
- ## 2. Analyse des Besoins et des Risques
- ### 2.1 Identification des Secteurs Visualisés
  
  L'analyse des besoins débute par un **diagnostic contextuel** permettant de caractériser précisément les zones à surveiller. Cette phase doit documenter les éléments suivants[12]:
- #### 2.1.1 Activité Principale
  
  Il s'agit de définir précisément la nature de l'activité exercée sur le site : activité commerciale (magasin, banque, supermarché), activité tertiaire (siège administratif, bureau), activité industrielle (usine, entrepôt), secteur public (école, hôpital, mairie), etc. Chaque type d'activité présente un **profil de risque distinct** et impose des exigences spécifiques[12].
- #### 2.1.2 Environnement
  
  L'environnement du site conditionne fortement les choix technologiques. Il faut documenter :
- **Conditions d'éclairement** : zones bien éclairées, zones de pénombre, zones sombres nécessitant une vision nocturne infrarouge
- **Conditions climatiques** : température, humidité, exposition aux intempéries (pluie, neige, brouillard), poussière
- **Conditions de circulation** : zones densément fréquentées ou isolées, flux de foules rapides ou lents
- **Topographie** : surfaces planes, zones surélevées, sous-sols, niveaux multiples[12]
- #### 2.1.3 Accessibilité
  
  Il faut identifier si les caméras et les équipements seront **facilement accessibles** aux personnes malveillantes, nécessitant ainsi une protection mécanique renforcée, ou s'ils sont **protégés naturellement** par la géométrie du site[12].
- #### 2.1.4 Présence Humaine
  
  La **densité et la nature de la présence humaine** influencent directement les exigences de performance du système :
- Nombre de personnes présentes simultanément
- Horaires de présence (24h/24, heures de bureau, horaires variables)
- Statuts des présents (employés, clients, visiteurs, inconnus)
- Possibilité de présence hors heures normales[12]
- #### 2.1.5 Exigences Particulières
  
  Certains secteurs d'activité imposen des **contraintes spéciales** :
- Secteur bancaire : surveillance des zones sensibles (coffres, comptoirs de caisse), conformité aux exigences de sûreté malveillance
- Secteur hospitalier : respect de la vie privée des patients, zones interdites de filmage
- Secteur éducatif : absence de filmage des zones de vie privée, accord avec les tuteurs légaux
- Secteur industriel : intégration avec d'autres systèmes de sécurité (détection d'intrusion, extinction automatique)[12]
- #### 2.1.6 Exigences Réglementaires
  
  Il faut examiner si le site est soumis à :
- Obligations de vidéoprotection (espace public, sûreté publique)
- Normes d'assurance spécifiques
- Codes d'accès professionnels (normes de sécurité des établissements financiers, normes hospitalières, etc.)[12]
- ### 2.2 Identification des Rôles
  
  Le référentiel APSAD R82 **énumère six rôles** potentiels qu'un système de vidéosurveillance peut assumer[1][12]. Chaque rôle impose des exigences techniques distinctes, notamment en termes de résolution, de champ visuel et de capacité d'enregistrement[1]. L'identification précise des rôles est donc critique :
- #### Rôle 1 : Aider à la Surveillance
  
  Ce rôle vise à **surveiller l'activité d'un site** en temps réel ou en temps différé, en permettant à un opérateur humain d'identifier les anomalies ou comportements suspects. Les exigences de résolution sont modérées : une visualisation permettant de discerner si une personne est présente et de suivre ses déplacements suffit souvent. Ce rôle est adapté aux salles de contrôle, aux accueils, aux zones de circulation principales[1][12].
- #### Rôle 2 : Déterminer l'Origine d'un Acte de Malveillance
  
  Ce rôle impose des exigences de résolution **très élevées** car l'objectif est de **pouvoir identifier les auteurs** d'actes délictueux (vols, dégradations, cambriolages) sur la base des enregistrements. Il est typique dans les environnements à risque (banques, bijouteries, dépôts de fonds)[1][12]. Les caméras doivent fournir des images d'une qualité suffisante pour permettre une identification par les autorités judiciaires.
- #### Rôle 3 : Lever le Doute en Cas d'Alarme
  
  Lorsqu'un système de détection d'intrusion ou un capteur déclenche une alarme, le rôle de **levée de doute** consiste à vérifier rapidement l'authenticité de l'alerte en visualisant la zone en question. Cela permet à un opérateur distant ou un télésurveillant de confirmer qu'une véritable intrusion est en cours avant de solliciter l'intervention des forces de l'ordre[1].
- #### Rôle 4 : Assister le Contrôle des Flux
  
  Ce rôle s'applique aux situations où l'on doit **compter ou analyser les flux de personnes ou de véhicules**, notamment pour la gestion du trafic, le contrôle des accès, l'analyse des affluences en milieu commercial. Les exigences de résolution sont modérées à moyennes selon la densité de flux[1][12].
- #### Rôle 5 : Détecter le Déplacement d'Objets ou d'Individus
  
  Ce rôle vise à **déclencher des alertes** basées sur des capteurs de mouvement ou sur de l'analyse vidéo intelligente. Il nécessite une vigilance continue et une **capacité de détection de présence**, même si les détails fins ne sont pas toujours discernables[1].
- #### Rôle 6 : Contribuer à la Gestion d'Activité ou à la Prévention
  
  Ce rôle s'applique aux situations où les enregistrements vidéo servent à **analyser l'activité** (comportements des clients en magasin, efficacité des processus de travail, prévention des accidents). Les exigences de résolution dépendent de la nature précise de l'analyse souhaitée[1].
- ### 2.3 Mode d'Exploitation Envisagé
  
  Le **mode d'exploitation** décrit comment le système sera utilisé au quotidien[12]:
- **Surveillance en direct** : opérateur humain dans un poste de contrôle
- **Enregistrement continu** : vidéo gravée en permanence, consultée ultérieurement en cas de besoin
- **Enregistrement sur événement** : enregistrement déclenché par un détecteur (détecteur de mouvement, capteur d'intrusion)
- **Télésurveillance** : surveillance par un opérateur distant (centre de télésurveillance certificié APSAD R31)[1][12]
- **Analyse vidéo intelligente** : traitement automatisé des images par un système d'IA pour détecter des anomalies
- ### 2.4 Critères d'Intégrité et Autonomie du Système
  
  Le référentiel exige une formalisation des **critères d'intégrité** du système, c'est-à-dire le niveau de **continuité de service** attendu[12]:
- **Niveau standard** : perte tolérable de quelques heures par an
- **Niveau renforcé** : continuité quasi-permanente requise, alimentations secondaires (batterie, onduleur) obligatoires
- **Autonomie minimum** : pour les installations sans alimentation de secours, capacité d'enregistrement minimal (par exemple, 4 heures minimum en cas de coupure d'alimentation)
- ### 2.5 Formalisation de l'Analyse des Besoins et des Risques
  
  Toute cette analyse doit être **documentée formellement** dans un rapport d'analyse des besoins et risques, généralement complété à l'aide du **tableau d'aide à l'analyse** (ANNEXE 3a du référentiel R82)[2][12]. Ce document remplit plusieurs fonctions :
  
  1. Il servira de **fondation au cahier des charges** de l'installation
  2. Il justifiera les **choix technologiques** en aval
  3. Il constituera une **pièce du dossier technique** remis au client à la fin du projet
  4. Il fournira le **cadre de référence** pour évaluer la conformité finale[2][12]
  
  ***
- ## 3. Conception du Système de Vidéosurveillance
- ### 3.1 Principes Généraux de Conception
  
  La phase de conception traduit les **besoins et risques identifiés** en une **architecture technique concrète**. Le système doit être dimensionné selon une approche rigoureuse fondée sur des normes reconnues[12].
- #### 3.1.1 Niveaux de Sécurité : Standard et Renforcé
  
  L'édition 2016 du référentiel R82 a introduit la distinction entre deux **niveaux de sécurité**[12]:
- **Niveau standard** : applicable à la majorité des installations courantes, offrant un bon compromis coût-performance
- **Niveau renforcé** : destiné aux sites sensibles (fonds et valeurs, secteur critique) ou lorsque le risque est évalué comme particulièrement élevé
  
  Les exigences techniques relatives à la caméra, la transmission, le stockage et l'alimentation peuvent différer selon le niveau choisi[12][13].
- #### 3.1.2 Classification des Zones de Visualisation selon EN 62676-4
  
  La norme européenne **EN 62676-4:2015** établit un standard international pour évaluer la capacité de visualisation des caméras, exprimée en **pixels par mètre (PPM)** ou **pixels par pied (PPF)**. Cette norme définit quatre **zones de visualisation** correspondant à des tâches opérationnelles distinctes[15][16]:
  
  | Zone | Densité PPM | Pixels/Mètre | Capabilité |
  |------|------------|--------------|-----------|
  | Détection | 25 PPM | 25 pixels/m | Déterminer la présence d'une personne/véhicule |
  | Observation | 62 PPM | 62 pixels/m | Observer des détails vestimentaires distinctifs |
  | Reconnaissance | 125 PPM | 125 pixels/m | Reconnaître une personne déjà observée |
  | Identification | 250 PPM | 250 pixels/m | Identifier une personne sans équivoque |
  
  Ces valeurs constituent des **minimums** permettant de réaliser les tâches dans des conditions d'éclairage standard. Des facteurs comme l'**éclairage insuffisant** ou le **mouvement rapide** peuvent nécessiter des densités supérieures (jusqu'à 350-400 PPM pour l'identification en conditions difficiles)[15][16][17].
- ### 3.2 Exigences de Prise de Vue
- #### 3.2.1 Implantation des Caméras
  
  L'implantation des caméras constitue l'une des **décisions les plus critiques** de la conception. Chaque caméra doit être positionnée pour[12]:
  
  1. **Couvrir l'intégralité des zones à surveiller** : identification des zones mortes ou de pénombre
  2. **Respecter les angles de champ** optimaux : prise en compte de la distorsion d'objectif (fish-eye pour larges champs, téléobjectif pour détails lointains)
  3. **Minimiser les reflets et les contre-jours** : éviter que les sources de lumière directe se reflètent sur l'objectif
  4. **Assurer l'accessibilité au nettoyage et à la maintenance** : retrait des caméras pour maintenance
  5. **Résister à la malveillance** : protection contre les jets de peinture, les masquages, les tentatives de destruction[12]
- #### 3.2.2 Dimensionnement d'un Objet ou d'une Cible
  
  Le **dimensionnement** vise à calculer si une caméra placée à une distance donnée avec une optique donnée produira une densité de pixels suffisante pour atteindre l'objectif visé (détection, reconnaissance, identification)[12].
  
  La **formule de dimensionnement** s'exprime ainsi :
  
  $$ \text{Distance maximale} = \frac{\text{Hauteur de la cible (m)} \times \text{Résolution horizontale (pixels)}}{\text{PPM requis} \times \text{Focale optique (mm)} \times 1000} $$
  
  Par exemple, pour **identifier un visage de 0,20 m de hauteur** avec une caméra de 1920 pixels de largeur, exigeant 250 PPM minimum, et une optique de 4 mm :
  
  $$ \text{Distance} = \frac{0,20 \times 1920}{250 \times 4 \times 1000} = \frac{384}{1000000} \approx 3,84 \text{ mètres} $$
  
  Dans la pratique, un **logiciel de calcul de positionnement** (comme IP Video System Design Tool) facilite ces calculs en superposant les zones sur un plan du site[15].
- #### 3.2.3 Caractéristiques des Caméras
  
  Les caméras doivent respecter des **exigences minimales de performance**[12][13]:
  
  **Résolution** :
- Minimum **2 mégapixels (1920 x 1080)** pour une surveillance standard
- **5 mégapixels ou supérieur** pour des tâches d'identification ou de reconnaissance dans de vastes zones
- **8 mégapixels ou 4K** pour des couvertures larges exigeant une identification
  
  **Sensibilité** :
- Sensibilité minimale permettant une **visualisation en conditions de faible luminosité** (généralement 0,1 lux minimum pour caméra couleur, 0,01 lux pour infrarouge)
- Évaluation de la **gamme dynamique** pour les zones alternant ombre et lumière[12]
  
  **Types de caméras** :
- Caméras **IP (Protocole Internet)** : approche moderne, réseau numérique
- Caméras **analogiques HD** : approche hybride, transmission coaxiale
- Caméras **thermiques** : vision nocturne infrarouge pour surveillance lointaine
  
  **Intégration cybersécurité** (depuis édition 2021) :
- Pour les installations de niveau renforcé, les caméras doivent être **certifiées « CNPP Certified »** attestant de leur robustesse contre les attaques numériques[3][18][13]
- Respect du référentiel APSAD D32 concernant les niveaux de sécurité informatique[3][13][19]
- #### 3.2.4 Éclairement de la Scène
  
  L'éclairage exerce une **influence décisive** sur la qualité de l'image vidéo[12]:
- **Zones extérieures bien éclairées** : éclairage naturel ou éclairage public
- **Zones faiblement éclairées** : nécessité d'éclairage supplémentaire (projecteurs LED, éclairage infrarouge non visible)
- **Zones alternant ombre et lumière** : exigence de **gamme dynamique** élevée (HDR - High Dynamic Range) ou utilisation de caméras infrarouge
  
  Les sources de lumière doivent être **positionnées** pour éviter les contre-jours qui rendraient les visages en silhouette[12].
- ### 3.3 Exigences Générales de Transport des Données
- #### 3.3.1 Transport des Données sur Site
  
  Le transport des données vidéo depuis les caméras vers le système d'enregistrement peut s'effectuer selon plusieurs architectures[12]:
  
  **Architecture coaxiale (traditionnel)** :
- Câbles coaxiaux RG59 ou similaire
- Avantage : compatibilité avec installations existantes
- Inconvénient : limitation de distance, encombrement, qualité limitée
  
  **Architecture IP (moderne)** :
- Câbles Ethernet catégorie 5e ou 6 (PoE - Power over Ethernet possible)
- Avantage : flexibilité, distances importantes, intégration réseau, résilience
- Inconvénient : complexité informatique, cybersécurité requise
  
  **Architecture hybride** :
- Combinaison de technologies (certaines caméras en IP, d'autres en coaxiale)
  
  La **bande passante** requise dépend du nombre de caméras, de leur résolution, du taux d'images par seconde (FPS) et du **codec de compression** utilisé[12].
- #### 3.3.2 Transport des Données à Distance
  
  Pour la **télésurveillance** ou l'accès distant aux enregistrements, le transport s'effectue via[12]:
- **Connexion Internet sécurisée** (HTTPS, VPN)
- **Liaison de données dédiée** (ADSL, fibre optique)
- Redondance pour garantir la continuité de service en cas de défaillance
- ### 3.4 Exigences de Restitution de l'Image
- #### 3.4.1 Exigences sur le Matériel
  
  Les **moniteurs ou écrans** doivent présenter des spécifications minimales[12]:
- **Taille minimale** : 17 pouces pour une visualisation confortable
- **Résolution** : minimale 1920 x 1080 pixels (Full HD)
- **Calibrage** : conformité aux normes de calibrage des écrans pour assurer une restitution fidèle des couleurs
- **Nombre d'écrans** : un écran principal par opérateur, complété éventuellement par des écrans de contexte
- #### 3.4.2 Configuration du Poste d'Exploitation
  
  Le **poste d'exploitation** (ou salle de contrôle) doit être dimensionné selon[12]:
- Nombre de caméras à superviser
- Nombre d'opérateurs disponibles
- Volume d'alarmes à traiter
- Temps de réaction requis
  
  Les exigences comprendront : chaîne de commandement clairement définie, **équipement de sécurité du poste** (accès restreint, traçabilité des opérations), **alimentation de secours** si la levée de doute sur alarme est critique[12].
- ### 3.5 Exigences de Sécurité
- #### 3.5.1 Intégrité du Système
  
  Le système vidéo doit être conçu pour **garantir l'intégrité** des données et des images enregistrées[12]:
- **Horodatage précis** : chaque image enregistrée doit porter un horodatage fiable (date et heure précises)
- **Localisation des images** : identification du numéro de caméra / lieu de chaque enregistrement
- **Traçabilité des accès** : enregistrement formalisé de qui a accédé aux images, quand et pourquoi
- **Protection contre la manipulation** : impossibilité de modifier les images sans le détecter
  
  Pour les systèmes de niveau renforcé, l'ajout de **signatures numériques** ou de **scellage** des enregistrements peut être requis[12].
- #### 3.5.2 Alimentation
  
  L'alimentation du système revêt une **importance capitale** car une interruption pourrait compromettre la surveillance[12][20]:
  
  **Alimentation Principale** :
- Fournie par le réseau électrique 230V standard
- Doit être assurée en permanence selon l'analyse des besoins[12]
  
  **Alimentation Secondaire** :
- **Batterie d'accumulateurs** (UPS - Uninterruptible Power Supply) : fournit l'énergie en cas de coupure réseau
- Capacité minimale : **15 minutes de secours** pour tous les systèmes[20]
- Pour les systèmes renforcés : capacité supérieure (30 minutes à 1 heure minimum)
- **Onduleur** : stabilise la tension et fournit l'énergie de secours de manière continue
  
  **Calcul de la Capacité de Secours** :
  $$ \text{Capacité (Ah)} = \frac{\text{Consommation totale (A)} \times \text{Durée requise (h)}}{\text{Tension nominale (V)}} $$
  
  Les caméras déportées doivent recevoir l'alimentation via **Power over Ethernet (PoE)**, permettant une **redondance** et une meilleure gestion de l'autonomie[12][20].
- #### 3.5.3 Sécurité des Postes
  
  Les **postes d'exploitation** doivent respecter des exigences de sécurité strictes[12]:
- **Accès restreint** : authentification par mot de passe fort (minimum 12 caractères, mixte alphanumériques et spéciaux)
- **Isolation de réseau** : les postes de visualisation ne doivent pas accéder à Internet public sans filtrage/proxy
- **Antivirus** : installation et mise à jour régulière de solutions antimalware
- **Logs d'audit** : enregistrement de toutes les connexions et opérations critiques
- **Politique de gestion des accès** : suppression immédiate des droits des employés partants, limitation du nombre d'administrateurs[12]
- #### 3.5.4 Sécurité Numérique et Cybersécurité
  
  L'édition 2021 du référentiel R82 intègre explicitement les exigences de **cybersécurité** conformément au référentiel APSAD D32[3][13]:
  
  **Exigences minimales** :
  
  1. **Segmentation de réseau** : isoler le réseau vidéo du réseau informatique général via un pare-feu (firewall)
  2. **Authentification forte** : mise en place de **contrôles d'accès** (login/password, certificats numériques)
  3. **Chiffrement** : transmission chiffrée des données (TLS 1.2 minimum)
  4. **Mise à jour logicielle** : procédure formalisée d'application des correctifs de sécurité
  5. **Formation des utilisateurs** : sensibilisation du personnel aux menaces cyber (hameçonnage, social engineering)
  
  **Niveaux de sécurité informatique** (similaires aux grades de sécurité EN 62676-1-1) :
- **Niveau 1** : exigences minimales, sites à faible risque
- **Niveau 2** : renforcement modéré, sites sensibles
- **Niveau 3** : renforcement substantiel, sites critiques
- **Niveau 4** : conformité maximale, environnements de très haute sécurité (secteur financier, défense)[3][13]
- ### 3.6 Exigences Spécifiques à la Télésurveillance
  
  Lorsque le système est supervisé à **distance** par un centre de télésurveillance certificié APSAD R31, des exigences supplémentaires s'ajoutent[12]:
- **Liaison de données** de **qualité garantie** (débit minimum, temps de latence faible)
- **Redondance de liaison** : au minimum deux chemins de transmission indépendants
- **Protocoles de levée de doute** : procédures précises pour confirmation d'alarme avant intervention
- **Temps de réaction** : délais formalisés pour traitement des alarmes et déclenchement d'interventions
- **Signature numérique** des alertes pour garantir leur authenticité
- ### 3.7 Exigences Spécifiques aux Fonds et Valeurs
  
  Les environnements manipulant des **fonds et valeurs** (banques, bijouteries, casinos) sont soumis à des exigences renforcées[12]:
- **Surveillance des accès** : caméras obligatoires aux points d'accès (portes, escaliers, ascenseurs)
- **Surveillance des zones sensibles** : salle de comptage, coffres-forts, zones de transit
- **Redondance** : systèmes de secours omniprésents (alimentation, transmission, enregistrement)
- **Intégrité** : impossibilité de coupure d'alimentation ou de masquage sans détection
- **Authentification** : contrôle d'accès multimodal (badge + code PIN + biométrie) pour les zones sensibles[12]
  
  ***
- ## 4. Réalisation de l'Installation
- ### 4.1 Principes Généraux
  
  La phase de **réalisation** concrétise la conception par l'installation physique de tous les éléments[12]:
  
  1. **Respect scrupuleux du cahier des charges** conçu à partir de l'analyse des besoins
  2. **Conformité aux normes et référentiels** (APSAD R82, EN 62676)
  3. **Traçabilité documentaire** de chaque étape (plans de câblage, schémas de connexion, photographies)
  4. **Qualité d'exécution** : installation réalisée par des techniciens formés et expérimentés
  5. **Gestion de projet** : respect des délais, budgets, livrables contractuels[12]
- ### 4.2 Les Différentes Liaisons
- #### 4.2.1 Liaisons Filaires
  
  Les liaisons **filaires** constituent l'architecture traditionnelle et demeurent largement utilisées[12]:
  
  **Câbles Coaxiaux** :
- Constitution : conducteur central enrobé d'une tresse de blindage
- Impédance : 75 ohms (standard pour vidéosurveillance)
- Types : RG59 (standard), RG6 (amélioré, distances plus longues)
- Avantages : immunité électromagnétique, économies
- Inconvénients : dégradation de signal au-delà de 300-400 mètres, larges diamètres de câbles
  
  **Câbles Ethernet** :
- Catégorie 5e (10Mbps) ou supérieure (Cat6, Cat6A pour 10Gbps+)
- Standards : EIA/TIA 568A ou 568B
- Avantages : distances pratiquement illimitées (avec répéteurs), flexibilité, support multimédia
- Inconvénients : sensibilité aux interférences si mal blindés, coût initial plus élevé[12]
- #### 4.2.2 Liaisons Radio
  
  Les liaisons **radio** s'avèrent utiles lorsque le câblage s'avère impractique (sites historiques, zones d'accès difficile)[12]:
- **Liaisons Wifi** : 2.4 GHz ou 5 GHz, porté 100-300 mètres en espace ouvert
- **Liaisons haut débit** : technologies propriétaires longue portée (1-3 km)
- **Inconvénients** : interférences possibles, latence, sécurité renforcée requise[12]
- #### 4.2.3 Liaisons Infrarouges
  
  Les liaisons **infrarouges** (optiques) offrent[12]:
- **Avantages** : très haut débit, immunité électromagnétique totale, sécurité
- **Inconvénients** : sensibilité aux brouillards et conditions météorologiques, nécessité de ligne directe, coût élevé
- #### 4.2.4 Combinaison des Liaisons
  
  La plupart des installations modernes utilisent une **combinaison multi-liaisons**[12] :
- Câblage Ethernet filaire du cœur du réseau (liaisons principales)
- Liaisons Wifi pour éléments mobiles ou déportés
- Liaisons radio pour couverture étendue
- Liaisons optiques pour liaisons critiques ultra-longue portée
- ### 4.3 Caractéristiques de la Télécommande et de la Télémétrie
  
  Lorsque le système intègre des caméras **motorisées** (PTZ - Pan/Tilt/Zoom), les protocoles de commande s'avèrent essentiels[12]:
- **Protocoles standards** : RS485 (transmission série), TCP/IP (réseau)
- **Retours de télémétrie** : position actuelle de la caméra, zoom, focus
- **Vitesse de réaction** : latence acceptable de commande à exécution
- **Cybersécurité** : authentification de l'opérateur avant chaque mouvement pour éviter les abus[12]
- ### 4.4 Masquage
  
  Le **masquage** (ou occultation) de certaines zones du champ vidéo peut être requis pour[12]:
- Respecter la **vie privée** : masquage des fenêtres d'immeubles d'habitation adjacents, des toilettes
- Respecter la **déontologie** : masquage des zones non concernées par la surveillance
- Respecter les **exigences légales** (CNIL) : limitation du champ aux seules zones autorisées
  
  Le masquage doit être effectué au niveau du **matériel** (obturateur optique, pare-soleil) ou du **logiciel** (pixelisation numérique), avec documentation claire[12].
- ### 4.5 Protection Contre les Chocs et les Influences Externes
  
  Les caméras et équipements doivent être **protégés** contre[12]:
- **Chocs mécaniques** : utilisation de dômes de protection, housses amovibles
- **Intempéries** : boîtiers IP67 minimum pour extérieur
- **Vandalisme** : caméras en dôme semi-encastré rendant l'accès difficile
- **Rayonnements** : protection EMI/RFI (interférences électromagnétiques)
- **Tempékilométre** : plages de températures de fonctionnement respectées
- ### 4.6 Distribution des Images
  
  Les images doivent être **distribuées** aux postes de visualisation selon les architectures[12]:
- **Architecture en étoile** : toutes les caméras convergent vers un NVR (Network Video Recorder) centralisé
- **Architecture distribuée** : enregistreurs locaux par zone géographique, synchronisés
- **Architecture cloud hybride** : enregistrement local + sauvegarde cloud pour redondance
- ### 4.7 Compression
  
  La **compression vidéo** s'avère nécessaire pour limiter l'utilisation de bande passante et d'espace de stockage[12]:
  
  **Codecs sans perte** :
- Lossless (LOCO) : aucune perte de qualité, fichiers volumineux
  
  **Codecs avec perte** :
- **MPEG-2/4** : compression intermédiaire
- **H.264/AVC** : réduction 50% vs MPEG-4, standard industrie
- **H.265/HEVC** : réduction 50% vs H.264, plus récent et exigent en calcul
- **VP9** : concurrence à H.265
  
  La **sélection du codec** doit tenir compte du **compromis qualité-stockage** : taux de compression de 50:1 est usuel, jusqu'à 100:1 pour stockage à long terme[12].
  
  ***
- ## 5. Contrôle et Mise en Service
- ### 5.1 Vérification Générale
  
  Avant toute mise en service opérationnelle, une **vérification générale** doit valider[12]:
- Présence de tous les équipements prévus
- Absence de dégâts visibles lors du transport/installation
- Câblage correct et connectique sécurisée
- Respect du cahier des charges au niveau des équipements
- ### 5.2 Vérifications Fonctionnelles
- #### 5.2.1 Contrôle de la Prise de Vue
  
  Chaque caméra doit être testée individuellement pour[12]:
- **Qualité d'image** : utilisation de la **cible normalisée NF EN 50132-7** (ANNEXE 2 du référentiel R82)
- **Champ visuel** : vérification que la zone couverte correspond au cahier des charges
- **Éclairement** : test en conditions de luminosité variées (jour, nuit, crépuscule)
- **Mise au point** : netteté satisfaisante aux distances prévues
- **Absence de défauts** : pixels morts, traces de poussière[12][21]
- #### 5.2.2 Contrôle de la Transmission
  
  La **transmission des données** est vérifiée pour[12]:
- Absence de perte de trame vidéo
- Débit de données conforme aux spécifications
- Délai de transmission (latence) acceptable
- Stabilité sur durée prolongée (test sur 8 heures minimum)
- #### 5.2.3 Contrôle de la Restitution
  
  Les images doivent être **correctement restitues** sur les moniteurs de visualisation[12]:
- Fidélité des couleurs
- Absence de distorsion
- Synchronisation temporelle des écrans multiples
- Facilité d'accès aux fonctions (pause, avance rapide, recherche par date/heure)
- #### 5.2.4 Contrôle des Exigences de Sécurité
  
  Les **fonctionnalités de sécurité** doivent être testées[12]:
- Horodatage correct et synchronisé (vérifier avec une source GPS ou serveur NTP)
- Traçabilité des accès aux enregistrements
- Impossibilité de modification des images (ou détection si modification tentée)
- Intégrité des données stockées (sommes de contrôle, checksums)
- #### 5.2.5 Contrôle des Alimentations
  
  **Alimentation principale** :
- Tension correcte (230V ± 10%)
- Absence de parasites
  
  **Alimentation de secours** :
- Test de basculement automatique en cas de coupure réseau
- Durée de secours conforme (minimum 15 minutes)
- Chute de tension maximale acceptable[12][20]
- #### 5.2.6-5.2.9 Contrôles Supplémentaires
  
  Selon le système[12]:
- Fonctionnement des **dispositifs d'alarme locaux** (sirène, clignotant)
- Transmission correcte au **poste d'alarme à distance** (télésurveillance)
- Liaisons **radio** (si présentes) : portée suffisante
- **Autres éléments** complémentaires : détecteurs, capteurs intégrés[12]
- ### 5.3 Résultats des Contrôles
  
  Tous les résultats doivent être **documentés** dans un **procès-verbal de mise en service** comprenant[12]:
- Date et heure des tests
- Identité du technicien ayant effectué les contrôles
- Liste des tests réalisés et résultats (conforme / non-conforme / remarque)
- Photographies des installations critiques
- Signature du responsable d'installation et du client
- ### 5.4 Mise en Service
  
  Une fois tous les tests validés, le système est **mis en service opérationnel**[12]. Le client doit recevoir:
- **Formation utilisateur** : exploitation des fonctionnalités de visualisation, recherche d'enregistrements, extraction de fichiers
- **Documentation technique** : manuels des équipements, schémas de câblage, adresses IP, mots de passe initiaux
- **Contrat de maintenance** : définition précise des obligations de maintenance préventive et corrective
- **Dossier technique complet** : tous les documents du projet, utilisé ultérieurement en cas de modification ou de sinistre[12]
  
  ***
- ## 6. Formation et Assistance aux Utilisateurs
  
  Le **référentiel R82 exige explicitement** une formation appropriée des utilisateurs du système[21][12]:
- ### Contenus de Formation Typiques
  
  1. **Exploitation du système vidéo**
	- Navigation dans l'interface utilisateur
	- Visualisation en direct
	- Recherche et replay d'enregistrements
	- Export d'images/vidéos
	  
	  2. **Recherche et analyse**
	- Recherche par date/heure
	- Recherche par zone de caméra
	- Analyse des événements/alarmes
	  
	  3. **Maintenance utilisateur**
	- Signalement des défaillances
	- Procédure de redémarrage du système
	- Nettoyage des dômes de caméra
	  
	  4. **Aspects légaux et déontologiques**
	- Respect de la vie privée
	- Droits des personnes filmées
	- Limitations légales d'utilisation des enregistrements
	- Procédures de demande d'accès aux images
	  
	  5. **Sécurité informatique** (nouvelle exigence depuis 2021)
	- Création/gestion des mots de passe
	- Identification des menaces cyber
	- Comportements suspects (hameçonnage, social engineering)[21][13]
	  
	  ***
- ## 7. Réception de l'Installation
- ### 7.1 Vérification de Conformité
  
  Le client et l'installateur procèdent à une **vérification formelle de conformité** du système par rapport au cahier des charges initial[12]:
- Tous les éléments convenus sont présents et fonctionnels
- Les spécifications techniques sont respectées
- Le système répond aux rôles définis lors de l'analyse de besoins
- Tous les niveaux de sécurité requis sont implémentés
- ### 7.2 Établissement du Procès-Verbal de Réception
  
  Un **procès-verbal de réception** est établi, signé par[12]:
- Le responsable de l'installation (installateur)
- Le représentant du client
- Éventuellement, un tiers auditeur (assureur, organisme de certification)
  
  Ce document atteste que l'installation est **conforme** et peut être remise en service.
- ### 7.3 Constitution du Dossier Technique
  
  Le **dossier technique** remis au client comprend[12]:
- Rapports d'analyse des besoins et des risques
- Cahier des charges technique
- Plans de câblage et schémas de réseau
- Procès-verbaux de mise en service et tests
- Procès-verbal de réception
- Notices techniques des équipements
- Liste des identifiants/mots de passe de maintenance
- Procédures d'exploitation courante
- Contrat de maintenance signé
  
  Ce dossier constitue la **fondation** pour le suivi ultérieur du système[12].
  
  ***
- ## 8. Maintenance
  
  La **maintenance** revêt une importance capitale pour garantir la pérennité fonctionnelle et la conformité du système au fil du temps[12][11].
- ### 8.1 Maintenance Préventive (Entretien Périodique)
  
  La maintenance préventive consiste en des **interventions programmées** visant à prévenir les défaillances[12]:
- #### 8.1.1 Fréquence des Visites de Maintenance Préventive
  
  Le référentiel APSAD R82 prescrit des **fréquences minimales** selon le niveau de criticité[12]:
- **Niveau standard** : intervention minimum **1 fois par an**
- **Niveau renforcé** : intervention minimum **2 fois par an** (soit semestrielle)
- Pour les systèmes critiques (fonds et valeurs, télésurveillance) : possibilité d'exigences plus fréquentes (mensuelles ou trimestrielles)
- #### 8.1.2 Nature des Opérations d'Entretien Périodique
  
  Les opérations de maintenance préventive incluent[12]:
  
  1. **Nettoyage mécanique**
	- Nettoyage des dômes de caméra (élimination poussière, pluie, pollution)
	- Inspection mécanique de la fixation des caméras
	- Vérification de l'absence de masquage ou de dégradation
	  
	  2. **Vérification fonctionnelle**
	- Test de chaque caméra individuellement
	- Visualisation des images pour détection de dégradation progressive
	- Test des mouvements PTZ (pan/tilt/zoom)
	- Vérification de l'horodatage et synchronisation temporelle
	  
	  3. **Vérification des systèmes de secours**
	- Test d'alimentation de secours (UPS/batterie)
	- Mesure de la capacité des batteries (état de charge)
	- Test du basculement automatique en cas de coupure
	- Vérification de la durée autonomie réelle vs spécifiée
	  
	  4. **Vérification d'enregistrement**
	- Test de l'enregistrement en continu
	- Vérification de la qualité d'images enregistrées vs spécifications
	- Mesure de l'espace disque utilisé et du taux de remplissage
	- Calcul de la durée réelle de conservation possible
	  
	  5. **Contrôle des systèmes de transmission**
	- Mesure de la **bande passante** utilisée vs disponible
	- Vérification des délais de transmission (latence)
	- Test des liaisons de secours (si présentes)
	  
	  6. **Mise à jour logicielle**
	- Vérification et application des correctifs de sécurité
	- Mise à jour des micrologiciels de caméras et serveurs
	- Test de stabilité post-mise à jour[12]
	  
	  7. **Audit de sécurité** (nouveau dans édition 2021)
	- Vérification des droits d'accès (utilisateurs actifs, suppression des comptes inutilisés)
	- Test des authentifications
	- Vérification de la traçabilité des opérations
	- Recherche de tentatives de connexions non autorisées[12][13]
- ### 8.2 Maintenance Corrective (Dépannage)
  
  La **maintenance corrective** intervient en réaction à une **défaillance signalée**[12]:
- **Défaillance de caméra** : intervention dans un délai garanti (par exemple, 24h pour niveau standard, 4h pour niveau renforcé)
- **Défaillance d'enregistreur** : remplacement rapide du disque dur ou du serveur si nécessaire
- **Défaillance d'alimentation** : remplacement de batterie, remise en service de l'UPS
- **Perte de transmission** : diagnostic de réseau, test des liaisons, remplacement de câbles ou d'équipements réseau
- **Défaillance logicielle** : redémarrage de services, réinstallation si nécessaire
  
  **Temps de réaction typique** :
- Niveau standard : 48 à 72 heures (dépannage sur site)
- Niveau renforcé : 24 heures garanti, 4 heures en cas de défaillance critère
- Sites sensibles (fonds/valeurs) : intervention immédiate (2-4 heures maximum)[12]
- ### 8.3 Suivi des Visites de Maintenance
  
  Chaque visite de maintenance doit être **documentée** dans un **compte rendu de vérification périodique Q82**[1][2][12]:
- Date, heure de début/fin de l'intervention
- Identité du technicien
- Résumé des opérations réalisées
- Résultats des tests (conforme/non-conforme/remarque)
- Pièces remplacées, numéros de série
- Durée réelle d'autonomie de batterie mesurée vs spécifiée
- Espace disque disponible et durée réelle de conservation calculée
- Signature du technicien et du responsable client
- Consignes pour l'utilisateur (dégagements à effectuer, redémarrages à prévoir)
  
  Ce document **Q82** s'accumule dans le **dossier de maintenance** et permet[1][2]:
- Un **suivi historique** de la vie du système
- Une **détection de dégradation progressive** (batterie perdant capacité, disques surchargés)
- Une **justification des modifications** (changement d'équipement, mise à jour)
- Une **preuve de conformité** continue, essentielle en cas de sinistre ou de litige[2][12]
- ### 8.4 Modifications Apportées à une Installation
  
  Tout changement significatif au système doit être **documenta formellement**[12]:
- Remplacement de caméra par modèle différent : justification technique, test de conformité
- Extension de couverture (ajout de caméra) : mise à jour du cahier des charges, analyse de besoins actualisée
- Changement de codec ou de résolution : impact sur stockage et bande passante
- Modification du schéma de sécurité : ajustement des droits d'accès, mise à jour des procédures
  
  Chaque modification doit être **approuvée par le client** et **documentée** avant implémentation[12].
- ### 8.5 Télémaintenance et/ou Téléparamétrage
  
  Les systèmes modernes permettent une **télémaintenance** à distance[12]:
- **Diagnostic à distance** : le prestataire se connecte au système pour diagnostiquer les pannes sans se déplacer
- **Mise à jour de configuration** : paramètres modifiés sans intervention sur site
- **Collecte de logs** : extraction des fichiers de diagnostic à distance
  
  Cette approche offre des avantages (coût réduit, intervention plus rapide) mais pose des **exigences de cybersécurité renforcées**[12]:
- Authentification multi-facteurs (login + code à usage unique)
- Session VPN chiffrée
- Journal détaillé de toute opération effectuée
- Accord préalable du client pour chaque intervention[12]
  
  ***
- ## 9. Déclaration de Conformité - Document N82
- ### 9.1 Objectif et Statut Légal
  
  La **Déclaration de Conformité N82** (ou **N82** tout court) est le **document attestant** que l'installation de vidéosurveillance a été réalisée **conformément au référentiel APSAD R82**[1][2][12].
  
  Ce document revêt une importance juridique considérable car[1][2]:
- Il engage la **responsabilité** de l'installateur certificié (NF Service & APSAD) qui l'émet
- Il est utilisé par les **assureurs** pour évaluer le respect des conditions d'assurance
- Il constitue une **preuve de conformité réglementaire** en cas de sinistre ou de litige
- Il peut être exigé par un **auditeur externe** (inspecteur public, expert judiciaire) pour valider le respect de normes
- ### 9.2 Contenu Typique du Document N82
  
  Le document N82 comprend généralement[1][2][12]:
  
  1. **Identification de l'installation**
	- Adresse du site
	- Date de mise en service
	- Responsable de l'installation
	  
	  2. **Identification de l'installateur**
	- Entreprise certifiée NF Service & APSAD
	- Numéro de certification APSAD
	- Responsable technique signataire
	  
	  3. **Synthèse de l'analyse des besoins et des risques**
	- Rôles du système
	- Niveau de sécurité (standard ou renforcé)
	- Critères d'intégrité
	  
	  4. **Description du système**
	- Nombre et type de caméras
	- Mode d'enregistrement (continu, sur événement)
	- Durée de conservation des images
	- Système de backup/redondance
	  
	  5. **Conformité aux exigences**
	- Respect des spécifications techniques pour chaque caméra
	- Respect des exigences de transmission, restitution, sécurité
	- Respect des exigences d'alimentation, de cybersécurité
	  
	  6. **Signature et engagement**
	- Signature du responsable technique de l'installateur
	- Engagement de conformité au référentiel R82
	- Durée de validité (généralement 12 mois)
- ### 9.3 Processus d'Émission et de Validation
  
  Le document N82 ne peut être émis que par une **entreprise certificée**[1][2]:
- L'entreprise doit détenir la **certification conjointe NF Service & APSAD Vidéosurveillance – Service d'installation et de maintenance**
- Elle doit respecter les procédures d'audit régulier par le CNPP
- Elle doit maintenir ses compétences techniques par formations continuées
  
  Le document N82 doit être **fondé sur une analyse réelle** du site réalisée avant installation. Un document générique ou formellement rempli sans vérification sur site constituerait une **faux** engageant la responsabilité pénale de l'installateur[1][2][12].
  
  ***
- ## 10. Compte Rendu de Vérification Périodique - Document Q82
- ### 10.1 Objectif et Statut Légal
  
  Le **document Q82** est le **compte rendu détaillé** remis au client à l'issue de chaque visite de maintenance préventive[1][2][12]. Il atteste que la maintenance a été réalisée conformément aux exigences du référentiel R82 et documente l'état du système à la date de visite.
  
  Ce document revêt une importance capitale car[1][2]:
- Il fournit au **client** une preuve que la maintenance contractuelle a été exécutée
- Il constitue une **trace documentaire** de l'évolution du système (dégradations détectées, pièces remplacées)
- Il est utilisé par les **assureurs** pour valider la conformité continue de l'installation
- Il peut être exigé par un **expert** en cas de sinistre pour justifier que le système était fonctionnel à la date critique
- Il démontre la **continuité de certification** de l'installation (pas d'interruption de maintenance)
- ### 10.2 Contenu Typique du Document Q82
  
  Chaque document Q82 comprend[1][2][12]:
  
  1. **Identification générale**
	- Numéro de la visite de maintenance (ex : Q82-2025-01)
	- Date et heure de la visite
	- Identification du technicien (nom, qualification)
	  
	  2. **Identification de l'installation**
	- Adresse du site
	- Numéro d'identification unique du système
	- Référence du contrat de maintenance
	  
	  3. **Résumé des opérations réalisées**
	- Nettoyage des caméras (oui/non, date du dernier nettoyage)
	- Test de visualisation des images (chaque caméra testée)
	- Test d'enregistrement
	- Test d'alimentation de secours
	- Test des liaisons de transmission
	- Mises à jour logicielles appliquées
	  
	  4. **Résultats des tests détaillés**
	- Pour chaque caméra : état conforme/non-conforme (avec remarques)
	- Qualité d'images estimée (bonne/acceptable/dégradée)
	- Horodatage vérifié (oui/non, écart éventuel)
	- Enregistrement vérifié (oui/non, nombre d'images/seconde conforme)
	  
	  5. **Tests d'alimentation de secours**
	- Type de batterie/UPS
	- Tension mesurée : [valeur] V (conforme si 230V ± 10%)
	- Durée réelle de secours mesurée : [durée] (conforme si ≥ 15 minutes)
	- Calcul de l'autonomie réelle du stockage : [durée de conservation possible]
	  
	  6. **Anomalies détectées**
	- Liste des éléments non-conformes (caméra défaillante, disque presque plein, mises à jour en retard)
	- Sévérité estimée (critique/majeure/mineure)
	- Recommandations d'actions correctives
	  
	  7. **Pièces remplacées**
	- Type de pièce, numéro de série ancien/nouveau
	- Date de remplacement
	- Justification (défaillance, prévention, obsolescence)
	  
	  8. **Observations générales et conseils**
	- État général du système
	- Prévisions de maintenance future (ex : batterie à remplacer dans 6 mois)
	- Recommandations pour l'utilisateur
	  
	  9. **Signature et engagement**
	- Signature du technicien
	- Signature du représentant client (preuve de réception)
	- Timbre/cachet de l'entreprise de maintenance
- ### 10.3 Périodicité de Remise des Documents Q82
- **Niveau standard** : remise minimum **1 fois par an**
- **Niveau renforcé** : remise minimum **2 fois par an**
- Les documents Q82 s'accumulent dans le **dossier de maintenance** du client
- En cas de défaillance ou de sinistre, les **Q82 antérieurs** constituent une documentation historique essentielle[1][2][12]
  
  ***
- ## 11. Intégration des Exigences de Cybersécurité (APSAD D32)
- ### 11.1 Évolution vers la Sécurité Informatique
  
  L'édition février 2021 du référentiel APSAD R82 a intégré explicitement les **exigences de cybersécurité** conformément au référentiel APSAD D32[3][13]:
  
  Ceci reconnaît que les **systèmes de vidéosurveillance sont désormais connectés en réseau** et exposés aux menaces cyber :
- **Intrusions de réseau** : tentatives de prise de contrôle du système par accès non autorisé
- **Rançongiciels (ransomware)** : cryptage des enregistrements avec demande de rançon
- **Manipulation d'images** : modification des enregistrements par un attaquant
- **Attaques par déni de service (DDoS)** : surcharge du réseau videosurveillance pour l'indisponibiliser
- **Vol de données** : extraction des images stockées par un cybercriminel[3][13]
- ### 11.2 Niveaux de Sécurité Informatique
  
  Le référentiel APSAD D32 définit **quatre niveaux de sécurité informatique** (similaires aux grades de sécurité EN 62676-1-1)[3][13]:
  
  | Niveau | Descriptif | Sites Typiques |
  |--------|-----------|-----------------|
  | 1 | Exigences minimales, environnement à très faible risque cyber | Petits commerces, entrepôts ruraux, parkings privés |
  | 2 | Renforcement modéré, environnement à risque cyber moyen | Bureaux, petites usines, installations dans zone urbaine |
  | 3 | Renforcement substantiel, environnement sensible | Banques, sites gouvernementaux, hôpitaux, data centers |
  | 4 | Conformité maximale, environnement de très haute sécurité | Ministères, défense, organismes critiques |
- ### 11.3 Exigences Techniques par Niveau
- #### Niveau 1 (Minimal)
- Authentification simple (login/password)
- Isolation du réseau vidéo du réseau public par pare-feu basique
- Mise à jour logicielle au moins annuelle
- #### Niveau 2 (Modéré)
- Authentification avec mots de passe forts (12 caractères minimum, alphanumériques + spéciaux)
- Segmentation de réseau (VLAN, firewall applicatif)
- Chiffrement TLS 1.2 minimum pour transmissions distantes
- Mise à jour logicielle semestrielle
- Formation utilisateur à la cybersécurité
- #### Niveau 3 (Substantiel)
- Authentification multi-facteurs (login + code à usage unique)
- Certificats numériques pour caméras/serveurs
- VPN ou autre tunnel chiffré pour accès distant
- Segmentation réseau stricte (zones démilitarisées, proxies)
- Journalisation exhaustive de tous les accès
- Mise à jour logicielle trimestrielle ou après découverte de faille
- Tests réguliers de résilience (simulation de pannes)
- Conformité à ISO 27001 recommandée[3][13]
- #### Niveau 4 (Maximal)
- Authentification ultra-forte (certificats physiques, biométrie)
- Redondance complète de tous les composants critiques
- Chiffrement Haute Sécurité (AES-256)
- Cloisonnement physique des réseaux (pas de wifi)
- Audit de sécurité régulier par tiers indépendant
- Récupération après sinistre garantie en moins d'une heure
- Conformité ISO 27001 obligatoire[3][13]
- ### 11.4 Matériels Certifiés « CNPP Certified »
  
  Pour les installations de niveau 2 et supérieures, l'utilisation de **matériels certifiés « CNPP Certified »** est fortement recommandée ou obligatoire[3][18][22]:
  
  Ces certifications attestent que :
- Les caméras/serveurs ont subi des **tests de robustesse** contre les attaques connues
- Ils respectent les **exigences minimales** de performance DORI (Détection, Observation, Reconnaissance, Identification)
- Ils disposent de **mécanismes de sécurité** validés par un tiers indépendant (CNPP)
- Ils offrent des **mises à jour régulières** de sécurité
  
  ***
- ## 12. Conformité Réglementaire et Bonnes Pratiques
- ### 12.1 Conformité aux Lois Françaises
  
  Au-delà du référentiel APSAD R82, un système de vidéosurveillance doit respecter**plusieurs lois françaises**[4][5]:
- #### Code de la Sécurité Intérieure (L.251-1 et suivants)
  
  Applicable à la **vidéoprotection** (systèmes sur espace public ou lieux ouverts au public) :
- **Autorisation préfectorale** requise (procédure simplifiée depuis 2010)
- **Finalités limitées** : lutte contre la malveillance, terrorisme, accidents de la circulation
- **Durée de conservation maximale** : 1 mois (sauf procédure judiciaire)
- **Signalisation visible** obligatoire
- **Suppression automatique** après durée autorisée
- **Contrôle préfectoral** et **contrôle CNIL**[5][9]
- #### Loi Informatique et Libertés (n° 78-17 du 6 janvier 1978)
  
  Avant la loi du 23 mai 2023, la vidéosurveillance privée échappait techniquement à la CNIL. Depuis cette loi, toute caméra enregistrant des images filmant au-delà du strict cadre privé (visiteurs, salariés, zones partagées) est considérée comme un traitement de données personnelles[4][5].
- #### Règlement général sur la Protection des Données (RGPD - 2018/679)
  
  Depuis mai 2018, le RGPD s'applique à tous les traitements de données à caractère personnel au sein de l'UE, incluant la vidéosurveillance[4][5]:
- **Licéité du traitement** : base légale requise (intérêt légitime, exécution de contrat, obligation légale)
- **Loyauté et transparence** : information des personnes filmées
- **Minimisation des données** : les données collectées doivent être nécessaires et proportionnées aux finalités
- **Limitation de conservation** : durée de rétention justifiée et limitée
- **Intégrité et confidentialité** : mesures techniques et organisationnelles pour protéger les données
- **Responsabilité** : documentation et gouvernance du traitement[4][5]
- ### 12.2 Déclaration à la CNIL
  
  Pour les installations en environnement **professionnel ou public** couvrant plus d'une petite zone, une **déclaration à la CNIL** est généralement requise ou fortement recommandée[4][5]:
  
  Le responsable de traitement doit :
- Informer la CNIL du traitement
- Fournir les coordonnées du Délégué à la Protection des Données (DPO) si applicable
- Décrire les mesures de sécurité mises en place
- Justifier la base légale du traitement
  
  La CNIL peut alors demander des informations supplémentaires ou imposer des modifications au système[4][5].
- ### 12.3 Durée de Conservation Recommandée
  
  Bien que la loi permette jusqu'à 1 mois, une pratique prudente recommande[8][9][10]:
- **Conservation minimum : 7 à 10 jours** (permettre découverte d'incident, procédures disciplinaires initiales)
- **Zones sensibles** : 15 à 30 jours (enquête plus approfondie)
- **Sites critiques** (banques, justices) : 30 jours complet
- Au-delà d'1 mois : seulement en cas de procédure judiciaire active (avec trace documentée)
  
  La **durée choisie** doit être mentionnée dans l'**autorisation préfectorale** pour systèmes publics, ou dans la **politique de confidentialité** pour systèmes privés[8][9].
- ### 12.4 Signalisation Obligatoire
  
  Pour tout système captant des personnes au-delà du cadre strictement privé, une **signalisation visible** est obligatoire[4][5]:
  
  **Contenu minimum du panneau** :
- Pictogramme de caméra clairement visible
- Texte : "Site sous vidéosurveillance"
- Nom/coordonnées du responsable du traitement
- Mention des droits : "Accès, rectification, suppression de vos données possible auprès de [contact]"
- Durée de conservation des images
  
  Les panneaux doivent être placés à l'**entrée principale** du site et aux **principaux points d'accès**[4][5].
  
  ***
- ## Conclusion
  
  Le référentiel **APSAD R82** fournit un cadre complet et reconnu mondialement pour la conception, la mise en œuvre, la réception et la maintenance des systèmes de vidéosurveillance. Son approche méthodique en quatre phases (analyse des besoins et des risques → conception → réalisation → maintenance) garantit que chaque installation répond précisément aux besoins spécifiques du site tout en respectant les exigences techniques minimales, les normes de sécurité et les dispositions légales en matière de protection des données.
  
  L'intégration des exigences de cybersécurité dans l'édition 2021 du référentiel reconnaît la réalité moderne : les systèmes de vidéosurveillance sont des **systèmes informatiques critiques** exposés aux menaces cyber. L'application rigoureuse des exigences du référentiel D32 garantit la **résilience** et la **confidentialité** des enregistrements vidéo.
  
  Pour les installateurs et prescripteurs, l'application du référentiel R82 offre une **protection juridique** considérable : la démonstration de conformité aux exigences du référentiel constitue une preuve tangible du respect des normes professionnelles. Pour les clients, l'exigence d'une **certification APSAD** lors de la sélection d'un installateur garantit l'intervention d'une entreprise soumise à des **audits réguliers** et à des **critères de qualité stricts**.
  
  La **documentation formalisée** tout au long du projet (déclarations N82, comptes rendus Q82) crée une **traçabilité complète** de la vie du système, essentielle en cas de sinistre, litige ou investigation. Cette approche documentaire transforme la vidéosurveillance d'une simple installation technique en un **véritable système de gestion** professionnel et responsable.
  
  ***
  
  **Sources Citées :**
  
  [1] Securitas, 2025. Qu'est-ce que le référentiel APSAD R82.
  [2] CNPP, 2021. Mise en œuvre du référentiel APSAD R82 - Vue PDF.
  [3] CNPP, 2021. Référentiel APSAD R82 Vidéosurveillance - Édition 2021.
  [21] CNPP, 2021. Référentiel APSAD R82 Vidéosurveillance - ANNEXE 2 Méthode d'essai.
  [12] IHF, 2016. Règle APSAD R82 (Février 2016) Vidéosurveillance.
  [11] Faceaurisque, 2021. Référentiel APSAD R82 – Vidéosurveillance – Règle d'installation.
  [18] Groupe PERIN Sécurité, 2025. Nos certifications.
  [13] Faceaurisque, 2021. Référentiel APSAD R82 – Évolutions liées à la cybersécurité.
  [19] CNPP, 2021. Référentiel APSAD D32 Cybersécurité - Additif Novembre 2021.
  [20] Anitec, 2016. Nécessité de sécuriser l'alimentation des installations VIDEO par onduleurs.
  [22] CNPP, 2025. Caméras vidéosurveillance – Certification CNPP Certified.
  [4] DS Avocats, 2021. La vidéosurveillance et l'intérêt légitime du responsable de traitement.
  [5] UCLY, 2024. Comment s'assurer de la conformité au RGPD des installations de vidéoprotection.
  [6] Filière 3E, 2017. Sûreté Malveillance.
  [7] Legifrance, 2007. Arrêté du 3 août 2007 portant définition des normes techniques.
  [15] YouTube, 2020. Partie 2 : Les zones de visualisation caméra, EN62676-4.
  [8] CNIL, 2023. Vidéoprotection : combien de temps peuvent être conservées les images.
  [16] TP-Link France, 2023. Qu'est-ce que DORI ?
  [9] CNPP, 2024. Vidéosurveillance : quelles sont les réglementations.
  [17] JVSG, 2024. Comment surveiller des couloirs par vidéosurveillance.
  
  Citations :
  [1] Qu'est-ce que le référentiel APSAD R82 - Securitas https://www.securitas.fr/actualites-et-ressources/blog-securite/qu-est-ce-que-le-referentiel-apsad-r82/
  [2] [PDF] Mise en œuvre du référentiel APSAD R82 - Vue PDF https://www.cnpp.com/print/pdf/commerce_product/707
  [3] Référentiel APSAD R82 Vidéosurveillance - Cybel - CNPP Éditions https://cybel.cnpp.com/livre-referentiel-apsad-r82-videosurveillance-2021
  [4] La vidéosurveillance et l'intérêt légitime du responsable de traitement https://www.dsavocats.com/videosurveillance-linteret-legitime-responsable-de-traitement/
  [5] Comment s'assurer de la conformité au RGPD des installations de ... https://www.ucly.fr/videoprotection-et-rgpd
  [6] [PDF] Certifications conjointes - NF Service & APSAD - Sécuris https://www.securis-extincteurs.fr/files/medias/documents/Certification_APSAD.pdf
  [7] Arrêté du 3 août 2007 portant définition des normes techniques des ... https://www.legifrance.gouv.fr/loda/id/JORFTEXT000000649127
  [8] combien de temps peuvent être conservées les images - CNIL https://www.cnil.fr/fr/cnil-direct/question/videoprotectionvideosurveillance-combien-de-temps-peuvent-etre-conservees-les
  [9] Vidéosurveillance : quelles sont les réglementations - CNPP https://www.cnpp.com/articles-reglementaires/videosurveillance-prive-publique-quelles-reglementations
  [10] [PDF] la vidéoprotection - ADM54 https://www.adm54.asso.fr/UserFiles/File/webinaires/2021/reunion-de-la-commission-rurales-sur-la-videoprotection/support.pdf
  [11] Qu'est-ce que le référentiel Apsad R82 ? - Sotel Banques https://banques.sotel.fr/le-mag/quest-ce-que-le-referentiel-apsad-r82/
  [12] [PDF] Règle APSAD R82 (Février 2016) Vidéosurveillance SOMMAIRE https://www.ihf.fr/wp-content/uploads/2016/03/290612-R%C3%A8gle-APSAD-R82-F%C3%A9vrier-2016.pdf
  [13] Référentiel APSAD R82 – Vidéosurveillance – Règle d'installation https://www.faceaurisque.com/base-reglementaire/referentiel-apsad-r82-videosurveillance-regle-dinstallation/
  [14] Concevoir et mettre en oeuvre un système de vidéosurveillance https://formations.batiactu.com/formation/formation-concevoir-et-mettre-en-oeuvre-un-systeme-de-videos-17344.php
  [15] Partie2: Les zones de visualisation caméra,EN62676-4. Conception ... https://www.youtube.com/watch?v=3LrS_rxjGgg
  [16] Qu'est-ce que DORI ? | TP-Link France https://www.tp-link.com/fr/support/faq/4098/
  [17] APSAD - Kiece https://www.kiece.fr/apsad/
  [18] Nos certifications - Groupe PERIN Sécurité https://www.perin.fr/qui-sommes-nous/nos-certifications
  [19] Référentiel APSAD D32 Cybersécurité - Cybel - CNPP Éditions https://cybel.cnpp.com/livre-referentiel-apsad-d32-cybersecurite-2021.html
  [20] [PDF] Demande d'autorisation : Vidéoprotection - Anitec https://www.anitec.fr/wp-content/uploads/2017/04/Necessite-de-securiser-lalimentation-des-installations-VIDEO.pdf
  [21] Référentiel APSAD R82 Vidéosurveillance; ANNEXE 2 Méthode d ... https://cybel.cnpp.com/lire-referentiel-apsad-r82-videosurveillance-2021/12-57
  [22] Caméras vidéosurveillance – Certification CNPP Certified https://www.cnpp.com/tester-certifier/cnpp-certified-surete/videosurveillance
  [23] ANNEXE 3a Tableau d'aide à l'analyse des besoins et des risques ... https://cybel.cnpp.com/lire-referentiel-apsad-r82-videosurveillance-2021/13-61
  [24] R82 - Vidéosurveillance - Février 2021 - France-Sélection https://franceselection.fr/surete/203-r82-videosurveillance-fevrier-2021-nouvelle-edition.html
  [25] Vidéosurveillance : le référentiel APSAD R82 évolue - Préventica https://www.preventica.com/magazine/actualites/videosurveillance-le-referentiel-apsad-r82-evolue-08032016
  [26] Que veut dire APSAD ? Définition de la certification APSAD - Anco https://www.anco.pro/blog/apsad/
  [27] Vidéosurveillance : règle d'installation https://documentation.chu-lyon.fr/opac?id=7f37dda0-26d1-4746-93bc-95d68fb436bf
  [28] Référentiel APSAD R82 Vidéosurveillance; - Cybel - CNPP Éditions https://cybel.cnpp.com/livre-referentiel-apsad-r82-videosurveillance-2021?vue=extrait
  [29] Formation : concevoir, installer de la vidéosurveillance - CNPP https://www.cnpp.com/formations/surete/concevoir-et-mettre-en-oeuvre-un-systeme-de-videosurveillance
  [30] Sécurisation des systèmes de contrôle d'accès physique et ... https://messervices.cyber.gouv.fr/guides/securisation-des-systemes-de-controle-dacces-physique-et-videoprotection
  [31] Référentiel APSAD R82 Vidéosurveillance - Édition février 2016 https://cybel.cnpp.com/lire-referentiel-apsad-r82-videosurveillance/9-53?vue=pdf
  [32] Tout savoir sur la certification APSAD de nos systèmes de sécurité https://www.jdc.fr/blog/tout-savoir-sur-la-certification-apsad-de-nos-systemes-de-securite
  [33] Vidéosurveillance - Règle d'installation - Référentiel APSAD R82... https://www.eyrolles.com/Loisirs/Livre/videosurveillance-9782355053436/
  [34] Vidéosurveillance : règle d'installation Catalogue en ligne - ENSOSP https://crd.ensosp.fr/index.php?lvl=notice_display&id=29723
  [35] Référentiel APSAD R82 Vidéosurveillance - Édition février 2016 https://cybel.cnpp.com/lire-referentiel-apsad-r82-videosurveillance/3-17?vue=pdf
  [36] [PDF] Référentiel de certification NF367 – I81 V9 juin 2018 - Anitec https://www.anitec.fr/wp-content/uploads/2017/04/NF367-I81V9juin2018Ptg-intrusion-002.pdf
  [37] [PDF] ADDITIF Novembre 2021 - RÉFÉRENTIEL APSAD D32 https://cybel.cnpp.com/static/uploadfolder/140-Additif%20D32_Novembre%202021.pdf
  [38] Qu'est-ce que le référentiel Apsad R82 ? - Sotel Groupe https://www.sotel.fr/le-mag/quest-ce-que-le-referentiel-apsad-r82/
  [39] Installation / maintenance système de vidéo surveillance APSAD R82 https://www.pic-matic.fr/video-surveillance/installation-maintenance-systeme-de-video-surveillance-apsad-r82
  [40] Renouvellement certification APSAD - Anaveo https://www.anaveo.fr/presse/renouvellement-certification-apsad/
  [41] Sûreté : mise à jour des référentiels APSAD R81 et R82 - CNPP https://www.cnpp.com/blog/systemes-de-protection-contre-la-malveillance-decouvrez-les-mises-jour-de-nos-referentiels-apsad-r81-et-r82
  [42] [PDF] 3.4.2 Configuration du poste d'exploitation 3.5.1 Intégrité du système https://cybel.cnpp.com/download.php?extrait=9782355052231
  [43] Référentiel APSAD R82 Vidéosurveillance; ANNEXE 1 Déclaration ... https://cybel.cnpp.com/lire-referentiel-apsad-r82-videosurveillance-2021/11-55
  [44] VIDEOPROTECTION - Référents Sûreté https://www.referentsurete.fr/videoprotection.html
  [45] [PDF] Sûreté Malveillance https://www.filiere-3e.fr/wp-content/uploads/2017/01/087_112_Technologies-s%C3%BBret%C3%A9-malveillance.pdf
  [46] Vidéo Protection La R82 | PDF | Télévision en circuit fermé - Scribd https://fr.scribd.com/document/580951479/Video-Protection-La-R82-1
  [47] Installer la vidéosurveillance dans son établissement https://www.lhotellerie-restauration.fr/actualite/installer-la-videosurveillance-dans-son-etablissement-62433
  [48] [PDF] MALVEILLANCE n°4 VIDÉOPROTECTION / VIDÉOSURVEILLANCE https://www.culture.gouv.fr/Media/Thematiques/Securite-Surete/Fichiers/surete-vol-malveillance/fiche-surete-n-4-videoprotection-videosurveillance-2024
  [49] [PDF] Référentiel de certification NF367 – I82 - Hypercable https://www.hypercable.fr/images/stories/Referentiel_NF367-I82_mai_2010-V1.pdf
  [50] CNIL, Délibération du 15 juin 2023, n° 2023-059 | Doctrine https://www.doctrine.fr/d/CNIL/2023/CNILTEXT000048490272
  [51] Demande d'autorisation pour l'installation et utilisation de la ... https://www.seine-maritime.gouv.fr/Demarches/Videoprotection/Demande-d-autorisation-pour-l-installation-et-utilisation-de-la-videoprotection
  [52] L'IEC présente une nouvelle norme pour la vidéosurveillance : IEC ... https://www.reddit.com/r/videosurveillance/comments/1o7cc9a/iec_introduces_new_standard_for_video/
  [53] Comment surveiller des couloirs par vidéosurveillance - JVSG https://www.jvsg.com/comment-surveiller-des-couloirs-par-videosurveillance/
  [54] Vidéoprotection et vidéosurveillance : quelles différences ? - Anaveo https://www.anaveo.fr/guide/videoprotection-videosurveillance-differences-entreprises/
  [55] Certification APSAD - Verisure https://www.verisure.fr/guide-securite/telesurveillance/certification-apsad
  [56] Comprendre les normes de la vidéosurveillance - Ubitech https://www.ubitech.fr/blog/74-comprendre-les-normes-de-la-videosurveillance
  [57] [PDF] Guide pratique et déontologique de la vidéoprotection à l ... - USH https://www.union-habitat.org/sites/default/files/articles/documents/2018-03/cahier%20141.pdf
  [58] L'édito de Dominique : aperçu de la nouvelle norme EN 62676-4 ... https://newsroom.axis.com/fr-ch/article/updated-iec-regulation
  [59] Protection > Nos solutions > Vidéoprotection - Guardian-Alarm https://www.guardian-alarm.fr/nos-solutions/videoprotection/
  [60] Vidéosurveillance - Foussier https://www.foussier.fr/videosurveillance/pg578
  [61] Demander une autorisation d'exploitation d'un système de ... https://www.haute-savoie.gouv.fr/Demarches/Activites-reglementees/Videoprotection/Demander-une-autorisation-d-exploitation-d-un-systeme-de-videoprotection
-
-