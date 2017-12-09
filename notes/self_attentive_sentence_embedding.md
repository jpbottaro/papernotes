### [A Structured Self-attentive Sentence Embedding][1]

**Authors**: Zhouhan Lin, Minwei Feng, Cicero Nogueira dos Santos, Mo Yu, Bing Xiang, Bowen Zhou, Yoshua Bengio

**Conference**: ICLR 2017 - [Open Review][2]

Authors introduce the idea of having N different embeddings for a sentence, each
one mapping to a different concept (N being a hyperparameter). Each embedding
is the weighted sum (i.e. attention) of the hidden representations of an RNN,
trained supervised on a specific task. They also introduce a simple regularizer
term that encourages diversity in the N embeddings.

#### Key Points

* Cramming all into 1 vector might be too limiting, extend to 2d.
* Having N embeddings can help relieve burden on LSTM to carry long-term
  dependencies.
* Enforce diversity in the embeddings with regularization.
* Interpretable output as heat maps over words (it's actually over the RNN
  embeddings).

#### Notes & Questions

* The attention mechanism doesn't seem to need an RNN, why didn't they try it
  with other models below (or even just plain ol' word embeddings)?
* How to set the new hyperparameter, if it could be a funciton of sentence
  length.
* Would be nice to see more experimentation vs other approaches.

#### Tags

* Representation Learning
* Sentence/Doc embeddings
* RNN
* Author Profiling
* Yelp (Sentiment Analysis)
* SNLI

[1]: https://arxiv.org/pdf/1703.03130 "Paper"
[2]: https://openreview.net/forum?id=BJC_jUqxe "Open Review"
