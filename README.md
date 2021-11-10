
# Sentiment Analysis over

  

## Abstract

Using natural language processing to express the sentiment of all quotes, our project aims to analyze the happiness level of the authors over a period of time. We will then observe how the years passing by affected different occupations, correlate how historical events changed the morale of workers in different fields or more generally, determine which profession makes people happier.

  

## Research Questions

- Which professions make the people the happier

- Correlate the positivity of different professions such as medical workers, finance workers, and climate activists with multiple history events such as the COVID19 pandemic, the subprime crisis, or global warming.

- In the case of quotes that are classified as neutral, how could we accentuate the positivity evaluation?

  

## Additional datasets

Because our model might classify more quotes as neutral than either clearly positive or negative, one way of accentuating the positivity classification of the authors would be, using either web scraping or the wikidata API.

We would like to also use 3 additional datasets: DATASET 1 2 3

## Methods

One of the possible methods would be to use in the first place the VADER (Valence Aware Dictionary and sEntiment Reasoner) program to obtain a first evaluation of all quotes, and in the case of unsatisfying results we could implement our own NLP model based on the BERT pipeline.

https://github.com/cjhutto/vaderSentiment

  

We will perform distributions test

  

## Timeline & Milestones

We decided to split the timeline into 3 sub-milestones.

- **25th of November**: The goal would be to have achieved sentiment analysis on all quotes, having a skeleton of the webpage presenting first visualizations results and have our datasets cleaned and analyzed. The notebook writing should be almost finished.

- **10th of December**: This is a milestone where our project should be almost completed. We should have a webpage with the wanted visualizations. The mathematical analysis should be completed. The notebook should also be finalized.

- **17th of December**: Final deadline milestone. We will need to finish the webpage, tweak the last visualizations, update and finalize the readme (add the collaboration of each member for example), complete the remaining details.

@startmermaid

sequenceDiagram

12.11 ->> 25.11: A1 : Create website skeleton

12.11 ->> 25.11: A2: Create first visualizations

12.11 ->> 25.11: A3: Complete the notebook

12.11 ->> 25.11: A4: Prepare & clean the datasets

  

25.11 ->> 10.12: A1 & A4: Complete the visualizations

25.11 ->> 10.12: and integrate them to the website

  

25.11 ->> 10.12: A2: Complete math analysis

25.11 ->> 10.12: A3: Finalize the notebook

  
  

10.12 ->> 17.12: A1 & A4: Finalize Webpage Visualisations

10.12 ->> 17.12: and details

10.12 ->> 17.12: A2: Complete Git Readme

10.12 ->> 17.12: A3: do smthing

  

 @endmermaid
  
  

## Questions

- Can we drop the probability column ?
