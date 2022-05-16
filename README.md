# solidity-interview-questions
a list of questions / answers and code snippets from various solidity interviews

* When would you use storage vs calldata (inside function params) ?
  - All state variables and arrays declared outside of the function are state variables and stored in sotrage by default. Storage means data is stored directly on the Blockchain, and the location persistent. Because state can be altered in a contract (e.g: within a function), storage variables must be mutable.
  - Calldata is temporary storage similar to memory (will discuss this later), the main difference being calldata "storage" is non-modifable meaning once function parameters are passed you cannot modify them inside the function. Calldata is cheaper than memory and mostly used with external function types.

* When would you use memory vs calldata?
  - Memory is reserved for variables that are defined within the scope of a function. They only persis while a function is called and thus are temporary variables that cannot be accessed outside this scope (e.g: anywhere else in your contract besides within that function). However, they are mutable within that function.
  - Calldata is an immutable , temporary location where function arguments are stored, and behaves mostly like memory. Arrays and structs with calldata data location can also be returned from functions. Calldata is only valid for parameters of external contract functions. Any variable defined as calldata cannot be modifiable, meaning you cannot change the value of the state of that variable. The data passed into the function is not modified but will be used within the function and a new variable will be returned.
