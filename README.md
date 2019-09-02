# EOS-compiler-options

This repo will preserve a number of compiler options for `eosio-cpp` in order to (1) optimize code size (RAM saving), (2) optimize performance (CPU saving).

At the moment `eosio-cpp -Os -finline-hint-functions -fno-elide-constructors -O2` proves to be one of the most efficient options for RAM saving.
