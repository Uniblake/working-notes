# 15.02.2022

Shufan

## Finished

- writing own smart contract

- evm basics from Hubert


## Notes

1. constructors: it is an optional function to initialize state variable, one contract with only one constructor.
2. when deployed to blockchain, the constructor code and any internal code used only by constructor are not included.
3. info attached to msg:
    a. msg.data (bytes): complete calldata
    b. msg.gas (uint): remaining gas - deprecated in version 0.4.21 and to be replaced by gasleft()
    c. msg.sender (address): sender of the message (current call)
    d. msg.sig (bytes4): first four bytes of the calldata (i.e. function identifier)
    e. msg.value (uint): number of wei sent with the message
4. transaction order is only competitive and exploitable between different addresses, transactions from the same address must obey the order according to the nonce.
5. block stamp is controlled by the miner, which would be +-15s, this can be inaccurate and exploit by the miner, but too early or too late will all be bad.
6. each contract protect its own storage.
7. solidity allow divide 0, which will return 0.
8. inheritance linerization.
9. When Solidity constructors take arguments, include them in the header or at the constructor of the derived contracts.

## Questions

what is the difference between the gas, wei, eth, decimal.
10^18 Gwei == 1 eth. gwei is just another denomination of ether.
and it's much easier to specify gas price in gwei.