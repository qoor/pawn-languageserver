# pawn-ls
This project is the implementation of language server for PAWN Language.

## Features
- [ ] Code Completion
- [ ] Hover
- [ ] Signature
- [ ] Diagnostic

## Requirements
- CMake version 3.11 or higher
- C compiler
- C++ compiler that supports C++17 standards or higher

## Getting Started
1. Clone this repo
```shell
git clone https://github.com/qoor/pawn-ls.git
```

2. Generate build files using CMake
```shell
# In the top-level directory of this project.
# Note that DO NOT name the build directory 'build'.
# You can use any build system to build.
# Example:
cmake -G "Ninja" -S . -B out
```

3. Build binaries
```shell
# using CMake
cmake --build out
# or build system
# Example:
ninja -C out
# or
cd out && ninja
```

## Contribute
This project is follow the [Google C++ Style Guide](https://google.github.io/styleguide/cppguide.html) unless it is a `third_party`.

All codes in `third_party` uses their style.

## License
pawn-ls is licensed under [2-clause BSD](LICENSE).
