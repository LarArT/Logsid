- Voici les deux options pour intégrer ce diagramme d'implications topologiques dans votre Logseq.
  La version **Mermaid** est fortement recommandée car Logseq la convertit automatiquement en un schéma visuel interactif.
- graph TD
    %% Définition du style général
    classDef default fill:#f9f9f9,stroke:#333,stroke-width:1px;
  
    %% Colonne de gauche (Séparation / Métriques)
    Metric --> Paracompact
    Separable_metric["Separable metric"] --> Metric
    Separable_metric --> Regular_Lindelof["Regular Lindelöf"]
    Compact_metric["Compact metric"] --> Separable_metric
    Compact_metric --> Compact
    Compact_metric --> Complete_metric["Complete metric"]
  
    %% Colonne centrale (Axiomes de séparation verticaux)
    Paracompact --> Normal
    Normal --> Completely_regular["Completely regular"]
    Completely_regular --> Regular
    Regular --> Hausdorff
  
    %% Colonne de droite (Compacité)
    Compact --> Sigma_compact["σ-compact"]
    Sigma_compact --> Locally_compact["Locally compact"]
    Sigma_compact --> Paracompact
    Locally_compact --> Completely_regular
    Locally_compact --> Baire
    Complete_metric --> Baire
  
    %% Note de bas de page
    subgraph Note [" "]
        direction LR
        text["Sans hypothèse additionnelle, aucune implication n'est réversible."]
    end
    style Note fill:none,stroke:none
- ### Option 2 : Version Markdown (Sous forme de liste hiérarchique)
  Si vous préférez une structure de blocs purement textuelle pour structurer vos notes, voici la traduction des relations logiques :
  * **Hausdorff**
   * \Leftarrow **Regular**
     * \Leftarrow **Completely regular**
       * \Leftarrow **Normal**
         * \Leftarrow **Paracompact**
           * \Leftarrow **Metric**
             * \Leftarrow **Separable metric**
               * \Leftarrow **Compact metric**
           * \Leftarrow **Regular Lindelöf**
             * \Leftarrow **Separable metric**
           * \Leftarrow **\sigma-compact**
             * \Leftarrow **Compact**
               * \Leftarrow **Compact metric**
       * \Leftarrow **Locally compact**
         * \Leftarrow **\sigma-compact**
  * **Baire**
   * \Leftarrow **Locally compact**
   * \Leftarrow **Complete metric**
     * \Leftarrow **Compact metric**
  > **Note :** Sans hypothèse additionnelle, aucune de ces implications n'est réversible.
-
- $$
  \begin{array}{rcccl}
  & & \text{Hausdorff} & & \\
  & & \uparrow & & \\
  & & \text{Régulier} & & \\
  & & \uparrow & & \\
  & & \text{Complètement régulier} & \Longleftarrow & \text{Localement compact} \implies \text{Baire} \\
  & & \uparrow & & \uparrow \qquad \qquad \qquad \quad \uparrow \\
  & & \text{Normal} & \Longleftarrow & \sigma\text{-compact} \\
  & & \uparrow & \nearrow & \\
  \text{Métrique} & \implies & \text{Paracompact} & \Longleftarrow & \text{Régulier Lindelöf} \\
  \uparrow & & & \nearrow & \\
  \text{Métrique séparable} & \longrightarrow & \longrightarrow & & \\
  \uparrow & & & & \\
  \text{Métrique compacte} & \implies & \text{Compact} & & \\
  \end{array}
  $$