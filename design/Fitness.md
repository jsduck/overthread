# Main

## Grand total:
+ Calculated as the sum of all other individual fitness criterias, squished into a range from 0 to 1
+ Each other criteria will have an important level, which is used to adjust their value in contrast with the other coefficients
+ If the position in the game's story coefficient has an importance of 50%, it means it contribute to 50% of the grand total's values, lowering the other coefficients

## Averge party level:
+ Obtained as the real averege level between all 6 party pokemons
+ When the game starts, this fitness variable will be 0 until the the program obtains a starter pokemon
+ For each emtpy slot in the party, a -1 penalty will be aplied before the levels are "avereged"
+ After the starter is obtained, this value will be (6-5)/6 = 0.16, a -5 value is substracted as there are 5 empty party slots
+ Its role is to incentivise the AI to capture and level their party in order to reach higher fitness level

## Relative position in the game's story:
+ This is an arbitrary value given depending on how far has the AI reached in the game's main story
+ Certain positions in the map will be acting as checkpoints to increase the "story value"
+ When the game starts, this value will be 0 and will be periodically increased for each semi-major breakthrough the AI reaches when it comes to story
+ If the AI gets defeated and respawns, trainer battle or other events values will be substracted accordingly
+ Certain items will also contribute to this number, such as obtaining the bike/ferry pass, as they are required to progress in the story
+ The number will be tweaked such as it is always higher than any other fitness criteria, as main testing criteria is finishing the game's story

## Time spent on basic actions:
+ A primarily negative criteria to guide the AI when it gets stuck in certain parts in the game
+ It will generally also include repetead movement in a direction that is impossible to move in due to an obstacle

## Exploration coefficient:
+ A value that will tackle how much off-track actions the AI has done
+ This is a positive value that I hope will help with resolving issues such as roaming, gambgling, contests, and other activities

## Material ratio:
+ A ratio between how much cash to item value the AI has
+ It is supposed to be adapted dynamically depending on how the previous generation performed
+ When the AI obtains too much money but has too little items, and is progressing slowly or not at all, this will begin dropping indefinetly
+ There is a possibility of it reaching negative values, however this criteria isn't as important as the rest, so the coefficient will be rather small

# Combat
 
# 