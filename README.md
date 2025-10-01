# Knapsack Dynamic Programming

## Formulation du problème 0-1

On dispose de **n objets**.  
Pour chaque objet *i*, on connaît :

- une valeur $m_i \in \mathbb{N}$
- un poids $w_i \in \mathbb{N}$

On dispose d’un sac pouvant contenir au maximum **W unités de poids**.  

Le but est de choisir un sous-ensemble d’objets pour **maximiser la somme des valeurs** tout en respectant la contrainte de capacité :

$$
\max_{u \in \lbrace 0,1 \rbrace^n} \; \sum_{i=1}^n m_i u_i 
\quad \text{tel que} \quad \sum_{i=1}^n w_i u_i \leq W
$$



## modélisation en programmation dynamique déterministe

On dénote :
- $T  = \lbrace 0,1,...n \rbrace$ : ensemble des "temps"
- $E = \lbrace 0, 1, ... W \rbrace$ : ensemble des états
- $C_{i-1} = \lbrace 0, 1 \rbrace \quad \text{si} \quad x < w_i \quad  \text{ou}  \quad \lbrace 0 \rbrace \quad \text{sinon}$ : espace d'action au temps $i-1$ pour $1 \leq i \leq n$ et $x \in E$


La fonction de valeur au temps $k \in T$ pour l'état $x \in E$ est donnée par la formulation récurrente suivante:


$$ v_n(x) = 0 \forall x \in \lbrace 0,...,W\rbrace $$ $$ v_k(x) = \sup \lbrace m_{k+1}u + v_{k+1}(x - w_{k+1}u) | u \in \lbrace 0,1\rbrace, w_{k+1}u \leq x \rbrace \quad \forall x \in E, 0 \leq k \leq n - 1 $$

La valeur cherchée est celle de $v_O(W)$. La politque optimale est $\pi_k(x) $ 0 \quad \text{si} \quad v_{k+1} = v_k(x) \quad \text{et} \quad 0 \quad \text\{sinon}$.
