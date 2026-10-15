- Voici la trame type d’un **Rapport d’Audit et de Diagnostic de Sûreté**, structurée selon la méthodologie enseignée au CESS (alignée sur les normes **ISO 19011**, **ISO 31000** et les exigences **SGDSN / APSAD**).
- # [Titre du Projet] — Rapport d'Audit & de Diagnostic de Sûreté
  
  **Référence du document :** AUD-SUR-[AAAAMM]-[CodeSite]
  **Classification :** Restreint / Confidentiel Sûreté
  **Date d'émission :** [Date]
  **Rédacteur(s) :** [Nom de l'Auditeur, Titulaire du CESS]
- ## 1. Synthèse Exécutive (Executive Summary)
  
  > 
  
  *Dédiée à la Direction Générale / Direction des Risques pour une prise de décision rapide.*
- **Objet de la mission :** Évaluation globale du niveau de sûreté du site [Nom du Site] face aux risques de malveillance.
- **Posture générale :** Synthèse du niveau de maturité sécuritaire actuel (faible, intermédiaire, élevé).
- **Niveau de risque global :** Synthèse des principales vulnérabilités critiques identifiées.
- **Budget estimatif du Plan d'Actions :** Enveloppe budgétaire globale (CAPEX/OPEX) pour la mise aux normes et la résorption des écarts.
- **Matrice synthétique de criticité :**
  
  | Domaine évalué | Conformité Réglementaire | Niveau de Protection | Priorité d'Action |
  
  | **Gouvernance & Procédures** | Conformité partielle | Moyen | P2 |
  
  | **Périmétrie (1ère ligne)** | Non-conforme | Faible | **P1 (Urgent)** |
  
  | **Périphonie & Volumétrie** | Conforme | Fort | P3 |
  
  | **Contrôle d'Accès & Obstacles** | Conformité partielle | Moyen | P2 |
  
  | **Convergence Cyber / OT** | Non-conforme | Faible | **P1 (Urgent)** |
- ## 2. Cadre Général & Périmètre de la Mission
- ### 2.1. Objet et Objectifs de l'Audit
- Évaluer la résistance du site face aux actes de malveillance (intrusion, vol, sabotage, ingérence, agression, terrorisme).
- Vérifier la conformité réglementaire (CSI, OIV/Directive REC, PPST/ZRR, IGI 1300 si applicable) et normative (APSAD, ISO).
- ### 2.2. Périmètre d'Audit
- **Périmètre géographique/physique :** [Description des emprises, bâtiments, réseaux et accès audités].
- **Exclusions :** [Mention explicite des éléments ou zones hors périmètre d'audit].
- ### 2.3. Référentiels d'Évaluation Utilisés
- **Normes ISO :** ISO 31000 (Management des risques), ISO 19011 (Audit), ISO 22301 (PCA).
- **Référentiels Métier :** APSAD R81 (Intrusion), R82 (Vidéoprotection), R101 (Contrôle d'accès).
- **Textes Réglementaires :** Code de la Sécurité Intérieure, Arrêtés OIV/SAIV, Guide ANSSI / SGDSN.
- ### 2.4. Méthodologie & Déroulement
- **Phase 1 :** Revue documentaire (Plan de masse, CCTP existants, consignes, registres, bilans d'incidents).
- **Phase 2 :** Investigations terrain (Inspection visuelle, tests de pénétration physique, tests fonctionnels).
- **Phase 3 :** Entretiens guidés (Responsable sûreté, agents de garde, DSI, exploitants techniques).
- ## 3. Cartographie des Risques & Analyse des Menaces
- ### 3.1. Identification des Actifs Critiques (Cibles)
- **Humains :** Personnel, visiteurs, VIP, sous-traitants.
- **Physiques :** Serveurs, TPC, automates SCADA/ICS, stocks à haute valeur, sous-stations électriques.
- **Immatériels :** Données R&D, fichiers clients, secrets de fabrique, image de marque.
- ### 3.2. Caractérisation des Menaces (Agent de menace & Scénarios)
- **Typologie retenue :** Vol simple/opportuniste, intrusion qualifiée, sabotage industriel, ingérence économique (*insider*), acte terroriste/attaque armée.
- **Évaluation des Scénarios de Menace (Méthode Bow-Tie / EBIOS RM) :**
	- *Scénario 1 :* Intrusion en périmétrie puis vol de données en ZRR.
	- *Scénario 2 :* Prise de contrôle à distance d'un automate de sûreté via le réseau OT.
- ### 3.3. Évaluation du Risque Brut vs. Risque Résiduel
- **Grille de cotation :** Matrice d'évaluation Impact (1 à 5) × Vraisemblance (1 à 5).
- ## 4. Diagnostic Technique, Organisationnel & Humain (Constats d'Audit)
  
  > 
  
  *Chaque sous-section suit la structure : **Exigence du Référentiel → Constat de Terrain → Preuve d'Audit (Photo/Log) → Anayse d'Écart**.*
- ### 4.1. Organisation, Gouvernance & Facteur Humain
- Politique de sûreté, consignes d'exploitation et procédures dégradées.
- Formation, sensibilisation du personnel et gestion des risques d'ingénierie sociale.
- Contrôle des prestataires externes et gestion des contrats de sécurité privée (CNAPS, habilitations).
- ### 4.2. Sûreté Physique & Cercle de Protection (Concept de Défense en Profondeur)
- **1ère Ligne — Périmétrie (Limites de propriété) :** Clôtures, détection périmétrique, éclairage, franchissement.
- **2ème Ligne — Périphonie (Enveloppe du bâtiment) :** Résistance des ouvrants (EN 1627-1630), détection de bris de verre, contacts de porte.
- **3ème Ligne — Volumétrie (Intérieur & Zones Sensibles) :** Détecteurs infrarouges/hyperfréquences, détection volumétrique.
- ### 4.3. Contrôle d'Accès, Obstacles & Filtration
- Équipements de filtration (Tourniquets, SAS, obstacles anti-bélier PAS 68).
- Architecture technique (Badges DESFire, lecteurs OSDP Secure Channel, UCT, serveurs).
- Gestion des identités, droits d'accès, visiteurs et organigramme des clés mécaniques.
- ### 4.4. Vidéoprotection, Supervision & PC Sûreté
- Couverture vidéo, angles morts, efficacité de l'éclairage nocturne, rétention légale (30 jours).
- Outils de supervision (VMS/Hypervision), analyse intelligente d'images (VCA).
- État et sécurisation du PC Sûreté (Local blindé, secours électrique, télé-sécurité APSAD P3/P5).
- ### 4.5. Convergence Cyber-Sûreté & Automatismes (OT/SCADA)
- Isolation et partitionnement du réseau IP de sûreté (VLAN dédiés, DMZ, Air Gap).
- Sécurisation des automates (GTC/GTB), durcissement des postes de supervision et gestion des mises à jour.
- Risques liés aux accès distants de télémaintenance.
- ## 5. Plan d'Actions Correctives & Préconisations (PDS)
  
  Les préconisations sont classées par niveau de priorité :
- **Priorité 1 (P1 - Immédiat) :** Risque critique ou non-conformité légale majeure.
- **Priorité 2 (P2 - Moyen terme) :** Amélioration significative de la résilience du site.
- **Priorité 3 (P3 - Long terme) :** Optimisation fonctionnelle et modernisation.
- ### 5.1. Matrice des Recommandations
  
  | ID | Domaine | Intitulé de la Préconisation | Type (Humain/Tech/Org) | Priorité | Estimation Coût (€) | Delai Vise |
  
  | **REC-01** | Cyber-Sûreté | Isoler le réseau IP du VMS sur un VLAN chiffré dédié | Tech | **P1** | 5 000 € | 1 mois |
  
  | **REC-02** | Périmétrie | Remplacer la clôture Nord et poser un câble sensoriel | Tech | **P1** | 45 000 € | 3 mois |
  
  | **REC-03** | Procédures | Mettre à jour les consignes de levée de doute au PCS | Org | P2 | 2 000 € | 2 mois |
  
  | **REC-04** | Accès | Migrer les lecteurs de badges vers le protocole OSDP v2 | Tech | P2 | 18 000 € | 6 mois |
- ### 5.2. Chiffrage Budgétaire & Feuille de Route (Roadmap)
- **Investissements (CAPEX) :** Matériels, travaux de blindage, déploiement réseau.
- **Fonctionnement (OPEX) :** Contrats de maintenance, gardiennage, licences d'exploitation VMS.
- ## 6. Annexes
- **Annexe 1 :** Fiches de relevé de terrain et photographies des non-conformités (masquées).
- **Annexe 2 :** PV des tests de pénétration physique et d'ingénierie sociale.
- **Annexe 3 :** Extraits des bilans d'incidents des 12 derniers mois.
- **Annexe 4 :** Attestation de qualification de l'auditeur (CESS).