# Klotski-Solver
This program solves the Klotski(Hua Rong Dao) sliding puzzle game with ten pieces on a board that is 4 spaces wide and 5 spaces tall.

## Puzzle Description
The puzzle consists of the following ten pieces:

- One 2x2 piece. (called Cao Cao in Hua Rong Dao)
- Five 1x2 pieces placed horizontally or vertically.
- Four 1x1 pieces.

Once the ten pieces are placed on the board, two empty spaces should remain. The goal is to move the pieces until the 2x2 piece is above the bottom opening, allowing Cao Cao to escape through the Hua Rong Dao/Pass.

## Program Description
The program(source code) implements the following search algorithms:

- Depth-first search
- A* search
- It also includes the implementation of two heuristic functions for A* search:
  - Manhattan distance heuristic
  - Advanced heuristic function (admissible and dominates the Manhattan distance heuristic -- see the pdf file)
  
The program takes an input file that contains the initial board configuration and outputs the solutions found by DFS and A* to two separate plain text output files, in a specified format that willl be described below.

How to Run
To run the program, use the following command:

`python3 hrd.py <input file> <DFS output file> <A* output file>`

For example, to solve puzzle 5 with the input file "puzzle5.txt", the command would be:

`python3 hrd.py puzzle5.txt puzzle5sol_dfs.txt puzzle5sol_astar.txt`

The DFS solution will be stored in "puzzle5sol_dfs.txt" and the A* solution will be stored in "puzzle5sol_astar.txt".

## Input Format
The input file should be a plain text file containing the initial configuration of the Hua Rong Dao puzzle. The format should follow these rules:

- The file should have 5 rows and 4 digits per row.
  - Use 0 to represent empty squares.
  - Use 7 to represent single pieces.
  - Use 1 to represent the 2x2 piece.
  - Use one of {2, 3, 4, 5, 6} to represent the 5 1x2 pieces (numbers are assigned at random).

For example:

2113<br />
2113<br />
4665<br />
4775<br />
7007<br />

## Output Format
The program outputs two plain text files containing the DFS and A* solutions, respectively. The format of the output files should match the following rules:

- The first line should indicate the cost of the solution.
- Each subsequent line represents a state of the puzzle, with two consecutive states separated by an empty line.
  - Use 0 to represent empty squares.
  - Use 4 to represent single pieces.
  - Use 1 to represent the 2x2 piece.
  - Use 2 to represent horizontal 1x2 pieces.
  - Use 3 to represent vertical 1x2 pieces.

For example:


Cost of the solution: 116<br />
3113<br />
3113<br />
3223<br />
3443<br />
4004<br />
<br />
3113<br />
3113<br />
3223<br />
3443<br />
0404<br />
<br />
3113<br />
3113<br />
3223<br />
3443<br />
0440<br />
