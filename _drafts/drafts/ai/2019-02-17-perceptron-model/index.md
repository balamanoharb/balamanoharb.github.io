



https://towardsdatascience.com/perceptron-the-artificial-neuron-4d8c70d5cc8d
https://towardsdatascience.com/perceptron-learning-algorithm-d5db0deab975



There is an important correction in the toy example and code used for perceptron. 

There are two alternate ways of writing the perceptron function:
w2x2 + w1x1 >= b
w2x2 + w1x1 + w0 >=0
By comparing the two expressions, it's easy to see that wo=-b
We will now focus on the second form w2x2 + w1x1 + w0 >=0 or w2x2 + w1x1 + w0x0 >=0 where x0=1
When y_pred=0 and y=1, the update rule is
w = w + x, which expands to
w2 = w2 + x2
w1 = w1 + x1
w0 = w0 + x0 ==> w0 = w0 + 1 ==> -b = -b + 1 ==> b = b - 1
When y_pred=1 and y=0, the update rule is 
w = w - x, which expands to
w2 = w2 - x2
w1 = w1 - x1
w0 = w0 - x0 ==> w0 = w0 - 1 ==> -b = -b - 1 ==> b = b + 1
Note the difference in signs for the updates of w (w1, w2) and b.
In the hands-on videos and in the "toy example", the update of b is incorrectly done (sign of 1 is wrong).
The notebook available at "Download Materials" has been updated to correct for this error.