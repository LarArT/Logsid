- Voici une fiche de révision structurée et synthétique basée sur les données de la télédétection fournies dans le document :
- # Fiche de Révision : Les Données de la Télédétection
- ## 1. Les Plateformes d'Observation
- **Définition :** Enregistrement de signaux de la surface terrestre à l'aide de capteurs embarqués sur des plateformes distantes (satellites, avions, drones).
- **Satellites d'observation de la Terre :**
	- **Orbites quasi-polaires :** Orientées nord-sud (passage proche des pôles, laissant une infime zone non imagée).
	- **Orbites héliosynchrones :** Passage à la verticale d'un point toujours à la même heure, garantissant une illumination quasi similaire.
	- **Caractéristiques :** Altitude autour de 800 km, durée de vie de 5 à 10 ans. Temps de revisite de 10 jours à 1 mois (réduit à moins d'un jour grâce aux constellations).
- **Autres plateformes (Avions / Drones) :**
	- Mesures non régulières (liées aux campagnes de vol).
	- **Avantage :** Faible altitude offrant une excellente **résolution spatiale** pour imager de petits objets géologiques en complément des satellites.
- ## 2. Les Types de Capteurs
- **Capteurs passifs :** Captent les signaux d'une source externe réfléchie par la Terre (ex. : capteurs optiques mesurant la lumière solaire réfléchie, l'œil humain, les yeux des insectes).
- **Capteurs actifs :** Enregistrent un signal émis par le capteur lui-même et réfléchi par la surface (ex. : radars, lidars, écholocation des chauves-souris/dauphins).
- **Sensibilité spectrale :** Chaque capteur analyse une bande de fréquence limitée du spectre électromagnétique (visible, ultraviolet, infrarouge, micro-ondes).
- ## 3. Spécificités des Capteurs Optiques et Radar
- ### A. Capte6urs Optiques
  https://explorer.maap.eo.esa.int/
- **Fonctionnement :** Imagerie à la verticale ou avec dépointage (permettant d'augmenter la fréquence de revisite ou de générer des vues stéréoscopiques pour des Modèles Numériques de Terrain - MNT).
- **Bandes spectrales :** Bleu, vert, rouge, infrarouge, parfois infrarouge thermique et ultraviolet.
- **Réflectance :** Varie selon la longueur d'onde et la nature de la surface (ex. : la végétation a une forte réflectance dans l'infrarouge, l'eau dans le bleu ou le vert).
- ### B. [[Capteurs Radar]] (SAR)
- **Fonctionnement :** Émettent une onde sur le côté (angle d'incidence de 20° à 45°) et enregistrent une information complexe (amplitude et phase).
- **Directions :**
	- *Azimuth* (parallèle à la trajectoire).
	- *Distance ou range* (ligne de visée, projetée au sol en *ground range*).
- **Amplitude :** Dépend de l'orientation de la cible, de sa rugosité, de sa teneur en eau et du type de sol.
- **Déformations géométriques radar :**
	- **Foreshortening (raccourcissement) :** Pentes vers le satellite raccourcies avec forte énergie rétrodiffusée.
	- **Layover (repliement) :** Pentes supérieures à l'angle d'incidence entraînant une inversion et une superposition d'altitudes.
	- **Lengthening (allongement) :** Pentes opposées allongées avec de faibles amplitudes.
	- **Deshadow (ombre) :** Zones non imagées situées dans l'ombre.
- **Phase :** Permet d'obtenir des variations de distance centimétriques (interférométrie) ou le contenu en vapeur d'eau atmosphérique.
- ## 4. Principales Données Open Source (Satellites)
  
  | Satellite / Constellation | Type | Résolution spatiale | Fréquence de revisite / Particularités |
  
  | **Sentinel-2** (ESA) | Optique | 10 m (4 bandes) | Tous les 5 jours à l'équateur (grande fauchée ~300 km). |
  
  | **SPOT** | Optique | 10 m à 1,5 m (selon version) | Archive historique depuis 1986 ; facultés stéréoscopiques (MNT). |
  
  | **Landsat** (NASA / USGS) | Optique | 15 m (Landsat 8, 11 bandes) | Profondeur historique depuis 1972 ; revisite de 16 jours. |
  
  | **Planetscope** | Optique | ~3 m | Constellation > 130 satellites ; revisite inférieure à la journée. |
  
  | **Pléiades** *(partenariats)* | Optique | 70 cm | Haute résolution utile pour les petits objets (mouvements de terrain). |
  
  | **Sentinel-1** (ESA) | Radar (SAR) | 3 m (range) / 15 m (azimuth) | Fauchée de 250 km ; revisite générale de 12 jours (6 jours en constellation). |