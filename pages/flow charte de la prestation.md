- ```mermaid
  graph LR
      %% Styles des entités (Cercles) et des événements (Rectangles)
      classDef entity fill:#ffffff,stroke:#1e293b,stroke-width:2px,rx:20px,ry:20px;
      classDef event fill:#ffffff,stroke:#334155,stroke-width:1.5px,rx:5px,ry:5px;
  
      %% Acteurs / Entités (Ligne verticale gauche)
      subgraph Acteurs
          direction TB
          Hess["Hess"]:::entity
          Clark["Clark"]:::entity
          Toka["Toka"]:::entity
      end
  
      %% Événements chronologiques
      E1["Returns from Germany<br><i>(Sep 19)</i>"]:::event
      E2["Meet at Brown Park<br><i>(Sep 25)</i>"]:::event
      E3["Telephone contact<br><i>(Sep 26)</i>"]:::event
      E4["Meet package from Hess to Clark<br><i>(Oct 3)</i>"]:::event
      E5["Meet at Brown Park<br><i>(Oct 5)</i>"]:::event
  
      %% Relations et flux d'événements
      Hess --> E1
      E1 --> E4
      
      Clark --> E2
      Toka --> E2
      
      E2 --> E3
      E3 --> E4
      
      Clark --> E5
      Toka --> E5
  
      linkStyle default stroke:#334155,stroke-width:1.5
  ```
-