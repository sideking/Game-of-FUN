```mermaid
flowchart TD
    Veille[Veille] --> |interaction| MainMenu[Menu Principal]
    MainMenu --> |Bouton pour instruction| Instructions[Instructions]
    Instructions --> |Fermer les instructions| MainMenu
    MainMenu --> |Début du jeux slingshot| DébutJeux
```
