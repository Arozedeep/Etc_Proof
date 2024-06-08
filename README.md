# My Token

The purpose of this project is to create a customizable token using Solidity.

## Description

This Solidity contract defines a basic token called MyToken. It includes public variables for storing the token name, abbreviation, and total supply, as well as a mapping for storing token balances. The contract also includes functions for minting new tokens and burning existing tokens. Overall, the contract provides a foundation for creating and managing a simple token.

## Getting Started

### Executing program

To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.

Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension. Copy and paste the following code into the file:

```
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.18;

contract MyToken {

    // public variables here
    string public tokenName = "UniversalCoin";
    string public tokenAbbrv = "UC";
    uint public totalSupply = 1000;

    // mapping variable here
    mapping(address => uint) public balances;

    // mint function
    function mint (address _address , uint _value) public {
        totalSupply += _value;
        balances[_address] += _value;
    }

    // burn function
    function burn ( address _address , uint _value) public {
        if (balances[_address] < _value) {
            revert("Not enough Balance");
        }
        else {
        totalSupply -= _value;
        balances[_address] -= _value;
        }
    }
}
```

To compile the code, click on the "Solidity Compiler" tab in the left-hand sidebar and then click on the "Compile Eth_Proof.sol" button.

Once the code is compiled, you can deploy the contract by clicking on the "Deploy & Run Transactions" tab in the left-hand sidebar. 

Once the contract is deployed, you can interact with it by calling the different functions. 






