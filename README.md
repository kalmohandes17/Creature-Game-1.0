# Object-Project-1.0

Instructions

In this project, you will design a game where a human player acts as a predator, while various objects symbolize its prey. The primary objective for the player is to pursue, catch, and consume the prey, accumulating calories to stay alive and continue hunting. The player uses up calories with every move and will perish if the calorie count reaches zero.

We'll utilize the GameBoard class from the first project to depict the struggle for survival.

To make this work, you will develop a couple new classes:

The Creature class will represent individual prey moving across the board.
The CreatureList class will keep a record of all living creatures, and facilitate operations on them collectively.
The main() function, where most of the code is pre-written, manages user interactions and invokes methods (primarily on the creature list) to alter the simulation state as it evolves.
Steps to Complete

Part A

Examine main.cpp to familiarize yourself with the structure of the two upcoming classes and the controller code that will utilize their methods.
Declare the instance variables for Creature.
Create public getter methods and private setter methods for Creature.
Implement the body of the Creature methods, using the commentary in the source file as guidance.
For CreatureList, declare its sole instance variable: a vector holding pointers to Creature instances. This variable will not require getters or setters.
Develop the body of the CreatureList methods, referring to the annotations in the source file for direction.
Part B

Now we'll improve the simulation to incorporate a calorie mechanism for the creatures. Like the player, creatures will expend calories while moving. When the player eats a creature, the player will gain whatever calories the creature has at that moment. When creatures expend all of their calories, they will stop moving and regain calories as they rest.

To implement this, here's an approach you may use:

Add two integer instance variables to Creature: _calories (indicating current calorie count) and _initialCalories (storing the original value of _calories). Provide getters and setters for both.
Add a boolean instance variable in Creature named _resting with an initial value of false. Implement its getter and setter methods.
Modify the Creature constructor to initialize _calories using the final value from the input lines. Assign the same value to _initialCalories.
Implement a rest() method. While resting, the creature increases its calorie store by 5 calories for each turn it rests. Code the constant 5 as a const int at the top of the file, or as a static const int in the Creature class
The rest() method must also decide when a creature has recuperated sufficiently to resume movement. Write code to test whether the creature's calories exceed 75% of their initial value (this is why you recorded _initialCalories in the constructor).
Modify the takeTurn() method to either move or rest depending on whether it is resting.
Adapt the move() method to decrease calories by kPlayerCaloriesPerMove whenever the creature moves. If a creature's calories fall to zero or below, it needs to rest; so it must begin resting.
Improve the Creature's toString() method to include its calorie count in the output string.
Within the main loop, locate the line where a player consumes a creature. Previously, the player's calories increased by a constant named kCalorieGainPerMeal. Abandon this constant. Instead, the player should assimilate the calorie count of the creature they just ate.
