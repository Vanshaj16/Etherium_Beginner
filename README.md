# Project: Create a Token

This Solidity program is to create a token using Solidity programming language.The purpose of this program is to help those people who want to create their own token in easy and understandable way by apply the important concepts of solidity programming language.

## Description

This program is a smart contract on creating a token written in Solidity, a programming language used for developing smart contracts on the Ethereum blockchain.The program contain public variables which are type state variable.There is a mapping used to get the amount of the token of the given address (address => value).There are two functions- the first function is the mint function that takes two parameters: an address and a value. The function then increases the total supply by that number and increases the balance of the “sender” address by that amount.And the second function is the burn function, which works the opposite of the mint function, as it will destroy tokens.It will take an address and value just like the mint functions.Then will deduct the value from the total supply and from the balance of the “sender”.

## Getting Started
https://gist.github.com/Vanshaj16

This is the source code to create a token.
### Executing program
To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.

Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension (e.g., MyToken.sol). Copy and paste the following code into the file:
```
// SPDX-License-Identifier: MIT
pragma solidity 0.8.26;
/*
       REQUIREMENTS
    1. Your contract will have public variables that store the details about your coin (Token Name, Token Abbrv., Total Supply)
    2. Your contract will have a mapping of addresses to balances (address => uint)
    3. You will have a mint function that takes two parameters: an address and a value. 
       The function then increases the total supply by that number and increases the balance 
       of the “sender” address by that amount
    4. Your contract will have a burn function, which works the opposite of the mint function, as it will destroy tokens. 
       It will take an address and value just like the mint functions. It will then deduct the value from the total supply 
       and from the balance of the “sender”.
    5. Lastly, your burn function should have conditionals to make sure the balance of "sender" is greater than or equal 
       to the amount that is supposed to be burned.
*/
contract my_Token {

    // public variables here
     string public tokenName ="Chennai Super Kings";
     string public tokenAbbrv ="CSK";
     uint public totalSupply = 0;

    // mapping variable here
     mapping (address => uint) public Balances;

    // mint function
     function mintFunction(address _address ,uint _value) public {
        totalSupply += _value;
        Balances[_address] += _value;

     }
    // burn function
     function burnFunction(address _address ,uint _value) public {
        if(Balances[_address] >= _value)
        {totalSupply -= _value;
        Balances[_address] -= _value;
        }
     }
}

```
To compile the code, click on the "Solidity Compiler" tab in the left-hand sidebar. Make sure the "Compiler" option is set to "0.8.26" (or another compatible version), and then click on the "Compile MyToken.sol" button.

Once the code is compiled, you can deploy the contract by clicking on the "Deploy & Run Transactions" tab in the left-hand sidebar. Select the "my_Token" contract from the dropdown menu, and then click on the "Deploy" button.

Once the contract is deployed, insert the Account address to the address bar in the mint and the burn function in the deploy sidebar. Now enter the value in the mint function value bar and see the result in the totalSupply and Balances bar. To burn an amount enter the value in the burn function bar. You an see the name of the token and addreviation of the token by clicking on the tokenName bar and tokenAbbrv bar.
## Authors

Vanshaj

vanshajsen16@gamil.com
