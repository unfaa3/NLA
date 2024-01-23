# Singular

If for $A \in \mathbb{C}^{n \times n}$ there exists a matrix $B \in \mathbb{C}^{n \times n}$ with $AB = BA = I_n$, then $A$ is called non-singular. Otherwise $A$ is called singular. 
$A$ is non-singular if and only if $\det(A) \neq 0$, which holds if and only if $\text{rank}(A) = n$.

# Norms

## norm definition

A function $\|\cdot\| : V \to \mathbb{R}$ is called a _norm_ on vector space $V$ if: 
1. $\|v\| \geq 0$ for all $v \in V$, $\|v\| = 0$ only if $v = 0$, 
2. $\|\alpha v\| = |\alpha| \|v\|$ for all scalars $\alpha$ and $v \in V$, 
3. $\|v_1 + v_2\| \leq \|v_1\| + \|v_2\|$ for all $v_1, v_2 \in V$ (so-called triangle inequality).

For example, given a real number $p \geq 1$, the $p$-norm on $\mathbb{C}^n$ is defined by $$ \|x\|_p := \left( \sum_{j=1}^{n} |x_j|^p \right)^{1/p}, $$
## norm on $\mathbb{C}^n$

$$\|x\|_1 = \sum_{j=1}^{n} |x_j|$$ $$ \|x\|_2 = \left( \sum_{j=1}^{n} |x_j|^2 \right)^{1/2} = (x^{H}x)^{1/2} \quad (\text{Euclidean or 2-norm}), $$ $$ \|x\|_\infty = \max_{1 \leq j \leq n} |x_j| \quad (\text{maximum or } \infty\text{-norm}). $$
## norm on $\mathbb{C}^{n \times n}$

### induced norm

If $\| \cdot \|$ is any norm on $\mathbb{C}^n$, then the function

$$\| \cdot \|_*: \mathbb{C}^{n \times n} \rightarrow \mathbb{R} \text{ with } \|A\|_* := \max_{x \in \mathbb{C}^n, \|x\|=1} \|Ax\| = \max_{0 \neq x \in \mathbb{C}^n} \frac{\|Ax\|}{\|x\|}$$

is a norm on $\mathbb{C}^{n \times n}$, which is called the matrix norm induced by $\| \cdot \|$.

# Consistent norm

## definition

Definition 0.6. Let $| \cdot |$, $\| \cdot \|$, $\| \cdot \|_*$ be norms on $\mathbb{C}^{n \times m}$, $\mathbb{C}^{m \times k}$, $\mathbb{C}^{n \times k}$, respectively. These norms are called consistent, when

$$\|AB\|_* \leq |A| \cdot \|B\|$$

holds for all $A \in \mathbb{C}^{n \times m}$ and $B \in \mathbb{C}^{m \times k}$. A single norm $\| \cdot \|$ on $\mathbb{C}^{n \times n}$ is called consistent if

$$\|AB\| \leq \|A\| \cdot \|B\|$$

holds for all $A, B \in \mathbb{C}^{n \times n}$.

## lemma

If $\| \cdot \|$ is any consistent norm on $\mathbb{C}^{n \times n}$, and $y \in \mathbb{C}^n \setminus \{0\}$, then the function

$$
\| \cdot \| : \mathbb{C}^n \to \mathbb{R} \quad \text{with} \quad \| x \| := \| x y^* \|
$$

is a norm on $\mathbb{C}^n$.


## Hermitian positive definite:

If $A \in \mathbb{C}^{n \times n}$ is Hermitian and

$$
x^H Ax > 0 \text{ for all } x \in \mathbb{C}^n \setminus \{0\}, \text{ or}
$$

$$
x^H Ax \geq 0 \text{ for all } x \in \mathbb{C}^n,
$$
then A is called Hermitian positive definite (HPD) or Hermitian positive semidefinite (HPSD), respectively.

### HPD lemma

If $A \in \mathbb{C}^{n \times n}$ is _HPSD_, then the following assertions hold:

1. $\lambda \geq 0$ for every eigenvalue $\lambda$ of $A$ (and $\lambda > 0$ if $A$ is _HPD_).
2. $X^HAX$ is _HPSD_ for all $X \in \mathbb{C}^{n \times k}$, and if $A$ is _HPD_ and $\text{rank}(X) = k$, then $X^HAX$ is also _HPD_.
3. $A(1:k,1:k) = \begin{bmatrix} a_{11} & \cdots & a_{1k} \\ \vdots & \ddots & \vdots \\ a_{k1} & \cdots & a_{kk} \end{bmatrix}$ is _HPSD_ for all $k = 1, \ldots, n$, and if $A$ is _HPD_, then $A(1:k, 1:k)$ is also _HPD_.


# normal

If $A \in \mathbb{C}^{n \times n}$ satisfies $A^H A = AA^H$ then $A$ is called _normal_. Note that Hermitian and unitary matrices are normal.

## Spectral decomposition of normal matrices

1. $A \in \mathbb{C}^{n \times n}$ is normal if and only if $A$ can be unitarily diagonalized, i.e., there exists a unitary matrix $U$ such that $U^H AU = D$ is diagonal.
2. $A \in \mathbb{C}^{n \times n}$ is Hermitian if and only if $A$ can be unitarily diagonalized and all the eigenvalues of $A$ are real.
3. $A \in \mathbb{C}^{n \times n}$ is unitary if and only if $A$ can be unitarily diagonalized and all eigenvalues $\lambda$ of $A$ satisfy $|\lambda| = 1$.
# unitary matrix:

If $A \in \mathbb{C}^{n \times n}$ satisfies $A^HA = I_n$, then $A$ is called unitary.

## unitary invariance


$$
\|UAV\|_2^2 = \max_{x \in \mathbb{C}^m} \frac{\|UAVx\|_2^2}{\|x\|_2^2} = \max_{x \in \mathbb{C}^m} \frac{x^HV^HA^HU^HAVx}{\|x\|_2^2} \quad (\text{set } y := Vx)
$$

$$
= \max_{y \in \mathbb{C}^m} \frac{y^HA^HAy}{\|y\|_2^2} = \max_{y \in \mathbb{C}^m} \|Ay\|_2^2 = \|A\|_2^2.
$$



