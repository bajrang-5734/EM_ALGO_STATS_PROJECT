# Convergence of EM Algorithm for Gaussian Mixture Models

## Overview  
This project investigates the convergence of the Expectation-Maximization (EM) algorithm for Gaussian Mixture Models (GMMs) and explores how mixing coefficients affect its speed. An enhanced Deterministic Anti-Annealing EM (DAEM) algorithm is proposed, along with a further modification to improve performance on datasets with larger covariance. The project compares the convergence rates of the standard EM, DAEM, and modified DAEM algorithms across various datasets, including noisy datasets like Wine and Iris.

---

## Key Highlights  

### 1. Convergence Analysis  
- The EM algorithm's convergence speed is influenced by the overlap of mixture components and the dynamic range of mixing coefficients.  
- Higher overlap and unbalanced mixing coefficients result in slower convergence.  

### 2. Proposed Algorithms  
- **Standard EM Algorithm**  
  \[
  h_j(t) = \frac{\alpha_j P(x_t | \mu_j, \Sigma_j)}{\sum_i \alpha_i P(x_t | \mu_i, \Sigma_i)}
  \]
- **DAEM Algorithm**  
  \[
  h_j(t) = \frac{(\alpha_j P(x_t | \mu_j, \Sigma_j))^\beta}{\sum_i (\alpha_i P(x_t | \mu_i, \Sigma_i))^\beta}
  \]  
  where \( \beta \) is the scheduling parameter.  
- **Modified DAEM Algorithm**  
  \[
  h_j(t) = \frac{(\alpha_j P(x_t | \mu_j, \Sigma_j))^{\beta + \alpha_j}}{\sum_i (\alpha_i P(x_t | \mu_i, \Sigma_i))^{\beta + \alpha_j}}
  \]  
  This modification improves DAEM performance for datasets with larger covariance (e.g., Iris dataset).  

### 3. Comparative Insights  
- The DAEM algorithm significantly outperforms the standard EM algorithm by overcoming local maxima and achieving global (or higher local) maxima.  
- On datasets with larger covariance, the modified DAEM algorithm further accelerates convergence.  

### 4. Complexity Considerations  
- DAEM and modified DAEM algorithms offer faster convergence but require higher computational resources. For general applications, the standard EM algorithm is often preferred due to lower complexity.  

---

## Experimental Results  

- **Noisy Datasets**: On the Wine and Iris datasets, the standard EM algorithm often gets stuck at local maxima, while the DAEM algorithm successfully converges to better solutions.  
- **Modified DAEM**: For datasets like Iris, where DAEM convergence is slower, the modified DAEM algorithm (using \( \beta + \alpha_j \)) enhances convergence speed without compromising accuracy.  

---

## Conclusion  

The DAEM algorithm provides faster convergence than the standard EM algorithm for GMMs with unbalanced mixing coefficients. The modified DAEM algorithm further improves performance on datasets with high covariance. However, due to lower computational requirements, the standard EM algorithm remains suitable for general applications.

---

## Future Scope  

- Extend experiments to more complex, high-dimensional datasets.  
- Explore hybrid approaches balancing computational efficiency and convergence speed.  

---

## References  

- Gaussian Mixture Models and Expectation-Maximization Algorithm  
- Deterministic Annealing and Anti-Annealing Techniques  
