Net Solver
==========

An [OpenCV](https://opencv.org/) based C++ program for solving a Net puzzle from a captured board image. **Net** is one of many puzzles from [Simon Tatham's puzzle collection](https://www.chiark.greenend.org.uk/~sgtatham/puzzles/).

**THIS IS A WORK-IN-PROGRESS REPOSITORY**

Requirements
------------

- GCC 11.2 or higher
- CMake 3.20 or higher
- OpenCV 4.5 or higher

Installation
------------

Use CMake to build binaries

    mkdir -p build
    cd build
    cmake ..
    make && make install
    cd ..
    ./bin/ngsolver board.png

License
-------

© 2021 Zobayer Hasan.

Open sourced under MIT license, the terms of which can be read here — [MIT License](./LICENSE).
