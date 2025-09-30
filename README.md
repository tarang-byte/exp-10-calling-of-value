# exp-10-calling-of-value
For code 1:- Here’s the step-by-step algorithm for your program (swap using pass-by-value):
1. **Start.**

2. **Initialize variables.**
   Set `a = 5`, `b = 2`.

3. **Call the swap function with addresses.**
   Execute `swap(&a, &b)`.

   * Inside the call: `x` points to `a`, `y` points to `b`.

4. **Inside `swap(int *x, int *y)`:**

   1. `temp = *x`

      * Store the value at address `x` (current value of `a`, i.e., 5) into `temp`.
   2. `*x = *y`

      * Write the value at address `y` (current value of `b`, i.e., 2) into the location pointed to by `x` (so `a` becomes 2).
   3. `*y = temp`

      * Write `temp` (5) into the location pointed to by `y` (so `b` becomes 5).
   4. **Return** to `main`.

5. **After return to `main`:**

   * `a` now holds `2`, `b` now holds `5`.

6. **Output results.**
   Print:

   * `value of a is: 2`
   * `value of b  is: 5`

7. **End.**

**Why this works:** Passing `&a` and `&b` gives the function direct access to the original variables via pointers, so changing `*x` and `*y` modifies `a` and `b` in place.

For code 2:-
Here’s the step-by-step algorithm for your program (swap using **pass-by-value**):

1. **Start.**

2. **Initialize variables in `main`.**
   Set `a = 5`, `b = 2`.

3. **Call the function with copies.**
   Execute `swap(a, b)`.

   * Inside the call, parameters receive copies: `x = 5`, `y = 2`.

4. **Inside `swap(int x, int y)`:**

   1. `temp = x` → `temp = 5`.
   2. `x = y` → `x = 2`.
   3. `y = temp` → `y = 5`.
   4. **Return** to `main`. (Only the local copies `x` and `y` changed; `a` and `b` in `main` remain unchanged.)

5. **Back in `main`:**

   * `a` is still `5`.
   * `b` is still `2`.

6. **Output results.**
   Print:

   * `value of a is: 5`
   * `value of b  is: 2`

> Note: In your code, the second `cout` is missing `b`. It should be:
> `cout << "value of b  is:" << b << endl;`

code 3:-
Here’s the step-by-step algorithm (pass-by-reference increment):

1. **Start.**

2. **Initialize in `main`.**
   Set `sal = 27000`.

3. **Call function.**
   Execute `increment(sal)`.

   * Parameter `s` is a **reference** to `sal` (i.e., `s` is another name for `sal`).

4. **Inside `increment(int &s)`:**
   a) Compute `s = s + 5000` → since `s` references `sal`, `sal` becomes `32000`.
   b) Print `salary inside function32000`.
   c) Return to `main`.

5. **Back in `main`:**

   * `sal` is now `32000` (it was modified through the reference).

6. **Output final value.**
   Print `salary inside main32000`.

7. **End.**

*Note:* The printed text has no space after “function”/“main” because the strings don’t include a trailing space. If you want a space, write `"salary inside function "` and `"salary inside main "`.
