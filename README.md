# Compiler

Course project for Compilers (L.EIC - FEUP, 2024/2025)

### Overview

This compiler translates J-- source code to Java bytecode through multiple compilation stages:
```
J-- Source → AST → Symbol Table → OLLIR → Jasmin → JVM Bytecode
```

### Features

* **Lexical and Syntax Analysis**: ANTLR4 grammar for J-- language parsing
* **Semantic Analysis**: Type checking, method validation, variable declaration verification
* **Code Generation**: OLLIR intermediate representation generation
* **Backend**: Jasmin bytecode generation for JVM execution

### J-- Language Support

* Classes with inheritance
* Methods (including `main` method)
* Variables and arrays
* Control flow (`if`, `while`)
* Expressions and operators
* Method calls and object instantiation
* Varargs parameters

### Architecture

#### Core Components

* `Javamm.g4` - ANTLR grammar definition
* `JmmSymbolTableBuilder` - Symbol table construction
* `OllirGeneratorVisitor` - OLLIR code generation
* `JasminGenerator` - JVM bytecode generation

#### Analysis Passes

* Variable declaration checking
* Type compatibility verification
* Method signature validation
* Argument type checking
* Varargs semantics

### Compilation Pipeline

1. **Parsing**: Source code → AST using ANTLR
2. **Symbol Table**: Extract classes, methods, variables
3. **Semantic Analysis**: Type checking and validation
4. **OLLIR Generation**: Intermediate representation
5. **Jasmin Generation**: JVM bytecode assembly

### Usage

The compiler processes `.jmm` files containing J-- source code and produces corresponding `.class` files for JVM execution.

### Project Structure
```
src/
├── ast/           # AST node definitions and utilities
├── analysis/      # Semantic analysis passes
├── symboltable/   # Symbol table implementation
├── optimization/  # OLLIR generation
└── backend/       # Jasmin bytecode generation
```

---

### Contributors

Group members:
1. Luna Cunha (up202205714@up.pt)
2. Marta Martins (up202206369@up.pt)
3. Tiago Santos (up202207073@up.pt)

