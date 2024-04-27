1. How do you handle corrupted or missing data in a dataset or imbalanced dataset?
   - What do you mean by `Corrupted` data, --> can we do an outlier detection to validate the Corrupted data or any heuristics/ rule based algorithms , 
   - To handle missing data points --> if the dataset is large enough dropping the rows can be an option, but if it is not then `Data Imputation/ Data Augmentation techniques` can be the way to go.
   - To handle Imbalanced Dataset -> #TODO 
1. Do you know what Spark is? Do you have any experience using it?
   - yes, a distributed data processing engine based on cluster model with multiple worker nodes and a driver node for each cluster. Spark allows parallel computing for data processing /  transformations
   - written in Java or Scala
   - Read up on Apache Parquet or columnar data storage formats
   - Read up on Ray or Dask ( Ray --> Personal Preference )
2. Understand about `Data models( Graph Data Model, Document/Non-relational Data Model, Relational Data Model)`  and `data formats` clearly.
3. Bias-Variance and it's tradeoff
4. Supervised Machine Learning vs Unsupervised with examples and what makes each algo supervised / unsupervised in nature ? --> Level Up -  Implementation using `Numpy and Python`
5. Performance Metrics, Confusion Matrix and when to use which one --> understand this with clarity
6. Probabilistic models in ML or let's say Supervised Learning ( Naive Bayes, Logistic Regression, Cross Entropy and other algorithms which leverage probability concepts)
7. Underfitting and Overfitting , ways to overcome them
8. Backpropagation and Gradient Descent
9. Pseudo code for Parallel Inference or Batch Processing or Parallel Implementation --> Give more details 
10. Building Data Pipelines, Data Engineering basics --> #TODO 
11. Data Normalisation and Data Standardisation
12. Ensemble Learning and why to choose it over classical individual ML models ?
13. List of Activation Functions and byte-sized explanation of each -> #TODO have to do this
    - [[Activation Functions]]

15. Dimensional Reduction --> Ways to achieve it
16. [[ML Observability and Explainability]]
17. Testing Data & ML Pipelines
    - [[Testing ML Pipelines]]
18. [[Linear Regression and Polynomial Regression Analysis]]
19. Design patterns for Data Science enthusiasts:
    - Factory Pattern : decouple data IO
    - Strategy Pattern : decouple algorithms
20. Understand in depth the following ML algorithms and get a hold of the industry accepted `keywords` :
    - Regression analysis algorithms : 
      1. Linear Regression - both simple and multi-variable
      2. Logistic Regression
      3. Polynomial Regression
      4. Ridge and Lasso Regression
      5. Elastic Net Regression
    - Clustering Algorithms : 
      1. K-means clustering
      2. Hierarchical clustering
      3. DBSCAN
	- Decision Trees
	  1. Random Forest
	  2. Decision tree
	- Dimension Reduction algorithms:
	  1. PCA
	  2. LDA
	- SVMs aka Support Vector Machines, RBFs ( Radial Basis Functions)
	- Ensemble Learning algorithms: include both `Bagging` and `Boosting`
	  1. XGBoost
	  2. LightGBM
	  3. CatBoost
	  4. AdaBoost
	- K-NN( k nearest neighbors)
	- Bayesian Optimisation Algorithms
21. Maths for Machine Learning
    - [Reference Blog for Guide](https://medium.com/enjoy-algorithm/detailed-maths-topics-in-machine-learning-ca55cd537709) #TODO  Try to complete 75% of whats there given in this article
    

- [[ML Hyperparameter Optimization]]
- [Deep Learning Course](http://www.cse.iitm.ac.in/~miteshk/CS7015_2018.html#quizzes)
- [Python Cheat Sheet](https://medium.com/@roelljr/ultimate-python-cheat-sheet-practical-python-for-everyday-tasks-c267c1394ee8)

> [!Follow the best practices while building ML models]
> - [ML Best Practices](https://scikit-learn.org/stable/common_pitfalls.html)
> - [Github Link 1](https://github.com/alirezadir/Machine-Learning-Interviews)
> - Use scikit-learn (  not pandas ) for Feature Engineering
> - Use stratified splits in classification tasks
>   - `X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.33, random_state=42, stratify=y)`
>- Speed up hyperparameter tuning with the n_jobs parameter
> 	 - `# grid search with all processors`
`GridSearchCV(estimator=SVC(),`
`param_grid={'C': [1, 10], 'kernel': ('linear', 'rbf')},`
`n_jobs=-1)`

https://freedium.cfd/https://towardsdatascience.com/7-scikit-learn-best-practices-for-data-scientists-f232a6ed2756





#### Focus Roadmap  

- ==Read CS229 Lecture Notes and Implement Assignments==
- ==Do some Hands-On in Machine Learning [ref 1](https://jakevdp.github.io/PythonDataScienceHandbook/)==
- ==Read Articles and try to stay up to date with current status quo in the domain of AI-ML==
- ==Complete proper NLP Course with notes and Hands-on==
- ==If Possible Do some open source contributions or build your own personal project and show case it via LinkedIn or Twitter==
- ==Try to complete this and note the major takeways : [`MiniTorch: A DIY Course on Machine Learning Engineering`](https://www.youtube.com/playlist?list=PLO45-80-XKkQyROXXpn4PfjF1J2tH46w8)==
- ==Understand and implement all architectures in Deep Learning and Classical ML and NLP==



### Annotated Data Science and ML Interviews:

**Amazon Data Scientist Mock Interview - AB Testing**
   - How do you measure the effectiveness of a recommendation system?
   - Suppose a new recommendation system is prepared, how would you know if this new version is better or should be used ?
   - can i use user's multiple search sessions to improve the recommendation system ? --> will it violate the assumptions for the AB test ?
   - how can I perform the AB test ?
   - design the architecture , p-test and t-test ? how will they fit together ?
   - how do you know or decide the statistical values ? ( power, alpha, sample size )
   - what if the new system is not effective ?



##### List of Companies Engineering Blogs to read
- [Doordash data science engineering](https://doordash.engineering/category/data-science-and-machine-learning/)
- [Airbnb AI Engineering Blog](https://medium.com/airbnb-engineering/ai/home)
- [Algolia](https://www.algolia.com/blog/ai/)
- [Amazon Science](https://www.amazon.science/blog?q=&f0=0000016e-2ff0-da81-a5ef-3ff057f10000&f0=0000016e-2ff1-d205-a5ef-aff9651e0000&f0=0000016e-2fb1-d205-a5ef-afb9d52c0000&f1=0000016e-4cbd-dae1-a36e-edfd29030000&f1=0000016e-39f9-d205-a5ef-bff9944b0000&f1=0000016e-4373-de2e-a76e-cff717cf0000&f1=0000016e-4373-d9b0-a7fe-f77ffa230000&f1=0000016e-4373-d9b0-a7fe-f77fb1890000&f1=0000016e-adb9-d30f-ad6e-adbbe5d10000&f1=0000016e-4cbb-d83c-a1ef-eebbe51b0000&f1=0000016e-4375-de2e-a76e-cff71bf60000&f1=0000016e-6174-d83c-a1ef-e7f423c50000&f1=00000171-3b46-d3a8-ab71-bfd7b3d00000&s=1&expandedFilters=Research%2520area%2CTag%2CConference%2CAuthor%2CDate%2C)
- [AWS](https://aws.amazon.com/blogs/machine-learning/)
- [Booking.com](https://blog.booking.com/#datascience)
- [Bumble](https://medium.com/bumble-tech/tagged/data-science)
- [Databricks](https://databricks.com/blog/category/engineering/data-science-machine-learning)
- [Dropbox](https://dropbox.tech/machine-learning)
- [Etsy](https://codeascraft.com/tag/machine-learning/)
- [Expedia](https://medium.com/expedia-group-tech/tagged/machine-learning)
- [Github](https://github.blog/?s=machine+learning)
- [Google](https://ai.googleblog.com/)
- [Grab](https://engineering.grab.com/categories/data-science/)
- [Grammarly](https://www.grammarly.com/blog/engineering/category/nlp-ml/)
- [Instacart](https://tech.instacart.com/tagged/machine-learning)
- [Instagram](https://instagram-engineering.com/tagged/machine-learning)
- [Intuit](https://quickbooks-engineering.intuit.com/tagged/machine-learning)
- [LinkedIn](https://engineering.linkedin.com/blog/topic/machine-learning)
- [Lyft](https://eng.lyft.com/tagged/data-science)
- [Meta (Facebook)](https://engineering.fb.com/category/ml-applications/)
- [Microsoft](https://medium.com/data-science-at-microsoft)
- [Netflix](https://netflixtechblog.com/tagged/machine-learning)
- [Nextdoor](https://engblog.nextdoor.com/tagged/machine-learning)
- [Nvidia](https://blogs.nvidia.com/blog/category/deep-learning/)
- [Paypal](https://medium.com/paypal-tech/tagged/machine-learning)
- [Pinterest](https://medium.com/pinterest-engineering/machine-learning/home)
- [Shopify](https://shopify.engineering/topics/data-science-engineering)
- [Slack](https://slack.engineering/tags/machine-learning/)
- [Soundcloud](https://developers.soundcloud.com/blog/category/machine%20learning)
- [Spotify](https://engineering.atspotify.com/category/maching-learning/)
- [Square](https://developer.squareup.com/blog/category/data-science/)
- [Stackoverflow](https://stackoverflow.blog/tag/machine-learning/)
- [Swiggy](https://bytes.swiggy.com/tagged/swiggy-data-science)
- [Toptal](https://www.toptal.com/developers/blog/tags/machinelearning)
- [Twilio](https://www.twilio.com/blog/search?q=machine+learning)
- [Twitter](https://blog.twitter.com/engineering/en_us/tags.eng--machine-learning)
- [Uber](https://eng.uber.com/category/articles/ai/)
- [Walmart](https://medium.com/walmartglobaltech/tagged/data-science)
- [Wayfair](https://www.aboutwayfair.com/careers/tech-blog?q=&s=0&f0=00000178-3b97-d9a4-a37a-fbf7441c0000&f0=0000017b-63b6-d47e-adff-f7bfd6ba0000&f0=00000178-3b97-d9a4-a37a-fbf744d20000&f0=00000178-3b97-d9a4-a37a-fbf7460c0001&f0=0000017b-63b7-dad3-a3fb-7fb7466f0000&f0=0000017a-ed9d-df9d-a17e-fdbf992a0000&f0=0000017b-63b5-d47e-adff-f7bda4220000)
- [Zalando](https://engineering.zalando.com/tags/machine-learning.html)
- [Zendesk](https://medium.com/zendesk-engineering/data/home)
- [Zillow](https://www.zillow.com/tech/ai-ml/)


##### Additional Ref:
- https://github.com/ashishtele/Quick-Notes-for-ML-DS/tree/main?tab=readme-ov-file
- https://www.holehouse.org/mlclass/
- https://aman.ai/
- https://colah.github.io/
- https://wandb.ai/fully-connected/blog/nlp?page=2
- ==**https://medium.com/bitgrit-data-science-publication/a-roadmap-to-learn-ai-in-2024-cc30c6aa6e16**==
- 