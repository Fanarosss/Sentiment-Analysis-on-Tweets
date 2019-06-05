<h2>Project on Data Mining.</h2><br>

We were provided with ~30.000 tweets and called to do:<br>
<ul>
<li>Data Analysis
<li>Vectorization with Bag of words, Tf idf and Word embeddings
<li>Classification with SVM, KNN and Round Robin
</ul>
<br>

Vectorization + Classification method accuracies:<br>
<p align="center"><img src="/vectorization_scaling.png"></p>

<p>
w2v+100 means word2vec with 100 features and w2v+300 with 300 features (per word).<br>
Also for the accuracy we combined the word embeddings features with some lexicas in a result of 306 features <b>per tweet</b>
</p>
<br>
[ For the training of word embeddings we used gensim model as a neural network. ]
