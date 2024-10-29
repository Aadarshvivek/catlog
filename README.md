Here's a README file you can use for your GitHub repository for this assignment:

---

# Catalog Placements Assignment - Online

## Overview

This repository contains a solution for a simplified implementation of **Shamir's Secret Sharing** algorithm as part of a coding assignment. The goal is to find the constant term, `c`, of an unknown polynomial given in specific test cases.

## Problem Statement

The task involves solving for the constant term, `c`, of a polynomial represented by the following structure:

\[ f(x) = a_m x^m + a_{m-1} x^{m-1} + ... + a_1 x + c \]

Where:
- `m` is the degree of the polynomial.
- `c` is the constant term to be found.

The polynomial's points are provided in JSON format, with x-values and encoded y-values that are in various numeric bases. This requires decoding the y-values into decimal format, using a minimum of `k` points to determine the polynomial coefficients. 

### Input Format

The input is provided in a JSON file. Each test case contains:
- `n`: The number of points (x, y) provided.
- `k`: The minimum number of points needed to find the polynomial coefficients (using interpolation).

Each point is structured as follows:
```json
"x_value": {
    "base": "numeric_base",
    "value": "encoded_y_value"
}
```

### Output

For each test case, the program should output the constant term, `c`, of the polynomial.

## Solution Approach

1. **Parse JSON Input**: Read the test cases from a JSON file.
2. **Decode y-values**: Convert the y-values from their given base to decimal.
3. **Apply Polynomial Interpolation**: Use Lagrange interpolation or a similar method to calculate the polynomial coefficients.
4. **Extract the Constant Term (c)**: Once the polynomial is formed, retrieve the constant term.

### Assumptions and Constraints

- The coefficients are positive integers within the range of a 256-bit number.
- The provided points (n) will always be greater than or equal to the required minimum points (k).
- The degree of the polynomial (m) is determined by `m = k - 1`.

## Sample Input

```json
{
    "keys": {
        "n": 4,
        "k": 3
    },
    "1": {
        "base": "10",
        "value": "4"
    },
    "2": {
        "base": "2",
        "value": "111"
    },
    "3": {
        "base": "10",
        "value": "12"
    },
    "6": {
        "base": "4",
        "value": "213"
    }
}
```

## Sample Output

```plaintext
Constant term (c): <calculated_value>
```

## Implementation Details

- **Language:** Any language except Python.
- **Approach:** Polynomial interpolation using Lagrange’s formula or other polynomial coefficient solving methods.

## How to Run

1. Clone this repository.
2. Open the project in an IDE of your choice.
3. Make sure to have the test JSON file in the root directory.
4. Run the main file to calculate the constant term, `c`.

## Example Usage

```bash
# Assuming the main file is written in Java, compiled, and run with:
java Main input.json
```

## Notes

- **Testing Environment:** Any IDE or environment can be used.
- **Duration:** The assignment is designed to be completed within 70 minutes.
- **Submission:** Push your solution to a GitHub repository and submit the link along with your output.

---

