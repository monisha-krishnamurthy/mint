# Mint Programming Language

A Java interpreter for a small programming language, built as a four-person team project for ASU's SER 502: Language and Programming Paradigms, Spring 2025.

**Stack:** Java · ANTLR 4.13.2 · Visitor pattern

## Language features

- Integer, floating-point, Boolean, and string values.
- Arithmetic, comparison, logical, and ternary expressions.
- Variable declarations, assignments, and type checking.
- Conditionals, `for`/`while` loops, `break`, and `continue`.
- Console output through `say` and `sayln`.

## Example

```text
mint_int x = 10;
mint_int y = 5;
sayln(x + y);

mint_if (x > y) {
    sayln("x is greater than y");
}
```

See [sample programs](data/) for more language examples.

## Build and run

Install a Java JDK with `javac`. The repository includes the ANTLR runtime and generated parser sources.

```bash
git clone https://github.com/monisha-krishnamurthy/mint.git
cd mint
mkdir -p build
javac -cp antlr-4.13.2-complete.jar -d build src/gen/*.java src/runtime/*.java
java -cp "build:antlr-4.13.2-complete.jar" runtime.MintMain data/sample1.mint
```

These commands use macOS/Linux classpath syntax. On Windows, use `;` instead of `:` in the runtime classpath. The interpreter prints program output followed by the parse tree.

## Architecture

`Mint.g4` defines the grammar. ANTLR produces the lexer and parser in `src/gen/`. `src/runtime/MintEvaluator.java` evaluates the parse tree, while `MintMain.java` loads and executes a source file.

## My contribution

As documented in the [team contribution record](doc/contribution.txt), I contributed to lexer rules, grammar cleanup, ANTLR setup, and evaluator logic for logical, equality, and ternary expressions. I also validated expression corner cases and grammar/evaluator alignment and contributed to project documentation and presentation material.

## Team and project materials

Kiran Venkatachalam · Monisha Krishnamurthy · Rahul Ravindra Reddy · Vishnu Kumar Adhilakshmi Kalidas

- [Design and milestone documents](doc/)
- [Final presentation video](https://www.youtube.com/watch?v=M7XdcvXsQSI)

This repository is a fork of the shared course project. Sample programs demonstrate behavior; they are not an automated test suite with expected-output assertions.
