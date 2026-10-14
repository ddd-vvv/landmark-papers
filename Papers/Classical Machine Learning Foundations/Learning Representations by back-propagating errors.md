# Metadata
 * Title: Learning Representations by back-propagating errors
 * Authors: David E. Rumelhart, Geoffrey E. Hinton & Ronald J. Williams
 * Published: 09 October 1986.
 * Nature 323, 533-536 (1986).
# Introduction
* Back-propagation is a new learning procedure for networks of [[Neuron | neuron-like]] units.
* Repeatedly adjusts the weights of the connections in the [[Neural Networks | network]] so as to minimize a measure of the difference between the actual output vector of the net and the desired output vector. (This is remanent of [[Neuroplasticity]]).
* Internal 'hidden' units come to represent important features of the task domain and the regularities in the task are captured by the interactions of these units.
* This ability to create new features distinguishes this procedure from earlier, simpler methods.
# Content
* The aim is to find a procedure that will allow a [[Neural Networks | neural network]] to develop an internal structure that is appropriate for a particular task domain.
* For that, it's used a desired state [[Vector | vector]] of the output units for each state vector of the input units.
* This is relatively easy if the inputs units are directly connected with the output units.
* With hidden units , whose actual or desired states are not specified, this become more complex.
* For actually achieving the goal, the learning procedure must decide which hidden units should be active.
* Lets consider a simple [[Neural Networks | neural network]] , one with and input layer, any number of intermediate layers and an output layer.
	* Connections within a layer or from higher to lower layers are forbidden, but connections can skip intermediate layers.
	* Lets consider and input vector, then the states of the units in each layer are determined by applying equations $(1)$ and $(2)$ to the connections coming from lower layers.
	* Input $x_j$ to unit $j$ is a [[Mathematics/Linear function|linear function]] of the outputs $y_i$ of the units that are connected to $j$ and of the wrights $w_{ij}$ $(1)$.
	* We can add biases to the units by introducing an extra input to each unit which always has a value of 1. That weight is called the bias and is equivalent to the threshold of the opposite sign $(2)$.
$$ 
	x_j = \sum_i y_i w_{ij} \tag{1}
$$
$$
y_j = \frac{1}{1+\exp{-x_j}} \tag{2}
$$
* Those are not the only functions usable. Any input-output function which has a bounded derivative will do.
* But the usage of [[Linear function|linear function]] for combining the inputs to a unit before applying the non linearity simplifies the learning procedure.
* Now the objective is to find a set of weights that ensure that for each input vector, the output vector produced by the network is the close or the same as the desired output vector.
* For a fixed, finite set of input-output cases, the total error in the performance of the network with a particular set of weights can be computed by comparing the actual and desired outputs for every case. The total error $E$ is defines as:
$$
E = \frac{1}{2} \sum_c \sum_j (y_{j,c} - d_{j,c})^2 \tag{3}
$$
	* Where:
		* c is the index over input-output pairs.
		* j is an index over output units.
		* y is the actual state of an output unit.
		* d is its desired state.
* To minimize $E$ by [[Gradient descent | gradient descent]], it is necessary to compute the partial derivative of $E$ with respect to each weight in the network.
* This is the sum of the partial derivatives for each of the input-output cases.
* For each case, the partial derivative of the error with respect to each weight is computed in two passes.
	* Forward pass is made using equations $(1)$ and $(2)$.
	* Backward pass propagates derivatives from the top layer back to the bottom one:
		* Starts by computing $\partial E / \partial y$ for each of the output units. 
		* Differentiating $(3)$ for a particular case, c, and suppressing the index $c$ gives:
$$
\partial E / \partial y = y_j - d_j \tag{4}
$$
		* We can then apply the chain rule to compute $\partial E / \partial x_j$
$$
\partial E / \partial x_j = \partial E / \partial y_j \cdot dy_j / dx_j
$$
		* Differentiating equation $(2)$ to get the value of $dy_j/dx_j$ and substituting gives:
$$
\partial E / \partial x_j = \partial E / \partial y_i \cdot y_j (1 - y_j) \tag{5}
$$
		* Then, we know how a change in the total input $x$ to an output will affect the error.
		* For a weight $w_{ij}$. from $i$ to $j$ the derivative is:
$$
\begin{split}
\partial E / \partial w_{ij} & = \partial E / \partial x_j \cdot \partial x_j / \partial w_{ji} \\
& = \partial E / \partial x_j \cdot y_i
\end{split}
\tag{6}
$$
		* The output of the $i^{th}$ unit the contribution to $\partial E / \partial y_i$ resulting from the effect of $i$ on $j$ is simply
$$
\partial E / \partial x_j \cdot \partial x_j / \partial y_i = \partial E / \partial x_j \cdot w_{ji}
$$
		* So taking into account all the connections emanating from unit $i$ we have
$$
\partial E / \partial y_i = \sum_j \partial E / \partial x_j \cdot w_{ij}
\tag{7}
$$
		* This procedure can be repeated to compute the term for successively earlier layers.
* One way of using $\partial E / \partial w$ is to change the weights after every input-output case. This has the advantage that no separate memory is required for the derivatives.
* An alternative is to accumulate $\partial E / \partial w$ over all the input-output cases before changing the weights.
* The simplest version of gradient descent is to change each weight by an amount proportional to the accumulated $\partial E / \partial w$.
$$
\Delta w = - \epsilon \partial E / \partial w \tag{8}
$$
* This method does not converge as rapidly as methods which make use of the second derivatives.
* It can be significantly improved, by using an accelerate method in which the current gradient is used to modify the velocity of the point in weight space instead of its position
$$
\Delta w(t) = - \epsilon \partial E / \partial w(t) + \alpha \Delta w(t-1)
\tag{9}
$$
* Where: 
	* $t$ is incremented by $1$ for each sweep through the whole set of input-output cases.
	* $\alpha$ is an exponential decay factor between $0$ and $1$ that determines the relative contribution of the current gradient and earlier gradients to the weight change.
* The most obvious drawback of the learning procedure is that the error-surface may contain [[Local minimum|local minimum]], so that [[gradient descent]] is not guaranteed to find a [[Global minimum|global minimum]].
* However, in the experience, the network very rarely gets stuck in poor local minima that are significantly worse than the global minimum.
