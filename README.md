# pubtcrs

<a href="https://hub.docker.com/r/pbradley/pubtcrs/">
  <img src="https://img.shields.io/docker/build/pbradley/pubtcrs.svg" alt="Docker Build Status">
</a>

This repository contains C++ source code for the TCR clustering and correlation analyses described in the manuscript "Human T cell receptor occurrence patterns encode immune history, genetic background, and receptor specificity" by William S DeWitt III, Anajane Smith, Gary Schoch, John A Hansen, Frederick A Matsen IV and Philip Bradley.

At the moment (version 0.1), the code is specialized for beta-chain repertoire analysis and uses a TCR representation that includes the V-gene family and the CDR3 sequence (for example, "V19,CASSIRSSYEQYF"). We plan on extending to the alpha chain and adding other TCR representations in the future.

- `pgen` computes TCR generation probabilities.

- `tcrdists` computes TCR-TCR sequence distances using the TCRdist measure

- `neighbors` computes TCR-TCR neighbor relations based on co-occurrence and sequence similarity. It can also perform DBSCAN clustering if desired.

- `correlations` computes TCR-feature correlation p-values for user-defined features.

# REQUIREMENTS

This software depends on header files included with the BOOST C++ library. You can download the library here:

<https://www.boost.org/users/download/>

# COMPILING

Edit the "BOOSTDIR" line in the Makefile to point to the location where your BOOST download is installed. Then type `make`. The binary executable files will be placed in the `bin/` directory.

# THANKS

We are using the TCLAP header library for parsing command line arguments. As suggested by the TCLAP docs, we have included the header files within this repository for ease of compiling. Please see the author and license information in `include/tclap/`

http://tclap.sourceforge.net/

# TESTING

There are some simple bash scripts that run simple tests in the `test/*/` directories. To run them all:

```
cd test/
./runall.bash
```

