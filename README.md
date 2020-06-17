# mussel
mussel is the shortest and fastest script available today to build working cross
compilers that target musl libc.

## Features
1. Up-to-date: uses latest available upstream sources for packages.
2. Fast: probably the fastest script around to build a cross compiler targetting
musl libc, also it's written entirely in POSIX DASH.
3. Short: has the least amount of steps (see below) required to build a cross
compiler targetting musl libc (even less than [musl-cross-make](https://github.com/richfelker/musl-cross-make)).
4. Small: all installation steps use `install-strip` when applicable.
5. POSIX Compliant: written entirely in POSIX DASH.
6. Well Documented: the script has comments (that are state of the art
information) all over the place explaining what is being done.

## Packages
1. `binutils`: 2.34
2. `gcc`: 10.1.0
3. `gmp`: 6.2.0
4. `isl`: 0.22.1
5. `mpc`: 1.1.0
6. `mpfr`: 4.0.2
7. `musl`: 1.2.0

## Patches
1. For `gcc`:
  * [Enable-CET-in-cross-compiler-if-possible.patch](https://raw.githubusercontent.com/glaucuslinux/glaucus/master/cerata/gcc/patches/upstream/Enable-CET-in-cross-compiler-if-possible.patch)
2. For `musl`:
  * [0002-enable-fast-math.patch](https://raw.githubusercontent.com/glaucuslinux/glaucus/master/cerata/musl/patches/qword/0002-enable-fast-math.patch)

## Additional Patches for `powerpc64`
3. For `musl`:
  * [0001-powerpc-support.patch](https://raw.githubusercontent.com/glaucuslinux/glaucus/master/cerata/musl/patches/glaucus/0001-powerpc-support.patch)
  * [0001-powerpc64-support.patch](https://raw.githubusercontent.com/glaucuslinux/glaucus/master/cerata/musl/patches/glaucus/0001-powerpc64-support.patch)

## Usage
1. Make sure you are in an empty directory
2. Run `./mussel.sh` (yup that's basically it)

## How is mussel doing it?
1. Configure `musl`, and only install its `headers`
2. Configure, build and install cross `binutils`
3. Configure, build and install cross `gcc` (without `libgcc`)
4. Build `musl`, and only install its `libs` and `tools`
5. Build, and install `libgcc`

## Optional Steps
* Build, and install `libstdc++-v3` (Enabled by default for C++ support)
* Build, and install `libgomp` (For OpenMP support, disabled by default)

## Credits and Inspiration
mussel is possible thanks to the awesome work done by Aurelian, [qword](https://github.com/qword-os), [The
Managram Project](https://github.com/managarm), and [glaucus](https://www.glaucuslinux.org/) (where it's actually implemented).

## Supported Architectures
* x86-64
* powerpc64

## Author
Firas Khalil Khana (firasuke) <[firasuke@glaucuslinux.org](
mailto:firasuke@glaucuslinux.org)>

## License
mussel is licensed under the Internet Systems Consortium (ISC) license.

## Dedication
mussel is dedicated to all those that believe setting up a cross compiler
targetting musl libc is a complicated process.

## Community
* [Discord](https://discord.gg/b6r2p3z)
* [Reddit](https://www.reddit.com/r/distrodev/)

## Mirrors
* [BitBucket](https://bitbucket.org/firasuke/mussel)
* [Framagit](https://framagit.org/firasuke/mussel)
* [GitHub](https://github.com/firasuke/mussel)
* [GitLab](https://gitlab.com/firasuke/mussel)
* [NotABug](https://notabug.org/firasuke/mussel)
* [SourceHut](https://git.sr.ht/~firasuke/mussel)
