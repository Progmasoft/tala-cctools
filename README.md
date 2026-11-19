<!-- SPDX-FileCopyrightText: 2026 Progmasoft <support@progmasoft.com> -->
<!-- SPDX-License-Identifier: MIT -->

# Tala CCTools

Tala CCTools are the assembler, the linker and the object file tools of TalaOS. They work on Mach-O alone and are
shipped in the `tala-cctools` package of the core repository.

Compatibility with Apple's cctools is the base: the commands take the options and write the output of their cctools
counterparts, so scripts and build systems written for them work unchanged. Compatibility with GNU Binutils is not a
goal. Where Apple's tools stop, a tool may do more; `otool`, for example, also does the work of `readelf` and
`objcopy`.

The table names, for each GNU Binutils tool, the tool of Tala CCTools that does its work; their options are cctools'.

| GNU Binutils | Tala CCTools |
| --- | --- |
| `as` | `as` |
| `ld` | `ld64` |
| `ar` | `ar` |
| `nm` | `nm` |
| `objdump` | `otool` |
| `readelf` | `otool` |
| `objcopy` | `otool` |
| `strip` | `strip` |
| `ranlib` | `ranlib` |
| `size` | `size` |

They are written in GNU99 under the
[Progmasoft Core C Coding Guidelines](https://github.com/Progmasoft/progmasoft-cpp) and built with BSD Make.

The repository builds several executables, and all of them have the one version in `VERSION`. The code they share
is in `common/`; the first piece is the command line parser, which reads each executable's options into typed fields
as described in [docs/architecture.md](docs/architecture.md). Building and testing are in
[docs/development.md](docs/development.md).

## License

[MIT](LICENSE.txt). Progmasoft's own code is also covered by the [Progmasoft Patent Grant 1.1](PATENTS.md); code
taken from elsewhere keeps its own license and notices. Participation follows the [Code of Conduct](CODE_OF_CONDUCT.md).
