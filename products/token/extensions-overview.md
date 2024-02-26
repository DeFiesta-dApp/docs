# Extensions overview

The ERC20 token standard provides a foundational framework for creating digital assets on the Ethereum blockchain. DeFiesta enhances this standard with a suite of extensions that add advanced functionalities tailored to various business needs. Below is a detailed overview of each extension available for ERC20 tokens created with DeFiesta:

## **Base**

The core of our ERC20 token includes all essential functionalities required by the ERC20 standard. This ensures compatibility across the Ethereum ecosystem, facilitating seamless exchanges, wallet support, and interaction with decentralized applications (dApps).

## **Burnable**

The Burnable extension adds a mechanism for reducing the total supply of tokens by removing a specified amount from circulation. This feature is particularly useful for managing token scarcity, conducting token buybacks, or implementing deflationary token economics. By burning tokens, you can increase the value of remaining tokens by reducing supply, a tactic often used to reward token holders or manage tokenomics dynamically.

## **Pausable**

The Pausable extension provides the ability to freeze all token transfers temporarily. This can be a critical feature in emergency situations, such as security breaches or critical bugs, where halting token movement is necessary to prevent exploitation or loss. It adds an extra layer of control and security, allowing token administrators to pause and resume token operations as needed.

## **Blacklist**

With the Blacklist extension, tokens can incorporate functionality to block transactions involving specific addresses. This feature is instrumental in complying with regulatory requirements, enhancing security measures, or preventing malicious actors from participating in the token ecosystem. Administrators can dynamically manage the blacklist, adding or removing addresses based on observed behavior or compliance considerations.

## **Permit**

Integrating the EIP-2612 ERC20 Permit functionality, this extension allows token holders to approve token transfers via off-chain signatures. This feature streamlines user interactions by eliminating the need for an initial on-chain transaction to approve token spending, thereby saving gas costs and enhancing user experience, especially in decentralized finance (DeFi) applications where user approval is frequently required.

## **Flash Mint**

The Flash Mint extension incorporates the flashmint functionality as per ERC-3156, enabling the minting of tokens within a transaction and their repayment by the transaction's end. This feature opens up possibilities for innovative financial instruments and mechanisms, such as arbitrage, collateral swapping, and liquidity provision, without requiring upfront capital.

## **Mintable**

This extension allows for the creation of new tokens, increasing the total supply at the discretion of designated token administrators. The Mintable feature is essential for projects that require a flexible supply mechanism, such as reward distribution, community incentives, or fundraising activities. It provides a controlled way to inject new tokens into circulation, subject to the governance model established by the token creators.

## **Limited Transfer**

The Limited Transfer extension enables setting restrictions on the maximum amount of tokens that can be transferred in a single transaction. This feature can be used to mitigate the impact of large, disruptive token movements, enhancing market stability and security. It offers token administrators the ability to enforce transfer limits, ensuring more gradual and controlled token distribution and movement.



Each of these extensions enriches the ERC20 token framework with additional capabilities, allowing token creators to tailor their tokens to specific project requirements and governance models. DeFiesta's suite of extensions ensures that your ERC20 token is not only compliant with the Ethereum standard but also equipped with the functionalities needed to succeed in the dynamic and diverse landscape of blockchain applications.\
