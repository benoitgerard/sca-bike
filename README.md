# Side-Channel Analysis of BIKE

This repository aims at containing elements to reproduce experiments from

"BIKE Key-Recovery: Combining Power Consumption Analysis and Information-Set Decoding"

published at ACNS conference in 2023.

## Disclaimer

Scripts are dedicated to the reproduction of the published results and are not
expected to be ran for other usage. This includes the following restrictions.

  1. The scripts are not expected to allow someone to attack some real-world implementation.
     This is a research project and no time has been spent to make anything generic.
     Scripts are only expected to work on the specific target that has been used
     in this work. Especially, trace pre-processing is not fully automated and
     is strongly linked to the experimental setup.

  2. The scripts have not been extensively tested on different platforms or in very
     specific environments. Authors decline any responsibility in the case where
     running the script would have some negative impact on the system. Indeed,
     some I/O operations in a working directory are performed to store temporary
     data. These operations are not handled in a "professionally secure way" that
     is ensuring that any unexpected behaviour will have no impact on the system.

Put another way: this is research work provided to the community to help
reproducibility and further works on the topic. This *is not* an industrial
product with an official support.

## Requirements

The attack is composed of two main steps.

  1. First, one recovers information from a power consumption measurement.
  2. Second, Prange information set decoding algorithm is fed with the obtained
     information to recover the secret key.

While the trace processing (first step) is performed using python scripts (and
here is detailed in jupyter notebooks), the second step of key recovery is a C++
program based on `NTL` library. The full list of requirements is given below.

### Python part

Here are the required packages to be able to run our notebooks.
  - built-in modules as `sys` or `os`,
  - `numpy`,
  - `scipy`,
  - `matplotlib`.

### C++ part

The `NTL` library in version 11.5.1.

## Branches and Versions

The repository is organised in a classical main/dev fashion.

### Main Branch

The main branch is expected to contain a commit tagged "acns23" corresponding
to the necessary material for reproducing experiments from the ACNS paper.
In case additional material is developed to go beyond the publication, it may be
made available in further commitments.

### Dev Branch

As expected from a development branch, the dev branch will contain pieces of scripts
used by authors that are being incorporated to the git but not yet clean (or tested)
enough to be integrated to the master branch.
Do not hesitate to take a look at this branch and the commit description but
remember it is in a development state.

### Tags

Currently there is no tag in the main branch: the code is being added to the dev
branch while being cleaned and organized for publication. At the point where
authors will have processed all the scripts they used, a commit with tag "acns23"
will be added to the master branch and documented in this readme file.

## Raw Experimental Data

To ease reproducibility, the curves used to run the notebooks of this repository can be found on zenodo (link below).

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.8010188.svg)](https://doi.org/10.5281/zenodo.8010188)

## Content

The repository contains the following files.

### Single-Trace Key Recovery

A notebook in which we present the full attack on a given curve.
The full attack path is performed for the reader to see its global scheduling.
Details on how each step is performed can be found in dedicated notebooks.

### Outer-Iterations Detection

In this notebook we detail the technique used to detect the outer-iterations that
is the iterations of the outer loop of the decoding algorithm.
This is the first step of the attack.
