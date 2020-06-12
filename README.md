# Venmo Text Analytics
Text Analytics on Venmo Transactions Data

<img src="https://digital.hbs.edu/platform-digit/wp-content/uploads/sites/2/2020/02/Venmo-1.png" height="300px">

#### Data

The data contains more than 7 millions transactions on Venmo.


#### Step 1: Classify Transactions

We first utilized the emojis package to convert emojis to text. Then we preprocessed the transaction description data by first removing the punctuations and stopwords, then tokenizing and lemmatizing the text data. After preprocessing the text data, we used the text dictionary provided to classify the transactions.

#### Step 2: Exploractory Data Analysis

Insights:
- 21% of transactions are emoji only
- the top 5 most popular emoji: '💸', '🍕', '🍻', '🎉', '🍷'
- the top three most popular emoji categories are Food, People, Activity

#### Step 3: Create Static User Spending Behavior Profile

For each user, create a variable to indicate their spending behavior profile. For example, if a user has made 10 transactions, where 5 of them are food and the other 5 are activity, then the user’s spending profile will be 50% food and 50% activity.

We first reshaped the data by combining the transactions of user1 and user2. As we assumed that the transactions that can't be classified by the dictionary would not be considered in the spending behavior, we then calculated the static spending behavior profile for each user.  

#### Step 4: Create Dynamic User Spending Behavior Profile

Explore how a user’s spending profile is evolving over her lifetime in Venmo. First of all, you need to analyze a user’s transactions in monthly intervals, starting from 0 (indicating their first transaction only) up to 12. For each time point, you need to compute the average and standard deviation of each spending category across all users.

We first filtered the transactions that exceed the 12th time points for each user. Then we calculated the dynamic spending behavior profile for each user at each time point.  

We then computed the average and standard deviation of each spending category across all users, at each time point, and plotted the average and average2 * standard deviation area. From the plot, we can see that most of the average spendings stabilized after customers’ first life point.

