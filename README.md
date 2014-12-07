Likelihood-Expection-Recommendation
==================================

I am attempting to write a recommender using the yelp academic dataset given a userid by analyzing a user's reviews and attempt to guess with maximum likelihood what  a user will like (i.e a small list of restaurants)

Research Ideology
==================================
My idea in a nutshell is to turn a decent size set of reviews into a corpus and establish semantic similarity between the words in the corpus in order to recommend food based venues taking into consideration other factors.

Algorithmic Methodology
==================================
My approach to this problem has the following subprocesses.
<ol>
<li>Filter the Yelp Academic Dataset to yield only food based venues</li>
<li>Using the [gensim](http://radimrehurek.com/gensim/) library, I attempt to establish contextual similarity between words through sentence vector comparisons. The model looks at the context in each word is mentioned an establishes similarity based on the surrounding words. You can read about it greater detail on [word2vec](http://radimrehurek.com/2013/09/deep-learning-with-word2vec-and-gensim/)  It is a great tool to build vectorization models using a new data set of text</li>
<li>The next step is to do entity extraction on each review to find out what each user is talking about in the review itself. There is a great paper on this describing it [here](http://ov-research.uwaterloo.ca/papers/Vechtomova_JASIST2013.pdf). I chose a more cut and dry approach and used an established grammar for extracting noun phrases used [here](http://textblob.readthedocs.org/en/latest/_modules/textblob/en/np_extractors.html) </li>
<li>After extracting noun phrases, I sought to look for an unsupervised or weakly supervised sentiment algorithm that uses probabilistic phrases with regard to entities within each text block to determine sentiment. A fairly useful algorithm was developed by [nik0spapp](https://github.com/nik0spapp/unsupervised_sentiment). I plan on using this to identify which sentences the entities in step 2 were extracted from and doing a sentence level disambiguated subjective analysis will give me a better idea of how the user actually felt about the entity in question</li>
<li>For the recommendation part, I plan on looking at the extracted entities of a user determine the sentiment associated with each enitity, and if the sentiment meets a certain threshold, then I will use the [word2vec](http://radimrehurek.com/2013/09/deep-learning-with-word2vec-and-gensim/) model to determine other entities in the corpus with contextual similarity and recommend a small list restaurants that meet a certain sentiment requirement from other users</li>
</ol>
