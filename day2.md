# 15.02.2022

Shufan

## Finished

- writing own smart contract

- writing tests

## Notes

1. inheritance: virtual: this function can be overloaded, override: this function is overriding another function. https://medium.com/upstate-interactive/solidity-override-vs-virtual-functions-c0a5dfb83aaf
2. abstract contract: if there is any function un-implemented in a contract, then it is an abstract contract.
3. address:
    1. address(this) indicates to the address of the contract instance.
    2. address/ address payable: cast by payable(address).
5. library: 
    1. is just another type of contract, usability, economical (save gas cause deploy once).
    2. is stateless, has no storage.
    3. doesn't hold ether, not allowed to payable functions.
    4. cannot be inherit or inherit.
    5. cannot be destroyed.
6. selfdestruct can be leveraged to transfer ether to any address, thus never use address(this).balance, cause it can be manipulated. "this" indicates a contract instance. balance can be called on address.
7. javascript, variable scope: 
    1. var: the scope is the function body
    2. let: the scope is inside the bracket {}
8. inline assembly: do operations that solidity cannot, which may save gas
9. levels of call, send, transfer: 
    1. call, lowest, no protection
    2. send, with return, with stack depth and gas limits, will not revert the transaction
    3. transfer, with extra protection, if revert, then revert whole transaction, and has gas limit.



questions:
1. create2: precompute the contract address and then deploy it.
2. how self-destruct is executed. 