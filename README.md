# Computational Theory SHA-256 Implementation
**By Karolis Bandziulis** <br>
**Student ID:** G00417529 <br>
**Module:** Computational Theory <br>
**Language:** Python 3.12.5 <br>

## Overview
This repository is a learning journal that contains a comprehensive implementation and analysis of the Secure Hash Algorithm 2 (SHA-256).

This project was completed in five core steps:

1. **Binary Operations:** Implementation of the fundamental bitwise logic (Ch, Maj, Sigma) required for the compression function, utilizing a custom Metaclass for strict type enforcement.
2. **Constant Generation:** Calculation of the 64 round constants ($K$) derived from the fractional cube roots of primes.
3. **Message Padding:** Development of a preprocessing module to format messages into 512-bit blocks, using Python Generators for memory-efficient stream processing.
4. **Hash Computation:** Integration of the message schedule and compression loop to build the full hashing function, validated against the standard hashlib library.
5. **Security Analysis:** A practical investigation into password security, using Rainbow Tables to successfully reverse hashes and demonstrate the vulnerability of unsalted passwords.

## Code Quality & Linting
This project is linted and formatted using [Ruff](https://docs.astral.sh/ruff/), the modern standard for Python code quality.
- Ruff was selected over legacy tools like [Flake8](https://flake8.pycqa.org/en/latest/) specifically for its superior handling of Jupyter Notebooks.
    - **Native .ipynb Support:** Unlike [Flake8](https://flake8.pycqa.org/en/latest/) which requires wrapper tools like [nbqa](https://nbqa.readthedocs.io/en/latest/) to parse a notebook, Ruff natively understands the cell structure of Jupyter notebooks.
    - **Context Aware:** Ruff minimizes false positives by understanding the difference between notebook cells and standard script files, ignoring issues that arise from scripting within a .ipynb notebook.
        - If you attempt to lint this notebook with [Flake8](https://flake8.pycqa.org/en/latest/) you may encounter errors that are ill-suited for .ipynb notebooks, as [Flake8](https://flake8.pycqa.org/en/latest/) lacks context.

## Requirements
This project relies on [hashlib](https://docs.python.org/3/library/hashlib.html) for validation, comparing the output of my custom implementation against the standard library.
Upon testing, [hashlib](https://docs.python.org/3/library/hashlib.html) behavior may vary across environments. To ensure this notebook and its implementation work exactly as expected, please use ``Python 3.12.5``.

### Install Dependencies
This project uses the following dependencies:
- **Standard Library:** unittest, math, hashlib
- **External Libraries:** numpy

### How To Run
1. Clone this repository
````
git clone https://github.com/KarolisBz/computational-theory-assessment-G00417529.git
cd computational-theory-assessment-G00417529
````

2. Install dependencies
````
pip install numpy notebook
````

3. Launch Jupyter notebook
````
jupyter notebook
````

4. Execute the Project
    - Open ``problems.ipynb`` from the interface and run all cells sequentially from top to bottom.

## References
All references are mentioned inline or in markdown at [problems.ipynb](problems.ipynb) to provide the context in which they are used in.

- [Unittest](https://docs.python.org/3/library/unittest.html)
- [Type aliases](https://docs.python.org/3/library/typing.html)
- [Int truncation](https://docs.python.org/3/library/functions.html#int)
- [FIPS 180-4: Secure Hash Standard](https://nvlpubs.nist.gov/nistpubs/FIPS/NIST.FIPS.180-4.pdf)
- [numpy.floor](https://numpy.org/devdocs/reference/generated/numpy.floor.html)
- [All() Built in function](https://docs.python.org/3/library/functions.html)
- [Docstring Conventions](https://peps.python.org/pep-0257/)
