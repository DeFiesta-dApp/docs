# Functional overview

## Technical Overview

The Presale contract offers a comprehensive suite of functions aimed at enabling project owners to initiate, manage, and conclude a token presale event. Key features include the ability to set up multiple presale rounds with different rates, manage participant whitelists, and automatically contribute to liquidity pools post-presale.

The Presale contract is an advanced smart contract framework for conducting token presales on the Ethereum blockchain. It incorporates various security measures, including a ReentrancyGuard to prevent re-entrant attacks and an Ownable pattern to restrict certain actions to the contract owner. The contract integrates with Uniswap for liquidity addition and supports both ERC-20 tokens and native ETH for bidding. It is meticulously designed to automate the presale process, from token purchase to liquidity provision, ensuring a seamless experience for both project owners and participants.

## Function Overview

### **owner**

Returns the current owner's address of the contract.

### **transferOwnership**

Transfers ownership of the contract to a new account. Only the current owner can call this function.

### getConfig

Returns the current configuration of the presale, including its status, refund type, rounds information, time settings, claimability status, associated tokens, and governance settings. This function is crucial for external parties and interfaces to understand the presale's current setup and parameters.

### getUser

Retrieves detailed information about a specific user's participation in the presale, such as their total auctions, biddings, pending claims, and whitelist status. It's essential for participants to track their investments and entitlements.

### getAffiliate

Provides data regarding an affiliate's performance within the presale, including total biddings contributed through their referrals and the number of contributions made. This function supports affiliate marketing efforts, rewarding users for bringing in new investors.

### buy

Allows participants to invest in the presale by purchasing auction tokens with the presale token or native currency. It requires specifying the amount, affiliate (if any), and permit data for EIP2612 compliance. This function is the core of the presale, enabling token sales and tracking investments.

### claim

Enables users to claim their purchased tokens after the presale concludes, assuming the presale is in the claimable state. It ensures participants can receive their tokens according to the presale terms.

### initialization

Sets up the presale with specific rounds, rates, and timeframes. This function is called by the presale owner to configure the presale parameters before launching. It's a one-time operation that transitions the presale status from not initialized to in progress.

### close

Concludes the presale, transitioning its status to closed. It triggers the liquidity addition process, ensuring that a portion of the collected funds is used to provide liquidity on a DEX. This step is crucial for ensuring the token's post-presale liquidity and stability.

### claimability

Sets the claimability status of the presale, dictating whether participants can claim their tokens. It provides flexibility in managing the post-presale phase, allowing the owner to enable or disable token claims based on external factors.

### pause

Pauses or unpauses the presale, providing the owner with the ability to temporarily halt the presale due to unforeseen circumstances or issues that require resolution. It helps maintain the integrity of the presale process.

### whitelistable

Enables or disables the whitelisting requirement for the presale, allowing the owner to restrict participation to approved addresses only. This function is vital for conducting private or restricted presales.

### whitelist

Manages the whitelist entries, adding or updating the status and rebate settings for participants. It's used to control access to the presale and offer incentives to selected participants.

