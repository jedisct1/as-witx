![WITX code generator](logo.png)
================================

![CI status](https://github.com/jedisct1/witx-codegen/actions/workflows/ci.yml/badge.svg)
[![crates.io](https://img.shields.io/crates/v/witx-codegen.svg)](https://crates.io/crates/witx-codegen)

# WITX-CodeGen: A WITX code and documentation generator

WITX is a way to describe types and function interfaces from WebAssembly modules.

From this, code generators can generate code that accesses data and calls functions from different languages using the same layout and calling conventions.

WITX is the description language used by [WASI](https://wasi.dev). This tool uses the next (as on April 5th, 2021) revision of the format, as implemented in version 0.10 of the Rust `witx` crate.

WITX-CodeGen is written in Rust, but was designed to generate code for multiple languages that is simple to use. It can also produce multiple documentation formats.

It supersedes `as-witx`, `zig-witx`, `witx-docgen`, `witx-overview-docgen` and `witx-generate-raw`.

## Installation

* Via `cargo`:

```sh
cargo install witx-codegen
```

* Precompiled binaries: tarballs and Debian/Ubuntu packages are available [here](https://github.com/jedisct1/witx-codegen/releases/latest).

## Usage

```text
WITX code generator for WebAssembly guest modules

USAGE:
    witx-codegen [FLAGS] [OPTIONS] <witx_files>...

FLAGS:
    -h, --help            Prints help information
    -H, --skip-header     Do not generate a header
    -I, --skip-imports    Ignores imported types and functions
    -V, --version         Prints version information

OPTIONS:
    -m, --module-name <module_name>
            Set the module name to use instead of reading it from the witx file

    -o, --output <output_file>         Output file, or - for the standard output
    -t, --output-type <output_type>
            Output type. One in: {assemblyscript, rust, overview, markdown}
            [default: assemblyscript]

ARGS:
    <witx_files>...    WITX files
```

## Backends

* [X] AssemblyScript ([example](https://github.com/jedisct1/witx-codegen/blob/master/example-output/assemblyscript.ts))
* [X] Rust ([example](https://github.com/jedisct1/witx-codegen/blob/master/example-output/rust.rs))
* [X] API Overview ([example](https://github.com/jedisct1/witx-codegen/blob/master/example-output/overview.txt))
* [X] Markdown documentation ([example](https://github.com/jedisct1/witx-codegen/blob/master/example-output/markdown.md))
* [ ] Zig
* [ ] TinyGo
* [ ] C/C++
* [ ] HTML documentation

## Example inputs

See the [`test`](https://github.com/jedisct1/witx-codegen/tree/master/test) folder for examples of WITX input files.

