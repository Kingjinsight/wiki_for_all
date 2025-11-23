# SciKit Learn

It is an open source machine learning library that supports supervised and unsupervised learning. It also provides various tools for model fitting, data preprocessing, model selection, model evaluation, and many other utilities.

## Functions

### Models

- `sklearn.cluster.KMeans(n_cluster)
- `sklearn.neighbors.KNeighborsClassifier(n_neighbors,)


### Metrics

- `sklearn.metrics.pairwise_distances()`: Compute the distance matrix from a feature arary X and optional Y, by default "Euclidean distance".
- `sklearn.metrics.accuracy_score(y_true, y_pred)`: Accuracy classification score.

### Preprocessing

- `sklearn.preprocessing.StandardScalar()`: Standardize feature by removing the mean and scaling to unit variance
    - Usually we define a **scaler** as `sklearn.preprocessing.StandardScalar()`, because we hope to use the same scaler in both training data and test data
    - then we use `scaler.fit(data)` to calculate **mean** and **unit variance**, which will save in scaler
    - finally we transform our data by using `scaler.transform(data)`
    - you can also directly using `scaler.fit_transform(data)`

### Model selection

- `sklearn.model_selection.train_test_split(*arrays, train_size, test_size)`: Split arrays or matrices into random train and test subsets.
- `sklearn.model_selection.cross_val_score(estimator, X, y, cv, scoring="accuracy")`: Evaluate a score by cross-validation.
