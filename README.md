# Gas Optimisation Challenge
The task is to optimise a smart contract by applying various gas optimisation techniques.

## Explanation of changes made:

1. Fixed Size Array: Instead of using a dynamic array (`uint[]`), we use a fixed-size array (`uint[10]`). Fixed-size arrays are more gas-efficient because Solidity does not need to perform dynamic memory allocation.

2. Caching State Variable: We cache the length of the numbers array in a local variable (`arrayLength`) to avoid repeated storage reads in the loop. This avoids redundant storage reads inside the loop, reducing gas consumption.

3. Unchecked Block: We wrap the loop in an `unchecked` block. This allows skipping certain checks like integer overflow. Since we know the loop range is safe, we can use the `unchecked` block to optimize gas consumption.

4. For Loop Increment Syntax: The for loop increment syntax is changed to `++i` to reduce gas consumption.
