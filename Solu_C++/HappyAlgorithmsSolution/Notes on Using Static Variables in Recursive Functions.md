Notes on Using Static Variables in Recursive Functions
Use static variables in recursive functions to persist state/data across recursive calls without needing extra parameters.

Use a bool firstCall flag to initialize or reset these static variables on the very first call of the recursion, ensuring that subsequent external calls start fresh.

Reset firstCall to true when the recursion hits the base case so the function can be safely reused in future calls.

For void recursive functions, perform output or side effects (like printing or modifying globals) inside the function instead of returning values.

Alternative design patterns avoid static variables by:

Passing state as additional parameters in the recursion, or

Splitting logic into helper functions, for cleaner design, better modularity, and easier testing.