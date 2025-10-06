## Intro

The library implements a regular expression engine based on nondeterministic
finite automata (NFA). It uses the [Thompson's
construction](https://en.wikipedia.org/wiki/Thompson%27s_construction)
algorithm to transform regular expressions into NFAs. 
Supported features:

- common operators like `*`, `+`, `?`, and `|`
- ranges, e.g. `[a-z]`
- groups, e.g. `(abc)`
- starting and ending position indicators: `^` and `$`
- the caret `^` operator



## Running Tests

To check the installation was successful, it will be a good idea to run the
tests. The library uses pytest as a testing framework. If you've followed the
instructions from the previous section, pytest is already installed in your
virtual environment.

To run the tests do

```console
$ pytest tests/
```

To get a test coverage report run

```console
$ pytest --cov=regex tests/
```



## API

The API is simple and consists of one function named `match`. The function
takes a POSIX-like regular expression and a string and returns `True` or
`False` depending on whether the string matcher the expression or not.



The function raises the `MalformedRegex` exception if the regular expression
can't be parsed.

## Command Line Tool

The library ships with the command line tool named `regex`. It is a simple
app that takes a regular expression as its first argument and a string as
the second. For example:

```console
$ regex "a?a?b" "ab"
The string 'ab' matches
```

