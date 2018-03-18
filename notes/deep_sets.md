### [Deep Sets][1]

**Authors**: Manzil Zaheer, Satwik Kottur, Siamak Ravanbakhsh, Barnabas Poczos,
Ruslan Salakhutdinov, Alexander Smola

**Conference**: NIPS 2017

Authors investigate tasks and architectures where the inputs can be sets (that
is, the order should be irrelevant). They propose a fundamental architecture
whose properties they claim are both necessary and sufficient. It's also shown
how this applies to several tasks (set regression, set expantion, etc.), later
materialize it with NNs and apply it to several problems and datasets with
relative success.

#### Key Points

* Claim/Theorem: Any function S(X) is permutation invariant to elements of X _if
  and only if_ it can be decomposed into p(§x ¢(x)) (TODO write formula).
* DeepSet architecture using an NN for both p and ¢.
* Optional inclusion of context as a conditional of ¢.

#### Notes & Questions

* Got mixed feelings about the paper, it looks very rigorous and applies
  the method to several datasets and tasks. On the other hand, explanations
  for motivations and proofs weren't very easy to follow (a big part
  definitely due to my lack of depth in the field), specially in section 2
  (proof of universality and others).
* Interesting to revisit their claim that "parameter tying" is the only way
  to achieve order-invariant architectures.

#### Tags

* ESPGame
* IAPRTC
* Input Sets

[1]: https://arxiv.org/abs/1703.06114 "Paper"
