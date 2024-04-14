# Debugging Recursion 🐛

Ok let's take a closer look at our `5!` problem from _Factorial Functions_ and see exactly what's happening.

### Recursive Evaluation
Let's remind ourselves of the math involved when solving `n!`. 

> The factorial of a non-negative integer, 𝑛 denoted by 𝑛! (pronounced n factorial) is the product of all non-negative integers from 𝑛 down to 1 and where 0! is accepted to have a value of 1.

> 𝑛!=𝑛×(𝑛−1)×(𝑛−2)×… ×3×2×1 𝑓𝑜𝑟 𝑎𝑙𝑙 𝑛>0 𝑎𝑛𝑑 0!=1


To solve this problem using **Recursion**, we can think of it happening in 2 stages.

#### Stage 1 📚
