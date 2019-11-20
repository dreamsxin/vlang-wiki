V uses C as the primary backend. 

Many people find this choice strange, and one of the most common comments/suggestions is "Why not use LLVM?"

1. Using a C backend is a completely valid strategy (for example, the first C++ compiler Cfront did exactly this). C can be viewed as a modern cross-platform assembly language.
To the end user it doesn't really matter what intermediate step is used to generate their binary, as long as it works, and the performance is good. 

2. Easy bootstrapping and development. To bootstrap V, you need to download `v.c` and run `cc v.c`. That's it. No dependencies, no bootstrapping chains, nothing. The developers of the language don't need to work on two parallel implementations, new features can be introduced and used in the language right away.

V has been 100% written in V since the release:

<img width="1004" src="https://user-images.githubusercontent.com/687996/69198808-15876600-0b47-11ea-96f9-1bab32b8415f.png">



3. C gives us amazing platform support. C runs on everything, literally everything. LLVM supports lots of platforms and architectures, but it will never beat C. Being able to run V software on everything that C supports is huge.

4. Great tooling. Warnings, static analyzers, Valgrind, etc help to ensure that everything is correct. Writing programs that pass `-Wall -pedantic`, Clang analyzer, PVS, and result in zero Valgrind warnings/errors is a dream of any C/C++ developer. With V it's going to be guaranteed for every V program. (We are not there yet, but very close.)

5. Stability. New languages using LLVM directly are going to crash often. That's inevitable, and can be seen across all new languages using LLVM. The V compiler hasn't crashed once for me, and I haven't received any crash reports from other users.

6. Simplicity. LLVM is a huge C++ dependency, meaning that both developers of the language and the users are forced to install it. Calling C++ is not easy from V/C, so C wrappers have to be used, increasing the number of dependencies and complexities.

There is one clear drawback: you are limited by the capabilities of C. So far I've only faced some minor annoyances that could be easily overcome. Luckily V is a very small and simple language close to C.

By the time of the 1.0 release, V will also have direct x64 machine code generation (similar to TCC), but the C backend will always be available, for production builds and for all supported platforms.