##Scope

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
        - ``` javascript
            function foo(a) { /*RHS*/
                var b = a; /*LHS for b, RHS for a*/
                return a + b; /*RHS for a and b*/
            }

            var c = foo( 2 ); /*LHS for c and a (tricky one: a = 2)*/
        ```
        - 