Course 2/5 of Deep Learning Specialization Course by Andrew Ng

[Week 1] 

1. Setting up your ML Application

    It's a highly iterative process

    It Can be said to comprise of 3 steps:

    1. Idea
    2. Code
    3. Experiment

    ML application areas in the current trends include NLP, Vision, Speech recognition, Structured data.

    Experience in one application areas do not apply in other application areas even for experts. It thus involves going through the iterative process to come up with a good a solution.

    First step, is working with your data and segmenting it into train, dev and test sets and build algorithms around that to evaluate your models as well as gauging how well it's performing.

    Data segmentation criteria differ, previously it was a common practice i.e 70/30 but  in the modern big data era it has become a common practice to do a 60/20/20 ratio.

    Mismatched train/test distribution is one of the common mistakes to avoid. The rule of thumb is to ensure that the data comes from the same distribution.

2. Bias/Variance

    Bias, is under-fitting scenario in ML

    Variance scenario when your learning algorithm fits the data very well i.e over fitting

    Evaluation model for bias/variance is checking the train set error and the dev set error.

    High variance scenario: train set error 1% and Dev set error 11%

    High bias scenario: train set error 15% and Dev set error 16%

    High bias & variance scenario 15% and 30% 

    Low bias & variance scenario 0.5% and 1%

    Optimal Bayesian (Bayes) error ranges around 0% for humans.

3. Basic Recipe for ML "Bias and Variance problem"

    Does your algorithm have a high bias (underfit) on train set performance? Try

    Try bigger network

    Neural Net Architecture

    Train longer

    Does your algorithm has high variance (dev set performance)? Try

    More data

    Regularization

    Neural Net architecture

4. Regularization

    Logistic Regression

    L2 regularization is the most common type of regularization

    ||w||^2 = W.T * W (lambda/2m ||w||^2 ) for logistic regression

    L1 regulation 

    Neural Network regulation

    L2 regulation is also call the "weight decay"

    Frobenius norm ||w||^2

    Why regularization prevents over fitting?

    It penalizes the large weights to be close to zero.

    Dropout Regularization

    It's a regularization technic.

    It sets a probability limit to remove a node to end up with a small network.

    Implementing dropout: "Inverted Dropout"

    It's hard to monitor gradient descent when implementing dropout regularization.

    Other Regularization Methods

    A few other regularization technics to prevent over-fitting. The notion is that getting more data may be expensive and difficult.

    Some of these technics include:

    Data augmentation -  generate more data from your current dataset e.g horizontal flip, random zoom, random rotation, distortions

    Early stopping - This is a technic of stopping model training when your train accuracy/error reaches a particular level,

5. Input normalization

    Normalizing training sets

    This is scaling the inputs to a common range, say 0-1 to make them look more symmetric.

    This can be help to help the gradient descent descend more quickly unlike in unnormalized cases where the gradient will oscillate for long before convergence.

    general norm formula: 

    (x-mean)/ std deviation

    Vanishing or exploding gradients

    This refers to derivatives getting very big or very small when training DNNs

    This has the effect to make the gradient learn slowly

    Weight initialization for DNNs

    This is a partial solution to avoid Vanishing/Exploding gradients for DNNs

    This is achieved by  applying variance to weights i.e Var(W) for ReLU = sqrt(2/n^[L-1]), tanh =  sqrt(1/n^[L-1]), Xavier initialization = sqrt(2/ n^[L-1] * n[x])

6. Numerical appromixation of gradients

    Checking your derivative computation

    Two sided difference performs better than 1 sided difference and is much more accurate

    Gradient checking

    It's a technic for verifying that your implementation of your backprop is correct.

    Reshape W, b into a big Vector Theta, concat all  W's and b's

    Reshape all dW, db into a big vector dTheta

    Implement a loop  to check dTheta approx  and dTheta proximity to each to each other i.e Euclidean distance

    Some notes for grad check:

    used only for debugging

    include regularization term

    dropout should be turned off

    run at random initialization; perhaps after some training to make sure the grad doesn't work for some values.