# Battle of the Boards - Board game rank classification 
John Naujoks - [Mando Iwanaga](https://github.com/mandoiwanaga)
***
[Complete testing and workflow (Jupyter Notebook)](https://github.com/jnawjux/mod3_project/blob/master/final.ipynb)

[Web Scraping & API call workflow (Jupyter Notebook)](https://github.com/jnawjux/mod3_project/blob/master/bgg_scrape.ipynb)

[Stakeholder Presentation (Google Slides)](https://docs.google.com/presentation/d/1gYG9376JoFvMicMIsHURCwtKGJCtEXhjXfAyygJ4iEo/edit?usp=sharing)

[Custom functions (Python)](https://github.com/jnawjux/mod3_project/blob/master/functions.py)

***
### Concept
There is an awesome and robust community online who regularly rates board games on BoardGameGeek.com. Using the ratings and game metadata found on the site, our goal was to see if we can create a classification model to determine whether based on each games features, we could determine whether it would rank in the top 25% of games.  Successfully creating such a model could be used to help designers and companies get a good understanding of any current trends in the style of games that are popular among board game enthusiasts, which in turn give a sense of how a new concept may perform.

### Data Source & Preparation
We used a mix of API calls and web scraping to derive our data from BoardGameGeek.com to obtain a dataset of all new games released in the past 4 years (2014-2018). We used the top 25% of this set of data as our target. The scores on the site can be quite strict (the highest ever by a game out of 10 being 8.5), so binary classification of the ratings made the most sense to help look for trends.  We factored in several features such as player count, weight (a reviewer given rating of complexity), themes, and game mechanic elements. 

### Modeling & Evaluation
We tried several classification models (Descision Trees, Random Forect, XGBoost, Logistic Regression) to find which worked best achieve a good score in our key metrics (focusing primarily on Log Loss and ROC AUC Score). The model we found that performed the best was a Gradient Boosting Classifier model, giving an ROC Score of .75.  We cross validated our model and performed hyperparameter tuning to help improve our score. 

### Insights
Through our research, the two things we found most influential to the success of a game were weight and mechanics.  Being a gathering for enthusiasts, more complex games were often given more favorable reviews.  Certain mechanics appeared to be favored as well, such as card drafting, cooperative play, and hidden traitor.  The theme seemed to have very little effect. The main takeaway from this experiment we found was that a game should provide a solid challenge and be able to accomodate a large group. 

