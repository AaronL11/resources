\newpage

# Metaheuristics

## Local Search

## Global Search

## Single Solution

## Population Based

## Simulated Annealing

## Swarm Intelligence

### BOIDs

### Ant Colony Optomization Algorithm

$$
\Delta\tau^k_{ij}=
\begin{aligned}
    &{Q\over L_{ij}}\\&0
\end{aligned}
$$

The probability of an ant $k$ to go from $i$ to $j$ $\left(p^k_{ij}\right)$ is the *attractivenes* of the path $\eta_{ij}$ and the number of pheromones $\tau_{ij}$, each scaled by an exponent $\alpha$ and $\beta$. You then divde by the total attractiveness of each other path:
$$
p^k_{ij}={\left(\tau_{ij}\right)^\alpha\left(\eta_{ij}\right)^\beta\over\sum^m_k\left(\tau_{ij}\right)^\alpha\left(\eta_{ij}\right)^\beta}\qquad\eta_{ij}={Q\over L_{ij}}
$$

Pheromones evaporate over a constant time given the following formula:
$$
\tau^k_{ij} = (1-\rho)\tau^k_{ij}+\sum^m_k\Delta\tau^k_{ij}
$$

All in all we have four constant that we can scale to fit our model:
$$
\begin{aligned}
    Q = ?\\
    \alpha = ?\\
    \beta = ?\\
    \rho = ?
\end{aligned}
$$

### Bee Algoritm

