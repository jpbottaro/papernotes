### [Neural Speed Reading via Skim-RNN][1]

**Authors**: Minjoon Seo, Seowon Min, Ali Farhadi, Hannaneh Hajishirzi

**Conference**: ICLR 2018

Authors propose an optimization for RNNs inspired on speed reading. RNN has
big and small cells, and a classifier decides per-word which one to use. They
assert that it achieves similar performance on classification & QA tasks, and
has speed improvement on CPU.

#### Key Points

* On some tasks, most words are not important, learn what to skim.
* Can give _latency_ improvement.
* 2 cells, big and small, decide at each step which one to use (can be
  generalized to N cells).
* Gumbel-softmax to make differentiable, and loss penalization to encourage
  skimming.

#### Notes & Questions

* Interesting to see how they make the discrete decision (skim or not skim) to
  be differentiable via the Gumbel-softmax.
* Would it be applicable only in tasks where details are more important than
  general subject?

#### Tags

* RNN
* Text Classification
* Question Answering
* Rotten Tomatoes
* IMDb
* SQuAD
* CBT

[1]: https://arxiv.org/abs/1706.03762 "Paper"
