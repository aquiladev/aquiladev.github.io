# Transferring dynamic types between contracts in Solidity
In current Solidity implementation it is not possible to return dynamic content from external function calls.
For instance you would like to return string from one smart contract to another.

It is not possible to do it in a nice way, but possible to do in a dirty way via assembly. I'll explain what I'm talking about.

### Smart Contracts
Let's start from smart contracts structure.
Here are two contracts, `Storage` contains data, `Accessor` contains instanse of `Storage` contract.
```
contract Storage {
    function get() public pure returns(string) {
        return "nisl rhoncus mattis rhoncus urna neque viverra justo nec ultrices dui sapien eget mi";
    }
}

contract Accessor {
    Storage private store;

    function Accessor(address _store) public {
        store = Storage(_store);
    }
}
```

### How `Accessor` could retrieve string value from `store.get()` call?

Here is long answer:
```
function get() public view returns (string) {
    return getAsm(store, "get()", 84);              // 84 is length of string, we will come back to it 
}

function getAsm(address _addr, string _func, uint256 _len) public view returns (string data) {
    uint ptr;
    bytes4 sig = bytes4(keccak256(_func));          // function without parameters, otherwise it is more complicated
    assembly {
        ptr := mload(0x40)                          // move pointer to free memory spot
        mstore(ptr, sig)                            // put function sig at memory spot

        let result := call(5000, _addr, 0, ptr, 0x4, ptr, add(_len, 0x40))

        if eq(result, 0) {
            revert(0, 0)
        }

        ptr := add(ptr, 0x40)
        mstore(0x40, add(ptr, add(_len, 0x40)))    // set storage pointer to new space
    }

    data = string(toBytes(ptr, _length)); 
}

uint internal constant WORD_SIZE = 32;             // size of a word, in bytes.
uint internal constant HEADER_SIZE = 32;           // size of header.

function toBytes(uint _addr, uint _len) internal pure returns (bytes memory bts) {
    bts = new bytes(_len);
    uint btsptr;
    assembly {
        btsptr := add(bts, HEADER_SIZE)
    }
    copy(_addr, btsptr, _len);
}

function copy(uint _src, uint _dest, uint _len) internal pure {
    // Copy word-length chunks while possible
    for (; _len >= WORD_SIZE; _len -= WORD_SIZE) {
        assembly {
            mstore(_dest, mload(_src))
        }
        _dest += WORD_SIZE;
        _src += WORD_SIZE;
    }

    // Copy remaining bytes
    uint mask = 256 ** (WORD_SIZE - _len) - 1;
    assembly {
        let srcpart := and(mload(_src), not(mask))
        let destpart := and(mload(_dest), mask)
        mstore(_dest, or(destpart, srcpart))
    }
}
```

### 84
Remember this part?
```
function get() public view returns (string) {
   return getAsm(store, "get()", 84);
}
```
The magic number is length of string in `Storage` contract. I used the constant to simplify solution,
otherwise it would be highly complex.

Length can be retrieved from `call()` result, from header,
but in this case it is not possible to allocate memory and retreive length in one go, we need do call `call()` function twice.

### Magic numbers
You can see lots of magic numbers which have different explanations. In order to understand better purpose of those functions 
and variables would be better to check [documentation](https://solidity.readthedocs.io/en/v0.4.21/assembly.html).

Tags: Ethereum, Blockchain, Solidity, Solidity 0.4.18
