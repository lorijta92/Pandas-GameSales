#### Goal:
Analyze purchasing data of a fantasy game. Evaluate player demographics and purchasing patterns using Pandas and Jupyter Notebook.

#### Process:
There were several individual steps to this analysis which are noted in the notebook itself. However, this analysis is broken up into three major parts: gender, age, and sales.

Before diving into the subsections, I first took an overview of the data, finding the total number of players who made purchases in the game by taking the length of unique screen names. I then performed basic calculations to find the total number of unique items, average purchase price, total number of purchases, and total revenue before storing all of that information into a data frame. 

I then moved onto analysis by gender.  I wanted to extract the percentage and count of players in each of the three gender groups, but because players can make multiple purchases, I first dropped any duplicate screennames, to have a list of unique players only. I then used `.value_counts()` on that data to get the count of players for each group and used those counts to determine the percentage split before formatting the data and storing it in a data frame. 
