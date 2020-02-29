# Problem Statement

The purpose of this project is to identify Lepton Flavor Violations (LFVs).  A LFV is a transition in the [lepton space](https://en.wikipedia.org/wiki/Subatomic_particle#/media/File:Standard_Model_of_Elementary_Particles.svg) that does not conserve the Lepton number (a quantum property of lepton types).  This is significant because such a change would indicate a _violation_ of the Standard Model of physics.  The data is from the LHCb (Large Hadron Collider-beauty) experiment at CERN.  Being able to detect such events using machine learning is critical because of what they suggest and because a ML method can process exponentially more data and much faster than a scientist could.

-------

# Executive Summary

This data is from the [Flavors of Physics](https://www.kaggle.com/c/flavours-of-physics-kernels-only/overview) Kaggle Competition.

As a group, we are are interested in physics and especially the exotic objects, especially the various fields of quantum dynamics and the cutting-edge experimentation being done at CERN.  When we saw this, we knew we had to attempt it.

The data were assembled from a database so it was very clean: no missing data or anything looked wrong to us.  The only real cleaning we did was to shorten or reformat the column names.  The data was difficult when visualizing because there are roughly 50 features in the set including the target.  Apart from the target, which is binary, all of the features contain numeric data.  The large number of features made it difficult to satisfactorily visualize the data because we would have ended up with more than 100 charts, which is not ideal: we chose to use violin plots because they visualize the distribution of the data over a box plot.  When visualizing the data we noted that the target is the majority of the data, which we have not encountered before and is unusual because the description of the data suggested this phenomenon is rare.  This is a concern because it suggests that the data may have been altered to have a good balance of classes.

When we were planning our feature engineering, we realized that they are no exceedingly strong correlations amongst features so we changed our focus to reduction of dimensionality.  Since there are so many features, we figured that exposing the models to all features in the data would significantly increase the variance in the models.  To that end we decided to use this project to compare the performance of models with data subject to Principal Component Analysis (PCA) and the raw data.

We chose to use a total of five classification models composed of three types: distance-based, tree-based, and boosted logistic regression models.  Each of the five models algorithms produced two models: one based on the original data and one based on the data put through PCA.  Comparing models was based on two sets of evaluators: a confusion matrix and a set of four classification metrics.  The best model was chosen on a combination of the two but also by comparing the PCA and original data.  Once we had chosen our best model, we plotted a ROC curve and visualized the metric scores.

-------

# Conclusions & Recommendations

After tuning and evaluating each model, we were able to determine that our best model is an XGBoost classifier with the original data.  This was surprising to us because we had believed that PCA would improve our models' performance.

It was difficult choosing our best model because, while our best model had better test scores, our second best model was much less overfit.  Due to the potential significance of the results, we felt it was best for us to choose our highest performing model.  Overall our model scores were very high, especially our AUROC and Matthews Correlation Coefficient , 0.88 and 0.76, both of which indicate a model with high performance.  Additionally, we had minimal numbers of false positives and negatives.

While we are confident with our model's performance, we believe there is still room for significant improvement.  Going forward, we would like to experiment with feature engineering and further tune the model.  That being said, time is a limiting factor: the XGBoost algorithm is not the fastest and can take a very long time when grid-searching.

-------

# Next Steps

-------

# Links

- The Google Slides presentation can be found [here]().
