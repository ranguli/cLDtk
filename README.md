# cLDtk
C99 loader for the [LDtk](https://ldtk.io/) map editor, using [Parson](https://github.com/kgabis/parson) for JSON parsing.

This is a fork of the [original](https://github.com/PompPenguin/cLDtk) by PompPenguin. This forks builds the library with CMake (see [Getting Started](#getting-started)). For future plans, see [Roadmap](#roadmap)

## Documentation

There original author of cLDtk wrote some [examples](https://github.com/ranguli/cLDtk/tree/main/examples) (including for Raylib!) which should useful for gaining a basic understanding of how the library works. 

I'd like to add API documentation using Doxygen at some point in the future.

## Getting Started

The easiest way to add cLDtk to a CMake project is to use `FetchContent`. It will automatically download and build the project for you when you run `cmake`.

```cmake
# CMakeLists.txt
include(FetchContent)
set(FETCHCONTENT_QUIET FALSE)

# Adding cLDtk
FetchContent_Declare(
    cLDtk 
    GIT_REPOSITORY "https://github.com/ranguli/cLDtk.git"
    GIT_TAG "main"
    GIT_PROGRESS TRUE
)

FetchContent_MakeAvailable(cLDtk)
```

Keep in mind that the `main` branch might not be stable, and you may be better off using a release tag. 

Then you'll be able to link `cLDtk` in CMake using:

```cmake

target_link_libraries(my-cool-project PRIVATE cLDtk)

```


## Building

Assuming you don't want to use the method mentioned above of directly fetching and building CLDtk as a dependency in your `CMakeLists.txt` file, you can also build it using the standard 'clone and make' approach:
``` 
git clone https://github.com/ranguli/cLDtk
cd cLDtk
mkdir build && cd build
cmake .
make
```

## Roadmap
- [x] Building with CMake instead of `gcc` commands
- [ ] API documentation with Doxygen
- [ ] Integrate GitHub actions for builds
- [ ] Start versioning the project (i.e releases)
- [ ] Code cleanup / refactoring
