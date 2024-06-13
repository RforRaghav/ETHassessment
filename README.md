# MyToken Contract

## Simple Overview

The MyToken contract is a basic implementation of a cryptocurrency token on the Ethereum blockchain. It facilitates  token creation (minting) and destruction (burning), along with functionality to monitor balances associated with different addresses.

## Description

The MyToken contract simplifies token management on Ethereum. It supports minting new tokens to increase total supply and address balances, and burning tokens to decrease total supply and address balances. The contract maintains balance records using a mapping and enforces sufficient balance checks before token burning.

## Getting Started

### Installing

To begin using the MyToken contract, set up a Solidity development environment. Recommended tools include Remix IDE, Truffle, or Hardhat.

## Executing Program

### How to run the program

Open your Solidity development environment (e.g., Remix IDE).
Create a new file named MyToken.sol.
Copy and paste the following code into MyToken.sol:
solidity

// SPDX-License-Identifier: MIT
pragma solidity 0.8.18;

contract MyToken {

    // Public variables
    string public name = "META1";
    string public symbol = "MTA1";
    uint256 public totalSupply = 0;

    // Mapping of balances
    mapping(address => uint256) public balances;

    // Mint function
    function mint(address _address, uint _value) public {
        totalSupply += _value;
        balances[_address] += _value;
    }

    // Burn function
    function burn(address _address, uint _value) public {
        if (balances[_address] >= _value){
            totalSupply -= _value;
            balances[_address] -= _value;
        } 
    }
}

Ensure the Solidity compiler is set to version 0.8.18.
Compile the contract to check for syntax errors.
Deploy the contract to a local or test Ethereum network using Remix or your preferred deployment tool.
## Authors
Raghav Sharma

@RforRaghav

## License

This project is licensed under the MIT License - see the LICENSE.md file for details

