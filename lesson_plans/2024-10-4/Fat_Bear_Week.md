# October 4, 2024
It's Fat Bear Week next week! In honor of Fat Bear Week, let's figure out which of my bear-like Pokemon is largest relative to its size. 

Some more background: 
* Pokemon Go recently added a minigame called showcases. In showcases, people enter Pokemon to a contest, and they are 
scored based on their weight, height and their individual values (IVs). The (simplified for this lesson) score assigned to the Pokemon is 
$$\text{Score} = 800 \times \text{StandardizedHeight} + 150 \times \text{StandardizedWeight} + 50 \times \text{NormalizedIVs}$$
  * IVs refer to the sum of the attack, defense, and hp of a Pokemon. Pokemon attack, defense and hp are random numbers between 0 and 15.
So, if the attack is 5, the defense is 7, and the hp is 15, then the total IVs are 27. The normalized IVs of this Pokemon would be 27/45 = 0.6.
    * We could also normalize attack, defense, and hp, then average the result to get the same value. In the example above, normalized attack is 5/15 = 0.3333,
normalized defense is 7/15= .4666, and normalized hp is 15/15=1. The average of .3333, .4666, and 1 is 0.6.
    * To get the normalized IVs, I want you to normalize the attack, defense and hp columns *first* using the techniques from the book. Then create a new column which is `NomalizedIVs` which is the mean
of the normalized stats.
  * To get the StandardizedHeight and StandardizedWeight, use the Pokemeans.csv file. There, I have the average height and average weight of each of the bear Pokemon.
   * Pokemon uses the convention that the standard deviation of the height of a Pokemon is the average height divided by 8. This same convention applies to weight.
   * You'll need to create new columns in the dataframe that give the average height, average weight, standard deviation of height, and standard deviation of weight in your main dataframe.

1. Download the Fat_Bear.csv and Pokemeans.csv files from Canvas (Files -> Data Sets -> October 4).
2. Upload both files to Google Colab.
4. Make a DataFrame that consists only of columns that will help you answer the question "which bear-like Pokemon is the highest-scoring?"
   * I have 60 bear-like Pokemon, but the dataset has 63 rows. There is a Bulbasaur that needs to be removed. Also, there must be duplicates. See if you can remove the duplicates and the Bulbasaur.
   * You'll need to extract the Pokemon name if there is a modifier. For example, "Snorlax Shadow" should really just be "Snorlax."
   * Pay attention to units. The height and weight are measured in different units than the average weight and average height.
5. Your final product should be a DataFrame with a score column. You should be able to tell me the highest-scoring Pokemon, and the lowest-scoring Pokemon.
