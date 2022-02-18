# 15.02.2022

Shufan

## Finished

- solidity vulnerabilities

## Notes

1. Calls execution:
    1. internal calls are executed via jumps in the code, array arguments are passed internally by pointers to the memory.
    2. Internal calls for public functions are expensive because internal function calls expects the arguments to be allocated to memory, since the public function does not know if the invocation is external or internal, it copies the arguments to memory and hence is more expensive
    3. calldata is only available for the external function: 
    4. the delegate call will execute on the current function layout

2. the library contract address should be set constant/immutable, or a privileged user can recast the contract to sth that evil.

1. The next piece of information that we need, is that Solidity defaults complex data types, such as structs, to storage when initialising them as local variables. 


4. example of gas stipend attached to a call: partner.call.gas(50000).value(amountToSend)();

5. check if an address has an contract or not:
`
function isContract(address _addr) private returns (bool isContract){
  uint32 size;
  assembly {
    size := extcodesize(_addr)
  }
  return (size > 0);
}
`

## Questions:

2. 
`
func1() {
    winner.send(winAmount);
    payedOut = true;
}

func2() {
    winner.transfer(winAmount);
    payedOut = true;
}
func3() {
    winner.call(){value: 1 ether};
    payedOut = true;
}
`