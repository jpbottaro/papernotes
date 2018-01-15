### [MinimalRNN: Towards More Interpretable and Trainable Recurrent Neural Networks][1]

**Authors**: Minmin Chen

Simple RNN architecture inspired by [Chaos Free Networks][2], with comparable performance
to current ones. Improves trainability with faster convergance, and interpretable internals.
Leaves the job of embedding the input to an generic encoder (FFN in the paper), and is
internally confined to said space. Achieves same performance as GRU/CFN with
a ~40%/20% reduction in training time respectively.

#### Key Points

* Inspired by CFN, forbids mixing of dimentions in the state.
* Single gate, weighted average of previous state and input.
* Jacobian's singular values close to 1, providing stable training.
* Very easy to interpret weights.
* Author suggests MinimalRNN could possibly capture longer range dependencies
  given how well-conditioned the Jacobians are. 

#### Notes & Questions

* It would seem both CFN and MinimalRNN loose expresability by doing away with
  mixing of dimentions their states.
* Only an internal dataset, so results aren't replicable. How well it does on
  public datasets (e.g. language modeling or NER).
* Since it reuses the latent space from the encoder instead of creating a new
  one, it seems it's left to the encoder to ensure it can be as expressive as
  other RNN architectures.

#### Tags

* RNN
* CFN
* MinimalRNN
* Internal Datasets

[1]: https://arxiv.org/abs/1711.06788 "Paper"
[2]: https://arxiv.org/abs/1612.06212 "A recurrent neural network without chaos"
