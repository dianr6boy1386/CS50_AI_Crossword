# CS50 AI Crossword

## By Dyan Ahmadi

A constraint satisfaction problem solver that generates crossword
puzzles from a given structure and word list.

The project uses constraint satisfaction techniques to assign words to
crossword variables while satisfying word length and letter intersection
constraints.

## Features

-   Enforces word length constraints with node consistency.
-   Enforces intersection constraints with arc consistency using AC-3.
-   Uses backtracking search to find a complete solution.
-   Selects variables using the Minimum Remaining Values heuristic.
-   Uses degree as a tie-breaker when selecting variables.
-   Orders domain values using the Least Constraining Value heuristic.
-   Prints completed crosswords directly in the terminal.
-   Can save completed crosswords as image files.

## Project Structure

``` text
crossword/
├── assets/
│   └── fonts/
│       └── OpenSans-Regular.ttf
├── data/
│   ├── structure0.txt
│   ├── structure1.txt
│   ├── structure2.txt
│   ├── words0.txt
│   ├── words1.txt
│   └── words2.txt
├── crossword.py
├── generate.py
└── README.md
```

## How It Works

The solver models the crossword as a Constraint Satisfaction Problem.

Each crossword entry is represented as a variable. The domain of each
variable contains possible words. Constraints come from the length of
each entry and the intersections between entries.

The solver follows these main steps:

1.  Initialize a domain of possible words for every crossword variable.
2.  Enforce node consistency by removing words with incorrect lengths.
3.  Apply AC-3 to enforce arc consistency between intersecting
    variables.
4.  Select an unassigned variable using Minimum Remaining Values and
    degree.
5.  Try domain values using the Least Constraining Value heuristic.
6.  Use backtracking to continue searching until a complete consistent
    assignment is found.

## Requirements

Python 3 is required.

The image-saving functionality requires Pillow.

Install Pillow with:

``` bash
pip install pillow
```

## Running the Solver

From the project directory, run:

``` bash
python generate.py data/structure0.txt data/words0.txt
```

You can also use the other provided datasets:

``` bash
python generate.py data/structure1.txt data/words1.txt
python generate.py data/structure2.txt data/words2.txt
```

## Saving the Solution

To save the generated crossword as an image:

``` bash
python generate.py data/structure0.txt data/words0.txt output.png
```

The generated image will be saved using the filename provided as the
third argument.

## Technologies

-   Python
-   Constraint Satisfaction Problems
-   Backtracking Search
-   Node Consistency
-   Arc Consistency
-   AC-3
-   Minimum Remaining Values
-   Degree Heuristic
-   Least Constraining Value
-   Pillow

## Course

This project is part of CS50's Introduction to Artificial Intelligence
with Python.
