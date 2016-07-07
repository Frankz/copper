# (Mis)Optimization

Surprise: Enabling optimizations (`--release`) optimizes away our whole program!

Solution:

- Split program into a library to avoid the aggressive pre-linking removal of symbols.
- Use volatile loads/stores to prevent the compiler from optimizing away/coalescing memory accesses.
- Add linker script assertions to avoid future misoptimizations.
