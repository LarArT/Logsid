- Dans l'exemple 61 du document, la division de l'écart-type par la racine carrée de n (\sigma/\sqrt{n}) ne correspond pas à l'écart-type d'une donnée individuelle, mais à l'**erreur standard de la moyenne**.
  Voici pourquoi cette division est nécessaire d'un point de vue mathématique et statistique :
- ### 1. La variance d'une somme de variables
  L'exemple 61 porte sur la **moyenne empirique** \bar{X}_n, qui est définie comme la somme de n observations divisée par n:
  
  En probabilités, quand on additionne des variables indépendantes, leurs variances s'additionnent:
  * Var(X_1 + \dots + X_n) = n \sigma^2.
- ### 2. Le passage à la moyenne
  Puisque la moyenne est cette somme divisée par n, et que d'après les propriétés de la variance Var(aX) = a^2 Var(X), on obtient:
  * Var(\bar{X}_n) = Var(\frac{1}{n} \sum X_i) = \frac{1}{n^2} Var(\sum X_i) = \frac{1}{n^2} (n \sigma^2) = \frac{\sigma^2}{n}.
- ### 3. L'écart-type (Erreur Standard)
  L'écart-type étant la racine carrée de la variance, l'écart-type de la moyenne (noté SE pour *Standard Error*) devient naturellement:
  
  [Image de la distribution de la moyenne empirique montrant son rétrécissement quand n augmente]
- ### Pourquoi est-ce logique ?
  * **Réduction de l'incertitude :** Plus la taille de l'échantillon (n) est grande, plus la valeur de \frac{\sigma}{\sqrt{n}} est petite.
  * **Stabilité :** Cela signifie que la moyenne d'un grand groupe est beaucoup plus stable et moins "éparpillée" que la valeur d'un seul individu. C'est ce que l'on appelle la **Loi des Grands Nombres**.
  Dans la statistique de test de l'exemple 61, on divise par ce terme pour savoir si l'écart observé entre votre moyenne et la théorie est "normal" (au regard de la dispersion attendue pour cette taille d'échantillon) ou s'il est exceptionnel.
-
-