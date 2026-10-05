# Pascal-Like Language Parser

A **recursive-descent parser** for a Pascal-like programming language, built in C++ as part of CS 280 (Programming Languages) at NJIT.

## What It Does

Takes a Pascal-like source file and checks if it's syntactically valid. It either:
- ✅ Prints the program name, declared variables, and constants — then `DONE`
- ❌ Prints descriptive error messages showing exactly where and what went wrong

## Language Features Supported

- `PROGRAM`, `BEGIN`, `END` block structure
- `CONST` and `VAR` declaration sections
- Types: `INTEGER`, `REAL`, `BOOLEAN`, `CHAR`, `STRING`
- Statements: assignment (`:=`), `IF/THEN/ELSE`, `WRITELN`, `WRITE`, `READLN`
- Expressions with full operator precedence (`+`, `-`, `*`, `/`, `DIV`, `MOD`, `AND`, `OR`, `NOT`)
- Relational operators (`=`, `<`, `>`) — no cascading allowed

## How to Build & Run

```bash
g++ -o parser prog2SP26.cpp lexSP26.cpp s_bhat_parser.cpp -std=c++17
./parser yourfile.pas
```

## Example Output (success)

```
Program Name: circle
Declared Variables:
a, b, i, j, p, r

Defined Constants:
factor, pi

DONE
```

## Example Output (error)

```
12: Missing Assignment Operator.
12: Incorrect Simple Statement.
12: Missing Statement for If-Then-Part.
12: Incorrect Structured Statement.
12: Syntactic error in the statement.
12: Incorrect Program Body.
12: Incorrect Program Body.
Unsuccessful Parsing
Number of Syntax Errors 7
```

## Project Structure

| File | Description |
|------|-------------|
| `s_bhat_parser.cpp` | Recursive-descent parser (my implementation) |
| `lexSP26.cpp` | Lexical analyzer (provided) |
| `lexSP26.h` | Lexer header (provided) |
| `parserSP26.h` | Parser header / function prototypes (provided) |
| `prog2SP26.cpp` | Driver program (provided) |

## Error Detection

The parser catches and reports:
- Missing operators, semicolons, parentheses
- Undeclared or redefined variables and constants
- Incorrect types in declarations
- Illegal `ELSE` clauses
- Missing `END` for compound statements
- Invalid relational expressions (cascading)
- And more — 19 test cases all passing ✅

## Tech

`C++17` · Recursive Descent Parsing · Lexical Analysis
