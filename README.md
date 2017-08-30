# Comparison of [Lyra2][1] and [lyra2-java][2]

This repository provides a performance comparison between the original C implementation of Lyra2 and its Java port. Lyra2 is a memory-hard password hashing scheme which allows its user to configure both memory and processing time required to compute the hash. The original repository for Lyra2 can be [found here][3].

The gist of the comparison: the Java version is slower and requires more memory. This happens because the Java version has to perform extra steps to produce exactly the same results as the original C implementation. These include explicit endianness conversion and explicit modulo/remainder computations for unsigned 64 bits integers. Without these extra steps different hashes are produced for the same input parameters but significant speed-up is achieved.

 ![alt text](https://raw.githubusercontent.com/all3fox/lyra2-compare/master/src/figures/mcost_256.png )

  ![alt text](https://raw.githubusercontent.com/all3fox/lyra2-compare/master/src/figures/tcost_256.png )

[1]: https://github.com/all3fox/Lyra
[2]: https://github.com/all3fox/lyra2-java/
[3]: https://github.com/leocalm/Lyra
