# CKY and Earley Parsing Algorithms

This notebook explores two fundamental parsing algorithms in Natural Language Processing (NLP): the CKY algorithm and the Earley algorithm.

## Overview

The notebook provides implementations and explanations of both algorithms:

- **CKY Algorithm:** A bottom-up, dynamic programming approach used for parsing sentences with context-free grammars (CFGs) in Chomsky Normal Form (CNF).
- **Earley Algorithm:** A more general parsing algorithm that can handle any CFG, including those with ambiguity and null productions.

## Contents

- **CKY Parsing:**
    - Implementation of the CKY algorithm in Python.
    - Example usage with a sample grammar and sentence.
    - Explanation of the algorithm's steps and complexity.
- **Earley Parsing:**
    - Base case and general case implementations of the Earley algorithm.
    - Explanation of the algorithm's chart, states, and operations (predictor, scanner, completer).
    - Comparison of Earley and CKY algorithms.
