
# Sentiment Analysis over

  

## Abstract

Using natural language processing to express the sentiment of all quotes, our project aims to analyze the happiness level of a subset of authors over a period of time. We could focus on a specific set of authors that are working in a similar field. We will then observe how the years passing by affected these group of people and correlate how historical events changed the morale of those workers or more generally, determine which profession makes people happier.

  

## Research Questions

- Which professions make the people the happier
- See the evolution of the positivity of all speakers on a given period of time.
- Correlate the positivity of different professions such as medical workers, finance workers, and climate activists with multiple history events such as the COVID19 pandemic, the subprime crisis, or global warming.
- In the case of quotes that are classified as neutral, accentuate the positivity evaluation.

  

## Additional datasets

Because our model might classify more quotes as neutral than either clearly positive or negative, one way of accentuating the positivity classification of the authors would be, using either web scraping or the wikidata API.


We would like to also use 3 additional datasets: DATASET 1 2 3

## Methods

### Web scraping
Using the web-api we created a mapping between the occupations code and the english translation of the profession. 
### Sentiment analysis
One of the possible methods would be to use in the first place the VADER (Valence Aware Dictionary and sEntiment Reasoner) program to obtain a first evaluation of all quotes, and in the case of unsatisfying results we could implement our own NLP model based on the BERT pipeline.

https://github.com/cjhutto/vaderSentiment

  

We will perform distributions test

  

## Timeline & Milestones

We decided to split the timeline into 3 sub-milestones.

- **25th of November**: The goal would be to have achieved sentiment analysis on all quotes, having a skeleton of the webpage presenting first visualizations results and have our datasets cleaned and analyzed. The notebook writing should be almost finished.

- **10th of December**: This is a milestone where our project should be almost completed. We should have a webpage with the wanted visualizations. The mathematical analysis should be completed. The notebook should also be finalized.

- **17th of December**: Final deadline milestone. We will need to finish the webpage, tweak the last visualizations, update and finalize the readme (add the collaboration of each member for example), complete the remaining details.
- 
<div align="center">  
  
| |  25.11 | 10.12  |  17.12 |   
|---|---|---|---|
|  Maxime |  Create website skeleton | Complete the visualizations <br> and integrate them to the website| Complete math analysis  |
|  Loïc |  Create first visualizations| Complete the visualizations <br> and integrate them to the website|  Complete math analysis |
| Jonathan  |   Prepare & clean the datasets |  Complete math analysis|  Finalize Webpage Visualisations <br> and details  |
| Xavier  | Complete the notebook  |  Finalize the notebook| Finalize Webpage Visualisations <br> and details |

</div>



  
  

## Questions

- Can we drop the probability column ?
