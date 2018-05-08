# Various Input layer info

## General
+ The network will recieve different input depending on what category of activity it is doing
+ Neuron inputs will be a real number varying from 0 to 1, this will also include a 'trigger' neuron for each category, signifying whether it is active or not
+ More in-depth matters such as typing for pokemons isn't percieved as input as it is not a 'direct' input in the sense that it is not percieved at first glance, instead it will be obtained from pokemons name and potential abilities used in the first layer
- Amount of neurons needed : 540

## Category 1 - World
+ Active when any sort of movement on the game map is expected
+ Orientation - 4 neuron
+ View matrix - 224 neurons : 1 for each tile
- Amount of neurons : 228

## Category 2 - Battle
+ Only active when the AI is either challening or being challenged to a pokemon battle
+ It is split into 4 subcategories, Enemy Data, AI Data, AI Party Data and AI Item Data
- Amount of neurons : 284

### Subcategory 1 - Enemy Data
+ Name + Gender                         - 30 neurons : 26 for letters, 1 for gender and 3 miscellaneous
+ Estimate of enemy HP                  - 1 neuron
+ Status                                - 1 neuron
+ Level string                          - 1 neuron
+ Remaining Enemies                     - 6 neurons  : 1 for each party memeber
+ Est. of charges per moves USED left   - 4 neurons  : 1 for each move 
+ Est. of possible moves unused         - 4 neurons  : 1 for each move
+ Est. of potential healing items left  - 10 neurons : reserved for further development
- Grand Total : 57 neurons

### Subcategory 2 - AI Data
+ Name + Gender                         - 30 neurons : 26 for letters, 1 for gender and 3 miscellaneous
+ Exact value of HP                     - 1 neuron
+ Status                                - 1 neuron
+ Level string                          - 1 neuron
+ Est. experience to lvl up             - 1 neuron
+ Exact number of charges per move left - 4 neurons : 1 for each move 
- Grand total : 38 neurons

### Subcategory 3 - AI Party Data - Also used outside of battles to view party pokemons in the Main Menu
+ Name + Gender for each party slot - 180 neurons : 30 neurons for each
+ HP for party slot                 - 6 neurons   : 1 for each 
+ Currently selected member         - 1 neuron
- Grand total : 187 neurons

### Subcategory 4 - AI Item Data
+ Exact number of healing items left                - 1 neuron
+ Exact number of temporary enhancement items left  - 1 neuron
+ Exact number of status cancellation items left    - 1 neuron
- Grand Total : 3 neurons  

## Category 3 - Menu
+ Concerns itself with the menu items and their meaning
+ For each possible 'menu' dialog a neuron is reserved :
    + Main Menu     - 4 neurons : 1 for each listing minus the save/option/exit choices
    + Battle Menu   - 8 neurons : 4 for the main battle menu, 4 for the possible move choices
    + Item Menu     - 3 neurons : 1 for each subcategory, 1 for items, 1 for keyitems and 1 for pokeballs
    + Selected Menu - 6 neurons : 2 for genenral interactions and 4 for maximum amount of extra variables
- Amount of neurons : 21

## Category 4 - Interaction
+ Activated when the AI is interacting with any kind of item/npc that is involved in an event or produces dialog
+ For the sake of simplicity, bike riding/running/swimming is considered an event
+ Movement State    - 1 neuron
+ Activity State    - 3 neuron : 1 for the current activity and 2 miscellaneous
- Amount of neurons : 4