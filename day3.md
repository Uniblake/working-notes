# 15.02.2022

Shufan

## Finished

- do coverage tests

- truffle basics

1. When using elements that are smaller than 32 bytes, your contract gas usage may be higher: cause solidity work on 32bytes, so there would be more operations to reduce the element size to the desired size.
2. It might be beneficial to use reduced-size types if you are dealing with storage values because the compiler will pack multiple elements into one storage slot, and thus, combine multiple reads or writes into a single operation.
3. mappings and dynamic arrays: are considered to occupy only 32 bytes with regards to the rules above and the elements they contain are stored starting at a different storage slot that is computed using a Keccak-256 hash.
4. layout in storage: how the address of the mapping/array is computed
5. we can distinguish a short array from a long array by checking if the lowest bit is set: short (not set) and long (set).
6. There is an assembly way to get string length.
7. boolean use uint8, better to pack into uint256 to save slots.
8. variables are initialized with 0x0, do not initialize it manually for saving gas.
9. string smaller than 32 bytes are ok, they can be stored in one slots.
10. avoid repetitive checks across functions.
11. calling internal function is cheaper
12. layout in memory:
    1. four 32-bytes slots reserved.
        1. two for scratching space for hash functions
        2. one for current allocations pointer (free memory pointer)
        3. zero slots
    2. solidity always alloc at free memory pointer, and never free memory.
    3. There are some operations in Solidity that need a temporary memory area larger than 64 bytes and therefore will not fit into the scratch space. They will be placed where the free memory points to, but given their short lifetime, the pointer is not updated. The memory may or may not be zeroed out. Because of this, one should not expect the free memory to point to zeroed out memory.
13. constant and immutable:
    1. constant is sth that will be set at compile time.
    2. immutable is sth that will be set at construction time (inside constructor when deploying) or at declaration. it cannot be read during construction time.
14. functions outside any contract is free functions, they are implicitly internal, and will be included in any contract that call them.
15. dynamic array is only available in storage but not in memory 
16. fallback: when call a function not exist, when no receive function, when no function signature is specified in a call (a call with empty call data).
17. the first 4 bytes of a function call select the function.



## Answers to the questions:
1. 

2. in storage a string less than 32 will take one slot.

3. no, we cannot use push in memory array. a push means we need to make a dynamic array, like copy paste all the existing elements to a new array from the free pointer, and then finally add the new element to the last.
4. a constant need to be defined at the declaration, it will be set at the compile time. an immutable can be defined in the construction time or the declaration.

