# itgroove Coding Style Guide

The purpose of this style guide is to create a collaborative coding style baseline for itgroove. 

This guide will follow the below format to address both generalities and details:

*In principle :* General guiding principles around the topic. 

*In practice :* Specific implementation details required by itgroove of it's developers.

<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
**Table of Contents**  *generated with [DocToc](https://github.com/thlorenz/doctoc)*

- [1. General](#1-general)
- [2. Comments](#2-comments)
- [3. Naming Schemes](#3-naming-schemes)
  - [3.1 Variable Names](#31-variable-names)
  - [3.2 Function and Method Names](#32-function-and-method-names)
- [4. Readability](#4-readability)
  - [4.1 Spacing](#41-spacing)
  - [4.2 Braces](#42-braces)
  - [4.3 Lines](#43-lines)
- [5. Maintainability](#5-maintainability)
- [6. Classes](#6-classes)
- [7. Errors](#7-errors)
- [8. Portability](#8-portability)
- [9. Repository](#9-repository)
- [10. Best Practices](#10-best-practices)
  - [10.1 Work out loud](#101-work-out-loud)
  - [10.1 DRY - Don't repeat yourself](#101-dry---dont-repeat-yourself)
  - [10.2 YAGNI - You ain't gonna need it](#102-yagni---you-aint-gonna-need-it)
  - [10.3 KISS - Keep it simple silly](#103-kiss---keep-it-simple-silly)
  - [10.4 Fail fast, fail often](#104-fail-fast-fail-often)
  - [10.6 POLA - Principle of least astonishment](#106-pola---principle-of-least-astonishment)
  - [10.7 Should I use cool new feature "X"?](#107-should-i-use-cool-new-feature-x)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->



## 1. Objective 

*The objective of these itGroove coding standards* 

* To maximize code readability and maintainability by making a teams code base look like a single person has written it.
* To speed up writing code. Simple rules to follow means developers won't have to make continuous judgements about how code looks and presents.
* To read each others code faster and discern patterns visually without having to read each token.
* To encapsulate the shared experience of many developers so we can learn from each others mistakes. 
* To free us to think in higher abstractions and come up with new patterns instead of enforcing what we have always seen or done. 

Note - Being that there is no right or wrong coding standard, a team has to "just pick something" for each category and stick with it. Thus this guide is a collection of "just pick somethings" developed by the itgroove team in August, 2018.  

## 2. Comments

1. Before commenting, strive to make code readable and self-documenting through effective naming practices and known programming styles.
2. Every comment represents a failure to express yourself clearly in code.
3. Since devs can't be relied on to always accurately update comments, inevitably code comments evolve into lies.

* Avoid obvious, self-evident and unnecessary comments. Never state the obvious!
* Adding a comment at beginning of each block of code emphasizes visual separation.
* Comment code according to the JSDocs markup language -- MORE DETAIL NEEDED HERE -- 
* If you need comments to explain the various parts of a function, perhaps you should break into sub-functions.
* Short comments of 1 - 2 lines should use // where possible rather then /* */ to make commenting out large sections easier when debugging.
* Comments have their place - explain why error got tripped! If error will throw a bunch of complicated error code, have explanation so co-worker doesn't have to decipher it.
* Code that can't be made obvious (obscure bug, unlikely condition, something edge case) def should be commented. 
* comment the INTENT of the code, why it is doing something rather then what it is doing
* Comment to explain purpose of a class, function, endpoint.

## Documentation.js

itGroove has chosen the "documentation.js" framework to document it's code. All functions and methods should use the following markup style to explain the purpose of each piece of code. By filling in the required comments, documentation.js will automatically generate the required documentation that will be accesible to end users and clients.

* Use JSDoc style comments for functions, interfaces, enums, and classes.

## 3. Naming

* Use PascalCase for type names.
* Use PascalCase for enum values.
* Use camelCase for variable names. 
* Use camelCase for function names.
* Use camelCase for property names and local variables.
* Do not use "_" as a prefix private properties. 
* Do not use "I" as a prefix for interface names.
 
* Names should tell you why it's there, what it does, how to use it.
* Use whole, pronounceable English words and never use ambiguous abbreviations. 
* Ensure names are sufficiently different so you don't mistake a name for another similar one. 
* Disallowed words: anything to general or to vague ex. Manager, Processor, Data, Info.
* A name should be an obvious, logical name to search for in 100k lines of code. ex. A button to restore all is named restoreAllButton

### 3.1 Variable Names
* Use camelCase for variable names.
* When you can, use customary opposite pairs in var names such as min/max, begin/end, open/close.
* Boolean vars should contain 'is / has / can / use' which implies yes/no or true/false ex. fileIsFound, isValidEmail.
* Use single letter var names for short loop indexes or array index ex. For(x = 0; x > 10, x++) or a[i].
* Even for a limited scope variable, still use meaningful name.
* Groups of enumerated types should share same prefix Ex. FONT_ARIAL and FONT_ROMAN

### 3.2 Function and Method Names
* Use camelCase for method and function names.
* Use verb-noun method - name routines that perform an operation-on-a-given-object ex. calulateTotalAmount()
* Can mention if there is heavy processing or side effects ex.. shutdown(), removeListener(), getWidth(), generateHistogram()
* Append computational qualifiers (Avg, Sm, Min, Max etc..) to end of var name where appropriate.

### 3.3 Class Names
* Class names are PascalCase. 
* If you use patterns that people are familiar with, it's an obvious name for your class ex. Listener, Visitor
* To help name class, describe to someone in less then 25 words without using if, and, or, but - the name will be in that sentence somewhere.

### 3.3 Object Names
*  
* 


## 4. Readability

1. The indenting style of code conveys logical structure and flow.
1. Point 1
1. Point 1

### 4.1 Spacing
* Do not mix spaces with the tab key - the number of spaces represented by a tab is different in different IDE's.
* An indent == 3 spaces??
* Use space after every comma in a list.
* Use space before and after every "=" of assignment, after every binary operators (+, -, /, *).


### 4.2 Braces
* Do braces begin directly after a function name or start on the next line?

### 4.3 Lines
* Try to keep lines short and clear as general rule - don't want to use horizontal scroll bar.
* Write one statement per line, not multiple statements per line .
* However if  breaking up longer line creates confusing looking code, a longer line is more readable and acceptable. 
* In long lines of similar code with minor variations, stacking vertically will emphasize patterns and make vertical similarities jump out. 

### 4.4 Code Cluster Sizes
* Functions should be under 10? 30? lines of code.
* Classes shouldn't be bigger then 5 member variables and a few hundred lines of code.
* Files shouldn't be longer then 500 lines of code so you can navigate effectively.

## 5. Maintainability
1. Software is a living work, the initial development is just the beginning - expect it to change and evolve.
1. Keep scope of variables as small as possible to avoid confusion and ensure maintainability.
1. Use vars and routines for one purpose only, avoid multipurpose routines that perform a variety of unrelated tasks.
1. Avoid deep nesting, makes code harder to read and follow.
1. Try to keep return point from a function as the last statement in the function.

* Don't put numbers directly in code, put in var that can be changed later .

## 6. Classes
* Most important things at the top, top down story you read.
* Public members first, protected second, private last - public members are most relevent to extension. 
* Try to minimize scrolling either vertically or horizontally.

## 7. Errors
* Always recover or fail gracefully - Report an error message and optimally attempt to continue.
* Provide useful error messages while also logging a programmer friendly message with enough user info so a support team can investigate the error.

## 8. Portability
* Program code should not contain "hard-coded" or literal values referring to environmental parameters such as file paths, user names, host names etc..
* Want code to run on different environments and not fail on systems with a different design then anticipated.
* Parametrize such vars and configure them for the hosting environment outside of the application such as on the application server or in database. 

## 9. Repository

* itgroove practices continuous integration and continous deployment via Visual Studio Team Services
* Policies will be forthcoming 

## 10. Best Practices

### 10.1 Work out loud
* Information should be shared in a timely manner with other team members, regardless of whether that information is deemed relevent. 

### 10.1 DRY - Don't repeat yourself
* This principle summarizes the essense of what it means to write good code, in all languages, at all levels.
* Every piece of knowledge should have a single, unambiguous, authoritative representation within a system 
* If you see the same code twice, wrap it in a function and maximize reusability. 
* DRY matters much less in testing code then it does in production code. 

### 10.2 YAGNI - You ain't gonna need it
* Don’t write code that you think you might need in the future but don't need yet - this is coding for imaginary future use cases. 
* YAGNI code can easily become dead code or will need rewriting because the future case will always turn out different then you imagined it

### 10.3 KISS - Keep it simple silly
* Less is more! The simplest solution is more then sufficient.
* Write as little code as possible, less to read, less to understand, less bugs to show up and have to fix.
* Either code belongs in the app or doesn't - Don't leave commented out code, it will confuse people. 
* Refactor whenever you see the need and have the chance. 

### 10.4 Fail fast, fail often
* Write defensively - always think about what can go wrong, what will happen on invalid input, what might fail, what will help you catch many bugs before they happen
* Check input on nonsensical input or invalid states as early as possible.
* Use error response's or message's that will make the exact problem clear to your caller.

### 10.6 POLA - Principle of least astonishment
* Choose a solution that everyone can understand.
* A component of a system should behave in a way a user expects it to, users should not be astonished by it's behavior. 

### 10.7 Should I use cool new feature "X"?
* Will everyone on my team understand the code? 
* Does it replace another less readable feature?
* Does it reduce redundancy/repetition?
* Does it add information for the reader?
* Does it reduce the likelihood of errors?

### 11 Types
* Do not export types/functions unless you need to share it across multiple components.
* Do not introduce new types/values to the global namespace.
* Shared types should be defined in 'types.ts'.
* Within a file, type definitions should come first.

### 12 Null and Undefined
* Use "undefined". DO NOT use "null".

### General Assumptions 
* Consider objects like Nodes, Symbols, etc. as immutable outside the component that created them. Do not change them.
* Consider arrays as immutable by default after creation.


### Classes 
* For consistency, do not use classes in the core compiler pipeline. Use function closures instead.

### Flags
* More than 2 related Boolean properties on a type should be turned into a flag.

### Strings
* Use double quotes for strings.
* All strings visible to the user need to be localized (make an entry in diagnosticMessages.json).

### Diagnostic Messages
* Use a period at the end of a sentence.
* Use indefinite articles for indefinite entities.
* Definite entities should be named (this is for a variable name, type name, etc..).
* When stating a rule, the subject should be in the singular (e.g. "An external module cannot..." instead of "External modules cannot...").
* Use present tense.

### General Constructs
* Do not use for..in statements; instead, use ts.forEach, ts.forEachKey and ts.forEachValue. Be aware of their slightly different semantics.
* Try to use ts.forEach, ts.map, and ts.filter instead of loops when it is not strongly inconvenient.

### Style
* Use arrow functions over anonymous function expressions.
* Only surround arrow function parameters when necessary. 
* For example, (x) => x + x is wrong but the following are correct:
    x => x + x
    (x,y) => x + y
    <T>(x: T, y: T) => x === y
* Always surround loop and conditional bodies with curly braces. Statements on the same line are allowed to omit braces.
* Open curly braces always go on the same line as whatever necessitates them.
* Parenthesized constructs should have no surrounding whitespace. 
* A single space follows commas, colons, and semicolons in those constructs. For example:
    for (var i = 0, n = str.length; i < 10; i++) { }
    if (x < 10) { }
    function f(x: number, y: string): void { }
* Use a single declaration per variable statement 
    (i.e. use var x = 1; var y = 2; over var x = 1, y = 2;).
* else goes on a separate line from the closing curly brace.
* Use 2 spaces per indentation.