### [A Literature Survey on Algorithms for Multi-label Learning][1]

**Authors**: Mohammad Sorower

Pre-NN craze survey (2010), presents common problem and algorithm transformations
for MLC (label powerset, binary relevance, SVM, etc.). Worth going back for the
evaluation metrics and datasets.

#### Key Points

* Problem Transformations: copy, select, ignore, label powerset(LP), binary
  relevance (BR), ranking by pairwise comparison (RPC), calibrated ranking
  (CLR).
* Algorithm adaptations: C4.5, tree bosting, lazy learning (kNN), BP-MLL
  (modified backprop for perceptrons), SVM, reduce dimentionality (MLSI/LDA),
  ensembles (RAkEL and random decision trees), generative models, PCC/EPCC.
* _Lots_ of eval metrics: example-based, label-based, ranking, hierarchical.
* Several datasets to use, where performance varies significantly depending on
  input type, # instances, # labels, cardinality, etc.

#### Notes & Questions

* Is anything applicable today? [This][2] shows that BR/LP/PCC all get beaten
  handidely by seq2seq, maybe some of the ranking ides in RPC or Hierarchical
  models can be embedded into EncDec models.
* Most datasets are small and don't cover today's text types (e.g. short-text
  tweets, blog posts, etc.). Investigate better datasets.
* Very little experimentation, would be interesting to have a showdown of
  current approaches on big datasets.

#### Tags

* MLC
* Survey

[1]: https://www.researchgate.net/publication/266888594_A_Literature_Survey_on_Algorithms_for_Multi-label_Learning "Paper"
[2]: https://papers.nips.cc/paper/7125-maximizing-subset-accuracy-with-recurrent-neural-networks-in-multi-label-classification "MLC via EncDec"
