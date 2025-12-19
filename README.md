# KoinKeren (KKRN) - ERC20 Token

KoinKeren is a professional **ERC-20** smart contract implementation written in **Solidity**. This project utilizes [OpenZeppelin Contracts](https://openzeppelin.com/contracts/), the gold standard for secure and community-vetted smart contract development.

## 🚀 Key Features

* **ERC-20 Standard**: Fully compliant with the Ethereum token standard, ensuring compatibility with wallets like MetaMask and decentralized exchanges (DEXs).
* **Burnable**: Includes a mechanism for token holders to permanently destroy their tokens, reducing the total circulating supply.
* **Mintable**: The contract owner has the authority to mint additional tokens to a specific address.
* **Access Control**: Implements the `Ownable` pattern to restrict administrative functions (like minting) to the authorized contract owner.

## 🛠️ Technical Specifications

* **Token Name**: KoinKeren
* **Token Symbol**: KKRN
* **Decimals**: 18 (Standard)
* **Solidity Version**: ^0.8.0
* **Libraries**: OpenZeppelin (ERC20, ERC20Burnable, Ownable)

## 📖 Code Overview

### Inheritance Structure
The contract inherits from three main modules:
1.  `ERC20`: Provides core token logic.
2.  `ERC20Burnable`: Enables the `burn()` and `burnFrom()` functions.
3.  `Ownable`: Manages ownership and permission-based access.

### The Constructor
Upon deployment, the total initial supply is minted directly to the deployer's address. 
```solidity
constructor(uint256 initialSupply) 
    ERC20("KoinKeren", "KKRN") 
    Ownable(msg.sender) 
{
    _mint(msg.sender, initialSupply * 10 ** decimals());
}
