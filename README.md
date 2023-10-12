# Solidity Project

This Solidity program is a smart contract designed to implement a basic cryptocurrency token. It includes public variables to store essential details about the token (Token Name, Token Abbreviation, Total Supply), a mapping of addresses to balances, and functions for minting and burning tokens while enforcing balance conditions.

## Description
This contract provides the foundation for a cryptocurrency token on the Ethereum blockchain:

Public Variables:
tokenName, tokenAbbreviation, and totalSupply store token information.

Balance Mapping:
balances associates addresses with token balances.

Mint Function:

mint(address _recipient, uint _value) increases the total supply and recipient's balance.

Burn Function:

burn(address _recipient, uint _value) decreases the total supply and sender's balance, with conditions to ensure the sender has enough tokens.
This contract is a versatile starting point for custom token development, ensuring secure issuance, transfers, and burning while safeguarding balances. Customize and expand it to suit your specific requirements.

## Getting Started

### Executing program

To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.

Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension (e.g., MyToken.sol). Copy and paste the following code into the file:
```
// SPDX-License-Identifier: MIT
pragma solidity 0.8.18;

contract MyToken {

    // public variables here
    string public tokenName = "TOKS";
    string public tokenAbbrv = "TKS";
    uint public totalSupply = 0;

    // mapping variable here
    mapping (address => uint) public balances;

    // mint function
    function mint(address _address, uint _value)public {
      totalSupply += _value;
      balances[_address] += _value;
    }

    // burn function
    function burn(address _address, uint _value)public {
      if (balances[_address] >= _value){
         totalSupply -= _value;
         balances[_address] -= _value;
      }
      
    }

}

```
To compile the code, click on the "Solidity Compiler" tab in the left-hand sidebar. Make sure the "Compiler" option is set to "0.8.4" (or another compatible version), and then click on the "Compile MyToken.sol" button.

Once the code is compiled, you can deploy the contract by clicking on the "Deploy & Run Transactions" tab in the left-hand sidebar. Select the  click on the "Deploy" button. Then click on the "Deployed Contracts" to see the drop down menu.

Copy the "Account" to clipboard then go through the "Deployed Contract" drop down menu. Click the "mint" to expand and paste the "Account" on the "_address". Put any value on the "_value" then click transact.

Click the "totalSupply" then you will see the unint value the same as the value you type in earlier.

Go to the "balances" and paste the account. Click the balances, you will see the same value with the "totalSupply"

Now go to the "burn" section. Paste the account and put a desired value. Take note that the value must be less than the value on the "balances" and "totalSupply", otherwise nothing will happen. 

Once the value in the burn section is transact, click the totalSupply and balances, you will see that the values are subtracted with the burn value.

## Authors

Contributors names and contact info

ex. Phoebe Kelly C. Liwanag

