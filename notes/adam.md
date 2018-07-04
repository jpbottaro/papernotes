### [Adam: A method for stochastic optimization][1]

**Authors**: Diederik P. Kingma, Jimmy Ba

**Conference**: ICRL 2015

SGD is the leading optimization algorithm in the field. Many approaches try to
exploit the training history to speed up training (e.g. Momentum, AdaGrad,
RMSProp, etc.). ADAM's proposal is to combine the idea of Momentum and
RMSProp/AdaDelta into one, with a slight correction for the bias at the start of
the training due to lack of proper history.

The main idea is to update the parameters directly proportional to the the first
movement (mean of last gradients, i.e. Momentum), and inversely proportional to the
second movement (mean of the squared gradients, i.e. RMSProp/AdaDelta/AdaGrad).
This provides an adaptive rate per parameter, giving stronger updates to
sparsely modified parameters, and weaker updates to frequent ones.

#### Key Points

* The history of gradient updates provides insight into how each parameter behaves.
* Adapt future updates based on the past, e.g. Momentum to travel ravines.
* Higher learning rate for parameters updated infrequently.
* Mixture of Momentum & RMSProp, with bias correction to account for initialization
  (first/second movements start as 0).

#### Notes & Questions

* In my experiments, ADAM does provide much higher convergence speed. But
  sometimes plain ol' SGD manages to achieve better final results (at the
  expense of much slower convergence). This has been seen by others, e.g.
  [SWATS][2].
* How general are the default parameters? They seem to work well out of the box,
  but some tinkering does sometimes result in improvements (e.g. lower
  beta2).

#### Tags

* Optimization
* MNIST
* IMDb
* CIFAR-10

[1]: https://arxiv.org/abs/1412.6980 "Paper"
[2]: https://arxiv.org/abs/1712.07628 "Improving Generalization Performance by Switching from Adam to SGD"
