# JiLang

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
![Language: Rust](https://img.shields.io/badge/Language-Rust-orange.svg)
![Status: Experimental](https://img.shields.io/badge/Status-Experimental-blue.svg)
[![Ask DeepWiki](https://deepwiki.com/badge.svg)](https://deepwiki.com/HelloAIXIAOJI/JiLang)

*A programming language based on JSON syntax - Now Turing complete!（Maybe?）*

[中文文档](README.zh.md)

## What is JiLang?

JiLang is an experimental programming language that uses JSON as its syntax. It allows you to write programs using familiar JSON structures while providing programming capabilities like variables, loops, conditionals, and functions.

```json
{
    "include": ["math"],
    "program": {
        "main": {
            "body": [
                {"echo": ["Hello, JiLang!", "\n"]},
                {"var": {"count": 0}},
                {"while": {
                    "condition": {
                        "op": "lt",
                        "left": "@var.count",
                        "right": 3
                    },
                    "body": [
                        {"echo": ["Count: ", "@var.count", "\n"]},
                        {"math.add": ["@var.count", 1]},
                        {"var": {"count": "@var.result"}}
                    ]
                }}
            ]
        }
    }
}
```

## Features

- **JSON-based Syntax**: Write programs using familiar JSON format
- **Variables and Constants**: Store and manipulate data
- **Control Structures**: If-else statements, while loops, for loops
- **Functions**: Define and call custom functions, including recursive functions
- **Modules**: Import and use built-in or custom modules
- **Weak Typing System**: Flexible type conversion, similar to PHP
- **Nested Data Structures**: Access multi-level object properties
- **System Command Execution**: Run external commands from JiLang code

## Installation

### Pre-compiled Binaries

Download the latest version from the [releases page](https://github.com/HelloAIXIAOJI/JiLang/releases).

### Building from Source

Ensure you have Rust installed, then:

```bash
git clone https://github.com/HelloAIXIAOJI/JiLang.git
cd JiLang
cargo build --release
```

The executable will be available at `target/release/JiLang`.

## Quick Start

1. Create a file named `hello.jl` with:

```json
{
    "program": {
        "main": {
            "body": [
                {"echo": ["Hello, World!\n"]}
            ]
        }
    }
}
```

2. Run it:

```bash
JiLang hello.jl
```

## Documentation

For a comprehensive guide to JiLang syntax and features, see:

- [Syntax Documentation](docs/syntax_en.md): Detailed syntax reference
- [Examples](docs/examples.md): Example programs demonstrating various features

## Key Concepts

- Programs are structured as JSON objects with a `program` property
- The `main` function is the entry point for execution
- Variables are referenced using the `@var.` prefix
- Module functions are called using `module_name.function_name` syntax
- Statements are represented as JSON objects with a single property

## Command Line Options

JiLang supports the following command line options:

```bash
# Display help information
JiLang --help

# Display about information
JiLang --about

# Display creator information
JiLang --creator

# Run in debug mode (show detailed execution information)
JiLang --debug my_program.jl

# Run in tolerance mode (report non-critical errors without terminating)
JiLang --ignore-non-critical-errors my_program.jl

# Check for errors without executing the program
JiLang --check my_program.jl
```

## Status

JiLang is currently in active development. With major improvements in version 0.4.0, the language features are becoming more complete, but it is still not recommended for critical production environments. It is both a programming experiment and an evolving tool. While we welcome all kinds of exploration, learning and contributions, please consider using more widely validated languages for enterprise-critical applications.

## License

JiLang is licensed under the MIT License. See [LICENSE](LICENSE) for details.

## Contributing

Contributions are welcome! Feel free to submit issues or pull requests.

## Acknowledgments

JiLang was created by AIXIAOJI as a fun programming experiment during the 2025 Labor Day holiday.
