
# RPG BATTLE ARENA

Welcome to the RPG BATTLE ARENA project! This Python script generates random health stats for warriors using a dice roll mechanic.

## Overview

The Character Stats Generator allows users to name three warriors and roll dice to determine their health stats. The game uses dice rolls to simulate randomness, adding an element of chance to the characters' health.

## Features

- User input for naming three warriors.
- Customizable dice sides for rolling.
- Random health stat generation based on dice rolls.
- Option to create new sets of warriors with different health stats.

## Installation

To run the Character Stats Generator, follow these steps:

1. **Clone the repository:**
   ```bash
   git clone https://github.com/Danilo-Mugnaini/rpg_battle_arena.git
   cd rpg_battle_arena
   ```

2. **(Optional) Create and activate a virtual environment:**
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows use `venv\Scripts\activate`
   ```

3. **Run the script:**
   ```bash
   python main.py
   ```

## Usage

1. Create two warrios, player 1 and 2.
2. The program will roll the dice and create random stats for each warrior.
3. Fight for your life in the battle arena!

## Mechanics

### Damage Calculation Explanation

In RPG Battle Arena, damage calculation is a critical component that determines the outcome of attacks between characters. Here's a detailed breakdown of how damage is calculated in the game:

#### 1. **Initial Parameters**

- **Attacker's Strength**: The base strength stat of the attacking character.
- **Attacker's Mana**: The mana stat of the attacking character, which can enhance damage.
- **Defender's Mana**: The mana stat of the defending character, affecting the attacker's mana boost.
- **Dice Roll**: A random roll between 1 and 20 that adds variability to the damage output.
- **Class Effectiveness**: Certain classes have a damage multiplier against other classes based on the Super Effectiveness Cycle.

#### 2. **Mana Boost Calculation**

The mana boost increases the damage based on the difference in mana between the attacker and defender:

\[ \text{Mana Boost} = 1 + \left(\frac{\text{Attacker's Mana} - \text{Defender's Mana}}{\max(\text{Defender's Mana}, 1)}\right) \]

- The boost is capped at a maximum of 20% (0.2).
- The boost only applies if the attacker's mana is greater than the defender's.

#### 3. **Class Effectiveness Multiplier**

An additional multiplier is applied if the attacker's class is more effective against the defender's class, based on a predefined cycle (HUMAN > ELF > WIZARD > ORC > HUMAN):

- If the attacker has a class advantage, a 10% (1.10) multiplier is applied.
- If not, the multiplier remains 1.0.

#### 4. **Base Damage Calculation**

The base damage is determined by combining the attacker's strength, the mana boost, and the effectiveness multiplier:

\[ \text{Base Damage} = \text{Attacker's Strength} \times \text{Mana Boost} \times \text{Effectiveness Multiplier} \]

#### 5. **Final Damage Calculation**

The final damage considers the dice roll and base damage, with additional chances for critical hits or misses:

\[ \text{Final Damage} = \left(\text{Dice Roll} + \text{Base Damage}\right) / 2 \]

- **Miss Chance**: There's a 10% chance that an attack will miss, resulting in zero damage.
- **Critical Hit Chance**: There's a 5% chance of landing a critical hit, increasing the damage by 50%.

#### 6. **Random Number Generation (RNG) Features**

RNG plays a crucial role in the dynamic nature of battles, introducing an element of unpredictability and excitement:

- **Dice Rolls**: At the start of each round, players roll a 20-sided die to determine the sequence of actions and modify damage calculations.
- **Miss Chance**: RNG determines whether an attack will miss, with a 10% chance for any given attack to deal zero damage.
- **Critical Hits**: A 5% chance is implemented using RNG, where an attack can deal 50% more damage, making critical hits a game-changing factor.
- **Healing Amount**: When a player chooses to heal, the amount restored is also determined by RNG, with a range typically between 5 and 15 health points.

#### **Example Calculation**

For instance, if a Human character attacks an Elf with a strength of 15, a mana of 10, and a dice roll of 12:

1. **Mana Boost**: If the Elf's mana is 5, the boost would be:

\[ \text{Mana Boost} = 1 + \left(\frac{10 - 5}{5}\right) = 1 + 1 = 2.0 \]

2. **Effectiveness Multiplier**: Human is effective against Elf, so:

\[ \text{Effectiveness Multiplier} = 1.10 \]

3. **Base Damage**:

\[ \text{Base Damage} = 15 \times 2.0 \times 1.10 = 33.0 \]

4. **Final Damage**:

\[ \text{Final Damage} = \left(12 + 33.0\right) / 2 = 22.5 \]

Thus, the Human character deals 22.5 damage to the Elf.

This comprehensive damage calculation system ensures that each battle is dynamic, strategic, and fair, incorporating various gameplay elements, character stats, and the exciting unpredictability of RNG.



## Contributing

If you would like to contribute to this project, please fork the repository and submit a pull request with your changes.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Contact

For any questions or feedback, please contact [Danilo-Mugnaini](https://github.com/Danilo-Mugniani).
