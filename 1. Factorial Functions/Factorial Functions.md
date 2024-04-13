# Factorial Functions 📚

We are going to explore Factorial Functions and compare two different approaches to solving these:

1. Recursion
2. Iteration

What does factorial mean? The factorial of a number is the product of all positive integers up to that number.

Therefore `5!` or _**five factorial**_ simply means multiply all the numbers from `5` down to `1`.

Example:
````
5! = 5 x 4 x 3 x 2 x 1 = 120
````

In Python, we can use two different methods to solve this type of problem.

## 1. Recursion - Factorial Function 👨🏽‍💻

Let's take a look at the example given to us in the textbook:


![image](https://github.com/ross-bish/Recursion-HL-/assets/83789503/a310a40d-9b87-4162-94a7-342ec182adbe)
![image](https://github.com/ross-bish/Recursion-HL-/assets/83789503/1624e26b-772f-40a0-b0b7-4bd22c50139e)

![image](https://github.com/ross-bish/Recursion-HL-/assets/83789503/c80f6b05-26b1-40fd-af3e-d215bedee025)
![image](https://github.com/ross-bish/Recursion-HL-/assets/83789503/e63f377b-976a-4cf8-8963-93bceceab092)

![image](https://github.com/ross-bish/Recursion-HL-/assets/83789503/d334269e-08ce-43a2-9ea2-58c3b40843d4)
![image](https://github.com/ross-bish/Recursion-HL-/assets/83789503/9dbe963c-33a6-4ace-add8-67fe365504d2)

![image](https://github.com/ross-bish/Recursion-HL-/assets/83789503/9965e462-45c9-4cd9-a7e9-dbfe401f5b5c)


**Part A - Parson's Problem 🧩**
- Using the example outlined above, create your own Recursive Function to calculate `5!`.
- The code below is jumbled up, rearrange it to create your function.

  
````py
if n > 1:
return 1
def factorial(n):
else:
return n * factorial(n - 1)
print(answer)   
answer = factorial(5)

````
**Part B**
- Test your function for different values (i.e. `4!`, `6!`, `10!`)

#### Let's take a closer look 🤓
In this _recursive approach_, the function calls itself with `n-1` until `n` reaches `1`. Then, it returns `1`. 

Each time it returns, it multiplies the current `n` with the result of the function call with `n-1`.

Recursion can be a bit mind-bending at first, but it's a powerful technique once you get the hang of it. Just remember to always have a **base case** to prevent infinite recursion!




## 2. Iteration - Factorial Function 👨🏽‍💻
Now, can you create a different solution to the same problem, using **iteration** instead of recursion?

**Part A - Parson's Problem 🧩**
- Create your own Iterating Function to calculate `5!`.
- The code below is jumbled up, rearrange it to create your function.

````py
print("Factorial of 5 using iteration:", result_iterative)
for i in range(1, n + 1):
result = 1
def factorial_iterative(n):
return result

# Calculate 5!
result_iterative = factorial_iterative(5)
result *= i

````

#### Let's take a closer look 🤓
In this _iterative approach_, we start with result initialized to `1`. Then, we iterate from `1` to `n`, multiplying ``result`` by each number in the range.


## Summary
Both approaches will give you the same result: ``120``. 

- However, the _recursive approach_ uses function calls and might be less efficient for larger values of `n` due to the overhead of function calls and the potential for [stack overflow](https://levelup.gitconnected.com/what-the-heck-is-a-stack-overflow-cb5bb17870a0). 

- The _iterative approach_ is generally more efficient and is preferred for factorial calculations.


# Extra Credit ✨📖
_Recursion_ and _Iteration_ are both powerful techniques for solving problems, and each has its own strengths and weaknesses. 

Here are some considerations for when to use recursion over iteration:

1. **When the problem can be naturally divided into smaller, similar subproblems:** Recursion is well-suited for problems that can be broken down into smaller instances of the same problem. Examples include tree traversal, factorial calculation, and recursive algorithms like quicksort and mergesort.

2. **When the problem can be elegantly expressed using recursive calls:** Some problems have recursive definitions, making recursion a natural choice. For instance, problems involving self-similarity or fractals often lend themselves to recursive solutions.

3. **When simplicity and clarity of code are more important:** In certain cases, recursion can lead to more concise and readable code compared to iterative solutions. Recursive code can closely mirror the mathematical or logical structure of the problem, making it easier to understand and maintain.

4. **When the problem requires backtracking or tree traversal:** Recursive algorithms are often used in scenarios where backtracking or tree traversal is needed, such as maze solving, pathfinding, or graph traversal problems.

However, there are also scenarios where recursion may not be the best choice:

1. **When efficiency and performance are critical:** Recursive solutions may incur additional overhead due to function calls and maintaining call stack. In such cases, iterative solutions might be more efficient and have better performance characteristics, especially for problems with large input sizes.

2. **When there is a risk of stack overflow:** Recursive solutions rely on the call stack, and excessively deep recursion can lead to stack overflow errors. Iterative solutions, which use loops, are typically more memory-efficient and do not suffer from stack overflow issues.

3. **When the problem requires deep recursion:** Some programming languages and environments impose limits on the depth of recursion, which can restrict the applicability of recursive solutions. In such cases, an iterative approach might be necessary.

Recursion is a powerful technique that is particularly well-suited for problems with recursive structure or when simplicity and clarity of code are important. However, it's essential to consider factors such as performance, memory usage, and potential stack overflow when deciding between recursion and iteration.
