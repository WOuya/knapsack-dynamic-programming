# knapsack-dynamic-programming


## Formulation du problème 0-1
On dispose de N objets. Pour chaque objet i, on connait:
- une valeur $m_i \in N$
- un poids $w_i \in N$

On dispose d'un sac contenant au maximum W unités de poids. 

Le but est de choisir un sous-ensemble d'objets pour maximiser la somme des valeurs en respectant les contraintes de poids :

$max_{u \in \{0,1\}^n} \sum_{i=1}^{n} v_i u_i $ tel que $\sum_{i=1}^n w_i x_i \leq W$
