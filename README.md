# Julia NaN Handling Bug
This repository demonstrates an uncommon bug related to how Julia handles NaN (Not a Number) values within conditional statements.  The `bug.jl` file showcases the issue, while `bugSolution.jl` provides a corrected version. The bug stems from the fact that comparisons involving NaN always return `false`, even `NaN == NaN` is false. This can lead to unexpected control flow.

## Bug Description
The original code does not explicitly check for NaN values in its conditional statement. Therefore, when NaN is passed as an argument, the condition `x > 0` evaluates to `false`, and the function returns `-NaN`, which is still NaN.  This might be unexpected behavior if a special handling of NaN cases is required.

## Solution
The solution involves adding explicit checks for NaN values using `isnan()` function before any condition checks or performing the main computations.