# rustfmt

A tool for formatting Rust code according to style guidelines.

## Gotchas
* For things you do not want rustfmt to mangle, use
```rust
 #[rustfmt_skip]
 ```
* When you run rustfmt use a file called rustfmt.toml to override the default settings of rustfmt.
* We create a functioning executable called rustfmt in the target directory

## How to build and test
You'll need a pretty up to date version of the **nightly** version of Rust.

`cargo build` to build.

`cargo test` to run all tests.

`cargo run -- filename` to run on a file, if the file includes out of line modules,
then we reformat those too. So to run on a whole module or crate, you just need
to run on the top file.

You'll probably want to specify the write mode. Currently, there are the replace,
overwrite and display mode. The replace mode is the default and overwrites the
original files after renaming them. In overwrite mode, rustfmt does not backup
the source files. To print the output to stdout, use the display mode. The write
mode can be set by passing the `--write-mode` flag on the command line.

`cargo run -- filename --write-mode=display` prints the output of rustfmt to the
screen, for example.
