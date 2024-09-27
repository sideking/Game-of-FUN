# idée 

## pitch

Le joueur incarne un survivant dans un monde post-apocalyptique où il doit se battre contre des monstres pour survivre. Armé d'un lance-pierre avec un viseur laser, le joueur navigue à travers plusieurs niveaux et il se bat contre des ennemis de plus en plus puissant. Entre chaques niveaux le joueur peut acheter des améliorations avant de continuer.

Le joueur aurait un lance-pierre dans les mains avec un pointeur laser pour viser. La bande servirait comme détecteur de tir. Pour des raisons sécuritaires, le joueur ne va pas avoir de vrai balle.

# Scénario intéractif

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

Il y aurait des nuages noir épais avec des éclairs pour rajouter a l'ambiance.

![torch](media/images/blue_torch.png)

Le joueur possèderait une lanterne bleue pour repousser la noirceur. La lampe agirait aussi comme compteur de point de vie.

![city](media/images/apocalyptic_city.png)

Le jeu se passerait dans une ville en ruine avec plusieurs environnements selon le niveau. il v aussi y avoir un décor de magasin entre les niveaux.

![monster](media/images/Monstres.png)

Les monstres sont des ombres ressemblant à ceux dans la photo. Ils seront fait d'une fumée noire avec de la lumière mauve sombre a l'intérieur. Si possible, il va y avoir plusieurs type de monstres.

![monster](media/images/colors.png)

J'ai choisi un thème de couleur plus sombre et plus froide pour venir augmenter l'ambiance d'apocalypse. De plus, ces couleurs viennent aider la détections du laser, car ils feront ressortir le rouge plus facilement.

# technologie
	
matériaux

logiciel
