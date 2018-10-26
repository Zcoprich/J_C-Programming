# Sea Battle #

## What is Sea Battle? ##

Sea Battle is a project designed to create a simplistic, electronic version of the board game, Battleship. It is a C++ designed program; thus, it must be run through an integrated development environment (IDE) such as Dev-C++ (the IDE I used to run the program). It consists of two header files, two class files, and a main file which begins the entire program. 

Sea Battle is a two player game. This requires the users to run the Sea Battle program on two separate computers with the appropriate IDE installed. Sea Battles is played in the same manner as Battleships. The two players take turn guessing the location of the other’s ships. One player will call out a location on the computer-generated grid in which he or she plans to attack. The defending player will say ‘hit’ if the attack lands on one of his or her ships or ‘miss’. If the attack also sinks one of the defending player’s ships he or she will call out ‘sink’ instead of ‘hit’. The process of updating the grid will be discussed in the main file section. The game continues until one player loses all ships.

## Main.cpp File ##

The main file is the core of the Sea Battle project. The purpose of the main file is to connect the other four files with the content within itself in order to run the project. Many of the variables used as a base for the two class files are created in the main file. 

When the user begins the program, the main file prints out the word ‘Sea Battle!’ as a series of ‘\’ and ‘/’ on the screen. It will then have the computer ask the player whether he or she is player one or player two and which player is going first. Depending on the player’s choice will determine if the player begins with the attacking prompt or the defending prompt.

The program will then print two grids generated through the grid file. They are both ten by ten grids but only the primary grid has all ships randomly placed on the grid. Each ship is labeled by one letter. ‘A’ is the aircraft carrier, which takes up five spaces. ‘B’ is the battleship that takes up four spaces. ‘C’ are the cruisers and ‘S’ are the submarines, which both take up three spaces and consists of two ships. ‘P’ are the three patrol boats, each taking up two spaces. The parts of the grid not containing one of the ships will have a ‘-’ in its place. This represents the water. The tracking grid represents the other player’s grid, which is designed to hide the location of their ships from the user until he or she hits one. How the grid is designed will be further discussed in the grid file section.

With the players and grid set up, the game can begin. The attacking player will call out a space on the tracking grid as well as input the coordinates into the computer. The defending player will then determine whether the attack was a hit, a miss, or a sink. If the attack was a hit, the computer will replace the ship’s letter with an ‘X’ on the defending player’s grid. Otherwise, the computer will replace it with a ‘/’ to represent a miss. The defending player will then tell the attacking player if the attack was successful or not. The attacking player will then enter ‘H’ for hit, ‘M’ for miss, or ‘S’ for sink and the tracking grid will be updated accordingly. If ‘S’ is chosen, the computer will subtract one from the defending player’s ship total. Each player has nine ships. The players will then switch: the attacking player will defend and the defending player will attack. This continues until one player loses all ships. The program will then print out a statement based on whether the user was the winner or the loser and then request the user to exit the program.

## Grid.h and Util.h files ##
Unlike the other three files, the grid header file and the util header file consists of only the basics of a class file. They act as a basic outline for the grid file and the util file. The constructor and methods are originally defined here but are not fully developed. However, all methods and variables created in the header file must be implemented (though they do not have to be run in the program) in the appropriate class file. The other difference between the header file and its corresponding class file is that the header file has a ‘.h’ extension at the end of its name while the class file and main has a ‘.cpp’ extension added.

## Util.cpp ##
The util file is designed to execute the basic utility functions needed to run the program. The main focus of this class file is the `get_cell()` method. This method is used to read a cell, a space generated in grid, in order to determine its current value and, during the game, update its value. This is the method that replaces the ship’s letter or the ‘-’ with an ‘X’ or a ‘/’. If the user’s choice was out of the grid’s range, the computer will prompt the user to try again.

## Grid.cpp ##
The grid file’s purpose is to create the grid the players will use to play Sea Battle. Each grid is originally generated to consist of only ‘-’ within it. When the program runs the `deploy_fleet()` method, it will randomly place the grid in a manner in which all ships will fit within the boundary of the grid. Whether or not a ship is vertical or horizontal upon placement is also randomly determined. 

The `set(Cell c, char k)` method will assign a new value to a cell. 

The `get(Cell c)` method will return coordinates inputted by the user. 

The `print()` method displays the grid generated by the computer. As the players play Sea Battle, the grid will update and will display the update whenever the print method is called.

## Sea_Battle.dev ##
I have stated there are five important files that make up Sea Battle. However, I have provided six files in the repository. Due to the design of C++, the main function cannot immediately connect all other files in order to run Sea Battle. 
When creating a program that will consist of two or more class/header files, it is important to place them in a project file. Sea_Battle.dev is an example of a project file. Its main purpose is to link all five files together so that the program can run. It does not contain any code that directly affects how the program itself is ran. It is also often created by the computer when placing all the files into a project.
If the project will not run but all files needed have been tested to compile smoothly, it is best to create a new project in a C++ IDE and transfer all files to the new project. The previous project file may not have properly been created, leading to a linking error in the program.
