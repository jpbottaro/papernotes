### [Dynamic Routing Between Capsules][1]

**Authors**: Sara Sabour, Nicholas Frosst, Geoffrey E Hinton

**Conference**: NIPS 2017

Capsules are a new NN building block that try to create viewpoint-invariant
knowledge, overcoming the perceived blind spots in CNNs. They represent
instantiation parameters for a specific object (lines, curves, figures),
which get combine into higher-level capsules (houses, trees, roads). They do
away with max-pooling by introducing the concept of routing-by-agreement,
where higher-level capsules combine lower-level ones if their instantiation
all 'agree' with the higher-level object being represented (e.g. a 'tree'
capsule might search that there's a log below, and leaves above, and each
one with the appropriate scale).

#### Key Points

* Capsules represent instantiation of parameters as a vector (e.g. size,
  orientation, color, hue). The length of the vector represents the probability
  that the entity is present in the input.
* Higher-level capsules contain each coupling coefficients, or how much the
  attend to Low-level capsules.
* The routing algorithm learns the coupling coefficients (i.e. who should look
  at what below).
* Margin loss to account for multiple positive labels (digits for MNIST).
* Extra regularizing loss to encourage the output digit layer to encode
  instantiation parameters, by asking it to reconstruct the original image (i.e.
  like an autoencoder).
* Much better test error with a lot fewer parameters, compared with CNNs with
  similar computation cost. Generalizes better to unseen affine transformations
  of the test set (affNIST).
* Is able to decompose overlapping digits in their MultiMNIST model, better than
  previous approaches.
* Drawback is that "\[...\] \[Capsules\] like to account for everything in the
  image \[...\]", as seen in their CIFAR-10 tests, where they hypothesis that
  varied backgrounds trouble the model.


#### Notes & Questions

* Nice intro summary in [The Morning Paper][2], and [video explanation][3].
* Authors (likely championed by Hinton) like to make some interesting parallels
  with biology and other disciplines: the connection to how we do vision in
  humans, and how capsules can be viewed as 'inverting graphics rendering'.
* MultiMNIST results look great, but the dataset has some extra information
  that is tailored for their method, specifically the original overlapped
  images allow them to reuse the reconstruction regularization (since they had
  the original images).

#### Tags

* Capsules
* MNIST

[1]: https://arxiv.org/abs/1710.09829 "Paper"
[2]: https://blog.acolyer.org/2017/11/13/dynamic-routing-between-capsules/ "The Mortning Paper"
[3]: https://www.youtube.com/watch?v=pPN8d0E3900 "Capsule Networks"
