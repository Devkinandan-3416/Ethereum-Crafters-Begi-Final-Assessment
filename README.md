# Ethereum Beginner Course Project: Create a token

This is the basic demonstration of creating our own token using the Solidity programming language. It serves the purpose of gaining the basic knowledge about how the transactions takes place between sender and reciever and how the individuals retain their token amount as balance.

## Description

This program is a simple contract written in Solidity that explains the creation of a token by any individual and how the different addresses are mapped to their individual amounts holding for confidentiality, integrity and reliability as being a decentralized system.
First, creating a simple contract inside which three public variables(token_name, token_abbv and total_supply) are created then map addresses with individual amounts and then crating mint and burn functions for adding and subtracting the amount value respectively as per sender/reciever's choice for minting or burning function to make transactions.

## Getting Started

### Executing program

To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.

Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension (e.g., myToken.sol). Copy and paste the following code into the file:

```javascript
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.7;

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

contract MyToken {

    // public variables here
    string public tName = "DEVCoin";
    string public tAbbrv = "DEVC";
    uint public totalSupply;

    // mapping variable here
    mapping(address => uint) public balances;

    // mint function
    function mint(address _v, uint _val) public {
        totalSupply += _val;
        balances[_v] += _val;
    }

    // burn function
    function burn(address _u, uint _val) public {
        if(balances[_u] >= _val) {
            totalSupply -= _val;
            balances[_u] -= _val;
        }
    }

}
```

To compile the code, click on the "Solidity Compiler" tab in the left-hand sidebar. Make sure the "Compiler" option is set to "0.8.7" (or another compatible version), and then click on the "Compile myToken.sol" button.

Once the code is compiled, you can deploy the contract by clicking on the "Deploy & Run Transactions" tab in the left-hand sidebar. Select the "myToken" contract from the dropdown menu, and then click on the "Deploy" button.

Once the contract is deployed, you can interact with it by calling the mint and burn functions. Click on the "myToken" contract in the left-hand sidebar, and then click on the "mint or burn" function. Finally, click on the "transact" button to execute the function and retrieve the balance by calling for the balance variable or totalSupply variable.

## Authors
Devkinandan Garg
