# Gas Optimisation Challenge
The task is to optimise a smart contract by applying various gas optimisation techniques.

## Explanation of changes made:

1. `Fixed Size Array`: Instead of using a dynamic array (`uint[]`), a fixed-size array (`uint[10]`) was used. Fixed-size arrays are more gas-efficient because Solidity does not need to perform dynamic memory allocation.

2. `Caching State Variable`: The length of the `numbers` array was cached in a local variable (`arrayLength`). This avoids redundant/repeated storage reads inside the loop, reducing gas consumption.

3. `Unchecked Block`: The `for loop` was wrapped in an `unchecked` block. This allows skipping certain checks like integer overflow. Since we know the loop range is safe, we can use the `unchecked` block to optimize gas consumption.

4. `For Loop Increment Syntax`: The for loop increment syntax is changed to `++i` to reduce gas consumption.
