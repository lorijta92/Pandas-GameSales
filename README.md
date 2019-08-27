## Goal:
---
Analyze purchasing data of a fantasy game. Evaluate player demographics and purchasing patterns using Pandas and Jupyter Notebook.

## Process:
---
There were several individual steps to this analysis which are noted in the notebook itself. However, this analysis is broken up into three major parts: gender, age, and sales.

Before diving into the subsections, I first took an overview of the data, finding the total number of players who made purchases in the game by taking the length of unique screen names. I then performed basic calculations to find the total number of unique items, average purchase price, total number of purchases, and total revenue before storing all of that information into a data frame. 

#### Gender
I then moved onto analysis by gender.  I wanted to extract the percentage and count of players in each of the three gender groups, but because players can make multiple purchases, I first dropped any duplicate screennames, to have a list of unique players only. I then used `.value_counts()` on that data to get the count of players for each group and used those counts to determine the percentage split before formatting the data and storing it in a data frame. 

The next step was to find the purchase count, average purchase price, total purchase value, and average total purchase per person by gender. I used `.groupby()` to group by gender and stored that object as the variable, `gender_groups`. Then I used `.count()` on that variable to get the purchase count by gender, `.mean()` for the average purchase price, `.sum()` for the total purchase value, and `.sum()` divided by `unique_gender` for the average total purchase per person. All those values were then stored in a data frame and formatted.

#### Age
Next was to find all the same metrics but for each age group. Players were placed into one of eight different age bins by using `pd.cut()` and then the same techniques used for the gender analysis were applied to the age groups.

#### Sales
Finally, I analyzed general sales, finding the top spenders, most popular items, and most profitable items. To find the purchase count, average purchase price, and total purchase value for top spenders, I first grouped by screen names and used `.count()`, `.mean()`, and `.sum()` on the `Price` column of the groupby object, before storing the values in a data frame. The data frame was then sorted in descending order using `.sort_values(ascending=False)` so that the larger values would be at the top of the data frame. 

For the most popular items, I grouped by both `Item ID` and `Item Name`. To find the purchase count, I used `.count()`, for total purchase value, I used `.sum()`, and for item price, I used `.max()` so as to not distort the values in the column whilst also being able to view the values of the groupby object. These values were stored in a data frame and sorted in descending order.

The most profitable items were found by simply using the data frame from “most popular items” and sorting the `Total Purchase Value` column in descending order. 
