# Setup groff (GNU roff)

[![Stand With Ukraine](https://raw.githubusercontent.com/vshymanskyy/StandWithUkraine/main/badges/StandWithUkraine.svg)](https://stand-with-ukraine.pp.ua)
![GitHub release](https://img.shields.io/github/v/release/fabasoad/setup-groff-action?include_prereleases)
![functional-tests](https://github.com/fabasoad/setup-groff-action/actions/workflows/functional-tests.yml/badge.svg)
![security](https://github.com/fabasoad/setup-groff-action/actions/workflows/security.yml/badge.svg)
![linting](https://github.com/fabasoad/setup-groff-action/actions/workflows/linting.yml/badge.svg)

This action sets up [groff (GNU roff)](https://www.gnu.org/software/groff).

## Prerequisites

<!-- prettier-ignore-start -->
| OS      | Supported | Tools            |
|---------|-----------|------------------|
| Linux   | Yes       | None             |
| macOS   | Yes       | `brew` or `bash` |
| Windows | No        | N/A              |
<!-- prettier-ignore-end -->

## Inputs

None

## Example

Let's try to run [hello-world.roff](./hello-world.roff) file using the workflow
below.

```yaml
name: Setup groff

on: push

jobs:
  setup:
    name: Setup
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: fabasoad/setup-groff-action@v1
      - run: groff -man -Tascii hello.roff
```

And you should see the following output:

```text
HELLO(1)                    General Commands Manual                   HELLO(1)

NAME
       hello - print Hello, World!

SYNOPSIS
       hello

DESCRIPTION
       The hello command prints "Hello, World!" to the standard output.

EXAMPLES
       hello

       Hello, World!


Hello Manual                       June 2024                          HELLO(1)
```
