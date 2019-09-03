# EOS-compiler-options

This repo will preserve a number of compiler options for `eosio-cpp` in order to (1) optimize code size (RAM saving), (2) optimize performance (CPU saving).

At the moment `eosio-cpp -abigen -finline-functions -fno-elide-constructors -Oz` proves to be one of the most efficient options for RAM saving.

### VSC EosFactory RAM-saving setup

c_cpp_properties.json

```json
{
    "configurations": [
        {
            "includePath": [
                "/usr/local/eosio.cdt/include",
                "/usr/local/eosio.cdt/include/libcxx",
                "/usr/local/eosio.cdt/include/eosiolib/core",
                "/usr/local/eosio.cdt/include/eosiolib/contracts",
                "${workspaceFolder}",
                "${workspaceFolder}/include"
            ],
            "libs": [],
            "codeOptions": [
                            "-abigen",
                            "-finline-functions",
                            "-fno-elide-constructors",
                            "-Oz"
                        ],
            "testOptions": [],
            "defines": [],
            "intelliSenseMode": "clang-x64",
            "browse": {
                "path": [
                    "/usr/local/eosio.cdt/include",
                    "/usr/local/eosio.cdt/include/libcxx",
                    "/usr/local/eosio.cdt/include/eosiolib/core",
                    "/usr/local/eosio.cdt/include/eosiolib/contracts",
                    "${workspaceFolder}",
                    "${workspaceFolder}/include"
                ],
                "limitSymbolsToIncludedHeaders": true,
                "databaseFilename": ""
            }
        }
    ],
    "version": 4
}
```
