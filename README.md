

# Showing social sentiment and perceptions using quotes

  

## Abstract

Using natural language processing to express the sentiment of all quotes, our project focuses on analyzing the happiness level of a subset of authors over a period of time. We then dive on a specific set of speakers that are working in a similar field, and try to observe how historical events/dates impacted the positivity levels expressed in their quotes. We aim to help understand how much a population, a small crowd, or even an individual can be impacted by important events such an economic crisis, pandemics, as well as more light-hearted periods like Christmas or even to study how some domains or subjects such as ecology are percieved by the population across the years.

  

## Research Questions

- Is there a link between one's profession and their mental state (positivity, negativity) ?
- How does the sentiment of a speaker change over a given period of time ?
- Can we correlate the positivity changes of different speakers' professions such as medical workers, finance workers, and climate activists with multiple history events such as the COVID19 pandemic, the subprime crisis, or global warming ?
- In the case of quotes that are classified as neutral, how could we accentuate the positivity evaluation ?

  

## Additional datasets

We plan to use additional dataset containing important dates and events that might have had an effect on the moral of the speakers. Because we did not find so far a satisfying dataset, we think it could be possible to create it ourselves using web-scraping and make sure to enrich it manually if it is lacking data. One possibility to obtain such a dataset could be by processing the headline of several newspapers over the desired period of time, or scrape various websites that contain important events and dates.

https://en.wikipedia.org/wiki/Timeline_of_the_21st_century<br/>
https://eu.usatoday.com/story/money/2020/09/06/the-worlds-most-important-event-every-year-since-1920/113604790/

Also, it could help us to find a dataset that groups occupations and domains but we may need to create it ourselves. We explain this part more precisely in the next section.

## Methods

### Preprocessing
For the preprocessing, the first step was to choose which features to keep or drop from the quotes dataset.
Since our questions focus on 2 main aspects, occupations and dates, we process the quotes such that we only keep the date, numOccurences, qids, quotation, quoteID and the speaker.
The phase, probas and URL are not needed for our project and thus we decided to remove them.
You can find our detailed thoughts and explanations about why we keep or drop the features in the notebook.

From this, we add another layer of preprocessing. When we work with the professions, we need the speaker in order to retrieve its occupations. Thus, we also create another dataset containing only the quotes that have a speaker (i.e removing the ones that have speaker equal to None). The Quotebanks dataset is formed in a way such that the speaker is the one with the highest probability but it sometimes is the case that it didn not find any speaker related to a quote hence the highest probability is none. In those cases, there may be a probability that is is a real speaker who made the quote but as it is less sure than 50% than it is really him we decided to drop those values. We already have a lot of data and we do not want to risk adding wrong entries in it. EXPLAIN ??

We also had to link speakers to their occupations (not just QID from wikidata) and for this we used the speaker_attributes files as well as wikidata_labels_descriptions in order to create a dictionary of QIDS and jobs.

### Sentiment analysis
One of the possible methods would be to use in the first place the VADER (Valence Aware Dictionary and sEntiment Reasoner : https://github.com/cjhutto/vaderSentiment) program to obtain a first evaluation of all quotes, and in the case of unsatisfying results, for example in the case VADER classifies the majority of our quotes as neutral,  we could implement our own NLP model based on the BERT pipeline.

Due to the huge number of different occupations in the data, we have to find a way to group the jobs together. Again, we could use NLP to help us clustering the jobs based on their description, making it easier to group the quotes by the occupations of their speakers. We also have other ideas such as using the wikidata structure to use the superclass/supergroup of the professions instead of focusing on the detailed one given in the dataset initially. To assess the feasability of such a clustering we already experienced with kmeans and we have seen promising results, we should be able to find a good clustering with a more fine tune model.

  
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
- As we want to focus on different group of speaker like medical workers, finance workers or climat activist for example, shall we focus on just clustering those kind of group hence having a more query like approach in forming them. Or we try to do clustering on the whole dataset as mentioned before hence having a lot of cluster and maybe less precise ones.
