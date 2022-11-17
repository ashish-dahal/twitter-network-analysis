
**Table of Contents**

=====================
[Introduction	4](#_Toc86609321)

[Data Collection	4](#_Toc86609322)

[Data Pre-processing	4](#_Toc86609323)

[Exploratory Data Analysis (EDA)	5](#_Toc86609324)

[Natural Language Processing (NLP)	7](#_Toc86609325)

[Network Analysis	8](#_Toc86609326)

[Conclusion	11](#_Toc86609327)






















**Figures**


[Figure 1: Tweets count based on countries	5](#_Toc86609384)

[Figure 2: Tweet count based on country class	6](#_Toc86609385)

[Figure 3: Tweet count by year	6](#_Toc86609386)

[Figure 4: Tweet count by username	7](#_Toc86609387)

[Figure 5: Wordcloud for tweets from developing countries	7](#_Toc86609388)

[Figure 6: Wordcloud for tweets from developed countries	7](#_Toc86609389)

[Figure 7: Twitter reply network of developed nations	9](#_Toc86609390)

[Figure 8: Degree centrality of usernames in developed nations	10](#_Toc86609391)

[Figure 9: Twitter reply network of developing nations	10](#_Toc86609392)

[Figure 10: Degree centrality of usernames in developing nations	11](#_Toc86609393)









# **Introduction**
`	`Gender inequality and how women are discriminated against in society have long been major topics on social media. However, because societal structure, culture, literacy, and other factors differ significantly between developing and developed countries, it is critical to determine whether public opinion on gender disparity differs in these countries as well. As a result, in this project, twitter data will be analyzed to identify significant influencers who vocalize their ideas on gender inequality on Twitter, as well as to see if there are any meaningful differences in the gender inequality issues discussed in developed and developing countries.
# **Data Collection**
`	`A python library called snscrape was used to scrape the data from twitter. Tweets containing various hashtags such as 'heforshe', 'genderequality', 'empoweringwomen', 'womenempowerment', 'feminism' etc., were collected. There were 160,000 tweets collected from 2014 to 2021, 20,000 tweets for each year. The data was saved as a JSON file to make it easy to import into pandas library.
# **Data Pre-processing**
`	`The data was uploaded in the google drive as it was faster to access it from there via URL than uploading it manually. 

- **Data Aggregation:** For the pre-processing, the chunks of data files were imported and aggregated into a pandas dataframe. Then the required columns were extracted from the dataframe that would be used for the analysis. 
- **Columns Extraction:** The columns included twitter usernames, user verification status, country, language, usernames of replied users, hashtags used etc.
- **Tweet Filtration:** Likewise, for the simplicity, tweets having location information and English language content were extracted.
- **Data Cleaning:** Hashtags, user mentions and URL were removed from the tweet content to make it easier for analysis.
- **Country Classification:** For simplicity, countries having Human Development Index (HDI) above 0.8 is classified as developed and rest are classified as developing.
# **Exploratory Data Analysis (EDA)**
`	`For any data science project, it is necessary to get the feel of the data before jumping into the analysis. For EDA, various visualizations were made such as the number of tweets based on countries, number of tweets based on developing or underdeveloped, yearly tweet distribution, and tweets distribution based on usernames.

![](Aspose.Words.37d741da-428e-4c5d-b7f8-b7f1126404c2.009.png)

*Figure 1: Tweets count based on countries*

`	`Figure 1 shows the top countries based on tweet count. USA has the highest number of tweets on gender issues as we filtered the dataset based on English language.

![](Aspose.Words.37d741da-428e-4c5d-b7f8-b7f1126404c2.010.png)

*Figure 2: Tweet count based on country class*

`	`The dataset is imbalanced between tweets from developed and developing nations. Mainly because we filtered the dataset based on English language and most country speaking English happen to be developed.

![](Aspose.Words.37d741da-428e-4c5d-b7f8-b7f1126404c2.011.png)

*Figure 3: Tweet count by year*

`	`2016 had the highest number of English language tweets relating to gender issues followed by 2017 and 2015. 2021 had the lowest number of tweets in this regard.

![](Aspose.Words.37d741da-428e-4c5d-b7f8-b7f1126404c2.012.png)

*Figure 4: Tweet count by username*

`	`Figure 4 shows the top usernames respective to the tweet count. The hypothesis was that these accounts are the potential influencers in our dataset relating to gender debate.
# **Natural Language Processing (NLP)**
`	`For NLP, libraries such as nltk, contractions, regex, and wordcloud were used. Vectorization and Clustering using the sklearn library. The data was first cleaned using regex expressions and then was tokenized. Likewise, stopwords were removed from the tweet content which included custom stopwords. Also, word clouds were generated for tweet content from developed and developing countries.

*Figure 5: Wordcloud for tweets from developing countries*

*Figure 6: Wordcloud for tweets from developed countries*

![](Aspose.Words.37d741da-428e-4c5d-b7f8-b7f1126404c2.013.png)![](Aspose.Words.37d741da-428e-4c5d-b7f8-b7f1126404c2.014.png)![](Aspose.Words.37d741da-428e-4c5d-b7f8-b7f1126404c2.015.png)![](Aspose.Words.37d741da-428e-4c5d-b7f8-b7f1126404c2.016.png)






`	`As we can see, the discussions are mostly about feminism movement, gender issues regarding race, work etc. in the developed nations. In developing nations, feminism movement is also prominent but it has some discussion about even serious topics such as sexual violence and rape.

![](Aspose.Words.37d741da-428e-4c5d-b7f8-b7f1126404c2.017.png)	**Clustering:** K-means clustering was used to cluster the tweet content. After some inspection of the obtained clusters, it was determined that five clusters were adequate to represent the tweet content. The tweet content clusters were labeled as follows for developed and developing nations:

![](Aspose.Words.37d741da-428e-4c5d-b7f8-b7f1126404c2.018.png)






`	`As we can see, while there is an overlap between the topics discussed in developed and developing countries like 'feminist movement', developed countries are more focused on discourse regarding systemic gender inequality, public ignorance, politics and distinguishing feminism from other terms. However, the public discourse in developing countries center around gender violence. Also, there are significant tweets ridiculing the feminist movement in developing countries.
# **Network Analysis**
`	`For the network analysis, networkx library was used. A twitter reply network was created where the nodes were the usernames of the twitter users. For the edges, source node was defined by the user who is replying and target node was the user being replied to. 

Also, the size of the nodes was defined by the degree centrality of the nodes where centrality refers to the number of incoming link and outgoing link. Similarly, only those nodes were labeled that had degree greater than 2 to avoid clutter. Thus, a reply network was created for the developed and developing countries.  

![](Aspose.Words.37d741da-428e-4c5d-b7f8-b7f1126404c2.019.png)



















*Figure 7: Twitter reply network of developed nations*
![](Aspose.Words.37d741da-428e-4c5d-b7f8-b7f1126404c2.020.png)



![](Aspose.Words.37d741da-428e-4c5d-b7f8-b7f1126404c2.021.png)










*Figure 8: Degree centrality of usernames in developed nations*
![](Aspose.Words.37d741da-428e-4c5d-b7f8-b7f1126404c2.022.png)

*Figure 9: Twitter reply network of developing nations*

![](Aspose.Words.37d741da-428e-4c5d-b7f8-b7f1126404c2.023.png)![](Aspose.Words.37d741da-428e-4c5d-b7f8-b7f1126404c2.024.png)















*Figure 10: Degree centrality of usernames in developing nations*
![](Aspose.Words.37d741da-428e-4c5d-b7f8-b7f1126404c2.025.png)![](Aspose.Words.37d741da-428e-4c5d-b7f8-b7f1126404c2.026.png)













`	`As we can see in figure 7 and 8, like we hypothesized, the usernames 'marymargaretau1' and 'dubie1151' are the top influencers in the developed nations' dataset who are related to the gender issues. Unsurprisingly, Donald Trump ('realdonaldtrump') is also in the chart as has been involved in the gender controversies multiple times. Also, there are no verified accounts that are top influencers of gender debate in the developed nations.

`	`In the developing nations (figure 9 and 10), 'nilimajumder' and 'dakki\_16' are the top influencers of gender debate. However, we can see one verified account i.e., Rupa Subramanya (rupasubramanya) in the top influencers list.
# **Conclusion**
`	`The project overall was able to achieve its specified goal within a limited timeframe. However, various bottlenecks and challenges posed a problem in completing the project. Some of the challenges were:

- **Project topic determination**: Determining the project topic which would be achievable in the given timeframe and also finding out how the network library can be used in the project was a challenging task. The problem was solved by thoroughly learning about the networkx library before determining the project topic and determine the topic accordingly.
- **Scraping data**: Twitter API has many limitations so other libraries such as twint and snscrape were used. Also, there were limitations posed by the capabilities of the libraries. It was solved by modifying the project scope before sending the proposal.
12
