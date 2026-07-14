# monolog

monolog is an experimental Logo interpreter written in C++. It includes tokenization, parsing, procedure dispatch, evaluation, and Allegro-based turtle graphics, with unit-style test programs alongside the language components.

## Technical stack

- C++17
- GNU Make
- Allegro 5 for windowing and turtle graphics
- POSIX-oriented build commands

## Build and test

Install Allegro 5 and a C++17 compiler, then use the Makefiles in the component directories.

```sh
make -C lang token_test tokenizer_test arg_test args_test ast_node_test
make -C main main
```

Run the generated `*_test.out` binaries after compilation. Exact targets vary by directory; inspect the local Makefile when working on a component.

## Status

Experimental and incomplete. Much of the interpreter pipeline exists, but the last development activity focused on parser errors and the project has no automated CI.

## Known limitations

- Build flags contain platform-specific Allegro assumptions.
- Graphics state can be lost around display flips.
- Built-in Logo vocabulary and graphics operations are incomplete.
- Memory safety, malformed-input behavior, and cross-platform builds need more testing.
- The repository uses hand-maintained Makefiles rather than a portable project generator.

## Next steps

Consolidate the build with CMake or Meson, add CI and sanitizer runs, formalize the supported Logo subset, improve parser diagnostics, preserve render state, and add integration tests for complete Logo programs.
