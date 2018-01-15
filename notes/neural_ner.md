### [Neural Architectures for Named Entity Recognition][1]

**Authors**: Guillaume Lample, Miguel Ballesteros, Sandeep Subramanian, Kuzuya Kawakami, Chris Dyer

Authors do away with hand-crafted features for NER, which have dominated the
task since its creation. They propose 2 models, LSTM+CRF and LSTM-based
transition-based parser, and experiment successfuly with characted-level
features. They how state-of-the-art results for multiple languages in
CoNLL02/03, with LSTM+CRF coming on top.

#### Key Points

* *Model 1*: BiLSTM provide word-level independent scores, CRF on top
  modeling bigram interactions between outputs.
* Additional hidden layer before CRF improved results.
* Tagging scheme doesn't matter much (IOBES didn't improve results).
* *Model 2*: Stack-LSTM, a transition-based parser whose REDUCE
  operations output NER tags, and greedy decoding.
* Both models use an BiLSTM-based characted-lever encoder of words.
* Pretrained embeddings and dropout are essential.
* SGD+Clipping was slower but ultimately better than Adagrad, ADAM, etc.


#### Notes & Questions

* The main addition seems to be using the LSTM char-level encoder, but otherwise
  similar to previous models using CNNs for that.
* The CRF feels like a patch for limitations of modeling the problem as
  sequence tagging with independent. Modeling only bigram interactions might
  prove a limitation when tags are longer than a couple of words.
* Moving away from sequence tagging into Encoder/Decoder might be a good
  direction, as mentioned in the end ([Gillick et al][2]).

#### Tags

* NER
* RNN
* Transition-based parser
* CoNLL02
* CoNLL03

[1]: https://arxiv.org/abs/1603.01360 "Paper"
[2]: https://arxiv.org/abs/1512.00103 "Multilingual language processing from bytes"
