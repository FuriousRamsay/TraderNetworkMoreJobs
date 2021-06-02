# Trader Network: More Jobs
This is a modlet to add additional Jobs/Challenges at the Traders

Can be installed for single player local games or server-side only when hosting a multiplayer server.

Currently tested with:
﻿	- Vanilla 19.4 B7
	﻿- Undead Legacy
	﻿- Darkness Falls

The following can be found as part of the Trader's job listing:

	Hold and Fetch (Tiers 1 through 5):
	- Phase 1: You are sent to a random POI which you have to clear
	- Phase 2: Once cleared, waves of zombies will spawn and you must kill a number of them in order to activate each subsequent wave
	- Phase 3: Fetch the Courier Satchel within the POI
	- Phase 4: A large number of zombies will spawn and you can either stay and fight or run back to the trader like a little baby
	- Phase 5: Get your reward from the trader you received the mission from
	﻿Note: you do not have to stay within the limits of the POI


The following can be purchased from the player vending machines at each trader. Each Tier increases in difficulty:

	The Hunt (Tiers 1 through 5):
	- Clear a number of mutant animals (current Vanilla set of animals with different skins and will retaliate)
	- Each wave is triggered by killing a number of them
	- The Trader Network supplies you with mechanical allies to assist you in your mission
		- Tier 1: dogs that will regenerate your stamina if you stay close
		- Tier 2: wolves that will regenerate your health if you stay close
		- Tier 3: lions that will burn nearby zombies and knockback foes in an area of effect
		- Tier 4: bears that will do explosive damage to nearby foes which will knock them down
		- Tier 5: androids that will shock nearby foes
	- Allies will only have enough power for a few minutes
	- Get your reward from any trader once the objectives have been met

	﻿Mini Horde (Tiers 1 through 5):
	- Phase 1: You are sent to a random location to activate your mission. It is recommended that you build some sort of defenses
	- Phase 2: Waves of zombies will spawn and you must kill a number of them in order to activate each subsequent wave
	- Phase 3: A large number of zombies will spawn and you can either stay and fight or run back to the trader like a little baby
	- Phase 4: Get you reward from any trader once the objectives have been met

﻿	Horde Training (Tiers 1 through 5):
	- You are given a challenge that can be activated at any location. The idea is to test out your horde base against waves of zombies, see how
	﻿  well it holds
	- Zombies will spawn over time, there are no special activations required for them to continue spawning
	- There are no rewards for this challenge. It is purely meant to assist in you testing out your defenses or offensive abilities (should you wish to
	﻿  try this out in the open)
	Note: 	Spawns occur over time and are essentially queued. You should do your best to stay and fight. If you leave and are in single player, the
﻿        	game will not clear the spawn queue (bug that has been submitted) which will cause NullException errors when you go back in. The spawns
		will not occur, but the game will still attempt to action the queue until the queue is empty. Spawning usually lasts 6 minutes total. One way to
		clear the queue is to close the game
	        Not much testing has been done in multiplayer. Feedback is welcome

﻿	Mechanical Allies (Tiers 1 through 5):
	- The following allies can be purchased and spawned:
		- Tier 1: dogs that will regenerate your stamina if you stay close
		- Tier 2: wolves that will regenerate your health if you stay close
		- Tier 3: lions that will burn nearby zombies and knockback foes in an area of effect
		- Tier 4: bears that will do explosive damage to nearby foes which will knock them down
		- Tier 5: androids that will shock nearby foes
	Note: There are two types:
		- a crate which can only be used in Single Player mode. They will not work in Multiplayer (game code limitations)
		- a dispatcher which will work in both modes but cannot be accurately spawned like the crate. A green marker will show on your compass to
		﻿﻿  indicate where the ally has spawned

	﻿Note: These are prototypes and aren't very optimized. They rely on the core game AI which still has to be improved.
	﻿﻿- Ally Function 1: attack nearby zombies and hostile animals
	﻿﻿- Ally Function 2: follow player up to a certain point
	﻿﻿The AI does not do very well inside a POI, but crates can be placed in single player as way to help defend in certain situation should you need
	﻿﻿some assistance

Installation Instructions:

﻿	Multiplayer Server Install:
	Copy the zz_Trader Network_MoreJobs folder into the \Mods folder of your 7DTD server folder
	Note: 	all FuriousRamsaySpawnAllyNPCTierX lines in traders.xml should be commented out as these only work in single player

	﻿Single Player Local Installs:
	Copy the zz_Trader Network_MoreJobs folder into the \Mods folder of your 7DTD game folder
	﻿﻿Note: 	all qc_FuriousRamsaySpawnAllyNPCTierX (random spawns) lines in traders.xml should be commented out as these items
	        ﻿﻿﻿aren't as good as FuriousRamsaySpawnAllyNPCTierX ones (placeable spawns)
		Yellow warnings on the console can be ignored. Some references were added in order to support how Darkness Falls splits
		the trader's inventories. They have no impact on the game when not found.

﻿If you connect to servers who run this modlet, you do not have to do anything as this mod is server-side and will be loaded when you connect

Warning: Please back up your saved world and character before installing this mod. The game does not handle the removal of accepted or completed
	 quests well and will reset your character should you decide to remove the mod after trying it out. This is unfortunately a known issue 
	 with how the game is currently designed and out of modder's control. One option is to leave the mod in and simply not make use of the 
	 additional challenges at the vending machines (which are pretty useless otherwise anyway). If you decide to not use the mod and wish to
	 no longer have any references to the Hold and Fetch jobs from the trader list, you can remove the following code from quests.xml:

	﻿<append xpath="/quests/quest_list[@id='trader_quests']">
		<quest id="quest_FuriousRamsayTier1_clearhold"/>
		<quest id="quest_FuriousRamsayTier2_clearhold"/>
		<quest id="quest_FuriousRamsayTier3_clearhold"/>
		<quest id="quest_FuriousRamsayTier4_clearhold"/>
		<quest id="quest_FuriousRamsayTier5_clearhold"/>
	</append>