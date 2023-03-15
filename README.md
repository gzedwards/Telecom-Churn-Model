# Telecom-Churn-Model

**Author:** Grant Edwards

## Overview

Microsoft wants to launch a new streaming and movie division to compete within the theatric box office and home entertainment industry that has high potential to generate revenue but is a competitive industry. To support the launch, we have analyzed data from past movies to find the best genres Mystery and Horror, with high return on investments and low cost of production. May would be an ideal launch month as it historically has a lower number of releases and the highest ROI. We also found that James Wan, David F. Sandberg, and M. Night Shyamalan would all make great directors for our starting films with their experience and success in these genres.
***

## Business Problem

Microsoft wants to start a new streaming and movie division to compete with the likes of Netflix, Hulu, Amazon, Apple, and other major streaming services after seeing competitors’ various success in the field and it is good for large businesses to expand into a variety of industries as to have a more diverse portfolio. The theatric box office and home entertainment is a $100 billion dollar industry (variety, 2022). With a sector this large and with high potential return on investment, it would be a great opportunity for Microsoft to achieve an additional source of revenue for Microsoft, it will be another means to reach more potential customers for other sectors of the organization. 

To find where to start this new division we will be answering the following questions:


* What is the best genre of movie to start with?
* When would be the ideal release date?
* Who should be chosen as the director for the film?

To accomplish this, we will be using data from IMDB, Rotten Tomatoes, TheMovieDB and The Numbers.

Breaking into the theatric and home entertainment industry can be difficult with many big competitors already established and can have large cost of entry, with many films costing tens or even hundreds of millions of dollars to produce. The reason why we are focusing on these key points is that we can find the best genres to break into the industry without high costs of production, when to launch our program, so that we are not getting lost in a sea of compaction, and finding a director who has already found success in the genre and the industry to give us a solid backbone to get off to a good start. 
***

## Data

The data we will be using for this project comes from Box Office Mojo, IMDB, Rotten Tomatoes, TheMovieDB and The Numbers. It contains information on movies, such as: the key personal involved in producing the films, reviews, and financials.
The key factors that we will be using to find achieve our goals of best genre, time of release and ideal director will be the financials of the movies (global gross and production budget), the release month of films and how films perform in each month, and who directed the most successful films in the genre that has the most potential. This should leave s with a solid starting point to break into the cinematic industry. 

The most important data we will be looking it is the financials. Besides global gross and the production budget, we will look at profit (global gross – production budget) and the return of investment (ROI = (profit/production budget)*100). There are other factors that we will not be going into that are not factored into this (such as advertising and other expenses). 
***

## Methods

We started by prepaering the data, making sure everything is either a float or integer, and that categorical data (like area code) are seperated into dummy columns. We then isolated our dependant (or target) variable, churn, and created train and testing dataset split to build and test our models and normalized our independent variables. We used confusion matrix, a mean cross validation (5 variable models), and returned the precision, recall, accuracy and F1-score for our models to see how they performed. 

For our first model we tried building with simple linear regression. 

We then tried build a decission tree and optimizing the tree. 

We then used a K-Nearest Neighbor model, pipeline methods and ensemble methods such as bagging, random forests, grid searches, gradient boost, adaboost, and xgboost. 


***

## Results

We found that Mystery and Horror are both high ROI genres with low cost of production and would make ideal starting genres for a new movie to start this program.
![graph1](./images/genreROI.png)
![graph2](./images/genreBudget.png)
***
For the release month May had both the highest ROI of all months and a lower number of release dates making it an ideal launch Month.
![graph3](./images/monthROI.png)
![graph4](./images/MonthSum.png)
***
We also found that James Wan, David F. Sandberg, and M. Night Shyamalan would all make great directors for our starting films with their experience and success in these genres.
![graph5](./images/directorMystery.png)
![graph6](./images/directorHorror.png)
***
Questions to consider:
* How do you interpret the results?
* How confident are you that your results would generalize beyond the data you have?
***


## Conclusions

The best performing model that we found, with confirmation from the cross validation, was a gradient boost model. It had a mean cross validation score of 97.72%, a recall score of 86.67%, a precision score of 98.11%, accuracy at 97.84%, and a F1-score of 92.04%.
 
The model had a couple of false positives, but mostly there were 16 false negatives. These false negatives were customers that churned, however the model could not predict them doing so. This was the lowest we were able to get any model while sticking with a random seed of 11 and is likely due to factors outside of our dataset that caused the customer to churn. People can be tricky to get a prediction on and what will make them want to drop a company’s services. Being able to accurately predict churning customers 86.7% is a great model and we can be confident that most, if not all, customers that are predicted to churn, will churn. This can make a useful tool for the company to help keep customer retention higher, by trying to work with the predicted churning customers to find what we can do to keep their business.
 
Unfortunately we did miss some churning customers, even when we focused the model to try and recall as many churning customers as possible. This can be due to many factors and as stated above people can be tricky to predict. There are many factors that can affect people and factors outside of the dataset that could cause the decision to influence people to drop our services. To understand what caused them to leave, we could reach out and see what the cause of their departures were.
 
To improve the model further, there could be opportunities to run more grid searches over different parameters, and work with more complex ensembles. This overall is a strong model that should help in identifying almost all churning customers and give the company an opportunity to reach out through a customer retention program to help prevent the customer from churning. 
***

## For More Information

Please review our full analysis in [our Jupyter Notebook](./micro-movie-project.ipynb) or our [presentation](./micro_movie_presentation.pdf).

For any additional questions, please contact **Grant Edwards, grantedwards11@gmail.com**

## Repository Structure

Describe the structure of your repository and its contents, for example:

```
├── README.md                           <- The top-level README for reviewers of this project
├── micro-movie-project.ipynb           <- Narrative documentation of analysis in Jupyter notebook
├── micro_movie_presentation.pdf        <- PDF version of project presentation
├── data                                <- Both sourced externally and generated from code
└── images                              <- Both sourced externally and generated from code
```
