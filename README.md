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

* The dashboard allows you to view the averages of xp per quest type for every level.
* Tableau link: https://public.tableau.com/app/profile/ryan.xiong/viz/NewWorldDSproject/Dashboard1?publish=yes
![Screenshot (20)](https://user-images.githubusercontent.com/91089401/144116126-4bdde6cc-cb85-4a71-99df-d07a97267f84.png)


* Outliers - main seems to have alot of quests that are within the top 2.5% (With the change of avg xp per quest type starting from 1850xp per quest versus without outliers dropping to 863xp per quest) Main quests seem to provide more value per quest.
* Looking at lower lvl quests (1-25) the main focus should be side and town quests
  *  When you become level 16 and above in the lower levels, your main focus should be main quests.
![Screenshot (25)](https://user-images.githubusercontent.com/91089401/144118172-415c4e62-b595-4b58-baa9-f9ef97a26041.png)
![Screenshot (24)](https://user-images.githubusercontent.com/91089401/144118215-fdc3369f-0d59-4598-8d0f-5e406317558b.png)

* Looking at the mid levels (26-45) the main focus should be on main quests. 
![Screenshot (27)](https://user-images.githubusercontent.com/91089401/144118269-339d80bd-1fd9-496d-9ddc-d42db327486b.png)
![Screenshot (26)](https://user-images.githubusercontent.com/91089401/144118303-17b0ad72-a230-4a84-a069-f92e29b6b4d0.png)

* Looking at high level quests (46-60) the main focus here is also the main quests.
![Screenshot (29)](https://user-images.githubusercontent.com/91089401/144118365-6e8995b8-f6c7-4e38-9fb3-118505a1d1d0.png)
![Screenshot (28)](https://user-images.githubusercontent.com/91089401/144118384-22018675-5000-4c62-b2c7-b479c82a5884.png)

## Conclusions 
* Main quests and Side quests are what a new player should focus on to level up the fastest.

## Further Analysis
* I would take a further look into the difficulty and the time it takes to complete a quest.
* This would give me a better understanding of which quests are the most efficient when trying to level up the fastest. 
  * *Gain the most experience (xp) per hour*.
* I would also take a look at leveling in crafting and refining skills as this is another type of leveling in the game. 
