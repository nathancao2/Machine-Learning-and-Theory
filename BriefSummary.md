Import all of your utilities 
Simple. Just import the tools that you need. In our case it would be numpy 
Load the data set; categorize it into x_train and y_train 
In the course they don’t have a data set, but if, for example, I have a dataset where the house cost depends on the size of the house, I would have an array where one column is x, and the other is y, and dataset[0] would be x, and dataset[1] would be y 
Compute the cost function 
So in our course it’s defined as a method which takes in the x_train, y_train, w (which is the slope of the line), and b (the y-intercept) 
The cost function is as follows: J(w, b) = 1/(2m) * \sum from i to m (w * x_train + b - y_train)^2
 (w * x_train + b - y_train)^2 is the squared error. Notice that w * x_train + b is our predicted value using the function we generated, and y_train is the actual value. The cost function is all about getting the average error, so that’s why it sums up the squared errors of all of the terms x^(i) from i to m (which is the shape of the array, or in other words the number of training examples). The term outside, 1/(2m), is where the average part comes in. You’re dividing the function by the number of training examples times two. 
Do the compute gradient 
So the gradient is essentially the partial derivative of the cost function. If you remember, the cost function is represented as a bowl shape. That’s always the case for linear regression. There’s three values that cause the bowl shape: the two inputs, and the output of the cost function. Essentially we just want to calculate how to get to the bottom of the bowl. Taking the derivative of the function and then inputting the input values for the derivative function will get you the slope of the line that points to the bottom of the bowl. 
Do the gradient descent function 
Now that we have the gradient, or the line that points to the bottom of the bowl, we need to actually change the values w and b so that we can fit the function to the data. The equation that we use to update these values is w = w - a*gradient, or b = b - a*gradient. It’s not supposed to be a, the variable is alpha. It’s the learning rate. Essentially it determines the size of the step that you take on the cost function graph. A good learning rate will eventually get you to the bottom of the graph; a learning rate that is too large will overshoot and you may never reach the bottom of the graph. A learning rate too small will take forever to get to the bottom, and that’s a waste of resources. That’s the idea of gradient descent which is a type of optimization algorithm. 
Then you can plot everything 
You just plot! 

In code 

Just write all of the import statements (typically you’d also import the dataset) 
Train the data for linear regression 
x _train = np.array[dataset[0]] //essentially this just uploads the column zero or x values of the data set into the x training values; we do np.array because we want to turn this into an array in order to perform linear algebra functions on it 
y_train  = np.array[dataset[1]] will upload the y training values 
Cost function 
We know that we need to find a function f(x) = wx + b that fits our line, and we need to determine the values of the parameters w and b 
Cost function (which is just a function that determines the amount of error a function has): J(w,b) = 1/(2m) \sum from i =0 to m-1 (wx^(i) + b - y_train^(i)) 
for i in range m{ //we do m iterations 
Compute cost 
Update the cost 
}
Compute the gradient
So we now need to compute the gradient, or in other words, the partial derivative of the cost function; this process will essentially give us the slope and the “direction” at which the cost function is pointing at for the given parameters
The way we’re doing this is by updating w and b simultaneously
So dw is formed by deriving with respect to w, and it’s simply 1/m * \sum from i = 0 to m-1 (f(w,b)-y^(i))x^(i) and the same for b. You’d just calculate the summation with a for loop 
Compute gradient descent
This is just basically where we apply the learning rate and we simultaneously update w and b to achieve our optimal result. 

