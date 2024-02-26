# Functional overview

## Technical Overview

The ERC20Token smart contract is a comprehensive implementation of the ERC20 token standard with a wide array of extensions that enhance its functionality beyond basic token operations. It is designed to be versatile and adaptable to various use cases, incorporating features such as burnability, pausability, blacklisting, permit-based approvals, flash minting, mintability, and transfer limitations. This contract serves as a robust foundation for deploying a feature-rich ERC20 token on the Ethereum blockchain.

## Function Overview

## Base

### **owner**

Returns the current owner's address of the contract.

### **transferOwnership**

Transfers ownership of the contract to a new account. Only the current owner can call this function.

### name

Returns the name of the token. This is typically a longer, descriptive name that can be recognized by users.

### symbol

Returns the symbol of the token. This is usually a shorter version of the name, designed for succinct display on exchanges and wallets.

### decimals

Returns the number of decimals used to represent the token. This detail affects how the token's transactions are calculated and displayed, making the token more user-friendly by allowing fractional transactions.

### totalSupply

Returns the total number of tokens in circulation. This value changes as new tokens are minted or existing tokens are burned.

### balanceOf

Takes an address as a parameter and returns the number of tokens held by that address. This function is essential for tracking token distribution among holders.

### transfer

Allows a token holder to transfer a specified amount of their tokens to another address. It requires the sender’s address and the amount to be transferred as parameters.

### allowance

Returns the remaining number of tokens that a spender is allowed to withdraw from an owner. This function is part of the approval mechanism in ERC20, facilitating third-party transfers.

### approve

Enables a token holder to approve a spender to withdraw up to an approved amount from their account. This function is crucial for enabling other contracts or addresses to use tokens on behalf of the token holder.

### transferFrom

Allows a spender to transfer an approved amount of tokens from one account to another. This function is used after approve has been called, enabling third-party transfers as per the approved allowance.

### increaseAllowance

Atomically increases the allowance granted to a spender by the caller. This is useful for incrementally adjusting the spending limit without needing to set a new allowance from scratch.

### decreaseAllowance

Atomically decreases the allowance granted to a spender by the caller. This function allows for reducing the spender's allowance, providing more control over how much they are allowed to spend.

## Burnable

### burn

Destroys a specified amount of tokens from the caller's balance. This function allows token holders to voluntarily reduce the circulating supply of tokens by permanently removing them from their balance.

### burnFrom

Allows a token holder to destroy a specified amount of tokens from another account, deducting from the caller's allowance for that account. This function is used when a token holder has approved another account to spend tokens on their behalf, and those tokens are to be burned, effectively reducing the total supply.

## Pausable

### paused

Determines the current state of the contract, indicating whether it is paused.

### pause

Enables the contract owner to halt all token transfers and other operations marked with the whenNotPaused modifier. This function can only be called when the contract is not already paused, ensuring that operations can only be paused once until explicitly unpaused.

### unpause

Allows the contract owner to resume normal operations after being paused. This function reverts the contract back to its normal state, allowing token transfers and other operations that were previously halted.

## Blacklist

### blacklist

Allows the contract owner to add or remove an address from the blacklist. When an address is blacklisted, it cannot participate in token transfers.

### getBlacklisted

Checks if an address is on the blacklist. It returns true if the address is blacklisted, otherwise false.

## Permit

### permit

Allows setting a value as the allowance of a spender over an owner's tokens, given the owner's signed approval. This method enables token holders to approve transactions without executing a transaction, removing the need for token holders to hold Ether for gas fees.

### nonces

Returns the current nonce for an owner. This nonce must be included whenever a signature is generated for permit. The nonce is used to ensure a signature can only be used once.

### DOMAIN\_SEPARATOR

Returns the domain separator used in the encoding of the signature for permit, as defined by EIP-712. The domain separator is a unique hash that identifies the contract and chain to prevent signature replay attacks across different domains or chains.

### eip712Domain

Provides a comprehensive overview of the EIP-712 domain in which the contract operates. It includes details such as the domain's name, version, chain ID, verifying contract, and other parameters as defined by the EIP-712 standard.

## Flash Mint

### setFlashFee

Allows the contract owner to set the flash loan fee and the receiver of the fee. This function is essential for configuring the economic parameters of the flash loan feature.

### maxFlashLoan

Returns the maximum amount of tokens that can be borrowed via flash loans. This function ensures there's a cap on how much can be loaned, based on the contract's logic.

### flashFee

Calculates the fee for a given flash loan amount. This function is critical for users to understand the cost of borrowing.

### flashLoan

Executes a flash loan, minting tokens to the receiver, who must repay the loan plus fees by the end of the transaction. This function is the core of the flash loan mechanism, enabling innovative financial operations within a single transaction.

## Mintable

### mint

Enables the contract owner to mint new tokens and allocate them to a specified address. This function increases the total supply of the token by the amount minted.

## Limited Transfer

### getTransferLimit

Provides the current transfer limit value. This function allows external entities, such as users and other contracts, to verify the maximum allowed transfer amount.

### setTransferLimit

Enables the contract owner to set or update the transfer limit. This function offers flexibility in managing the token's transfer policy, allowing adjustments in response to changing conditions or requirements.
