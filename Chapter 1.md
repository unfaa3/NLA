

# Singular value decomposition (SVD)

If $A \in \mathbb{C}^{m \times n}$ has rank $r$, then there exist [[Chapter 0#unitary matrix|unitary matrix]] $U \in \mathbb{C}^{n \times n}$, $V \in \mathbb{C}^{m \times m}$ and a diagonal matrix $\Sigma_+ = \text{diag}(\sigma_1, \ldots, \sigma_r)$ with $\sigma_1 \geq \ldots \geq \sigma_r > 0$, such that

$$
A = U \begin{bmatrix} \Sigma_+ & 0 \\ 0 & 0 \end{bmatrix} V^H, \quad \text{or} \quad A = \sum_{j=1}^{r} \sigma_j u_j v_j^H.
$$

The numbers $\sigma_1 \geq \ldots \geq \sigma_r > 0$ in (1.1) are called the (nonzero) singular values of $A$, and the columns of the unitary matrices $U$ and $V$ are called the left and right singular vectors of $A$, respectively.

## Proof
The matrix $A^H A$ is HPD ([[Chapter 0#Hermitian positive definite|Hermitian positive definite]]) since $x^H A^H A x = \| Ax \|_2^2 \geq 0$ for all $x \in \mathbb{C}^m$ ([[Chapter 0#norm on $ mathbb{C} n$|2-norm]]). Hence $A^H A$ can be unitarily diagonalized with nonnegative real eigenvalues ([[Chapter 0#HPD lemma|1]]). Denote the $r = \text{rank}(A) = \text{rank}(A^H A)$ positive eigenvalues by $\sigma_1^2 \geq \ldots \geq \sigma_r^2 > 0$ and $\Sigma_+^2 = \text{diag}(\sigma_1^2, \ldots, \sigma_r^2)$, and let the [[Chapter 0#Spectral decomposition of normal matrices|unitary diagonalization]] be

$$
V^H A^H A V = \begin{bmatrix} \Sigma_+^2 & 0 \\ 0 & 0 \end{bmatrix} = \begin{bmatrix} \Sigma_+^2 & V_1^{H}A^{H}AV_2 \\ V_2^{H}A^{H}AV_1 & V_2^{H}A^{H}AV_2 \end{bmatrix},
$$

for a unitary matrix $V \in \mathbb{C}^{m \times m}$. Then with $V = [V_1, V_2]$, where $V_1 \in \mathbb{C}^{m \times r}$, we see that $V_2^H A^H A V_2 = 0$, giving $AV_2 = 0$. Define $U_1 := AV_1 \Sigma_+^{-1}$, then

$$
U_1^H U_1 = \Sigma_+^{-1} V_1^H A^H A V_1 \Sigma_+^{-1} = I_r.
$$

We therefore can choose a matrix $U_2$ so that $U := [U_1, U_2] \in \mathbb{C}^{n \times n}$ is unitary. Then, by construction, $U_2^H AV_1 = U_2^H U_1 \Sigma_+ = 0$, so that

$$
U^H AV = \begin{bmatrix} U_1^H AV_1 & U_1^H AV_2 \\ U_2^H AV_1 & U_2^H AV_2 \end{bmatrix} = \begin{bmatrix} \Sigma_+ & 0 \\ 0 & 0 \end{bmatrix},
$$

completing the proof.

## SVD lemma 1

If $A \in \mathbb{C}^{n \times m}$ has an SVD, then the [[Chapter 0#unitary invariance|unitary invariance]] of the 2-norm shows that

$$
\|A\|_2 = \left\|\begin{bmatrix}\Sigma_+ & 0 \\ 0 & 0\end{bmatrix}\right\|_2 = \sigma_1.
$$
If $n = m$ and $A$ is nonsingular, then its SVD has the form $A = U\Sigma_+V^H$, where

$$\Sigma_+ = \text{diag}(\sigma_1, \ldots, \sigma_n) \quad with \quad \sigma_1 \geq \ldots \geq \sigma_n > 0$$.

Then $A^{-1} = V\Sigma_+^{-1}U^H$, and the unitary invariance of the 2-norm shows that

$$\|A^{-1}\|_2 = \frac{1}{\sigma_n}.$$
