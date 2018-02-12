### [Topically Driven Neural Language Model][1]

**Authors**: Jey Han Lau, Timothy Baldwin, Trevor Cohn

**Conference**: ACL 2017

Authors propose to generate a document representation conditioned on some
predefined N latent topics. This representation is then used as part of a
tradition LSTM-based language model.

#### Key Points

* CNN to embed full document, used then to generate attention distribution over
  the N topics.
* Final doc embedding _s_ as weighted sum of topic embeddings (based on attention
  above).
* Fixed vector _s_ is fed at each step of the RNN doing the language modeling
  task.
* LM trained to predict next word, TM trained as auto-encoder (predict random
  word in the document).

#### Notes & Questions

* While the 'topic' semantic might help to explain the model and try to
  interpret it, the topic-modelling part looks like 2 regular linear projections
  (with a softmax instead of sigmoid as in FFNs). They could've tested it
  against a normal FFN, or without any layers at all (just the CNN doc
  embedding).
* I like the idea of 'regularizing' the embeddings via auto-encoders, also seen
  in [Capsule Networks][2] and many other ones before.


#### Tags

* Topic Modeling
* Language Modeling
* IMBD
* BNC
* APNEWS

[1]: https://arxiv.org/abs/1704.08012 "Paper"
[2]: ./capsule_networks.md "Paper"
