The DUT has been [cloned from the cryptech.is project site] (https://git.cryptech.is/core/hash/sha3.git).

[tiny_sha3](https://github.com/mjosaarinen/tiny_sha3.git) implementation is used as a reference model to check the RTL DUT for any functional discrepancy that might exist in the RTL implementation.

An AXI4 lite wrapper has been created around the DUT.

## Required Software
1. Icarus Verilog version 10.2 or newer
2. Emabedded UVM downloadable from http://uvm.io/download

To run the simulation just go to the checked-out directory and type `make run` on a bash prompt.
