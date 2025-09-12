# Setup groff (GNU roff)

[![Stand With Ukraine](https://raw.githubusercontent.com/vshymanskyy/StandWithUkraine/main/badges/StandWithUkraine.svg)](https://stand-with-ukraine.pp.ua)
![GitHub release](https://img.shields.io/github/v/release/fabasoad/setup-groff-action?include_prereleases)
![functional-tests](https://github.com/fabasoad/setup-groff-action/actions/workflows/functional-tests.yml/badge.svg)
![security](https://github.com/fabasoad/setup-groff-action/actions/workflows/security.yml/badge.svg)
![linting](https://github.com/fabasoad/setup-groff-action/actions/workflows/linting.yml/badge.svg)

This action sets up [groff (GNU roff)](https://www.gnu.org/software/groff).

## Prerequisites

<!-- prettier-ignore-start -->
| OS      | Supported          | Tools  |
|---------|--------------------|--------|
| Linux   | :white_check_mark: | None   |
| macOS   | :white_check_mark: | `brew` |
| Windows | :x:                | N/A    |
<!-- prettier-ignore-end -->

## Inputs

```yaml
- uses: fabasoad/setup-groff-action@v0
  with:
    # (Optional) If "true" it installs groff even if it is already installed on
    # a runner. Otherwise, skips installation. Defaults to "false".
    force: "false"
```

## Outputs

<!-- prettier-ignore-start -->
| Name      | Description                        | Example |
|-----------|------------------------------------|---------|
| installed | Whether groff was installed or not | `true`  |
<!-- prettier-ignore-end -->

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
      - uses: actions/checkout@v5
      - uses: fabasoad/setup-groff-action@v0
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

## Contributions

![Alt](https://repobeats.axiom.co/api/embed/bad0e7e13e0dbf910bcea7d53b0d361fdffe6d6f.svg "Repobeats analytics image")
