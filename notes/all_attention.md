### [Attention is all you need][1]

**Authors**: Ashish Vaswani, Noam Shazeer, Niki Parmar, Jakob Uszkoreit, Llion Jones, Aidan N. Gomez, Lukasz Kaiser, Illia Polosukhin

**Conference**: NIPS 2017

Authors propose an encoder-decoder architecture using stacked self-attention and point-wise,
fully connected layers for both the encoder and decoder. The introduce
"Multi-Head Attention", linearly projecting the values/keys/queries and having N
parallel attention heads per layer. They argue that this improves computation
time and extraction of long term dependencies vs RNN/CNN-based architectures. With
several tricks and a lot of experimentation, they manage to achieve new
state-of-the-art for MT with less than 1/4 of the training cost of previous
models.

#### Key Points

* Positional encoding to surface input sequence order to the model.
* Scaled Dot Product Attention, same as dot-product but with an extra scaling
  factor (supposedly to account for saturation of non-linearities).
* Multi-Head Attention linearly projects keys, values and queries, and has N
  parallel attention dot products.
* Encoder/Decoder both have a Multi-Head Attention layer, followed by a Feed
  Forward (both with residual connections and normalization).
* Output is feed with the same layer as above (masked to be auto-regressive).
* Motivation is speed/parallelization and reduction of path length for
  long-range dependencies.

#### Notes & Questions

* It seems to require a _lot_ of experimentation to get to the configuration
  they found optimal (scaling of the dot-product, 6 layers per encoder/decoder,
  normalization, 8 heads).
* While it's true the long-term dependencies can now be modeled in constant
  time, the input is being manually crammed into a fixed vector. This might
  be loosing important information, and could require tuning depending on the
  type/domain of the input (e.g. long text, char-based, etc.).
* Code [looks great](https://github.com/tensorflow/tensor2tensor).

#### Tags

* Attention
* MT
* WMT2014

[1]: https://arxiv.org/abs/1706.03762 "Paper"
