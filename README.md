<img src="flip-tests.svg" alt="flip-tets">

# flip-tests

Quickly flip javascript tests between: only <--> disabled <--> default <--> only.

## What

Flips tests recursively in current path.

Flip between:

```
describe.only <--> xdescribe <--> describe <--> describe.only
it.only <--> xit <--> it <--> it.only
```

Also:

- Ignores files in .gitignore (if it exists)
- Will not change if not at start of line (or proceeded by blank space)
- Will maintain indentation
- Supports paths with spaces

## Why

Say you a working on a feature.
You have changed some code under test.
You have several tests marked `describe.only()` and/or `it.only`.
These tests under test might passing (or not).
You want to check that your other tests (not marked `.only()`) still pass.
But you don't want to muddy the ouput with the tests that you have marked
with `.only()`.

This is where flip-tests comes to the rescue.

## Prerequisites

- xargs
- sed (OSX inbuilt version tested only)
- [ripgrep](https://github.com/BurntSushi/ripgrep)

Works with mocha, jasmine, jest and any other test runner that uses `describe` and `it`.

## Getting Started

1.  Get flip-tests

```
git clone https://github.com/lukeaus/flip-tests.git
```

2.  add flip-tests to your path

3.  start flippin'

## Usage

From: `describe.only` and `it.only`

To: `xdescribe` and `xit`

`flip-tests -ox`<br /><br />

From: `xdescribe` and `xit`

To: `describe.only` and `it.only`

`flip-tests -xo`<br /><br />

From: `describe.only` and `it.only`

To: `describe` and `it`

`flip-tests -od`<br /><br />

From: `xdescribe` and `xit`

To: `describe` and `it`

`flip-tests -xd`<br /><br />

From: `xdescribe`, `xit`, `describe.only` and `it.only`

To: `describe` and `it`

`flip-tests -ad`<br /><br />

## Limitations

Tested on macOS only.

## Reporting bugs

Please use the GitHub issue tracker for any bugs or feature suggestions:

https://github.com/lukeaus/flip-tests/issues

## Contributing

Please submit patches to code or documentation as GitHub pull requests.

Contributions must be licensed under the MIT License. The contributor retains the copyright.
