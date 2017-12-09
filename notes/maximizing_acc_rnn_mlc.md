### [Maximizing Subset Accuracy with Recurrent Neural Networks in Multi-label Classification][1]

**Authors**: Jinseok Nam, Eneldo Loza Mencía, Hyunwoo J. Kim, Johannes Fürnkranz

**Conference**: NIPS 2017

Proposed 3 RNN-based models: 2 with fixed input (avg word embeddings) and one Encoder/Decoder (aka seq2seq). Compared against each other and other baselines (BC/LP/PCC/FNN), finding unsurprisingly that seq2seq outperforms all of them in most metrics.

They reaffirm (as reported in [Vinyals et al., 2015][2]) that ordering of the output matters. _Very_ detailed experiments.

#### Key Points

* _Model 1_: Fixed input (avg of words embeddings), decoder predicts all labels (positive & negative).
* _Model 2_: Input same as Model 1, decoder only predicts positive labels.
* _Model 3_: Sequential encoder/decoder. **Outperforms all others** in most tasks.
* _Training time_: **seq2seq takes 5 days** to train on the big BioASQ, while FastXML does it in 4 hours.
* _Evaluation measures matter_: Depending on the dataset, some metrics stop making sense (e.g. ACC on BioASQ). Also know when to optimize for macro (i.e. rare labels) vs micro (i.e. frequent labels).
* _Order matters_: experiments show that order had often significant impact (sometimes > 3 points). Forcing rare labels first when decoding produce better macro results, and having 'taxonomies' (big priors) also help depending on the task.

#### Notes & Questions

* Compromise on training time vs precision, several tools (FastXML/fastText) get good numbers much faster.
* Word embeddings fixed at training time. Maybe simpler models (e.g. Models 2) could benefit, while avoiding the penalty of a full RNN encoder.
* Can we let the model decide on the order of the output?
* Might we worth checking out author's [NN for MLC survey][3].

#### Tags

* MLC
* RNN
* Reuters-21578
* RCV1-v2
* BioASQ

[1]: https://papers.nips.cc/paper/7125-maximizing-subset-accuracy-with-recurrent-neural-networks-in-multi-label-classification "Paper"
[2]: https://arxiv.org/abs/1511.06391 "Order Matters: Sequence to Sequence for sets"
[3]: https://arxiv.org/abs/1312.5419 "Large-scale Multi-label Text Classification - Revisiting Neural Networks"
