# Rubik's Race Automated Strategy and Solver

## Introduction

The Rubik’s Race challenge resembles the 24-puzzle problem, involving the movement of individual tiles by a single position at a time. In the Rubik’s Race scenario, the goal is to generate a pattern across the 24 tiles matching the pattern within the goal state box. To address this challenge and achieve the desired pattern alignment, we employ the Iterative Deepening A* (IDA*) algorithm.

## Algorithm Design

Iterative Deepening A* (IDA*) is a graph traversal and pathfinding algorithm. Its purpose is to find the shortest path between a starting node and a set of goal nodes. IDA* combines elements of iterative deepening depth-first search and the A* search algorithm. It focuses on exploring promising nodes to optimize memory usage and employs a heuristic function, f(n) = g(n) + h(n), to estimate the cost.

IDA* differentiates from regular iterative deepening search by its ability to find optimal solutions. It prunes branches with costs exceeding a threshold and incrementally increases the threshold in each iteration, ensuring the shortest path is found.

## Heuristics

In our implementation, we use the Manhattan distance and misplaced tile heuristics during the construction of the pattern database. For color assignment in Rubik’s Race to the 24 puzzle, we rely on the Euclidean distance heuristic.

## Implementation

### Generating the Pattern Database

For the Rubik’s Race board, we transform it into a 25-puzzle board, focusing on the central 3x3 positions. We represent the empty block with 0 and assign a value of 1 to the remaining positions. We create groups of positions to explore different permutations, with the {7, 8, 9, 1}, {12, 13, 14, 1}, {17, 18, 19, 1} group selected for its speed and efficiency.

We utilize the breadth-first search algorithm to traverse every configuration of marked tiles within the blank spaces for each group, optimizing exploration.

### Matching 25 Puzzle Board Tiles to Rubik Race Tiles

To align the central 3x3 pattern of the 25-puzzle board with the Rubik’s Race board, we employ the Euclidean distance metric. This metric helps us identify the closest tiles in the 5x5 puzzle board to the corresponding pattern within the central 3x3 region. We assign the numbers 7, 8, 9, 12, 13, 14, 17, 18, 19, 1 to the respective colors on the Rubik’s Race board.


https://github.com/anupam-sharma-1/rubik_race/assets/13178379/30502272-c3c8-47f0-b388-54bd625abe09


By implementing these strategies and algorithms, we aim to optimize the solution for Rubik’s Race and address the challenges posed by this unique puzzle game.
