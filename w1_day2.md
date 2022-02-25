# 15.02.2022

Shufan

## Finished

- SI CTF

1. call with specified gas, _callable.call.value(0).gas(10000)("")
2. block.number is the current block, i.e. the block that will contain the current transaction.
3. when creating new contract, for user private key, the nonce start from 0, for contract, the nonce start from 1.
4. block.blockhash(block.number) always yield zero.
5. when using future block as a psudorandom source, make sure the block number is withint 256 block, or we will obtain the blockhash as 0
6. block.timestamp is the timestamp of the current block.

