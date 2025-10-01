# Knapsack Dynamic Programming

## Formulation du problème 0-1

On dispose de **n objets**.  
Pour chaque objet *i*, on connaît :

- une valeur $v_i \in \mathbb{N}$
- un poids $w_i \in \mathbb{N}$

On dispose d’un sac pouvant contenir au maximum **W unités de poids**.  

Le but est de choisir un sous-ensemble d’objets pour **maximiser la somme des valeurs** tout en respectant la contrainte de capacité :

$$
\max_{u \in \lbrace 0,1 \rbrace^n} \; \sum_{i=1}^n v_i u_i 
\quad \text{tel que} \quad \sum_{i=1}^n w_i u_i \leq W
$$



## modélisation en programmation dynamique déterministe

On dénote :
- $T  = \lbrace 0,1,...n\rbrace $  l'ensemble de "temps"
- $E = \lbrace 0, 1, ... W \rbrace$ l'ensemble des états
- $C_{i-1} = \lbrace 0, 1 \rbrace \quad \text{si} \quad x < w_i \quad  \text{ou}  \quad \lbrace 0 \rbrace \quad \text{sinon}$ espace d'action au temps $i-1$ pour $1 \leq i \leq n$ et $x \in E$
