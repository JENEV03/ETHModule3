# ETHModule3
# My Token

The main objective of this solidity program is to implement a token contract that enables users to mint and burn tokens. Additionally, the program allows for the tracking of balances associated with specific addresses, and employs conditional statements to ensure that certain processes are carried out only when feasible.

## Description

This program is a straightforward contract that utilizes a mapping data structure to maintain a record of the number of tokens owned by a given address. The program features two functions, one to create tokens and another to remove them. Overall, this program serves as a practical simulation, demonstrating the workings of minting and burning tokens.

## Getting Started

### Executing Program

To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.

Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension (e.g., myToken.sol). Copy and paste the following code into the file:

```solidity
// SPDX-License-Identifier: MIT
pragma solidity 0.8.18;
contract MyToken {
    string public tokenName = "JENEVIVE";
    string public tokenAbbrv = "JEN";
    uint public totalSupply = 0;
    
    mapping(address => uint) public balances;
    function mint (address _address, uint _value) public {
        totalSupply += _value;
        balances[_address] += _value;
    }
    function burn (address _address, uint _value) public {
        if(balances[_address] >= _value ) {
            totalSupply -= _value;
            balances[_address] -= _value;
        }
    }
}
