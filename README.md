# Bayesian optimization deep learning

***Objetive:***

This project is to classify if a person is wearing glasses or not using data contianing features, 
which were generated from a Generative Adversarial Neural Network (GAN). Here we used Bayesian optimization
to construct the architecture of Nentural Network (NN) and conduct paramter optimization of the NN.

***Bayesian optimization***

There are a lot of hyperparameters for machine learning models such as NN. Typically, random or grid search are effecient ways to conduct 
the optimization of models. They can be very time-consuming in some cases which waste time on unpromising areas of search space. Bayesian
optimization can overcome this problem by adopting an informed seach method in the space to find the optmized parameters.

Bayesian optimization works by constructing a posterior distribution of functions (gaussian process) that 
best describes the function you want to optimize. As the number of observations grows, the posterior distribution 
improves, and the algorithm becomes more certain of which  regions in parameter space are worth exploring and which are not. You can 
find more information and explination [here](https://github.com/fmfn/BayesianOptimization)

It's worthy to note that the Bayesian optimization is to find the maximum of a function. Thus, when we formulate a function and evaulation
metrics, we should take this part into consideration. For example, when we used log loss to evaluate our model performance, the smaller values
will be better. We should return a negative logloss to make it suitable for maximum of the defined function.

**Note:** It took a long time to run if you have a big dataset and wide boundary. You can refer to Colab for running the code.

***Data***

The data for this project can be downloaded from [Kaggle](https://www.kaggle.com/c/applications-of-deep-learningwustl-spring-2020)

Specificall, there are two data were used for this project:

 **(1)** training.csv, which include the 512 features one response variable glasses (1 represent have glass, 0 means no glasses).
 
 **(2)** submit.csv, which in fact is the test data which to measure how good of the model. (not really used in this project, but it's useful
 for the Kaggle practice)
 
 ***Method overview***
 
 (1) Data exploration
 
 (2) Check normality to see if we need to rescale the data
 
 (3) Define the NN model which can automatically generate optimal architecture of NN.
 
 (4) Define the loss function which we want to optimized, which can help determine the good hyperpameters.
 
 (5) Bayesian optimization and get the best model results.
 
 
 ***Reference***
 
 If you want to know about Bayesian optimziation. The follow sources can be helpful.
 
 Snoek, J., Larochelle, H., & Adams, R. P. (2012). [Practical bayesian optimization of machine learning algorithms](https://arxiv.org/pdf/1206.2944.pdf). In *Advances in neural information processing systems* (pp. 2951-2959).


* [bayesian-optimization](https://github.com/fmfn/BayesianOptimization)
* [Deep learning applications](https://github.com/jeffheaton/t81_558_deep_learning)
