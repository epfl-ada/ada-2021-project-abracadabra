

# The happiest jobs over time 

  

## Abstract

Using natural language processing to express the sentiment of all quotes, our project aims to analyze the happiness level of a subset of authors over a period of time. We will then focus on a specific set of authors that are working in a similar field, and try to observe how historical events/dates impacted the positivity levels expressed in their quotes.  Our project will help understanding how much a population has been impacted by some of the biggest catastrophe such as economics crisis or pandemics, as well as positive events like 

  

## Research Questions

- Is there a link between jobs mental state
- How does  the positivity of the speakers evoluate over a given period of time
- Can we correlate the positivity changes of different professions speakers such as medical workers, finance workers, and climate activists with multiple history events such as the COVID19 pandemic, the subprime crisis, or global warming.
- In the case of quotes that are classified as neutral, how could we accentuate the positivity evaluation.

  

## Additional datasets


We will use an additionnal dataset containing important dates and events that might have had effect on the morale of the speakers. Because we did not find so far a satisfying dataset, we decided to create it ourselve using web-scraping and make sure to enrich it manually if it is lacking data.  One possibility to obtain such a dataset could be by processing the headline of several newspaper over the wanted period of time, or scrape various websites that contains important events and dates.  



https://en.wikipedia.org/wiki/Timeline_of_the_21st_century
https://eu.usatoday.com/story/money/2020/09/06/the-worlds-most-important-event-every-year-since-1920/113604790/

## Methods
### Preprocessing
TODOTODOTODO


### Sentiment analysis
One of the possible methods would be to use in the first place the VADER (Valence Aware Dictionary and sEntiment Reasoner) program to obtain a first evaluation of all quotes, and in the case of unsatisfying results, for example in the case VADER classifies the majority of our quotes as neutral,  we could implement our own NLP model based on the BERT pipeline.


https://github.com/cjhutto/vaderSentiment

  

  

## Timeline & Milestones

We decided to arrange 2 minor milestones before the final deadline of the project.

- **25th of November**: The goal would be to have achieved sentiment analysis on all quotes, having a skeleton of the webpage presenting first visualizations results and have our datasets cleaned and analyzed. The notebook writing should be almost finished.

- **10th of December**: This is a milestone where our project should be almost completed. We should have a webpage with the wanted visualizations. The mathematical analysis should be completed. The notebook should also be finalized.

- **17th of December**: Final deadline milestone. We will need to finish the webpage, tweak the last visualizations details, update and finalize the readme (add the collaboration of each member for example), complete the webpage project description. Solve remaining problems. 

<div align="center">  
  
| |  25.11 | 10.12  |  17.12 |   
|---|---|---|---|
|  Maxime |  Create website skeleton | Complete the visualizations <br> and integrate them to the website| Complete math analysis  |
|  Loïc |  Create first visualizations| Complete the visualizations <br> and integrate them to the website|  Complete & finalize the readme |
| Jonathan  |   Prepare & clean the datasets |  Complete math analysis|  Finalize Webpage Visualisations <br> and details  |
| Xavier  | Complete the notebook  |  Finalize the notebook| Finalize Webpage Visualisations <br> and details |

</div>



  
  

## Questions

- Can we drop the probability column ?
