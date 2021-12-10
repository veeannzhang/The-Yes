Q1: Why are you designing the solution in this way?

    Basic idea: label the first 200 data manually by looking at the images and its description, then apply transfer learning to train on these 200 data, and make predictions on the other 800 products.

    The reason behind it is because we do not have ground truths for any of the data point, and the total amount of data is very little. Therefore, we need to label some of the data in order for our model to learn.


Q2: What are the aspects that you considered when designing?

    - Image may contain multiple products
    - Description solely might not be able to tell what product it is describing
    - Total amount of data is very small - only 1000 products and 200 training data, need to do data augmentation
    - Pre-trained nets are very large, need to do regularization(dropout) and k-fold cross-validation to overcome overfitting problem.



Q3: What are the cases your solution covers, how are they covered and why are they important?

    My solution covers some categories based on the keywords that I found in the description. For example, if a product has "heel", "heels" in the description, I am very sure it belongs to "SHOE" category. These keyword rule-based classifications are quite accurate in my opinion.


Q4: What are the cases your solution does not cover and what are the ways you can extend your current solution for them?

    My solution might not work very well with images with mixed products. E.g. A full dressed up lady with a handbag and the description is inferring the bag. For those images, we need information from description for us to make the judgment.


    If I have more time, I would like to train text classification models on the descriptions and make predictions based on that as well such that I can have some more information of the product. I will based on the probability of the text prediction and image prediction to make some strategies to filter out false image predictions. e.g. if the text looks like it is describing some clothes, but my image model predicts it's a bag, it should be reconsidered.
