# solidity-interview-questions
a list of questions / answers and code snippets from various solidity interviews

* When would you use storage vs calldata (inside function params) ?
  - All variables and arrays declared outside of the function are state variables and stored in sotrage by default. Storage means data is stored directly on the Blockchain.
  - Calldata is temporary storage similar to memory (will discuss this later), the main difference being calldata "storage" is non-modifable meaning once function parameters are passed you cannot modify them inside the function. Calldata is cheaper than memory and mostly used with external function types.

* When would you use memory vs calldata?
