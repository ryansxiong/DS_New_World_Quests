# New World Quests DS
Looking to see which quests a new player should focus on completing to level up the fastest. (Help the new player experience)

## Codes and Resources Used
* **Python Version**: 3.8
* **Packages**: Pandas, Numpy, Selenium, Seaborn, Matplotlib, OS
* **Visual Tools**: Seaborn, Pandas, Tableau
* **Source for Data**: https://nwdb.info/

## Data Collection
* Used selenium to webscrape data from https://nwdb.info/
* During the process, I noticed that the quest type was not defined in the data. I ended up adjusting the code to scrape the data separately for each type of quest (main, side, town, faction).

## Data Cleaning
After scraping the data, I cleaned the data for analysis. I made the following changes:

* Added 'type' column to each dataset to define the type of quest it was
* combined all datasets into one
* adjusted column names of 'level' and 'xp' (there was an extra space when searching the these columns)
* changed unrecognized symbols to value of 1 (these were not defined due to the row not having a level restriction)
* dropped NA values
* changed the value for when the level was shown as a range (only kept the minimum value to start the quest)
* changed the dtypes for the columns 'level' and 'xp' to integers
* separated levels into different sections (low [lvl 1-25], med [lvl 26-45], high [lvl 46-60])

## EDA
I analyzed the distributions of the data and the value counts of all the categorical variables to find if there were any trends. Below you will find the link to a dashboard that I created on tableau as well as some analysis on the data.

* https://public.tableau.com/app/profile/ryan.xiong/viz/NewWorldDSproject/Dashboard1?publish=yes
![Screenshot (20)](https://user-images.githubusercontent.com/91089401/144116126-4bdde6cc-cb85-4a71-99df-d07a97267f84.png)


* Outliers - main seems to have alot of quests that are within the top 2.5% (With the change of avg xp per quest type starting from 1850xp per quest versus without outliers dropping to 863xp per quest) Main quests seem to provide more value per quest.
* Looking at lower lvl quests (1-25) the main focus should be side and town quests
  *  When you become level 16 and above in the lower levels, your main focus should be main quests.
* Looking at the mid levels (26-45) the main focus should be on main quests. 
* Looking at high level quests (46-60) the main focus here is also the main quests.

## Conclusions 
* Main quests and Side quests give you the most xp
* I would suggest that new players focus on these types of quests to level up the fastest. 

## Further Analysis
* I would take a further look into the difficulty and the time it takes to complete a quest.
* This would give me a better understanding of which quests are the most efficient when trying to level up the fastest. 
  * *Gain the most experience (xp) per hour*.
* I would also take a look at leveling in crafting and refining skills as this is another type of leveling in the game. 
