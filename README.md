## Expression Evaluator

A Mathematical expression evaluator (constants only, no variables) written in C without dependencies. The evaluator parses and evaluates expressions in a single pass through rather than parsing & tokenizing the expression and calculating after.

### Usage:
The evaluation function which this library exposes to the client is called `eval()`, which takes a string containing the expression as the sole parameter. 
In order to use the `eval()` function, first download and build/link the source by running `make` in the root directory. 
Then, we can use `eval()` like so:
```c
#include "../path/to/evaluator.h"

...
...

char* expression = "3 * (2 * (1 + 1) ^ 2) + 2";
long result = eval(expression);       //  result will yield 26

char* expression2 = "(1 + 3 * (2 * (1 + 1) ^ 2) + 2) * 2 * 2 + 1";
long result2 = eval(expression2);     //  result will yield 109

expression3 = "(1 + 3 * (2 * (1 + 10 ^ 2) + 2) * 2 * 2 + 1";
long result3 = eval(expression3);     //  result will yield 0 due to Missing Closing Parentheses error

expression4 = "2 */ 2";
long result4 = eval(expression4);     //  result will yield 0 due to illegal Order of Operations error
```

More examples can be found in the `test/test_evaluator.c` file.

### TODO:
* Check for integer overflows
* Add support for evaluating decimals/floats/doubles
