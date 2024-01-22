
# Condition number

$$ k_f(x) = \|f'(x)\|\frac{ \|x\|_x}{\|f(x)\|_y} $$
This number measures the sensetivity of a solution of our problem to small perturbations in the input data.
## Definition 1

If $A \in \mathbb{C}^{n \times n}$ is [[Chapter 0#Singular|nonsingular]], and $\|\cdot\|$ is a norm on $\mathbb{C}^{n \times n}$, then

$$
\kappa(A) := \|A\|\|A^{-1}\|  \geq  \|AA^{-1}\| = \|I\|
$$

### Proof

Let $A \in \mathbb{C}^{m \times n}$ and $f: \mathbb{C}^n \to \mathbb{C}^m$ with $f(x) = Ax$. For any linear operator $L: \mathbb{C}^n \to \mathbb{C}^m$ we have any norms $\| \cdot \|$ on $\mathbb{C}^n$ and the [[Chapter 0#induced norm|induced norm]] on $\mathbb{C}^{m \times n}$

$$
\frac{\| f(x + \Delta x) - f(x) - L(\Delta x) \|}{\| \Delta x \|}
= \frac{\| A(x + \Delta x) - Ax - L(\Delta x) \|}{\| \Delta x \|}
= \frac{\| (A - L) \Delta x \|}{\| \Delta x \|}
$$

$f'(x) = A$ for any $x \in \mathbb{C}^n$.

$$
\Rightarrow k_f(x) = A \frac{\| x \|}{\| Ax \|} \text{ for } x \in \mathbb{C}^n \setminus \{0\}.
$$

If $A$ is [[Chapter 0#Singular|nonsingular]], we have $\| x \| = \| A^{-1} Ax \| \leq \| A^{-1} \| \| Ax \|$, thus

$$
\| x \| \leq \| A^{-1} \| \| Ax \|
$$

Therefore

$$
k_f(x) \leq \| A \| \| A^{-1} \| \text{ for every } x \in \mathbb{C}^n \setminus \{0\}.
$$

## Definition 2

Let $A \in \mathbb{C}^{n \times n}$ be nonsingular, and let $A = U\Sigma V^H$ be an SVD. Then $$\kappa_2(A) = \|A\|_2 \|A^{-1}\|_2 = \frac{\sigma_1}{\sigma_n}$$
### proof

use [[Chapter 0#unitary matrix|unitary matrix]]
$$A^{-1} = V\Sigma^{-1}_+ U^H, \quad A^H = V\Sigma_+ U^H, \quad A^{-H} = U\Sigma^{-1}_+ V^H,$$

then use [[Chapter 1#SVD lemma 1|SVD lemma]]

$$\|A\|_2 = \|A^H\|_2 = \sigma_1, \quad \|A^{-1}\|_2 = \|A^{-H}\|_2 = \frac{1}{\sigma_n}, \quad \kappa_2(A) = \kappa_2(A^H) = \frac{\sigma_1}{\sigma_n}, \quad \kappa_2(A^{H}A) = \left( \frac{\sigma_1}{\sigma_n} \right)^2 = \left( \kappa_1(A) \right)^2.$$



# Pertubation results

## Theorem 1

Let $A \in \mathbb{C}^{n \times n}$ and $\hat{A} = A + E \in \mathbb{C}^{n \times n}$ be nonsingular. Then for any [[Chapter 0#Consistent norm#definition|consistent norm]] $\| \cdot \|$ on $\mathbb{C}^{n \times n}$ we have

$$
\frac{\| \hat{A}^{-1} - A^{-1} \|}{\| A^{-1} \|} \leq \| A^{-1} E \| \leq \kappa(A) \frac{\| E \|}{\| A \|}
$$

Moreover, if $\kappa(A) \frac{\| E \|}{\| A \|} < 1$, then

$$
\frac{\| \hat{A}^{-1} - A^{-1} \|}{\| A^{-1} \|} \leq \frac{\kappa(A) \frac{\| E \|}{\| A \|}}{1 - \kappa(A) \frac{\| E \|}{\| A \|}}
$$

## Lemma 1

If $\| \cdot \|$ is a consistent norm on $\mathbb{C}^{n \times n}$, then for each $A \in \mathbb{C}^{n \times n}$ we have

$$
\|A\| \geq \rho(A),
$$

where $\rho(A) := \max\{|\lambda| : \lambda \text{ is an eigenvalue of } A\}$ is called the spectral radius of A.

