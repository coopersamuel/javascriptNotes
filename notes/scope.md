## Scope

#### Scope is a set of rules for looking up a variable by an identifier name, there is often more than one scope to consider in a given JavaScript program

- LHS/RHS lookup
    - LHS:
        - performed when a variable appears on the left side of an assignment operator `=`
        - `let a = 2;`
        - LHS doesn't care what variable is contained in `a`, all it cares about it finding `a` and putting a new value inside
    - RHS:
        - anything that is not a LHS lookup is considered a RHS lookup
        - RHS finds the actual value assigned to a variable
        - `console.log(a); // ==> 2`
        - this is considered a RHS lookup of `a`, and will grab the value of `2`
    - Example:
        ``` javascript
            function foo(a) { /*RHS*/
                var b = a; /*LHS for b, RHS for a*/
                return a + b; /*RHS for a and b*/
            }

            var c = foo( 2 ); /*LHS for c and a (tricky one: a = 2)*/
        ```
- Nested Scope
    - scopes can be nested similarly to the way blocks of code are nested, when a variable is not found in the immediate scope, the JS Engine will take a look at the parent scope. If the variable still cannot be found, it will continue to inspect the outer containing scope until the outermost or global scope is reached.
- Lexical Scope
    - two types of scope: lexical scope and dynamic scope, most languages use lexical scope including JavaScript
    - lex-time
        - the lexing process examines a string of source code characters and assigns semantic meaning to the tokens as a result of some stateful parsing
        - "To define it somewhat circularly, lexical scope is scope that is defined at lexing time. In other words, lexical scope is based on where variables and blocks of scope are authored, by you, at write time, and thus is (mostly) set in stone by the time the lexer processes your code." - YDKJS
        - essentially, lexical scope means that the programmer decides the scope during the authoring of the code