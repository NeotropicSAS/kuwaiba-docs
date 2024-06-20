# Kuwaiba Open Network Inventory Administrator’s Manual

This directory contains the source of the English version of "Kuwaiba Open Network Inventory Administrator’s Manual" book.

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