# ARCHIVED: USE advent-of-code instead

This repo has been archived use https://github.com/matt-gretton-dann/advent-of-code instead, which contains multiple years of Advent of Code.

# C++ Solutions to Advent of Code 2021

This repository contains solutions to the [Advent of Code 2021](https://adventofcode.com/2021)
Advent puzzles.  All solutions are written in C++.  The solutions aren't designed to be nice or
pretty.  Instead, I am using it as an experiment in understanding how I approach solving
problems.

Each Puzzle lies in its own directory named `puzzle-<day>-<number>`.

The solutions are authored by Matthew Gretton-Dann, and Copyright 2021, Matthew Gretton-Dann.  Licensed under Apache 
2.0 - see [license](./LICENSE).

## Running Puzzles

To run each puzzle do the following.

```sh
git clone https://github.com/matt-gretton-dann/advent-of-code-2021/
cd advent-of-code-2021
DAY=01 # Puzzle day number
PUZZLE=1 # Puzzle ID (1 or 2)
INPUT=input1.txt # Path to input to use
./driver $DAY $PUZZLE $INPUT
```

The steps above will rebuild the puzzle code each time.

## Building

To build the puzzles without running them invoke cmake as follows:

```sh
git clone https://github.com/matt-gretton-dann/advent-of-code-2021/
cd advent-of-code-2021
cmake -Bbuild -S. # Note the driver script also uses build.
cmake --build build
```

## Sources

All code is written in C++.

### Directory Layout

Each puzzle is in a self-contained directory `puzzle-DAY-NUMBER`, or `puzzle-DAY` if the same code can be used to 
solve both puzzles.  `DAY` is a two digit zero padded number, and `NUMBER` is either `0` or `1`.  

Within the directory there are the following files:

 * Mandatory: `CMakeLists.txt` which contains the build instructions.  Executable should be called the same as the 
   parent directory (so `puzzle-DAY-NUMBER` or `puzzle-DAY`).  See below for the expected command-line interface.
 * `input-DAY-NUMBER.txt`.  The example given in the problem description which a solution is wanted for.  *Note*: 
   That the number is present even if this is a `puzzle-DAY` directory.
 * Optional: `driver`.  Driver program to use if you can't just call the executable.  See below for command line
   interface.
 * Optional: `*.cc`: C++ sources.

### Command Line Interface

The executable command line interface should just take the input in on standard-input and print its
result on standard-output.

If this is not possible an executable script `driver` within the directory should be provided.  It should take two 
arguments - the executable to run and the input file to use.
