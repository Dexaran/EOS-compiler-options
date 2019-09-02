# EOS-compiler-options

This repo will preserve a number of compiler options for `eosio-cpp` in order to (1) optimize code size (RAM saving), (2) optimize performance (CPU saving).

At the moment `eosio-cpp -Os -finline-hint-functions -fno-elide-constructors -O2` proves to be one of the most efficient options for RAM saving.

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
            "codeOptions": [ "-Os",
                             "-finline-hint-functions",
                             "-fno-elide-constructors",
                             "-O2"
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
