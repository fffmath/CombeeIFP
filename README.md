# CombeeIFP

Code for the paper [“Solving Modular Linear Equations via
Automated Coppersmith and its Applications"](https://inscrypt2024.github.io/).

## Introduction

This is a Python implementation of G-EIFP based on [GIFP](https://github.com/fffmath/GIFP).

## Requirements

- [SageMath](https://www.sagemath.org/) with Python 3.11.1. SageMath 9.8 is recommended.

  You can check your SageMath Python version using the following command:

```bash
$ sage -python --version
Python 3.11.1
```

Note: If your SageMath Python version is older than 3.11.1, some features in some scripts might not work.

## Usage

Usage: sage eifp.sage `<modulus_bit_length>` `<alpha>` `<gamma>` `<delta>` `<beta1>` `<beta2>` `<m>`

For example

```bash
# Run experiments with modulus_bit_length set to 200.
sage eifp.sage 200 0.1 0.7 0.05 0.1 0.15 4
```

If the roots are successfully found, it returns 1; otherwise, it returns 0. The corresponding time for computing LLL and computing Grobner basis can be found in the `eifp.log` file.

### Debug

You can enable debugging by setting `logging.basicConfig(filename='gifp.log', level=logging.DEBUG, format='%(asctime)s - %(levelname)s - %(message)s')` in your code.

### Precautions

Like GIFP, we also introduces a new variable, 'w', to eliminate some 'z', which makes it more challenging to satisfy the Grobner basis Heuristic. However, in practice, it is not necessary to satisfy the Grobner basis Heuristic to find the desired 'p' and 'q'. We can use a combination of Grobner basis and gcd to compute the desired roots. Detailed anaysis can be bound in [GIFP-README](https://github.com/fffmath/GIFP/blob/master/README.md). Here we provide an example in [Example.md](Example.md)

### Author

You can find more information on [my personal website](https://www.fffmath.com/).

### License

This script is released under the MIT License. See the [LICENSE](LICENSE) file for details.
