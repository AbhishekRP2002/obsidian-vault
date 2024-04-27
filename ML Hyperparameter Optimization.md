Hyperparams -->  non-learnable parameters, which cannot be estimated by the model itself while training 

- Optuna - Hyperparam Optimisation framework --> based on Bayesian Optimisation method with the following key features:
  1. Distributed Computing and scalable
  2. compatible with Tensorflow and PyTorch
- Hyperopt - Framework for HPO as well --> Tree of Parzen Estimators (TPE) used in this
  1. adaptive in nature
- Techniques for HPO:
  - Manual Setting of Hyperparams or rule based or heuristics
  - Grid Search CV (Cross validation with Grid search) :
    - For each iteration it performs the cross validation techniques the get the best model with the hyperparameter setting for that iteration. --> high time complexity, sequential execution, doesn't consider history into account
    - Implement in Python: 
      1. take an algorithm with finite number of hyper parameters
  - Random Search CV or Randomised Grid Search CV
  - Bayensian Optimisation
  - Gradient based optimisation 
  #TODO Learn more about each of them and try to implement from scratch if possible

 [Reference Article](https://medium.com/@deniz.kenan.kilic/changing-hyperparameters-in-machine-learning-models-101-d969f51fe414)
