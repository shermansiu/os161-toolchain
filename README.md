# os161-toolchain
An updated version of the latest OS/161 toolchain that compiles!

The original source code was taken from: [here](http://os161.eecs.harvard.edu/download/).

The installation instructions are [here](http://os161.eecs.harvard.edu/resources/setup.html).

Patches applied/resources consulted:
- GCC:
  - `cfns.gperf:101:1: error: ‘const char* libc_name_p(const char*, unsigned int)’ redeclared inline with ‘gnu_inline’ attribute`:
    - https://stackoverflow.com/questions/41204632/unable-to-build-gcc-due-to-c11-errors
  - Broken t-scan test:
    - https://github.com/wbhart/mpir/issues/20
  - Missing GMP, MPFR, MPC:
    - https://stackoverflow.com/questions/9253695/building-gcc-requires-gmp-4-2-mpfr-2-3-1-and-mpc-0-8-0
- GDB:
  - sim_addr_range_hit_p defined multiple times:
    - Solution: move the inline function definition from sim-arange.c into sim-arange.h. (Referenced, but not solved [here](https://sourceforge.net/p/mspgcc/mailman/mspgcc-users/thread/5620133A.1030001%40serebryakov.spb.ru/):)

The code was compiled to ~/os161-support/tools/.
