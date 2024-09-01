# Monte-Carlo-Tree-Search
Monte Carlo Tree Search (MCTS) is a probabilistic search algorithm that uses random simulations to selectively (i.e. in an imbalanced manner) grow a game tree. MCTS has been particularly successful in domains with vast search spaces (i.e. game trees with high branching factor) where deterministic algorithms such as minimax (or alpha-beta pruning) have struggled.

This project contains a fast C++ implementation of the vanilla MCTS algorithm. This implementation (mcts.h/.cpp) uses abstract (aka pure virtual) classes for the concept of states and moves (state.h). The user of this implementation should extend these classes and implement their virtual methods according to his desired application. He can then use tree class provided in mcts.h to use this algorithm.

Two usage examples are provided along with said implementation (the Makefile compiles both):

1. The first is a simple Tic-Tac-Toe application of MCTS that I used to mainly debug and develop the MCTS algorithm.
2. The second is its application to Quoridor, a zero-sum two-player strategy game with a notoriously high average branching factor (more than Chess but less than Go). After some experimenting (especially with the rollouts) I believe I ended up with a fairly competent agent although there is definitely room for further tuning: a trade-off must be made between lightweight random rollouts and heavier rollouts with smarter actions taken.
