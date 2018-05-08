# Various Input layer info

## General
+ The network will recieve different input depending on what category of activity it is doing
+ Neuron inputs will be a real number varying from 0 to 1, this will also include a 'trigger' neuron for each category, signifying whether it is active or not
+ More in-depth matters such as typing for pokemons isn't percieved as input as it is not a 'direct' input in the sense that it is not percieved at first glance, instead it will be obtained from pokemons name and potential abilities used in the first layer

## Category 1 - World
+ Active when any sort of movement on the game map is expected
+ 

## Category 2 - Battle
+ Only active when the AI is either challening or being challenged to a pokemon battle
+ It is split into 4 subcategories, Enemy Data, AI Data, AI Party Data and AI Item Data

### Subcategory 1 - Enemy Data
+ Name + Gender
+ Estimate of enemy HP
+ Status
+ Level string
+ Remaining Enemies
+ Estimation of charges per moves USED left
+ Estimation of possible moves unused
+ Estimation of potential healing items left

### Subcategory 2 - AI Data
+ Name + Gender
+ Exact value of HP
+ Status
+ Level string
+ Experience
+ Exact number of remaining charges per move left

### Subcategory 3 - AI Party Data
+ Pokemon HP for party slot
+ Pokemon Name + Gender for each party slot

### Subcategory 4 - AI Item Data
+ Exact number of healing items left
+ Exact number of temporary enhancement items left
+ Exact number of status cancellation items left 

## Category 3 - Menu
+ Concerns itself with the menu items and their meaning

## Category 4 - Interaction
+ Activated when the AI is interacting with any kind of item/npc that is involved in an event or produces dialog