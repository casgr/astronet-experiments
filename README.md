# astronet-experiments
Experiments performed during the master thesis "Effects of Altering Input on a Convolutional Neural Network for Exoplanet Detection". All experiments are based on [Astronet](https://github.com/tensorflow/models/tree/master/research/astronet), and the accompanying [paper](http://iopscience.iop.org/article/10.3847/1538-3881/aa9e09/meta) by Chris Shallue and Andrew Vanderburg (2018). Users are able to replicate these experiments by following the original Astronet [tutorial](https://github.com/tensorflow/models/blob/master/research/astronet/astronet/README.md).

**Experiment 1 - **CNN With Added Local View****

The first experiment revolves around the addition of a new local view to the original CNN architecture. As illustrated in the figure below, the Neural Network is fed three lightcurve representations as input, being the original global view of length 2001, the initial local view with a width of 201, and a new local view of length 501. The latter focuses on the first part of the phase-folded lightcurve.

![EXP 1](https://i.postimg.cc/fTwR9FsR/newsit.jpg)

**Experiment 2 - ****CNN With Two Extra Local Views******

In contrast with the first experimental setup, the second experiment omits the local view used in the baseline architecture. Instead, two local views with a length of 1005 are used, in combination with the original global view. Each local view represents half of the phase-folded lightcurve as a more detailed representation.

![EXP 2](https://i.postimg.cc/SsrwFgvg/EXP2.png)

**Experiment 3 - ****CNN With Two Phase-Folded Representations******
The third experiment uses two global views with a width of 2001, and two local views of length 201 as CNN input. Each local and global view represents a phase-folded representation of half of the available Kepler data. Splitting the preprocessing over two halves of the dataset may preserve more subtle details in the data, that might have been lost in other experiments. This approach results in two sets of views which share the same general pattern, but differ in some specifics, as can be seen in the figure below.

![EXP 3](https://i.postimg.cc/MGYsvvmT/EXP3.png)

**Experiment 4 - ******CNN With Removal of Best-Fit Spline********

Furthermore, an experiment was performed to investigate the influence of the best-fit spline applied in Astronet, on the performance of the CNN. All conditions for this setup were equal to the baseline condition, with exception of the best-fit spline, which was removed altogether. This resulted in a global and local view, which contained representations that were closer to the original raw data.

**Experiment 5 - ********CNN With Gaussian Representation**********

Lastly, the final experiment applied one single input view containing a reduced representation of the phase-folded lightcurve, based on the application of a Gaussian pyramid. In the case of image processing, this results in smaller, blurred images which are reduced representations of the source image. The same technique can be applied to the preprocessed lightcurves, since these are represented by an one-dimensional grid of numerical values. The resulting input view has a width of 250, which is significantly smaller than the original global view.

![EXP 5](https://i.postimg.cc/XJmD0tgc/pasted-image-0.png)
