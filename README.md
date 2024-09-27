# idée 

## pitch

Le joueur incarne un survivant dans un monde post-apocalyptique où il doit se battre contre des monstres pour survivre. Armé d'un lance-pierre avec un viseur laser, le joueur navigue à travers plusieurs niveaux et il se bat contre des ennemis de plus en plus puissant. Entre chaques niveaux le joueur peut acheter des améliorations avant de continuer.

Le joueur aurait un lance-pierre dans les mains avec un pointeur laser pour viser. La bande servirait comme détecteur de tir. Pour des raisons sécuritaires, le joueur ne va pas avoir de vrai balle.

# scenar

```mermaid
	flowchart TD
	Veille[Veille] --> |interaction| MainMenu[Menu Principal]
	MainMenu --> |Bouton pour instruction| Instructions[Instructions]
	Instructions --> |Fermer les instructions| MainMenu
	MainMenu --> |Début du jeux slingshot| DébutJeux[Commencement de la partie]
	DébutJeux --> SpawnMonster[apparition de monstre]
	SpawnMonster --> |monstre se rapproche| AttackMonster{Attaquer le monstre?}

	AttackMonster --> |oui| DamageMonster[fait des dégâts au monstre]
	DamageMonster --> MonsterHP{nombre de point de vie restant au monstre}
	MonsterHP --> |plus que zéro| MonsterAlive[le monstre est encore en vie]
	MonsterHP --> |Moins que zéro| MonsterDead[le monstre est mort]
	MonsterAlive --> AttackMonster
	MonsterDead --> GetPoint[Recois des point dépendamment du monstre]
	MonsterDead --nombre de monstre tuer + que 20--> SpawnMonster


	MonsterDead -- nombre de monstre tuer + que 20 --> BossSpawn[Boss du niveau]
	BossSpawn --tue le boss--> LevelFinished[tu as réussi ce niveau]
	BossSpawn --le boss te tue--> ScoreBoard
	LevelFinished --magasin entre les niveau--> MagasinNiveau[Achète des améliorations entre les niveaux]
	MagasinNiveau -- ferme le magasin --> LoadNextLevel[charge le prochain niveau]
	LoadNextLevel --> DébutJeux

	AttackMonster --> |non| TakeDamage[Prend des dégâts]
	TakeDamage --> HPStatus{Il te reste des points de vie?}
	HPStatus --> |oui| AttackMonster
	HPStatus --> |non, tu meurs| ScoreBoard[Tableau des points]

	ScoreBoard --> |continuer| MainMenu
	

```


# moodboard

ambiance, sons, etc

![ambiance](media/images/ambiance.png)

![clouds](media/images/dark_clouds.png)

![torch](media/images/blue_torch.png)

![city](media/images/apocalyptic_city.png)

![monster](media/images/Monstres.png)

# technologie
	
matériaux

logiciel
