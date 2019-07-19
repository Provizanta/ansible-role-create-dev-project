

## Build
CMake defaultly generates `Makefiles`. Alternatively, `Ninja` generator can be used as (requires ninja build tools):

    cmake .. -G Ninja

In order to set a language specific compiler or custom linker, these can be passed to CMake as:

    cmake .. -DCMAKE_C_COMPILER=clang-3.6 -DCMAKE_CXX_COMPILER=clang++-3.6 -DCMAKE_LINKER=gold

### Build type
Build types determine which compiler flags should be added on compilation, supported build types:
  * `Release`
  * `Debug`
  * `MinSizeRel`
  * `RelWithDebInfo`

The desired build type can be passed in as In order to obtain the desired build type,

    cmake .. -DCMAKE_BUILD_TYPE=Release     # pass in the build type

#### Explicitly pass flags
Any additional compiler/linker flag can be passed in configuration phase:

    cmake .. -DCMAKE_C_FLAGS="-DEX3"        # pass a flag to the compiler
    cmake .. -DCMAKE_CXX_FLAGS="-DEX3"      # pass a flag to the compiler
    cmake .. -DCMAKE_LINKER_FLAGS="-lm"     # pass a flag to the linker

### Static analysis using Clang static analyzer
To run clang static analyzer prefix the `cmake` and `make` command with the `scan-build-X` command, which effectively overrides CC and CXX environment variables and replaces them with it’s own tools:

    scan-build-3.6 cmake ..
    scan-build-3.6 make

In order to select a specific compiler, use:

    scan-build-3.6 --use-cc=clang-3.6 --use-c++=clang++-3.6 -o ./scan_build_output/ make


## Install
Invoke the install target in order to install the project:

    make install

Explicit install directory for the installation can be passed as:

    make install DESTDIR=/tmp/dest	# creates the install path ${DESTDIR}/${CMAKE_INSTALL_PREFIX}


## Uninstall
Uninstall project:

    sudo xargs rm < install_manifest.txt
