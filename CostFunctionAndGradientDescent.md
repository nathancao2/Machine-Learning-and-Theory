# Cost function 

We know that regression models are mainly used to solve problems where there could be infinitely many answers. A very common example is the housing price problem.


![1_CmmqOLf8wlK93HXl3zgIfA](https://user-images.githubusercontent.com/71524984/179580172-792a5155-f6ad-40b2-b8ba-95c1dde265a3.png)


Above is a scatter plot with data points on Boston house pricing. It has a general trendline, which we can define as $y(x)_{w,b} = wx + b.$ The job for a regression model would be to figure out this trendline, so that we could make a prediction for some new input x (in this case it would be the size of the house). 

We could make some rough prediction for the model, but we can't guarantee whether it's the equation that models the data the best. This is where the cost function comes in. The cost function is defined by this equation: $J(w, b) = (\frac{1}{2m}) (\sum_{i=1}^m y(x^{(i)})-y^(i))^2.$ This basically takes the squared average of the differences between the trendline 


# Gradient descent 
