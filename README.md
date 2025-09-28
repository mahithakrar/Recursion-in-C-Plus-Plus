# Recursion in C++

##  Overview  
Recursion in C++ is a programming technique where a function **calls itself directly or indirectly** to solve a problem. Instead of using iterative constructs like `for` or `while` loops, recursion breaks down a problem into **smaller subproblems** of the same type until a base condition is met.  

Key points about recursion:
- Each recursive call creates a **new function instance** with its own local variables and execution context (stack frame).  
- Every recursion must have a **base case** to prevent infinite calls.  
- Problems like **factorial, Fibonacci sequence, Tower of Hanoi, binary search, and tree traversals** are naturally suited for recursion.  

---

## Theory  

###  Structure of a Recursive Function
A recursive function generally has two parts:
1. **Base Case** → The terminating condition that stops recursion.  
2. **Recursive Case** → The function calls itself with modified parameters.  

**Syntax Example:**
```cpp
returnType functionName(parameters) {
    if (base_condition) {
        // Base case
        return result;
    } else {
        // Recursive case
        return functionName(modified_parameters);
    }
}
```

###  How Recursion Works (Execution Flow)
1. **Function Call**: Each recursive call is pushed onto the call stack.  
2. **Recursive Expansion**: Calls continue until the base case is met.  
3. **Backtracking**: Once the base case is satisfied, results are returned back through the stack frames.  

---

###  Types of Recursion
1. **Direct Recursion**  
   - A function calls itself directly.  
   ```cpp
   void func() {
       func(); // Direct call
   }
   ```

  ### 🔹 Indirect Recursion
In indirect recursion, a function calls another function which eventually calls the first function again.  
This creates a cycle of recursive calls.  

**Example:**
```cpp
#include <iostream>
using namespace std;

void B(int n); // Forward declaration

void A(int n) {
    if (n > 0) {
        cout << n << " ";
        B(n - 1);  // Calls function B
    }
}

void B(int n) {
    if (n > 1) {
        cout << n << " ";
        A(n / 2);  // Calls function A
    }
}

int main() {
    A(10);
    return 0;
}
 ```

# Program Summary

##  1.Sum of First N Natural Numbers using Recursion
This program calculates the sum of the first **N natural numbers** using a **recursive function** in C++.  
- The user inputs a value `n`.  
- The function `sum(n)` computes the sum by repeatedly calling itself with a smaller argument (`n-1`) until it reaches the base case (`n == 0`).  
- The result is then returned and displayed.  

The program demonstrates the concept of **recursion**, where a function solves a big problem by breaking it into smaller subproblems until a terminating condition is met.  

---

##  Algorithm
1. **Start**  
2. Read the input value `n`.  
3. Call the recursive function `sum(n)`.  
4. Inside `sum(n)` function:  
   - If `n == 0` → return `0` (**base case**).  
   - Otherwise → return `n + sum(n - 1)` (**recursive case**).  
5. Continue recursion until the base case is reached.  
6. Backtrack through the recursive calls, adding all values.  
7. Display the final result (sum of first `n` natural numbers).  
8. **End**  

---

##  2.Reverse a String using Recursion in C++

This program takes a string as input and reverses it using a **recursive function**.  
- The recursive function `reverseString(str, start, end)` swaps characters from both ends (`start` and `end`) and moves inward.  
- The recursion continues until the `start` index is greater than or equal to the `end` index (base case).  
- Finally, the reversed string is displayed.  

This demonstrates how recursion can be applied to string manipulation problems.

---

##  Algorithm
1. **Start**  
2. Input a string from the user.  
3. Find the length of the string.  
4. Call the function `reverseString(str, 0, length - 1)`.  
5. Inside `reverseString(str, start, end)`:
   - If `start >= end`, return (base case).  
   - Otherwise:  
     - Swap `str[start]` and `str[end]`.  
     - Recursively call `reverseString(str, start + 1, end - 1)`.  
6. Continue recursion until all characters are swapped.  
7. Print the reversed string.  
8. **End**  

---

##  3.Factorial of a Number using Recursion in C++

This program calculates the **factorial of a number (n!)** using a **recursive function**.  
- Factorial is defined as:  
The factorial of a non-negative integer `n` is defined as the product of all positive integers less than or equal to `n`.
\[
n! = n \times (n-1) \times (n-2) \times \dots \times 1
and by definition, `0! = 1` and `1! = 1`.  
- The function `factorial(n)` calls itself with the argument `(n-1)` until the base case is reached (`n == 0` or `n == 1`).  
- The result is then returned and displayed in the main function.  

---

##  Algorithm
1. **Start**  
2. Input an integer `num` from the user.  
3. Call the function `factorial(num)`.  
4. Inside the function:  
 - If `n == 0` or `n == 1`, return `1` (**base case**).  
 - Otherwise, return `n * factorial(n - 1)` (**recursive case**).  
5. Multiply results during backtracking of recursive calls.  
6. Print the final factorial result.  
7. **End**  

---

##  Conclusion  
Recursion in C++ is a **powerful programming technique** that allows solving complex problems in a structured and elegant way. By dividing problems into smaller subproblems and solving them recursively, developers can write cleaner and more intuitive code.  
However, recursion should be used carefully:
- Always define a **base case** to avoid infinite recursion.  
- Be mindful of **stack memory limitations**.  
- For problems that involve very deep recursion, an **iterative solution** may be more efficient.  
In essence, recursion is most effective for problems naturally defined in recursive terms (like **factorial, Fibonacci, binary search, and tree/graph traversals**) and is an essential tool in every C++ programmer’s toolkit.  
