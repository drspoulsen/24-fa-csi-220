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

       assert isinstance(X_train, np.ndarray)
       assert isinstance(y_train, np.ndarray)
       assert X_train.shape == (80, 44)
       assert y_train.shape == (80,)`

8. Fit a Logistic Regression model. Consider checking the 
[docs](https://scikit-learn.org/stable/modules/generated/sklearn.linear_model.LogisticRegression.html).

* create an object of type `LogisticRegression`
* call the `model.fit()` function using the training data
* (you may need to increase the `max_iter` parameter to train your model.)

7. What are the model parameters?

8. Future work: how good is this model?

____

If you finish...

9. Also load in the `spectf.test` data as `X_test` and `y_test`

10. Write a function to evaluate your model. Be sure to compute all of these:
- precision on the training set
- recall on training set
- precision on the test set
- recall on the test set

I encourage you to use the existing libraries for 
[precision](https://scikit-learn.org/stable/modules/generated/sklearn.metrics.precision_score.html) 
and [recall](https://scikit-learn.org/stable/modules/generated/sklearn.metrics.recall_score.html#sklearn.metrics.recall_score).

11. You can also make a confusion matrix for your model on the test and training data.

12. Finally, experiment with the weighting factor

Background:

Logistic regression models have an important parameter called `class_weight`. 

**Theory:** Consider the following: 
- Many machine learning datasets are unbalanced. There are more examples of one type of answer than another.
- When the dataset is unbalanced the model will learn to be better at recognizing the bigger class.
- There's a tradeoff: there will be less accuracy for the other classes.
- Sometimes we want to prioritize one class over the others.

**Code:** set the class weight with a dictionary, like this:
`model = LogisticRegression(
    class_weight={0: 1, 1:10}
)`
This example makes class `1` ten times as important as class `0`.

Notice that although there's two weight numbers, the only thing that matters is
the ratio between them.

**TODO:** Run some experiments. How does performance change with different `class_weight` values? Describe your impressions here.

**TODO:** make a graph of precision and recall as a function of `class_weight`. 
Look below for some hints for making graphs. (The plot will be a little noisy. That's okay. The range of values is your choice.)

### Hints about making graphs:

Here's how to make simple graphs using `pyplot`. My example uses junk data for lists `x`, `y1`, and `y2`. If you use your own lists you should be able to tweak this example code from there.

    import matplotlib.pyplot as plt

    x = [1, 4, 7, 10, 15]
    y1 = [-12, 6, 10, 9, 2]
    y2 = [4, 8, 15, 3, -4]
    fig = plt.figure(figsize=(6, 4)) # plot size, in inches
    plt.plot(x, y1, '-k', label='y1') # - for lines, k for black
    plt.plot(x, y2, '-b', label='y2') # - for lines, b for blue
    plt.xlabel('x axis')
    plt.ylabel('y axis')
    plt.legend();
