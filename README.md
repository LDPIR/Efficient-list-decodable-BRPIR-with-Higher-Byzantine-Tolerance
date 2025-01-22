# Introduction
The ldBRPIR project includes benchmarking of the ldBRPIR scheme introduced in the manuscript "List-Decodable Byzantine Robust PIR: Lower Communication Complexity, Higher Byzantine Tolerance, Smaller List Size".

**What this codebase includes**: example and benchmark implementations in C++ for some of the schemes in the manuscript.

**What this codebase is not**: it is not for production use; it is not extensively tested.

# Platforms
In the draft, we measure the performance of our scheme on a computer with a 16-core intel Xeon Gold 6250 CPU @ 3.90GHz and 256 GB RAM, running Ubuntu 20.04. 
All of our experiments are single-threaded. 

## Setup and Building Instructions

First, install the library [FLINT 3.1.2](https://flintlib.org/downloads.html)) and [GMP 6.2.1](https://gmplib.org/#DOWNLOAD) required by this codebase. On several Ubuntu systems this can be done directly through the links above.

To build library and executables:
```shell
mkdir build
cd build
cmake ..
make
```

To try an example, run e.g.:
```shell
2025_list_decodable/2025_list_decodable
