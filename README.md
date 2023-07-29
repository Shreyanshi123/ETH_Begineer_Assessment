# Pokemon Token 
This is a solidity program used to create our own token with the help of basic functions and conditional statements in solidity programming.
# Description
This program is a simple contract written in solidity. The contract has three public variables that store the details about the token like tokenName, tokenAbbrv and totalSupply. Mapping is used to map an address with a value. This contract contains two functions mint and burn. Mint function is used to increase the totalSupply of our coin and in contrast burn function is used to destroy token.
# Getting Started
# Executing program
To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.
Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension (e.g., FirstToken.sol). Copy and paste the following code into the file:
// SPDX-License-Identifier: MIT
pragma solidity 0.8.18;
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
    string public tokenName = "AquaStellar";
    string public tokenAbbrv = "AQST";
    uint public totalSupply = 0;

    // mapping variable here
    mapping (address => uint) public balance;

    // mint function
    function mint ( address _walletAddress, uint256 _newValue) public {
        totalSupply = totalSupply + _newValue;
        balance[_walletAddress] = balance[_walletAddress] + _newValue;
    }

    // burn function
    function burn ( address _walletAddress, uint256 _recieveValue) public {
        if(balance[_walletAddress] >= _recieveValue)
        totalSupply = totalSupply - _recieveValue;
        balance[_walletAddress] = balance[_walletAddress] - _recieveValue;
    }
}

To compile the code, click on the "Solidity Compiler" tab in the left-hand sidebar. Make sure the "Compiler" option is set to "0.8.18" (or another compatible version), and then click on the "Compile Assessment.sol" button.

Once the code is compiled, you can deploy the contract by clicking on the "Deploy & Run Transactions" tab in the left-hand sidebar. Select the "Assessment" contract from the dropdown menu, and then click on the "Deploy" button.

once the contract is deployed, you can interact with it by calling the mint function.  Click on MyToken contract and select mint function. Provide adress and value to the mint function and click on transact to execute the function.

To check to supply of your token click on the public variables totalSupply in the contract section. It will display you the amount of token you minted.

Similarly, you can use the burn function and check the value by clicking on the ublic variable totalSupply.

# Authors
Shreyanshi Mishra
shreyanshimishra7689@gmail.com 

# License
This project is licensed under the MIT License - see the LICENSE.md file for details





