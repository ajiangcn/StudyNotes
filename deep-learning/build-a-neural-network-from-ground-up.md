This post lays out a skelton to build a neural network from ground up.

### High level steps to build a neural network

1. Initialize the parameters of the model
    * Define the model structure
    * Initialize the model parameters
2. Learn the parameters of the model by minimizing the cost - loop through the following steps
    * Calculate the current loss - forward propogation
    * Calculate the current gradient - backword propogation
    * Update the model parameters
3. Use the learned parameters to make predictions
4. Analyse the result

### Code sample

#### Initializing parameters

    def initialize(dim):
        w = np.zeros((dim, 1))
        b = 0
        return w, b

#### Forward and backward propogation

    def porpogate(w, b, X, Y):
        """
        Arguments:
        w : weights
        b : bias
        X : training data features
        Y : training data labels

        Return:
        cost : cost of current parameters
        dw : gradient of the loss with respect to weights
        db : gradient of the loos with respect to bias
        """

        cost = l(w, b, X, Y) # need to define the loss function
        dw = ?? # depending on the loss function used
        db = ?? # depending on the loss function used

        return cost, dw, db

#### Optimization (min-batch is not used here)
    
    def optimiza(w, b, X, Y, num_iterations, learning_rate):
        """
        Arguments:
        w : weights
        b : bias
        X : training data features
        Y : training data labels
        num_iterations : number of iterations for the optimization
        learning_rate : learning rate of gradient decent update
        
        Return:
        params : learned w, b
        costs : cost of current weights and bias
        """

        for i in range(num_iteration):
            cost, dw, db = propogate(w, b, X, Y>)

            w = w - learning_rate * dw
            b = b - learning_rate * db

            cost = l(w, b, X, Y)
        
        return w, b, cost

#### Prediction

    def predict(w, b, X):

### Model

    def model(X_train, Y_train, X_test, Y_test, num_iterations, learning_rate):
        dim = ?? # learned from the training data and model definition
        w, b = initialize(dim)

        w, b, cost = optimize(w, b, X_train, Y_train, number_iterations, learning_rate)

        Y_prediction_test = predict(w, b, X_test)
        Y_prediction_train = predict(w, b, X_train)

        perf_test = evaluate(Y_prediction_test, Y_test)
        perf_train = evaluate(Y_prediction_train, Y_train)
