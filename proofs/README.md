To run the SAW proofs, run `make verify` from this directory.

If `llvm-link` or `saw` are not in the path, you can specify their
locations with the `LLVM_LINK` and `SAW` variables to `make`.

Running `make` with no arguments will build the library appropriately
for use with SAW but skip the verification itself.
