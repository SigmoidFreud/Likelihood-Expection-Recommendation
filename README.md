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
<li>Parish</li>
</ol>
