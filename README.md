# Formal Languages & Automata

This repository contains implementations and exercises for a Formal Languages and Automata course, focused on:

- deterministic finite automata (DFA)
- nondeterministic finite automata (NFA)
- regular expression parsing and Thompson construction
- subset construction (NFA → DFA)
- lexical analysis using regex-based token specifications

It also includes a small expression evaluator (`src/main.py`) that tokenizes and simplifies list/lambda-style input files used by the provided bonus tests.

## Project structure

- `/src/DFA.py` – DFA data structure, simulation (`accept`), and state remapping
- `/src/NFA.py` – NFA representation, epsilon-closure, subset construction, state remapping
- `/src/Regex.py` – regex AST nodes + parser + Thompson conversion to NFA
- `/src/Lexer.py` – combined-token NFA/DFA lexer with max-munch and token priority handling
- `/src/main.py` – parser/simplifier runner for `.l` input files
- `/test` – homework/unit tests for DFA/NFA/regex/lexer behavior
- `/bonus_tests` – extra `.l` inputs and expected outputs (`ref/`)
- `check.sh` – script to run bonus tests and diff outputs

## Run

From the repository root:

```bash
python3 -m src.main bonus_tests/basic.l
```

Run bonus tests:

```bash
bash check.sh
```

Run unit tests (standard library `unittest`):

```bash
python3 -m unittest discover -s test -p "test_*.py"
```

## Notes

- The project is organized as educational homework stages (`test_hw_1.py`, `test_hw_2.py`, `test_hw_3.py`).
- Bonus tests validate the expression evaluator output against reference files.
