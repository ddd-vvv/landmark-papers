* Method for unconstrained [[mathematical optimization]].
* [[First-order]] [[iterative]] [[algorithm]] for minimizing a [[differentiable]] [[multivariate function]].
# Description
* [[multivariate function]] $f(x)$ is [[defined]] and [[differentiable]] in a neighborhood of a point $a$, then $f(x)$ decreases *fastest* if one goes from $a$ in the direction of the negative [[gradient]] of $f$ at $a$, i.e. $-\nabla f(a)$.
$$
a_{n+1} = a_n - \eta \nabla f(a_n)
$$
* For a small enough step size of [[learning rate]] $\eta \in \mathbb{R}_+$, then $f(a_n) \ge f(a_{n+1}$)