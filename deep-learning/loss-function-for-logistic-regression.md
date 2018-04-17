### Log loss function

Denote y as sample label and $\hat{y}$ as the predication

$$
l(\hat{y}, y) = -(y\log \hat{y} + (1-y)\log(1-\hat{y}))
$$

If y == 1 : $l(\hat{y}, y) = -y\log\hat{y}$, want $\hat{y}$ be large

If y == 0 : $l(\hat{y}, y) = -\log(1-\hat{y})$, want $\hat{y}$ be small

### Why is the above loss function?

Let's interpret $\hat{y}$ as the porbability of y == 1

If y == 1 : $P({y|x}) = \hat{y}$

If y == 0 : $P({y|x}) = 1 - \hat{y}$

Combined the above function together

$P({y|x}) = \hat{y}^y(1-\hat{y})^{1-y}$

Apply the log function to above formular

$\log P({y|x}) = y\log\hat{y} + (1-y)\log(1-\hat{y})$

To maximize the likelyhood is essentially minimize the loss function $l(\hat{y}, y) = -(y*\log\hat(y))$

