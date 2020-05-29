## Project Data Mining - Tweet Sentiment Analysis

We were provided with ~30.000 tweets and called to do:<br>
<ul>
<li>Data Analysis
<li>Vectorization with Bag of words, Tf idf and Word embeddings
<li>Classification with SVM, KNN and Round Robin
</ul>
<br>

Vectorization + Classification method accuracies:<br>
<p align="center"><img src="/vectorization_scaling.png"></p>

### Vectorization

#### Word Embeddings:
* w2v+100 = word2vec with 100 features
* w2v+300 = word2vec with 300 features


We combined the word embeddings features with a variety of lexicas, appending in the end of each feature vector 6 extra features about the general sentiment of the word, resulting in a result of 306 features per tweet.<br>
The best combination of lexicas was using the:

1. **affin lexica**, which is the more general,
2. **tweet lexica**, specified on tweet language such as hashtags, emojis and tweet slang.
3. **generic lexica**.

With this combination we saw a futher increase of 4-5% overall.

### Classification

#### SVM:
As we see, with the word embeddings and SVC classifier, we achieved a percision of around 60%.
To get to that percision, we tested a lot of things.
The **highest accuracy** was achieved with input the lowercase tweets (with stop words and punctuation, emoticons).

Mostly we used clean stemmed tweets without stopwords and emojis in order
1. to have an even compare with the previous algorithms
2. to have a representative scaling on features

#### K-NN:
KNNs accuracy is lower than SVM, and that is due to the fact that KNN is a non-parametric and lazy learning algorithm.
A very important characteristic about KNN is the cursing of dimensionality.
The algorithm performs better with lesser features rather than a large amount. In order to have lot of features, you have to have a lot of data (which we do not have). So let's see how KNN performs with a small amount of features at word embeddings.

#### Round Robin:
Provided the best result out of 3, with the word embeddings.
Selected hyper parameters:
* n_neighbors = 50
* algorithm='auto'
* metric='minkowski'

### Conclusions:
We tested lot of other things that didn't work such as:

- Using stemmed tweets for training and input to w2v.
- Using extra features such as minimum and maximum valences.
- K least positive words and K most positive words.
- Computing the "derivative" of the function that was draw by the valence of every word in the tweet. It was a sum which was
  1. increased when the "current_valence greater than previous_valence" and
  2. decreased when "current_valence less than previous_valence".
- Applied L2 and L1 normalization.


### Collaborators
* [Aslanidis Theofanis](https://github.com/Fanarosss)
* [Athinaios Konstantinos](https://github.com/kostasA97)
