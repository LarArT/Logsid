- https://eo4society.esa.int/wp-content/uploads/2024/10/French-Brochure-ESA-Radar-Course.pdf
  
  [[Cours en ligne analyse image radar]] 
  
  L'interprétation des images radar satellitaires (principalement les radars imageurs SAR - *Synthetic Aperture Radar*) obéit à des principes physiques et géométriques très différents de la vision humaine ou de l'imagerie optique classique.
  
  Voici une explication détaillée et pédagogique pour comprendre comment analyser ces images.
- ## 1. Le principe de base : un capteur actif et oblique
  
  Contrairement aux capteurs optiques qui photographient la Terre grâce à la lumière du Soleil (capteurs passifs), le radar est un **capteur actif** : il émet sa propre onde électromagnétique dans le domaine des **micro-ondes** (longueurs d'onde de l'ordre du centimètre) et mesure le signal réfléchi (l'écho).
- **Une visée latérale :** Le satellite n'éclaire pas le sol à sa verticale, mais de côté, selon un **angle d'incidence** généralement compris entre 20° et 45°.
- **La géométrie de l'image :** Une image radar comporte deux directions fondamentales :
	- La direction **d'azimut** : parallèle à la trajectoire du satellite (horizontal).
	- La direction de **distance (*range*)** : perpendiculaire à la trajectoire, représentant la ligne de visée du faisceau.
	  
	  En optique, deux objets sont séparés s'ils sont vus sous des angles différents. **En radar, deux points sont séparés s'ils sont situés à des distances différentes du capteur**. C'est ce qui rend l'interprétation initiale contre-intuitive.
- ## 2. L'interprétation de l'amplitude : que signifient les zones claires et sombres ?
  
  L'information d' **amplitude** correspond à la quantité d'énergie rétrodiffusée (renvoyée vers le satellite). Elle dépend de trois grands facteurs de la surface terrestre :
- **La rugosité :** Une surface lisse (comme l'eau calme ou une route goudronnée) agit comme un miroir : l'onde rebondit et s'éloigne du satellite. L'image apparaît **noire** (faible amplitude). À l'inverse, une surface rugueuse (forêt, blocs rocheux) diffuse l'onde dans toutes les directions, y compris vers le satellite : l'image apparaît **claire**.
- **La teneur en eau (humidité) :** L'eau augmente fortement la conductivité et la réflectance des sols pour les micro-ondes. Un sol gorgé d'eau renverra un signal plus fort.
- **L'orientation de la cible :** La géométrie des objets par rapport à l'angle de l'onde joue un rôle majeur, ce qui entraîne des déformations topographiques caractéristiques.
- ## 3. Les déformations géométriques spécifiques au relief
  
  En raison de la visée oblique, le relief terrestre subit des distorsions géométriques qu'il faut impérativement connaître pour ne pas commettre d'erreurs d'interprétation :
- **Le raccourcissement (*Foreshortening*) :** Les pentes orientées vers le satellite apparaissent comprimées, "raccourcies", et renvoient une énergie très forte (zones très brillantes).
- **Le repliement (*Layover*) :** C'est un cas extreme. Lorsque la pente du terrain est plus raide que l'angle d'incidence du radar, le sommet de la montagne est atteint par l'onde *avant* sa base. Le signal du sommet revient donc avant celui de la base : **les objets sont inversés dans l'image**, et des altitudes différentes se superposent.
- **L'allongement (*Lengthening*) :** Les pentes orientées dans la direction opposée au capteur (qui s'éloignent du satellite) s'étirent sur l'image et affichent des amplitudes faibles.
- **La zone d'ombre (*Deshadow*) :** Si la pente est trop prononcée, le faisceau radar ne peut pas l'atteindre. Cette zone cachée ne renvoie aucun signal et apparaît complètement noire.
  
  *Exemple concret :* Un volcan symétrique comme le mont Fuji apparaîtra totalement asymétrique sur une image radar, son flanc face au satellite étant ultra-brillant et compressé.
- ## 4. L'apport de la phase : l'interférométrie
  
  Au-delà de l'intensité (l'amplitude), le signal radar enregistre une **phase** (un nombre compris entre -\pi et \pi).
- En comparant la phase de l'onde émise et celle de l'onde reçue, il est possible de mesurer des variations de distance infimes entre le satellite et le sol, de l'ordre de **quelques centimètres**.
- Cette technique (l'interférométrie radar ou InSAR) est essentielle pour cartographier les déplacements de surface (tremblements de terre, affaissements miniers, glissements de terrain) ou évaluer la quantité de vapeur d'eau dans l'atmosphère.