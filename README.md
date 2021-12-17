

# Studying social sentiments of people from different work fields over time using quotes

  

## Abstract

Using natural language processing to express the sentiment of quotes, our project aims to analyze the happiness level of authors over a period of time. We then dive on a specific set of speakers that are working in a similar field, and try to observe how historical events/dates impacted the positivity levels expressed in their quotes. Our idea is that it is possible to observe the impact of events over specific field. For exemple, pandemics (H1N1 and covid) would be expected to increase the negativity of the sentiment express by the medical workers, the subprimes crisis would negatively impact the economy or an ecological disaster like Fukushima should have a bad impact on the environmental group. Such examples are the ones we decided  to work with because they had a real public importance and have been at the center of many discussions.
  
## Research Questions

- How does the sentiment flucutate over the years, over a period of time ?
- Can we correlate the positivity changes of different speakers' professions such as medical workers, finance workers, and climate activists with multiple history events such as the COVID19 pandemic, the subprime crisis, or an environmental disaster ?
- Is there a link between one's profession and their mental state (positivity, negativity) ?

## Methods

### Preprocessing
For the preprocessing, the first step was to choose which features to keep or drop from the quotes dataset.
Since our questions focus on 2 main aspects, occupations and dates, we process the quotes such that we only keep the date, numOccurences, qids, quotation, quoteID and the speaker.
The phase, probas and URL are not needed for our project and thus we decided to remove them.
You can find our detailed thoughts and explanations about why we keep or drop the features in the notebook.

From this, we add another layer of preprocessing. When we work with the professions, we need the speaker in order to retrieve its occupations. Thus, we also create another dataset containing only the quotes that have a speaker (i.e removing the ones that have speaker equal to None). The Quotebanks dataset is formed in a way such that the speaker is the one with the highest probability but it sometimes is the case that it didn not find any speaker related to a quote hence the highest probability is none. In those cases, there may be a probability that is is a real speaker who made the quote but as it is less sure than 50% than it is really him we decided to drop those values. We already have a lot of data and we do not want to risk adding wrong entries in it.
We also had to link speakers to their occupations (not just QID from wikidata) and for this we used the speaker_attributes files as well as wikidata_labels_descriptions in order to create a dictionary of QIDS and jobs.

### Dates
The main Data exploration part started by working with the dates and gaining a better understanding of this feature of the project. Every manipulations are explained in this notebook : [here](./Time_Notebook.ipynb)

### Sentiment analysis
We used several Sentiment analysis models. The main one we ended up using was VADER (Valence Aware Dictionary and sEntiment Reasoner : https://github.com/cjhutto/vaderSentiment). After Testing other models (TextBlob, Bert https://huggingface.co/siebert/sentiment-roberta-large-english) and tried many combination of them, we decided to stick with VADER as it gave the best evaluations over many different quotes we tested. In order to improve the scores obtained, we performed another preprocessing, such as extanding the contractions, lowering the texts, removing the punctuation directly on the quotes. Each step is described in our notebook [here](./Sentiment_analysis.ipynb)

### Clustering
We use a TF IDX matrix vectorizer and then K-means for the clustering. This part was a big challenge in our project as it was a way harder task than expected, the professions are so diversified and the description being really general which makes it hard to find meaningful clusters. We were able to form some good ones and decided to then group all the clusters that didn't make sense into oa single one and then filter it using a list of words to make an economy and ecology cluster appear. Leaving a big part of professions in a trash cluster as they did not interest us for this project.
You can find all of our work in the following notebook : [here](./PreprocessingAndClustering.ipynb)

## Notebooks
- PreprocessingAndClustering.ipynb : The notebook containing the preprocessing and the clustering of speaker in their respetive field.
- Time_Notebook.ipynb : The notebook containing all the analysis of the quotes over the years.
- Sentiment analysis.ipynb : The notebook containing all the analysis done for the sentiment analysis.

## Data Story
You can find our Data Story [here](https://ada-abracadabra.github.io/DataStory/)

## Contribution
- Maxime : Sentiment analysis and visualization.
- Loïc : Data exploration and clustering the speaker.
- Jonathan : Data exploration and time analysis.
- Xavier : Sentiment analysis and Data Story.
  
## Timeline & Milestones

We decided to arrange 2 minor milestones before the final deadline of the project.

- **25th of November**: The goal was to have our first touch with the sentiment analysis on all quotes, a clean way to process the data, having a skeleton of the data story and having some basic visualizations.

- **10th of December**: Here, we expected the main parts of the project to be completed. The explorations and the methods we want to use should be working with a subset of the whole data we want to use for the final experiments. The notebook were finalized implying the sentiment anylsis model to be now defined and that we were able to get the first insights to answer our research questions.

- **17th of December**: Final deadline milestone. The data story had to be written and checked, we tweaked the last visualizations details, updated and finalized the readme, and focused on the last small things to polish.
