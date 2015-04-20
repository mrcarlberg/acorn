
# Objective-J Parser

A tiny, fast JavaScript and/or [Objective-J][objj] parser with built in preprocessor. Written in JavaScript.

[objj]: http://www.cappuccino-project.org/learn/objective-j.html

It is extended from the [Acorn][acorn] JavaScript parser by Marijn Haverbeke:

[acorn]: http://marijnhaverbeke.nl/acorn/

Is used by the [Objective-J compiler][objj-compiler]

[objj-compiler]: https://github.com/mrcarlberg/ObjJAcornCompiler

It is 100% compatable with JavaScript with two extra options.

1: Turn on 'preprocess' to allow C like preprocess derectives.

It is 100% compatible with the Macros and Conditionals preprocessor directives defined in the [GNU C 4.0 Preprocessor User Guide](http://gcc.gnu.org/onlinedocs/gcc-4.8.1/cpp/index.html#Top).

Example:
```c
#define MAX(x, y) (x > y ? x : y)
var m1 = MAX(a, b);
var m2 = MAX(14, 20);
```
Will be parsed as if it was like this:
```c
var m1 = (a > b ? a : b);
var m2 = (14 > 20 ? 14 : 20);
```
For more info see http://www.cappuccino-project.org/blog/2013/05/the-new-objective-j-2-0-compiler.html

2: Turn on 'objj' to allow Objective-J syntax

See http://www.cappuccino-project.org/learn/objective-j.html

Use from command line with different options:
usage: acorn infile [--ecma3|--ecma5] [--strictSemicolons] [--trackComments] [--trackSpaces]
        [--locations] [--no-objj] [--no-preprocess] [--compact] [--silent] [--help]
