Thank you Kyle Wilson for the general outline of the lesson.

1. Download the [SPECTF Heart Data](https://archive.ics.uci.edu/dataset/96/spectf+heart)
2. Unzip the files and look for the `spectf.train` dataset.
3. Try looking at `spectf.train` in any text editor. Although it has a weird extension, it is just text.

In each row the first number is a `0` or `1` diagnosis code. The next 44 numbers are `[0-100]` continuous features computed from the image. We want to use the 44 features to build a logistic regression model to predict the diagnosis code.

4. write code that does the following:
* reads in `spectf.train`
* creates 2 numpy arrays called `X_train` and `y_train`
  * such that `y_train` is a 1-dimensional vector of `0`s and `1`s
  * such that `X_train` is a 2-dimensional matrices with 44 columns.
 
5. Run this code to check your work. This code will run silently if your data importing is correct. If there are errors, don't go on until you fix them!

`assert isinstance(X_train, np.ndarray)`

`assert isinstance(y_train, np.ndarray)`

`assert X_train.shape == (80, 44)`

`assert y_train.shape == (80,)`

6. Fit a Logistic Regression model. Consider checking the 
[docs](https://scikit-learn.org/stable/modules/generated/sklearn.linear_model.LogisticRegression.html).

* create an object of type `LogisticRegression`
* call the `model.fit()` function using the training data
* (you may need to increase the `max_iter` parameter to train your model.)

7. What are the model parameters?

8. Future work: how good is this model?



