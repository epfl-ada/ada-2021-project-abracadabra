

# Studying social sentiments of people from different work fields over time using quotes

  

## Abstract

Using natural language processing to express the sentiment of all quotes, our project focuses on analyzing the happiness level of a subset of authors over a period of time. We then dive on a specific set of speakers that are working in a similar field, and try to observe how historical events/dates impacted the positivity levels expressed in their quotes. Indeed we would expect that some events will impact more strongly specific field than others. We could choose important event like pandemics (H1N1 and covid) which are expected to impact negatively the sentiment of the medical field, the subprimes crisis which would negatively impact the economy or an ecological disaster like Fukushima would have a bad impact on the environmental group. Those kind of event are chosen because they had a huge impact and have been in the center of many discussions.
  
## Research Questions

- Is there a link between one's profession and their mental state (positivity, negativity) ?
- How does the sentiment of a speaker change over a given period of time ?
- Can we correlate the positivity changes of different speakers' professions such as medical workers, finance workers, and climate activists with multiple history events such as the COVID19 pandemic, the subprime crisis, or environmental disaster ?
- In the case of quotes that are classified as neutral, how could we accentuate the positivity evaluation ?


## Methods

### Preprocessing
For the preprocessing, the first step was to choose which features to keep or drop from the quotes dataset.
Since our questions focus on 2 main aspects, occupations and dates, we process the quotes such that we only keep the date, numOccurences, qids, quotation, quoteID and the speaker.
The phase, probas and URL are not needed for our project and thus we decided to remove them.
You can find our detailed thoughts and explanations about why we keep or drop the features in the notebook.

From this, we add another layer of preprocessing. When we work with the professions, we need the speaker in order to retrieve its occupations. Thus, we also create another dataset containing only the quotes that have a speaker (i.e removing the ones that have speaker equal to None). The Quotebanks dataset is formed in a way such that the speaker is the one with the highest probability but it sometimes is the case that it didn not find any speaker related to a quote hence the highest probability is none. In those cases, there may be a probability that is is a real speaker who made the quote but as it is less sure than 50% than it is really him we decided to drop those values. We already have a lot of data and we do not want to risk adding wrong entries in it.
We also had to link speakers to their occupations (not just QID from wikidata) and for this we used the speaker_attributes files as well as wikidata_labels_descriptions in order to create a dictionary of QIDS and jobs.

### Sentiment analysis
One of the possible methods would be to use in the first place the VADER (Valence Aware Dictionary and sEntiment Reasoner : https://github.com/cjhutto/vaderSentiment) program to obtain a first evaluation of all quotes, and in the case of unsatisfying results, for example in the case VADER classifies the majority of our quotes as neutral,  we could implement our own NLP model based on the BERT pipeline.

Due to the huge number of different occupations in the data, we have to find a way to group the jobs together. Again, we could use NLP to help us clustering the jobs based on their description, making it easier to group the quotes by the occupations of their speakers. We also have other ideas such as using the wikidata structure to use the superclass/supergroup of the professions instead of focusing on the detailed one given in the dataset initially. To assess the feasability of such a clustering we already experienced with kmeans and we have seen promising results, we should be able to find a good clustering with a more fine tune model.

### Clustering
We use a TF IDX matrix vectorizer and then K-means for the clustering. Clustering was a big challenge in our project as it was a way harder task than expected, the proffesion are so diversified and the description are really general which makes it hard to form meaningful cluster. We were able to form some good cluster and decided to then group all the cluster that didn't make sens into one again and then filter it using a list of words to make an economy and ecology cluster appear. Leaving a big part of profession in a trash cluster as they did not interest us for this project.

## Notebook
- PreprocessingAndClustering.ipynb : The notebook containing the preprocessing and the clustering of speaker in their respetive field.
- Time_Notebook.ipynb : The notebook containing all the analysis of the quotes over the years.
- Sentiment analysis.ipynb : The notebook containing all the analysis done for the sentiment analysis.

## Contribution
- Maxime : Testing and computing the data for the sentiment analysis.
- Loïc : Data exploration and clustering the speaker.
- Jonathan : Data exploration and plotting the number of quotes over the year.
- Xavier : Coming up with the NLP method to use and plotting the sentiment analysis.
  
## Timeline & Milestones

We decided to arrange 2 minor milestones before the final deadline of the project.

- **25th of November**: The goal would be to have achieved and studied our first model for the sentiment analysis on all quotes, having a skeleton of the webpage presenting first visualizations results and have our datasets cleaned and analyzed.

- **10th of December**: This is a milestone where our project should be almost completed. We should have a webpage with the wanted visualizations. The notebook should be finalized, meaning that our sentiment analysis model has to be defined and that we are able to answer general concepts of our research questions.

- **17th of December**: Final deadline milestone. We will need to finish the webpage, tweak the last visualizations details, update and finalize the readme (add the collaboration of each member for example), complete the webpage project description. Solve remaining problems. 

<div align="center">  
  
| |  25.11 | 10.12  |  17.12 |   
|---|---|---|---|
|  Maxime |  Create website skeleton | Complete the visualizations <br> and integrate them to the website| Solve remaining problems |
|  Loïc |  Test on the clustering| Clustering done with the category needed |  Complete & finalize the readme |
| Jonathan  |   Prepare & clean the datasets |  Plot for the number of quotes over the years |  Finalize Webpage Visualisations <br> and details  |
| Xavier  | Test the different sentiment analysis methods |  Finalize the notebook and use of occupations | Finalize Webpage Visualisations <br> and details/descriptions |

</div>

