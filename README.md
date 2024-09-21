# MyToken Solidity Contract

This Solidity contract implements a basic token system with minting and burning functionalities. It demonstrates the fundamental concepts of token creation, supply management, and conditional logic in Solidity. The contract is designed for educational purposes and serves as a foundation for those looking to learn more about smart contract development on the Ethereum blockchain.

## Description

**MyToken** is a simple ERC-20-like token contract with the following features:

- **Public Variables:** Stores the token name, abbreviation, and total supply.
- **Address Mapping:** Maintains a balance mapping that associates addresses with their respective token balances.
- **Minting Functionality:** Allows tokens to be minted (created), increasing both the total supply and the balance of the specified address.
- **Burning Functionality:** Allows tokens to be burned (destroyed), reducing both the total supply and the balance of the specified address, with a condition to prevent burning more tokens than an address holds.

This contract is a basic yet effective example for understanding how token supply management works on the Ethereum network.

## Getting Started

### Prerequisites

To interact with this contract, you'll need:

- An Ethereum-compatible wallet (e.g., MetaMask).
- Access to the Remix IDE, an online platform for writing, compiling, and deploying Solidity contracts.

### Executing the Program

1. **Open Remix:**
   - Go to [Remix](https://remix.ethereum.org/) in your web browser.

2. **Create a New File:**
   - In the left-hand sidebar, click the "+" icon to create a new file.
   - Name the file `MyToken.sol`.

3. **Copy and Paste the Code:**
   - Paste the following Solidity code into your new file:

   ```solidity
   // SPDX-License-Identifier: MIT
   pragma solidity 0.8.18;

   contract MyToken {

       // Public variables here
       string public tokenName = "SpiderMan";
       string public tokenAbbrv = "SPM";
       uint public totalSupply = 0;

       // Mapping variable here
       mapping(address => uint) public balances;

       // Mint function
       function mint(address _address, uint _value) public {
           totalSupply += _value;
           balances[_address] += _value;
       }

       // Burn function
       function burn(address _address, uint _value) public {
           if (balances[_address] >= _value) {
               totalSupply -= _value;
               balances[_address] -= _value;
           }
       }
   }
   ```

4. **Compile the Contract:**
   - Click on the "Solidity Compiler" tab in the left-hand sidebar.
   - Ensure the compiler version is set to "0.8.18" or compatible.
   - Click "Compile MyToken.sol" to compile the contract.

5. **Deploy the Contract:**
   - Switch to the "Deploy & Run Transactions" tab in the left-hand sidebar.
   - Select the `MyToken` contract from the dropdown menu.
   - Click "Deploy" to deploy the contract to the Ethereum network.

6. **Interact with the Contract:**
   - After deploying, the contract will appear in the left-hand sidebar.
   - You can now mint tokens by calling the `mint` function with an address and value.
   - To burn tokens, use the `burn` function, making sure the address has a sufficient balance.
   - Check balances using the `balances` mapping by providing an address.

## Author

Harshit Goyal

## License

This project is licensed under the MIT License. See the `LICENSE.md` file for details.
