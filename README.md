# sion-tests

Conformance suite shared by every Sion compiler stage (seed, self-hosted, future backends).

## Format
Each test is a pair in `tests/`:
- `NNN_name.sn`: the program
- `NNN_name.expected`: exact expected stdout
- `NNN_name.exit` (optional): expected exit code, default `0`. A trap exits with `101`.

A compiler passes if, for every pair, compiling and running the program prints the expected stdout and exits with the expected code.

## Rules
- One behavior per test. Name tests by what they prove.
- Tests 001-020 must stay inside Sion-0 so the seed can run them.
- Never edit an `.expected` file to make a compiler pass.
