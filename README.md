# Introduction to compilers
A compiler is a type of software that translates source code written in a programming language into machine code that can be executed on a computer. Compilers are an essential part of the software development process, as they allow developers to write code in a high-level programming language that is easier for humans to read and understand, and then convert it into a form that can be understood and run by a computer.

The process of compiling involves several steps, including lexical analysis (breaking the source code into smaller units called "tokens"), syntax analysis (checking the code for grammatical errors), semantic analysis (checking the code for logical errors), code generation (converting the source code into machine code), optimization (improving the efficiency and performance of the generated code), and linking (combining the generated code with other code libraries or object files).

Compilers are used in a wide variety of applications, including operating systems, web browsers, mobile apps, and more. By using a compiler, developers can create complex programs that can perform a wide range of tasks and functions.




## Table of Content
1. [The steps of a compiler](#the-steps-of-a-compiler)
2. [Lexical analysis](#lexical-analysis)

## The steps of a compiler
A compiler is a program that translates source code written in a programming language into machine code that can be executed on a computer. The process of compiling involves several steps:

1. Lexical analysis: The compiler breaks the source code into small pieces called "tokens," which represent the different elements of the programming language (such as variables, operators, and keywords).

2. Syntax analysis: The compiler checks the source code for grammatical errors, ensuring that it is written in a valid and correct format.

3. Semantic analysis: The compiler checks the source code for logical errors, ensuring that it makes sense and follows the rules of the programming language.

4. Code generation: The compiler generates machine code (also known as object code) from the source code. This machine code is a series of instructions that can be executed by the computer's processor.

5. Optimization: The compiler may perform various optimization techniques to improve the efficiency and performance of the generated machine code.

6. Linking: The compiler may also link the generated machine code with other code libraries or object files to create the final executable program.




## Lexical analysis
A lexical analyzer (also known as a lexer or a lexical scanner) is a program or component of a compiler that performs lexical analysis, which is the process of breaking the source code into a stream of smaller units called "tokens." These tokens represent the different elements of the programming language, such as keywords, operators, and identifiers.

The lexical analyzer reads the source code one character at a time and groups the characters into tokens based on the rules of the programming language. For example, in the C programming language, the lexical analyzer might recognize the characters "i", "n", and "t" as the beginning of the keyword "int", and group them together into a single token.

The output of the lexical analyzer is a list of tokens, which is then passed to the next phase of compilation (syntax analysis) for further processing. By breaking the source code into smaller, more manageable units, the lexical analyzer makes it easier for the compiler to understand and analyze the structure and meaning of the code.

### Lexical tokens
In the context of a compiler, a lexical token (also known as a lexeme) is a sequence of characters that represent a unit of meaning in the source code. For example, in the C programming language, the lexical tokens might include keywords (such as "int" and "while"), operators (such as "+" and "*"), and identifiers (such as variable names).

The structure of a lexical token depends on the programming language being used and the specific role that the token plays in the code. In general, a lexical token may consist of a single character (such as an operator or punctuation mark) or a sequence of characters (such as a keyword or identifier).

For example, in the C programming language, a lexical token may have the following structure:

* Keywords: A keyword is a reserved word in the language that has a specific meaning and cannot be used as an identifier. Keywords are typically written in lowercase and do not contain any spaces or special characters. Examples of keywords in C include "int", "while", and "return".

* Operators: An operator is a symbol that represents a specific operation or manipulation in the code. Operators may consist of a single character (such as "+" or "=") or a combination of characters (such as "&&" or "<<").

* Identifiers: An identifier is a name given to a variable, function, or other element in the code. Identifiers may consist of letters, digits, and underscores, and must begin with a letter or an underscore. Examples of identifiers in C include "x", "y", and "z".

Here is an example of how a lexical token could be represented as a struct in C#:
```cs
public struct Token
{
    public TokenType Type;
    public string Value;
}

public enum TokenType
{
    Keyword,
    Identifier,
    Operator,
    Literal,
    Punctuation
}
```
In this example, the `Token` struct has two fields: `Type`, which indicates the type of the token (such as a keyword or identifier), and `Value`, which stores the actual value of the token as a string. The `TokenType` enum defines the different types of tokens that can be represented by the `Token` struct.

Here is an example of how you could use the `Token` struct to represent a lexical token in a C# program:
```cs
Token token = new Token();
token.Type = TokenType.Keyword;
token.Value = "while";
```

This code creates a new `Token` struct and sets its `Type` field to `TokenType.Keyword` and its `Value` field to "while", representing the keyword "while" in the C# language.




# Syntax analysis
Syntax analysis, also known as parsing, is the process of checking the source code for grammatical errors and ensuring that it is written in a valid and correct format. Syntax analysis is typically the second phase of the compilation process, following lexical analysis.

During syntax analysis, the compiler constructs a tree-like representation of the source code called an "abstract syntax tree" (AST). The AST reflects the structure of the code and shows how the different elements (such as variables, functions, and control structures) are related to each other.

### Abstract syntax tree
Here is a visualization of an abstract syntax tree (AST) that could be generated by a syntax analyzer:
```
    +
   / \
  *   a
 / \
b   c
```

This AST represents the following arithmetic expression: "b * c + a". The tree is structured so that the root node represents the operator at the top level of the expression, and the child nodes represent the operands. In this example, the root node is the "+" operator and its two child nodes are the "" operator and the "a" operand. The "" operator has two child nodes, "b" and "c".

The AST captures the structure and meaning of the source code in a way that is easier for the compiler to understand and manipulate. It is typically used as the input for the next phase of compilation (semantic analysis) and is also used to generate the machine code that will be executed by the computer.

### Grammar
The syntax analyzer uses a set of rules called a "grammar" to determine the structure and meaning of the source code. The grammar defines the valid syntax of the programming language and specifies how the different elements of the language can be combined to form a correct program.

If the compiler finds any errors during syntax analysis, it will generate an error message indicating the location and nature of the problem. Syntax errors can occur if the source code does not follow the rules of the programming language, such as using an incorrect keyword or forgetting to close a bracket.

Here is a visualization of a simple grammar that could be used by a syntax analyzer:
```cs
expr ::= expr + term | term
term ::= term * factor | factor
factor ::= int | num | ( expr )
```

This grammar defines the rules for a simple arithmetic expression language, with non-terminal symbols for expressions, terms, and factors. The "::=" symbol indicates a production rule, and the "|" symbol separates alternative productions.

For example, the first rule states that an expression can be formed by an expression followed by a "+" operator and a term, or by just a term. The second rule states that a term can be formed by a term followed by a "\*" operator and a factor, or by just a factor. The third rule states that a factor can be an integer literal, a numeric literal, or an expression enclosed in parentheses.

The terminal symbols in this grammar are the keywords "int" and "num" and the operators "+" and "\*". The non-terminal symbols are "expr", "term", and "factor".
