# Debugging Recursion 🐛

Ok let's take a closer look at our `5!` problem from _Factorial Functions_ and see exactly what's happening.

### Recursive Evaluation 
Let's remind ourselves of the math involved when solving `n!`. 

> The factorial of a non-negative integer, 𝑛 denoted by 𝑛! (pronounced n factorial) is the product of all non-negative integers from 𝑛 down to 1 and where 0! is accepted to have a value of 1.

> 𝑛!=𝑛×(𝑛−1)×(𝑛−2)×… ×3×2×1 𝑓𝑜𝑟 𝑎𝑙𝑙 𝑛>0 𝑎𝑛𝑑 0!=1

- In our previous example, we used `1` as our _**base-case**_, to stop the function calling itself for infinity.
- In this example we are goign to use `0` as our _**base-case**_, as you might see that more commonly in problems down the line.

#### Question to make you think 🤔 
What is the value of `1!`? What is the value of `0!`? How are they both the same?
- Discuss this with your classmates.

<details>
  <summary>👀 Answer</summary>

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

## Using Recursion to solve `5!`
To solve this problem using **Recursion**, we can think of it happening in 2 stages.

#### Stage 1 📚
