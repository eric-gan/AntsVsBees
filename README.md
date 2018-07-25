# AntsVsBees

A tower defense game called Ants Vs. SomeBees inspired by PopCap Games' Plants Vs. Zombies. As the ant queen, you populate your colony with the bravest ants you can muster. Your ants must protect their queen from the evil bees that invade your territory. Irritate the bees enough by throwing leaves at them, and they will be vanquished. Fail to pester the airborne intruders adequately, and your queen will succumb to the bees' wrath.

## Usage:

1. Download the associated files

2. From the 'ants' folder, run the following command:

'''
python3 gui.py [-h] [-d DIFFICULTY] [-w] [--food FOOD]

Play Ants vs. SomeBees

optional arguments:
  -h, --help     show this help message and exit
  -d DIFFICULTY  sets difficulty of game (easy/medium/hard/insane)
  -w, --water    loads a full layout with water
  --food FOOD    number of food to start with (cheat code).
'''

## Instructions:

Each ant has various food cost, armor, and abilities. Prevent the bees from winning by putting ants on the tiles to attack the bees. You win if you eliminate all the bees, but if even one bee gets to your hive, you lose.

## Ants:

A HarvesterAnt is a type of Ant that adds one food to the colony total as its action.

A ThrowerAnt attacks the nearest bee to itself thats in the same lane as it.

A FireAnt has a special reduce armor method: when the FireAnt's armor reaches zero or lower, it will reduce the armor of all Bees in the same place as the FireAnt by its damage attribute.

The LongThrower can only throw at a Bee that is found after following at least 5 entrance transitions. So the LongThrower can't hit Bees that are in the same place as it or the first 4 Places in front of it. If there are two Bees, one too close to the LongThrower and the other within its range, the LongThrower should throw past the closer Bee, instead targeting the farther one, which is within its range.

The ShortThrower can only throw at a Bee that is found after following at most 3 entrance transitions. So the ShortThrower can only hit Bees in the same Place as it and 3 places in front of it.

The WallAnt does nothing each turn, but has a large armor value (4) instead of 1 like normal ants.

The NinjaAnt damages all Bees that pass by, but can never be stung. A NinjaAnt does not block the path of a Bee that flies by.

The ScubaThrower is a ThrowerAnt that can be placed in water.

HungryAnt will select a random Bee from its place and eat it whole. After eating a Bee, it must spend 3 turns digesting before eating again.

A BodyguardAnt differs from a normal ant because it is a container; it can contain another ant and protect it, all in one place. When a Bee stings the ant in a place where one ant contains another, only the container is damaged. The ant inside the container can still perform its original action. If the container perishes, the contained ant still remains in the place (and can then be damaged).

The BodyguardAnt provides great defense, but they say the best defense is a good offense. The TankAnt is a container that protects an ant in its place and also deals 1 damage to all bees in its place each turn.

The QueenAnt is a waterproof ScubaThrower that inspires her fellow ants through her bravery. The QueenAnt doubles the damage of all the ants behind her each time she performs an action. Once an ant's damage has been doubled, it is not doubled again for subsequent turns. If the queen ever has its armor reduced to 0, the bees win. The bees also still win if any bee reaches the end of a tunnel. There can be only one true queen. Any queen instantiated beyond the first one is an impostor, and should have its armor reduced to 0 upon taking its first action, without doubling any ant's damage or throwing anything. If an impostor dies, the game should still continue as normal. The true (first) queen cannot be removed. Attempts to remove the queen should have no effect.

SlowThrower applies a slow effect for 3 turns.

StunThrower applies a stun effect for 1 turn.

Technologies used: Python, Javascript, HTML