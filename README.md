# MyToken Contract

This Solidity program includes a token system that has a smart contract in the blockchain which is capable of minting and burning tokens that has public variables that saves token details and mapping to keep balances in check.

## Description

This contract creates a token creation system where users can create new tokens to mint new ones and burn existing ones, in which it can increase and decrease the token balance. The contract includes:
- Variables that stores the token name, token abbreviation, and the token's total supply.
- A mapping that assigns each balance to each address.
- The function to mint and burn tokens to make sure that the total supply and individual balances are properly adjusted to the user's liking.

## Getting Started

### Executing program

- To get started with the `MyToken` contract, you'll need to use the [Remix's Solidity IDE](https://remix.ethereum.org/).
- Once you are on the Remix website, create a new file named `MyToken` in the `contracts` directory and it must be saved as a .sol file extension (MyToken.sol).
- Copy and paste the `MyToken` contract code into the `MyToken.sol` file.
```
// SPDX-License-Identifier: MIT
pragma solidity 0.8.26;

contract MyToken {

    // public variables here
    string public tokenName = "FLAME";
    string public tokenAbbrv = "FLM";
    uint public totalSupply = 0;

    // mapping variable here
    mapping(address => uint) public balances;

    // mint function
    function mint (address _address, uint _value) public {
        totalSupply += _value;
        balances[_address] += _value;
    }

    // burn function
    function burn (address _address, uint _value) public {
        if (balances[_address] >= _value) {
            totalSupply -= _value;
            balances[_address] -= _value;
        }
    }
    
}
```
- Compile the contract by selecting the Solidity compiler and clicking the "Compile" button.

### Deploying the Contract

1. In Remix, go to the "Deploy & Run Transactions" tab.
2. Select the `MyToken` contract from the dropdown menu.
3. Choose the appropriate environment (e.g., JavaScript VM, Injected Web3 for MetaMask, etc.).
4. Click the "Deploy" button to deploy the contract.

### Interacting with the Contract

1. Once deployed, you can interact with the contract using the Remix interface.
2. Use the input fields and buttons provided by Remix to call the `mint` and `burn` functions.
3. Example:
   - To mint tokens, enter an address and a value, then click the `mint` button.
   - To burn tokens, enter an address and a value, then click the `burn` button.

## Authors

Miguel Lacanienta
[@MiguelLacanienta](https://www.facebook.com/miguel.lacanienta.16/)
