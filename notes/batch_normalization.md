### [Batch Normalization: Accelerating Deep Network Training by Reducing Internal Covariate Shift][1]

**Authors**: Sergey Ioffe, Christian Szegedy

In NNs, the distribution of each internal layer's inputs changes during training, as
changes in the model's parameters naturally affect previous layers' activations, and
their distribution. Authors call this phenomenon "Internal Covariate Shift", and
propose normalizing said inputs at each layer as a solution. To achive this,
they introduce a new differentiable transformation (i.e. layer) that centers its
inputs and fixes variance to the unit. They apply some simplifications, like
normalizing activations independently and calculating mean/variance per mini-batch
instead of the whole dataset.

They adapt the layer to CNNs and ensure deterministic predictions inference time,
achieving stat-of-the-art performance on ImageNet in an order of magnitude less
training steps than a non-BN model, and surpass it handily with an ensemble.

#### Key Points

* Hypothesis is that Internal Covariate Shift slows down training, forcing low
  learning rates.
* Optimization (e.g. gradient decent) needs to know about normalization,
  or it would be ignoring transformations to the activations it uses to compute
  the gradient.
* Introduce normalization as a layer, whitening the input.
* Make estimations of mean/variance on mini-batches.
* Add subsequent linear transformation to keep expressive power.
* Apply before non-linearity. They conjecture that doing after the affine
  transformation `is more likely to have a symmetric, non-sparse distribution,
  that is "more Gaussian"`y to have a symmetric, non-sparse distribution, that
  is "more Gaussian"`.
* It enables much higher rates, due to avoiding amplification of inputs as they
  propagate, scaling of parameters, and (conjecture) making Jacobians have
  singular values close to 1.
* No need for Dropout, as BN works as a regularizer already, affecting the
  activations of each training example by those in its random mini-batch.

#### Notes & Questions

* This is a few years old, BN seems to be the standard for deep CNNs, what
  happened to RNNs?
* Has this been adapted to other networks? (e.g. Attention-based FFN,
  Capsules, etc.).
* Strange to see that higher learning rates can result in _slower_ convergence,
  but higher final accuracy.

#### Tags

* Normalization
* ImageNet
* CNN

[1]: https://arxiv.org/abs/1502.03167 "Paper"
