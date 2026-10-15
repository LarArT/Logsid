- Pour comprendre le changement de variable sans s'enfoncer immédiatement dans l'algèbre, on peut imaginer une situation concrète : **le passage d'une commande de pizzas à la facture finale**.
  Voici comment le théorème de probabilités s'applique à ce cas de la vie réelle.
- ## La situation : Le diamètre de la pizza
  Imaginez un pizzaiolo artisanal. Les pizzas qu'il étale à la main ne font pas toutes exactement la même taille. On note X la variable aléatoire qui représente le **diamètre** de la pizza (en centimètres).
  À force d'observer sa production, le pizzaiolo sait que le diamètre X suit une certaine loi de probabilité (une courbe en cloche autour de 30 cm, par exemple). On connaît donc parfaitement la densité f_X.
- ## Le changement de variable : Le prix de la pizza
  Le patron de la pizzeria décide d'appliquer un tarif basé sur la quantité de pâte et d'ingrédients. Le prix dépend donc directement de l'**aire** de la pizza.
  La formule mathématique qui transforme le diamètre X en prix Y est notre fonction g(X) :
  * L'aire d'un disque est \pi \times R^2, soit \pi \times \left(\frac{X}{2}\right)^2 = \frac{\pi}{4}X^2.
  * Si le prix est fixé à 0,02 € par \text{cm}^2, la fonction de transformation est :
   
  La question du théorème est la suivante : **Si on connaît la répartition des diamètres (X), quelle est la répartition des prix payés par les clients (Y) ?**
- ## Pourquoi a-t-on besoin du "Jacobien" (la dérivée) ?
  C'est ici que l'intuition physique rejoint la formule. On pourrait penser qu'il suffit de remplacer le diamètre par le prix dans la formule de départ. Mais c'est faux, à cause d'un phénomène d'**étirement**.
  1. **L'effet non linéaire :** Si le diamètre passe de 20 à 21 cm (+1 cm), l'aire augmente d'environ 31\text{ cm}^2. Si le diamètre passe de 40 à 41 cm (+1 cm également), l'aire augmente cette fois d'environ 64\text{ cm}^2.
  2. **La concentration des probabilités :** Un écart de 1 cm sur les grandes pizzas crée une variation de prix beaucoup plus grande que sur les petites pizzas. Les probabilités vont donc "s'étaler" différemment sur l'axe des prix.
  C'est exactement le rôle de la dérivée \left| \frac{d}{dy} g^{-1}(y) \right| (ou du déterminant jacobien en plusieurs dimensions) dans la formule : **elle compense cet effet d'étirement ou de compression de l'espace**. Elle fait office de taux de change local pour que la somme totale des probabilités reste égale à 1 (soit 100 % des pizzas produites).
- ## En résumé
  * f_X\left(g^{-1}(y)\right) : On cherche d'abord quel diamètre (X) correspond au prix (Y) constaté à la caisse.
  * \left| \frac{d}{dy} g^{-1}(y) \right| : On applique un coefficient multiplicateur (la dérivée de la fonction réciproque) pour ajuster la probabilité au fait qu'un centimètre de diamètre ne vaut pas la même surface (ni le même prix) selon que la pizza est petite ou géante.
-
-