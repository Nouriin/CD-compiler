# Arithmetic Expression Compiler
Compiler front end in HTML/CSS/vanilla JS: lexer → recursive-descent parser (parse tree + AST) → semantic analysis → safe AST evaluation. No `eval`, no dependencies.

## Run
- GUI: open `index.html` in a browser (or VS Code "Live Server").
- Tests: `node tests/test-runner.js` (requires Node.js).

## Input format
One statement per line: `x = 4`, `y = 6`, `x + y * 2`. Variables must be assigned on an earlier line. The last line is the final result.

## Modules (`js/`)
| File | Purpose |
|---|---|
| lexer.js | Tokens with type, lexeme, line:col; reports invalid characters |
| grammar.js | Grammar text shown in the GUI |
| ast.js | AST node constructors, tree display helper |
| parser.js | Recursive-descent parser, builds parse tree + AST |
| semantic.js | Undefined-variable checks, symbol table |
| evaluator.js | Recursive AST evaluator, division-by-zero check |
| compiler.js | Runs the stages in order, stops at first failure |
| ui.js / main.js | Rendering and buttons |

Grammar, FIRST/FOLLOW and LL(1) table: `docs/grammar-and-transformations.md`.
