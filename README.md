# MCAP CMake Builder

This repo provide a wrapper to build and install [MCAP](https://github.com/foxglove/mcap) via CMake.

## Build

To build and install simply run:
```bash
$ cd mcap_build
$ mkdir build && cd build
$ cmake ../ && make install
```
you can change the install folder by setting `CMAKE_INSTALL_PREFIX` (as for any CMake project). 

## Usage
To include MCAP in your library first you need to add it to your CMake:
```cmake
find_package(mcap)

target_link_libraries(<target> PUBLIC mcap)
```

and in your code, you can include `reader.hpp` or `writer.hpp`. 


### Macros
* Do not add `MCAP_IMPLEMENTATION` macro, as that is handled for you by this wrapper.
* This Cmake wrapper automatically detect if `LZ4` and `zstd` are available, and
  * if present, links them to the `mcap` library
  * if they are not present automatically define `MCAP_COMPRESSION_NO_LZ4` and `MCAP_COMPRESSION_NO_ZSTD` 




