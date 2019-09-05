# PL 9/4/19

## What is a language?

- Consists of:
  - alphabet (a finite set of symbols)
  - set of all possible sequences of alphabet symbols 
    - i.e. (set of all sentences)
    - almost always infinite (a.l.a sentence length is not bounded)
  - meaning assigned to sequences in the set

## What is a programming language

A language that is:

- implementable on a computer (PL -> machine code)
- unambiguous (there's one meaning for each sequence in the sequence set)
- Turing complete (expressive enough to express any computable function)
  - (arithmetic, comparison, JMP, storage)


**Church's Thesis**

Any computable function can be expressed by a Turing machine.

**Turing completeness**

A language is turing complete if it is equivalent to a universal Turing machine.

**Turing machine**

[illustration required]

Has infinite tape. The tape is divided into cells. In each cell is a symbol. 
The head can read-write the symbols in a cell. Attached to the head is a 
state machine (an abstract box), which contains a finite number of states, and
a pointer to the current state. One of the states is called the 'halt state'; 
when the machine gets to that state, the problem is finished.

*Transition relation:* given a currrent state and the symbol under the head,
transition to a new state, write a new symbol under the head, and move the 
head position one cell to the left / right.

**A universal Turing machine**

A universal turing machine is a Turing machine that, given another Turing 
machine T and an input I, can produce the same result as T on input I.

*For any computable problem, there is a turing machine to solve this problem; 
a universal Turing machine can compute any computable problem.*

## What makes a language more "powerful" (Desirable)?

- conciseness (how much code is required to express a problem)
- clarity (readability)
- efficiency? (not necessarily a feature of the language, consider compiler)
- features that match the need
- firm mathematical foundation
  - prove that a project actually computes the specified problem
  - much easier to prove for functional than imperative language

## Categories of languages

### High level vs. Low level

*Low level*: close to the hardware, features reflect the underlying hardware 
(assembly).

*High level*: not low level. When programmers write in this language, he/she
probably has a different logic model than the actual features supported by the
underlying hardware.

*c is a high-level language with many low-level features.*

### Imperative languages

- variables are just locations in memory that can be overwritten
- flow of control serves to repeatedly assign / overwrite values to memory locations

A PL is imperative because it *instructs* how 'states' (values in memory) is 
changed.

### Functional languages

- variables represent values, not memory locations
- programs are made up of functions (in the mathematical sense, which is just an exact mapping of inputs to outputs)
- expresses repetition not through loops (because all variables are consts), but recursion

## Implementation of a PL

The two ways are *compilation* and *interpretation*.

**Compilers** translate programs written in a PL to machine code (which is a 
PL in and of itself).

**Interpreters** directly execute a program in its original image (the program
itself is not translated; the interpreter understands it).

You need an interpreter somewhere; you don't always need a compiler.

## Describing PLs

*Syntax*: defines the symbols used (the alphabet) and the set of valid 
sequences of symbols (the orders in which symbols can appear).

*Semantics*: rules assigning meaning to syntactically valid sequences.

## Phases of compilation

1. **Lexical analysis**: turns sequences of characters into words
   - Done by a 'lexer' (e.g. recognizes 'for' is the `for` keyword)
2. **Syntactic analysis (parsing)**: forms words into statements, functions, etc.
3. **Type checking**: check if there's invalid use of types (e.g. languages that do not support adding strings)
4. **Code generation**: outputting the program in the target language
5. **Optimization**: tries to make the generated program as efficient as possible (can occur throughout the various phases)
