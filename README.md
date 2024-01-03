# wine-sentiment-analysis
A Sentiment Analysis using the "Wine Reviews" Kaggle dataset

Using the "Wine Reviews" Kaggle dataset, I wanted to do a sentiment analysis based on the descriptions of wines given by various sommeliers.
I used pandas, numpy, nltk, matplotlib, seaborn, scikit, and transformers to analyze, plot, and compare model outputs.
I first used the VADERS model provided in the nltk python library. I found a positive trend with positive sentiment analysis scores as
point scores increased and a negative trend with negative sentiment analysis scores as point scores increased, which would make sense
as wines with higher scores would have more positive descriptions. Unfortunately, VADERS lacks contextual understanding and nuance, so I made
use of a pretrained RoBERTa model from cardiffnlp. This gave as stronger trends of positive SA scores with increasing points and negative SA
scores with increasing points, showing us that the RoBERTa model seemed to have greater insight. I then compared the VADER results against
the RoBERTa results, and found that RoBERTa has more positive results than the VADERS model. I then performed a multiple linear regression on both VADER and 
RoBERTa negative, neutral, and positive SA scores against point scores, to see if there was any dependance between the descriptions and how the 
points were scored. There was weak evidence to support any such dependance, which leads me to believe that descriptions and points are just
two different ways to evaluate a wine. 

There were some pitfalls to this analysis. For the dataset, it only had wines that were scored 80 and above out of 100, so it's already wines that are
considered satisfactory to some degree (they all pass if it was an exam). We also don't have a clear system to see how the wines were scored, if
such a system does exist between sommeliers, so it's hard to know if the wines were graded on subjective or objective factors. On the data processing
side, the RoBERTa model was trained on tweets, which is generally a different vocabulary and subject matter than wine descriptions. Wine descriptions 
by sommeliers are infamously obtuse, which is why I believe we find such strong neutral scores in both models. VADERS is untrained and RoBERTa is trained on Tweets which tend to be more declaritive statements.
If there already exists such a model that is trained on
wine descriptions and/or reviews, that would be better to use to derive the level of nuance that exists within this environment. 

Overall, this was my first sentiment analysis and I had fun time playing with the data to see what I could find. I was able to learn a lot about the
importance of the data I'm working with and what outcome I'm trying to find from it. 
