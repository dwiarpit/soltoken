# soltoken

This Solidity program is a simple "Token creating" program that demonstrates the basic syntax and functionality of the Solidity programming language. The purpose of this program is to serve as a starting point for those who are new to Solidity and want to get a feel for how it works.

# Deacription
This program is a simple contract written in Solidity, a programming language used for developing smart contracts on the Ethereum blockchain. This contract has function named mint and burn in which the mint function add some tokens in the address and burn function is used to burn some token.

# Getting started

Executing program
To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.

Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension (e.g., HelloWorld.sol). Copy and paste the following code into the file:


    //SPDX-License-Identifier: MIT
    
    pragma solidity ^0.8.8;
    
    contract SolToken {
        string public userToken;
        string public userTokenSymbol;
        uint256 public totalSupply;

    mapping(address => uint256) public balances;

    constructor(string memory _name, string memory _symbol, uint256 _totalSupply) {
         userToken = _name;
       userTokenSymbol = _symbol;
        totalSupply = _totalSupply;
        balances[msg.sender] = _totalSupply;
    }

    function mint(address _to, uint256 _value) public {
        totalSupply += _value;
        balances[_to] += _value;
    }

    function burn(address _from, uint256 _value) public {
        require(balances[_from] >= _value, "Insufficient balance");
        totalSupply -= _value;
        balances[_from] -= _value;
    }
    }

# Authors
 Arpit

# License
This project is licensed under the Apache License - see the LICENSE.md file for detail.

    
