Source:: https://openclassrooms.com/fr/courses/7779336-decouvrez-les-processus-au-coeur-de-la-logistique

- Distribution Resource Planning (DRP) fera une suggestion de commande à l’approvisionneur en prenant en compte différentes contraintes :
  
  disponibilité de la marchandise chez le fournisseur ; 
  
  optimisation du flux commandé (nombre d'unités minimum, etc.) ;
  
  délai de livraison de commande, dit Order Lead Time ou OLT.
- Code d'identification produit :
	- le SKU (Stock Keeping Unit) : code [8-12 caractères] défini par votre entreprise (peut être attribué par votre WMS). Cette codification est logique, et utilise une nomenclature représentant des caractéristiques du produit ;
	- ’EAN (European Article Number) et/ou l’UPC (Universal Product Code) : code universel [12 chiffres] accompagné d’un code barre. Sa composition correspond à une norme internationale, et représente des informations d’identification (telles que le fabricant, etc
- La hiérarchie des codes (GTIN)
  L'UPC et l'EAN font partie de la famille des GTIN (Global Trade Item Number). En logistique, on parle souvent de :
  GTIN-12 pour l'UPC.
  GTIN-13 pour l'EAN.
  GTIN-14 pour les cartons (souvent appelé ITF-14). Ce dernier permet aux scanners d'entrepôt de savoir qu'ils scannent un colis contenant plusieurs unités et non un produit individuel.
- Anatomie d'un code EAN-13
  Un code EAN-13 n'est pas une suite de chiffres aléatoires. Il suit une structure rigoureuse de 13 chiffres :
  Le Préfixe GS1 (3 chiffres) : Il indique le pays de l'organisation nationale où l'entreprise est enregistrée (ex: 300 à 379 pour la France, 540 à 549 pour la Belgique). Attention : cela indique l'origine de l'entreprise, pas forcément le lieu de fabrication du produit.
  Le Code Entreprise (4 à 6 chiffres) : Un numéro unique attribué à la marque par GS1.
  La Référence Produit (2 à 5 chiffres) : Numéro attribué par le fabricant pour désigner un article spécifique (une variante de couleur, de taille ou de poids).
  La Clé de Contrôle (1 chiffre) : Le dernier chiffre est calculé selon un algorithme mathématique basé sur les 12 précédents. Il sert à vérifier que le scanner a bien lu le code sans erreur.
- obtenir vos codes officiels :
	- ### ​1. Passer par l'organisme officiel : GS1
	  
	  ​Il n'existe qu'une seule source légale et universelle pour générer des codes EAN : **GS1**.
		- ​En France, il s'agit de **GS1 France**.
		- ​Évitez absolument les sites de "revente de codes-barres" à bas prix. Amazon et les grands distributeurs vérifient désormais la base de données GS1 (GÉPIR). Si votre code n'est pas enregistré au nom de votre entreprise, votre produit peut être banni de la plateforme.
- ### ​2. Le processus d'adhésion
  
  ​Pour obtenir vos codes, vous devez :
	- ​**Adhérer à GS1 :** Vous payez une cotisation annuelle (basée sur le chiffre d'affaires de votre entreprise).
	- ​**Recevoir votre GCP (Global Company Prefix) :** C'est votre identifiant d'entreprise (les premiers chiffres de vos futurs EAN).
	- ​**Créer vos fiches produits :** Sur la plateforme en ligne de GS1 (appelée "CodeOnline"), vous renseignez le nom de votre produit, sa marque, sa photo et ses caractéristiques.
-