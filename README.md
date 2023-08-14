# cLDtk
C99 loader for the [LDtk](https://ldtk.io/) map editor, using [Parson](https://github.com/kgabis/parson) for JSON parsing.

This is a fork of the [original](https://github.com/PompPenguin/cLDtk) by PompPenguin. This forks builds the library with CMake (see [Getting Started](#getting-started)). For future plans, see [Roadmap](#roadmap)

## Documentation

There original author of `cLDtk` wrote some [examples](https://github.com/ranguli/cLDtk/tree/main/examples) (including for Raylib!) which should useful for gaining a basic understanding of how the library works. 

I'd like to add API documentation using Doxygen at some point in the future.

## Getting Started

The easiest way to add `cLDtk` project is to add the files in the `src/` directory (`cLDtk.c`, `cLDtk.h`, `parson.c`, `parson.h`) into your project. Keep in mind that the
files on the `main` branch might not be stable, and you may be better off using a release tag. 

## Building

The building workflow for cLDtk is the standard 'clone and make' approach. Make sure you have `cmake` installed.

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
