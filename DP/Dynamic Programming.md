Usually, problems where you use DP can only be solved with DP (in a reasonable time complexity).
### What exactly is DP?
In short, dynamic programming is just optimized recursion.
### When should I consider using DP?
Problems that should be solved with DP usually have two main characteristics:
1. The problem will be asking for an optimal value (max or min) of something or the number of ways to do something.
2. At each step, you need to make a "decision", and decisions affect future decisions.

## Framework for DP
This framework is great for beginners as it works for any DP problem and provides a systematic way to develop algorithms, so it's a great tool to remember.

To create any DP algorithm, there are 3 main components.
1. A function or data structure that will compute/contain the answer to the problem for any given state
	1. Since we're starting with top-down, we will be talking about a function here. This involves two parts. First, we need to decide what the function is returning. Second, we need to decide on what arguments the function should take (state variables).
2. A recurrence relation to transition between states
3. Base cases

Back to [[README]]