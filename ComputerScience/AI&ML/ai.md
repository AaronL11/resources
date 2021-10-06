\newpage

# Artificial Intelligence

Artificial Intelligence is generally used to refer to a variety of techniques, approaches, and algorithms used to make machines solve problems. The problems AI is applied in usually involve complex and dynamic systems, as well as making decisions, but traditionally they were devised for more philosophical and logical tasks.



## Heuristics

A heuristic is a method that is not always optimal or perfect, but is practical and gives a sufficient solution. A heuristic could be something as simple as wearing only white shirts on weekends because that is when you wash the rest of your laundry.

Heuristics


## Decision Making

1. Maxi-Max
   * Maximize the maximum payoff. This is a rather optimistic approach.
2. Maxi-Min
   * Maximize the minimum payoff. This approach is more pessimistic.
3. Mini-Max
   * Minimize the maximum regret (opportunity loss). This algorithm is used in games like chess and tic tac toe to choose the board state that gives that is most favorable.

## Mini-Max

$$
\text{Regret} = \text{Best Payoff} - \text{Payoff Received}
$$

### $\alpha-\beta$ pruning

One issue with the minimax algorithm is how it will sometimes search paths that are redundant. This can take up more memory as well as processing time.

## Monte Carlo Tree Search (MCTS)

The MCTS algorithm is similar to the MiniMax algorithm. Instead of searching every node, however, the algorithm carves a path based on random decisions until it finds a favorable condition. This helps it approach to a favorable solution faster. Even if that solution isn't optimal, in a very large and complex system any sufficiently favorable solutions is better than an optimal solution. Often continually taking favorable solutions can help converge on to an optimal solution better than a very wide and long search.

## Goal Oriented Action Planning (GOAP)

Goal Oriented Action Planning is an AI method used in videogames for making decisions.

