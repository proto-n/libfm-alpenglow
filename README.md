# libfm-alpenglow

# This description is under construction

# Libfm evaluation with Alpenglow

[Alpenglow](https://github.com/rpalovics/Alpenglow) makes it possible to evaluate recommender models in an online setting. This repository contains an example of connecting Alpenglow's evaluation with [libfm](https://github.com/srendle/libfm). However, since libfm itself does not provide a training objective for ranking or top_k prediction, we use the fork [libfm with BPR](https://github.com/fabiopetroni/libfm_with_BPR) which extends libfm with the Bayesian Personalized Ranking objective, and is capable of generating top K lists.

## Implementation details

The simplest way of evaluating external batch models with Alpenglow is through the [ExternalModelExperiment](...) interface of Alpenglow's API. This experiment has two modes of operation -- one is "write", which writes the training data to disk, and the other is "read", which reads the predictions made by the external model and evaluates them.
