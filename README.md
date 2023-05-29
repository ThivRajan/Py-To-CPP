# Python to C++ Compiler

This compiler takes working Python code and outputs working C++ code.

## Supported Features

The compiler supports compilation of the following features:

- arithmetic expressions
- boolean expressions
- variable instantiation
- lists
- for/while loops
- conditional statements
- function declarations (but their arguments and return value must be typed) and calls

## Compilation Steps

We transform the given Python input using the following steps:

1. Generate an abstract syntax tree (AST)
2. Generate a symbol table
3. Generate a typed-AST
4. Perform type checking
5. Generate three-address code (3AC)
6. Generate C++ code

## Testing

To test our compiler, there is a `test_suite_script.py` which will run a test suite on multiple test cases. Run the tests with:

```
python3 test_suite_script.py
```

You will find the the input for these test cases in the tests directory and the output in the tests/output directory. The input test files will be named in the format _test_case_TYPE_ where _TYPE_ will be _PASS_ or _FAIL_. The _PASS_ tests are for cases that will successfully generate an IR and the _FAIL_ tests are for the cases that will fail at some step in our compiler.

The output files are named in the following format: `test_case_name_output.txt`. In each output file, you will see each step of our compiler. To verify the target code generation, the output section will be highlighted with text similar to: _==== TARGET CODE ====_. All other output sections will appear within the output file labeled similarly to the target code section.

To verify the target code, compare the target code to the source code line by line and verify that each line of python code has been correctly translated into C++ code. If the compiler raises an error, e.g. a variable being used before declaration, verify that the error is valid using the error message.
