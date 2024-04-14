# Debugging Recursion 🐛

Ok let's take a closer look at our `5!` problem from _Factorial Functions_ and see exactly what's happening.

### Recursive Evaluation 🤓
Let's remind ourselves of the math involved when solving `n!`. 

> The factorial of a non-negative integer, 𝑛 denoted by 𝑛! (pronounced n factorial) is the product of all non-negative integers from 𝑛 down to 1 and where 0! is accepted to have a value of 1.

> 𝑛!=𝑛×(𝑛−1)×(𝑛−2)×… ×3×2×1 𝑓𝑜𝑟 𝑎𝑙𝑙 𝑛>0 𝑎𝑛𝑑 0!=1

- In our previous example, we used `1` as our _**base-case**_, to stop the function calling itself for infinity.
- In this example we are going to use `0` as our _**base-case**_, as you might see that more commonly in problems down the line.

#### Question to make you think 🤔 
What is the value of `1!`? What is the value of `0!`? How are they both the same?
- Discuss this with your classmates.

<details>
  <summary>👀 Answer: </summary>

>
The _**factorial function**_, denoted by ``!``, is a mathematical operation that calculates the product of all
positive integers up to a given number. 

**Factorial of 1:**
   
   _By definition, the factorial of 1 is the product of all positive integers up to 1.  Since there's only one positive integer (which is 1), the factorial of 1 is simply 1.
   ``1! = 1``_

**Factorial of 0:**
   
   _The definition of the factorial function is based on the concept of permutations and combinations. If you think about it, there's only one way to arrange zero objects: doing nothing.
   Therefore, ``0!`` represents the number of ways to arrange zero objects, which is 1. ``0! = 1``._

Therefore, both ``1! = 1`` and ``0! = 1``. 😎

</details>

>

<br>

## Using Recursion to solve `5!`
To solve this problem using **Recursion**, we can think of it happening in 2 stages.

### Stage 1 📚
In the first stage _(illustrated below)_ the number whose factorial is being sought is multiplied by the factorial of the previous number. This _**‘chain’**_ of operations continues until ``0!`` is reached.

![image](https://github.com/ross-bish/Recursion-HL-/assets/83789503/930a8472-6e94-458d-92a2-ccfa7209ae0d)

### Stage 2 📚
In the second stage of the evaluation the chain is _**‘unwound’**_ starting from the evaluation of ``0!``. The result of this enables the completion of each successive step up the chain until ``5!`` is reached. This is depicted as follows:

![image](https://github.com/ross-bish/Recursion-HL-/assets/83789503/c9eeb059-e3e1-4232-b935-e54af1cd295f)


### Sample Code 👨🏽‍💻 
Now, try typing the code below into **Thonny**, and I want you to use the debugger 🪲 to try to visualise & understand **Stage 1** and **Stage 2** outlined above.

![image](https://github.com/ross-bish/Recursion-HL-/assets/83789503/56d2f181-9892-476b-87ca-76c0f98237dd)


#### 💡Note: 
> When using the debugger in Thonny, you must first save your python file.

> After you click on the debugger icon, click on the _**step into**_ icon.

![image](https://github.com/ross-bish/Recursion-HL-/assets/83789503/4c482ee4-c5b2-4a43-83f3-fa3d474247b9)

**Sample Code:**

````py

def factorial(n):
    if n > 0:                            # The base-case is set to 0
        return n * factorial (n - 1)     # Call the function within the function 
    else:
        return 1
    
print(factorial(5))                      # Call the function within your print statement
````

### Summary 📝

1. **Base Case**: A condition that stops the recursion. In the factorial example, it's when `n = 0`.
  
2. **Recursive Case**: The condition where the function calls itself with a simpler/smaller input.

   In the factorial example, it's `n * factorial(n - 1)`.

3. **Progress Toward Base Case**: Each recursive call should move closer to the base case.

   In the factorial example, `n` is decremented by 1 with each recursive call.

4. **Return Value**: Each recursive call returns a value, which is eventually used to compute the final result.

   In the factorial example, each call returns `n * factorial(n - 1)`.

 
Recursion can be a bit mind-bending at first, but it's a powerful technique once you get the hang of it, just remember to always have a base case to prevent _**infinite recursion!**_
Recursion in Python is elegant and often more readable than iterative solutions for certain problems.

However, it also has limitations like maximum recursion depth, which can lead to `RecursionError` if exceeded!

<br>

## Program Context and Call Stack 📚 
It is worth noting that recursion is considered to be computationally expensive because it requires a relatively large amount of memory to implement.

![image](https://github.com/ross-bish/Recursion-HL-/assets/83789503/eb873454-d2d8-4834-bae7-760421b83539)

To understand why it is the case, it is first necessary to understand two concepts: the **program context** and the **call stack**.

**Program Context**:
- The program context is like a snapshot of what's happening inside a program at any given moment.
- It includes things like where the program is in its execution (the current instruction), the values of variables, and other data.
- This context is crucial for Python to keep track of what's going on in the program.

**Call Stack**:
- The call stack is a memory area that Python uses to manage function calls.
- Every time a function is called, Python saves the current program context onto the call stack.
- This includes information like where the function was called from and the values of variables at that point.
- When the function finishes executing, Python "pops" or removes its context from the call stack.
- This process ensures that when the function returns, the program can pick up where it left off with the same context it had before calling the function.

In essence, the call stack helps Python keep track of where it is in a program and what needs to happen next, especially when functions are involved.

## Stack Overflow 📚
A stack overflow happens when the call stack runs out of space due to too many function calls, often caused by _recursive functions_ that don't have proper _base-cases_ or _termination conditions._

Let's break it down from the ground up:

1. **Memory Allocation**:
   - When a program runs, it needs memory to store various things like variables, function calls, and their associated data.
   - This memory is allocated in different areas, including the call stack.

2. **Call Stack Functionality**:
   - The call stack is a portion of memory used to manage function calls.
   - When a function is called, information about the function call, including parameters and local variables, is stored on the stack.
   - Each new function call adds a "stack frame" to the top of the stack.

3. **Recursion**:
   - Recursion occurs when a function calls itself.
   - With each recursive call, a new stack frame is added to the call stack.
   - The function's context (local variables, parameters, etc.) for each call is stored in these stack frames.

4. **Stack Overflow**:
   - A stack overflow happens when the call stack reaches its maximum capacity.
   - This can occur when there are too many recursive function calls or when the depth of the recursion is too high.
   - Each new function call adds a new stack frame, and if there are too many function calls without returning, the stack becomes full.

5. **Consequences**:
   - When a stack overflow occurs, it means **there's no more room on the call stack to store new function calls and their data.**
   - This situation is often caused by infinite recursion or excessively deep recursion.
   - The program can't continue executing because it can't allocate more memory for new stack frames.
   - **As a result, the program crashes, and an error message, such as "Stack Overflow" or "RecursionError," is typically displayed.**


## Example - Sum of first `n` integers. 👨🏽‍💻
The code shown below is a recursive implementation of the ``sumOfN`` function. The purpose of the function is to return the sum of the first ``n`` integers.

👉 Type up this code into Thonny & try for yourself. _(you will need to delete the line numbers.)_

````py
# A recursive function to add up the first n numbers. 
# Example: The sum of the first 5 numbers is 5 + the sum of the first 4 numbers
# So, the sum of the first n numbers is n + the sum of the first n-1 numbers

1.    def sumOfN(n):
2.    
3.        if n == 0:
4.            return 0
5.    
6.        return n + sumOfN(n-1)
7.
8.    # Call the function to test it
9.    answer = sumOfN(5)
10.   print(answer)

````

When **line 9** of the program is executed the program context is saved at the bottom of the call stack – shown in the illustration below.

This is the program context at the point when ``sumOfN(5)`` was called. 

The call stack is progressively built up in response to the successive recursive calls to the ``sumOfN`` function made on **line 6**. This continues until ``sumOfN`` is called with an argument of `0`.

![image](https://github.com/ross-bish/Recursion-HL-/assets/83789503/0cce46e0-76e3-4db1-8a08-a4dfceb4707f)

At this point the condition on **line 3** evaluates to ``True`` and the stack begins to unwind on a _**last-in, first-out (LIFO)**_ principle. 

The program context at the point of each call to ``sumOfN`` is restored in the reverse order to which it was saved. The addition operation on **line 6** is completed for each call, eventually leading to an answer of ``15``.

![image](https://github.com/ross-bish/Recursion-HL-/assets/83789503/5960d8ca-9766-4580-af69-378d40596647)

<br>
### Challenge ⚔️
Using your debugger 🪲 like the problem above, see if you can identify the different stages of what the Recursive function `sumOfN` does. 
