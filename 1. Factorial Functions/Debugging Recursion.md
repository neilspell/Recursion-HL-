# Debugging Recursion 🐛

Ok let's take a closer look at our `5!` problem from _Factorial Functions_ and see exactly what's happening.

### Recursive Evaluation 
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

````html

def factorial(n):
    if n > 0:    # The base-case is set to 0
        return n * factorial (n - 1)
    else:
        return 1
    
print(factorial(5))  # Call the function within your print statement
````

