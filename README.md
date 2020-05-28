<h1 align='center'> Generalised Interpretable Shapelets for Irregular Time Series<br>
    [<a href="https://arxiv.org/abs/TODO">arXiv</a>] </h1>

<p align="center">
<img align="middle" src="./paper/images/new_pendigits.png" width="666" />
</p>

A generalised approach to _the shapelet method_ used in time series classification, in which a time series is described by its similarity to each of a collection of 'shapelets'. Given lots of well-chosen shapelets, then you can now look at those similarities and conclude that "This time series is probably of class X, because it has a very high similarity to shapelet Y."

We extend the method by:
+ Extending to irregularly sampled, partially observed multivariate time series.
+ Differentiably optimising the shapelet lengths. (Previously a discrete parameter.)
+ Imposing interpretability via regularisation.
+ Introducing generalised discrepancy functions for domain adaptation.

This gives a way to classify time series, whilst being able to answer questions about why that classification was chosen, and even being able to give new insight into the data. (For example, we demonstrate the discovery of a kind of spectral gap in an audio classification problem.)

Despite the similar names, shapelets have nothing to do with wavelets.

----
## Library
We provide a PyTorch-compatible library for computing the generalised shapelet transform [here](./torchshapelets).

## Downloading the data
+ ``python get_data/uea.py``
+ ``python get_data/speech_commands.py``

## Reproducing experiments
In principle this can be done just via:
+ ``python experiments/uea.py``
+ ``python experiments/speech_commands.py``

However due to the high memory cost, we do not advise attempting this in one go and instead suggest using the scripts as a guide to understand how experiments are run, and only running a subset of experiments that are of most interest.

## Results
Accuracies on a collection of datasets:
<p align="center">
<img align="middle" src="./paper/images/results_table_full.png" width="666" />
</p>

The first 14 MFC coefficients for an audio recording from the Speech Commands dataset, along with the learnt shapelet, and the difference between them.:
<p align="center">
<img align="middle" src="./paper/images/new_speech_commands_heatmap.png" width="666" />
</p>

Interpreting why a class was chosen based on similarity to a shapelet:
<p align="center">
<img align="middle" src="./paper/images/new_pendigits.png" width="666" />
</p>

Using a pseudometric uncovers a spectral gap in an audio classification problem:
<p align="center">
<img align="middle" src="./paper/images/spectral.png" width="300" />
</p>

## Citation
