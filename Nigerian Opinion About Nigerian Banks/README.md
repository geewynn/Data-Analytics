# Sentimenst About Nigerian Banks

Whats do Nigerians on Twitter feel about their banks? Particularly the top banks. This question brought the curiousity that 
lead to this carrying out this project.


## Data Collection

- For this project I decided to deal with data from twitter(Nigeria Twitter).
- I used a scraper from this [repo](https://github.com/marquisvictor/Optimized-Modified-GetOldTweets3-OMGOT) which allowed me to get tweets.without being limited to
 the 30 days only option.
- I queried twitter by specifying the bank name in the query. For example "gtbank", access bank"
- I also set my location to Nigeria, so that twitter would return only the tweets with locations set to Nigeria.
- Example of one of the queries
  
  ``` python3 GetOldTweets3.py --querysearch "union bank" --near "Nigeria" --within 500km --maxtweets 2000 --output unionbank.csv ```
  
- I had to specify the number of tweets to get for each query and save the gotten tweets to a file. 
- Only about 3 search queries returned the 2000 tweets searched. This happened maybe because the other banks don't have much users on twitter or users did not specify their locations.

## Data Cleaning

- I had seperate csv file mainly because I saved each tweet query to a seperate file. So I had to concatenate each file to get one single file.
- On basic analysis, I found out that there where a lot of missing value on the text column. I dropped those.
- Also noticed that I had a lot of tweets that where just people giving out their account details for giveaways.
    - For tweet in this category, I dropped them because they just contained account numbers and bank name and will not add any sentiment to my model.
- Tweets containing hashtags where another form of giveaways and as all of those tweets contained mainly hashtags to trend a product or service. I had to drop them too.
- Removed all non letter characters form the texts
- Converted the tweets to lower case.
- Created a word count column to return each tweet word count. 
- Dropped each tweet with less than 10 word counts. They just contained the bank name.

## Tweet Sentiment
- For the actual sentiment analysis, I used [Textblob](https://textblob.readthedocs.io/en/dev/), A text processing library that gives a polarity score to each tweet.
- Textblob returns a score as seen in the table below.


    | Value | Score |
    |-------|-------|
    | 0     | neutral |
    | positive value{+) | Positive |
    | negative value(-) | Negative |
    
 ## Analysis
 ### Access Bank
 From the smaple of tweets used
 
 - Access bank had more positive tweets. More customers tweeted positive things about the bank and their services.
    - 52% Positive tweets.
    - 25& Neutral and,
    - 22% Negative Tweets.
    
    ![access](https://github.com/geewynn/Data-Analytics/blob/master/Nigerian%20Opinion%20About%20Nigerian%20Banks/images/access_count.png)
    
- The wordcloud for access bank shows access bank as the most frequent word, with other words such as account, money, transfer etc.
- Suprisingly, we can see other bank names here. This means other banks where mentioned more frequently in the tweets.

  ![access](https://github.com/geewynn/Data-Analytics/blob/master/Nigerian%20Opinion%20About%20Nigerian%20Banks/images/acc_word.png)
  
  
### Gauranty Trust Bank (GTBank)
- GTbank had more Neutral tweets from the sample of tweeter tweets. More tweets had no standing and could not be differantiated as positvie or negative.
 - 50% of tweets are neutral
 - 33% of tweets are positive
 - 17% of tweets are negative.
 
 
   ![gtbank](https://github.com/geewynn/Data-Analytics/blob/master/Nigerian%20Opinion%20About%20Nigerian%20Banks/images/gt_count.png)
 
 
- From the word cloud, we can see that gtbank and gtbank help where more frequent followed by words such as bank, need, money, please etc.

![gtb](https://github.com/geewynn/Data-Analytics/blob/master/Nigerian%20Opinion%20About%20Nigerian%20Banks/images/gt_word.png)

### Zenith Bank
- From the plots we see that we also had more neutral or non-diffrentiable tweets here.
 - 51% of the tweets where neutral.
 - 37% of tweets where positive.
 - 13% of the tweets are negative.
 
 
   ![zen](https://github.com/geewynn/Data-Analytics/blob/master/Nigerian%20Opinion%20About%20Nigerian%20Banks/images/zenit_count.png)
 
 
_ The word cloud shows zenith bank as the most frequent and it is accompanied by words like account, bank account, money etc.

   ![zenith](https://github.com/geewynn/Data-Analytics/blob/master/Nigerian%20Opinion%20About%20Nigerian%20Banks/images/zenith_word.png)

### United Bank of Africa

- Here we have more neutral tweets also.
 - 68% neutral tweets.
 - 29% positive tweets.
 - 1% negayive tweets.
 
   ![uba](https://github.com/geewynn/Data-Analytics/blob/master/Nigerian%20Opinion%20About%20Nigerian%20Banks/images/uba%20count.png)

- Looking at the word cloud, we see that uba bank is also the most frequent word.
   ![uba](https://github.com/geewynn/Data-Analytics/blob/master/Nigerian%20Opinion%20About%20Nigerian%20Banks/images/uba_word.png)
   

### First Bank of Nigeria
- Clearly we had more positive words almost a large percentage of tweets where positive.
  - 92% of the tweets where positive.
  - 4% where neutral.
  - 4% where negative.
  
  ![first](https://github.com/geewynn/Data-Analytics/blob/master/Nigerian%20Opinion%20About%20Nigerian%20Banks/images/first_count.png)
  
- From the word cloud we see words like strategic plan, pledges, support etc.
  ![fb](https://github.com/geewynn/Data-Analytics/blob/master/Nigerian%20Opinion%20About%20Nigerian%20Banks/images/first_word.png)
