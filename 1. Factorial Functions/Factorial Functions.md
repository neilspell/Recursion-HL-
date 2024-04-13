# Factorial Functions 📚

We are going to explore Factorial Functions and compare two different approaches to solving these:

1. Recursion
2. Iteration

What does factorial mean? `5!` or _**five factorial**_ simply means multiply all the numbers from `5` down to `1`.

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

### Challenges ⚔️
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

### Let's take a closer look 🤓
In this recursive approach, the function calls itself with `n-1` until `n` reaches `1`. Then, it returns `1`. 

Each time it returns, it multiplies the current `n` with the result of the function call with `n-1`.


## 2. Iteration - Factorial Function 👨🏽‍💻
Now, can you create a different solution to the same problem, using **iteration**?

**Parson's Problem 🧩**
- Create your own Iterating Function to calculate `5!`.
- The code below is jumbled up, rearrange it to create your function.

````py
def factorial_iterative(n):
    result = 1
    for i in range(1, n + 1):
        result *= i
    return result

# Calculate 5!
result_iterative = factorial_iterative(5)
print("Factorial of 5 using iteration:", result_iterative)
````
