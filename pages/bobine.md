# calcul intensité
- Dans ce schéma simplifié, pour mesurer l'intensité du courant qui traverse la bobine (et qui génère le champ magnétique), il faudrait placer un appareil de mesure capable de supporter et d'enregistrer un courant impulsionnel très élevé.
  Placement Conceptuel :
  L'appareil de mesure devrait être placé en série avec la bobine, dans le chemin de décharge du condensateur. Sur le schéma, cela signifierait l'insérer sur le fil qui relie l'interrupteur et le condensateur à la bobine, ou sur le fil qui relie la bobine à la masse (GND), juste avant ou juste après la bobine.
  Voici où le placer conceptuellement (représenté par 'A' pour Ampèremètre/mesureur de courant) :
  [Source de Courant Haute Tension]
         |
         +-----[Interrupteur (Rapide)]-----+
         |                               |
       [Condensateur (Haute Capacité)]   |
         |                               |
         +-------------------------------+-----[ A ]-----[Bobine (Coil)]-----Région du Cerveau
                                         |
                                       [Diode (Protection)]
                                         |
                                        GND
  
  Pourquoi un Multimètre Standard n'est PAS Adapté :
  Il est crucial de comprendre qu'un multimètre standard ne convient absolument pas pour cette mesure dans un vrai circuit TMS. Voici pourquoi :
   * Courant Très Élevé : L'intensité du courant dans une bobine TMS atteint des niveaux très élevés (plusieurs milliers d'ampères) pendant un temps très court. Les multimètres standard sont limités à quelques ampères au maximum.
   * Nature Impulsionnelle/Transitoire : Il ne s'agit pas d'un courant continu ou alternatif stable, mais d'une impulsion très brève. Les multimètres ne sont pas conçus pour capturer et mesurer précisément le pic d'une impulsion aussi rapide et intense.
   * Risque de Destruction : Placer un multimètre standard dans un tel circuit le détruirait instantanément et représenterait un danger.
  Équipement Réellement Utilisé :
  Dans les systèmes TMS réels ou pour la recherche, on utilise des équipements spécialisés pour mesurer ce type de courant pulsé, comme :
   * Pinces ampèremétriques transitoires ou sondes de courant (souvent basées sur l'effet Hall ou des transformateurs de courant type Rogowski) connectées à un oscilloscope numérique rapide. Ces dispositifs permettent de visualiser et de mesurer l'amplitude et la forme de l'impulsion de courant sans être insérés directement dans le circuit haute tension.
   * Des shunts de mesure (résistances de faible valeur et de haute puissance) en série avec la bobine, mais la chute de tension à travers le shunt est alors mesurée par un oscilloscope rapide (cela nécessite que le shunt puisse supporter le courant de pointe et la puissance dissipée).
  Donc, bien que le placement conceptuel soit en série avec la bobine, la mesure réelle nécessite un équipement bien plus sophistiqué qu'un simple multimètre.
-