# Side-Channel Analysis of BIKE

This repository aims at containing elements to reproduce experiments from

"BIKE Key-Recovery: Combining Power Consumption Analysis and Information-Set Decoding"

published at ACNS conference in 2023.

## Disclaimer

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

To ease reproducibility, some acquired data will be made available on a data sharing
platform. The choice of the platform is not made yet: this section of the readme
will eventually be updated accordingly.

