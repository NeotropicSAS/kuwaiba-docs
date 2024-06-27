# Kuwaiba Open Network Inventory Tutorials

This directory contains a set of tutorials depicting several use cases where Kuwaiba can be used effectively.

## Requirements
Building the book requires [Rust] and [mdBook]. Once the first is installed, the second can be installed using [Cargo], Rust's package manager:

```bash
$ cargo install mdbook --locked --version <version_num>
```

## Building

To build the book, type:

```bash
$ mdbook build
```

## The Book
The book is generated inside a directory called `book` next to `src`.

[Rust]: https://www.rust-lang.org
[mdBook]: https://github.com/rust-lang/mdBook
[Cargo]: https://github.com/rust-lang/rust/blob/master/src/tools/rustbook/Cargo.toml