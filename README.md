# idée 

## Pitch

Le joueur incarne un survivant dans un monde post-apocalyptique où il doit se battre contre des monstres pour survivre. Armé d'un lance-pierre avec un viseur laser, le joueur navigue à travers plusieurs niveaux et il se bat contre des ennemis de plus en plus puissant. Entre chaques niveaux le joueur peut acheter des améliorations avant de continuer.

Le joueur aurait un lance-pierre dans les mains avec un pointeur laser pour viser. La bande servirait comme détecteur de tir. Pour des raisons sécuritaires, le joueur ne va pas avoir de vrai balle.

## Scénario intéractif

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


## Moodboard

### Moodboard d'ambiance

ambiance, sons, etc

![ambiance](media/images/ambiance.png)

crédit pour images: <br>
Nuages: [Metlink](https://www.metlink.org/experiment/why-do-clouds-look-black/)  <br>
Torche: [Adobe](https://stock.adobe.com/)  <br>
Ville: [Archdaily](https://www.archdaily.com/998267/architecture-after-civilization-design-in-the-post-apocalypse)  <br>
Monstre: [The Final Station (jeu vidéo)](https://thefinalstation.com/) <br>
Lance-Pierre: [Pro-Green](https://www.pro-greens.com/hunting-professional-catapult-laser-slingshot-with-rubber-aim-point-target-hot-RURDGElAVhlXRVJV)

***
#### Lance-pierre
![Slingshot](media/images/slingshot.png)

Le lance-pierre sera l'arme principale du joueur. Il le tiendra dans ses main pour viser sur la projection sur un mur.

#### Nuages
![clouds](media/images/dark_clouds.png)

Il y aurait des nuages noir épais avec des éclairs pour rajouter a l'ambiance.

#### Torche bleu
![torch](media/images/blue_torch.png)

Le joueur possèderait une lanterne bleue pour repousser la noirceur. La lampe agirait aussi comme compteur de point de vie.

#### Ville apocalyptique
![city](media/images/apocalyptic_city.png)

Le jeu se passerait dans une ville en ruine avec plusieurs environnements selon le niveau. il v aussi y avoir un décor de magasin entre les niveaux.

#### Monstres
![monster](media/images/Monstres.png)

Les monstres sont des ombres ressemblant à ceux dans la photo. Ils seront fait d'une fumée noire avec de la lumière mauve sombre a l'intérieur. Si possible, il va y avoir plusieurs type de monstres.

#### couleurs
![couleurs](media/images/colors.png)

J'ai choisi un thème de couleur plus sombre et plus froide pour venir augmenter l'ambiance d'apocalypse. De plus, ces couleurs viennent aider la détections du laser, car ils feront ressortir le rouge plus facilement.

### Moodboard de sons

#### ambiance de base

[Vent et tonnere](https://www.soundeffectsplus.com/product/storm-wind-and-thunder-01/)

[pluie légère](https://soundbible.com/2011-Rain-Background.html)

Mélange des deux pour faire une ambiance tendu.

#### Monstres

[Bruit de vieille radio](https://www.soundeffectsplus.com/product/antique-tube-radio-being-tuned-02/)

[Bruit de pas dans une forêt](https://www.soundeffectsplus.com/product/footsteps-walking-in-forest-01/)

Faible bruit provenant des monstres avec des bruit de pas occasionnel.

#### Lance-Pierre

[Élastique cartoon](https://pixabay.com/sound-effects/slingshot-1-40486/)

[Arc](https://soundbible.com/1780-Bow-Fire-Arrow.html)

Un bruit d'élastique mais un peu moins cartoon. Il jourait lorsque le joueur tire sur la bande.

#### Torche

[Bruit de feu](https://soundbible.com/1543-Fireplace.html)

Bruit de feu irrégulier qui s'affaiblit dépendamment de la vie restante du joueur.

#### Musique

idk yet, any ideas?

## technologie

### Support médiatique

Une application créé dans unity qui sera projeté sur un mur par un projecteur. Une caméra filmera cette projection pour capter la position de la couleur rouge (le laser). Quand la bande du lance-pierre sera relâcher, un message sera envoyer vers l'application pour "tirer" sur la position du point rouge. Des haut-parleurs des 2 côté de la projection créeront une ambiance stéréo qui différera selon l'action du joueur.

### Matériaux

Un capteur pour quand la bande du lance-pierre dépasse le centre du lance-pierre après avoir été tiré. <br>

Un system de projection. <br>
Un system de tracking pour la couleur rouge. <br>
Model 3D créé par imprimante 3D

### Logiciel

Unity pour la création de l'application <br>
Visual studio pour la programmations de unity <br>
Maya ou Blender (pour la création du lance-pierre) <br>
