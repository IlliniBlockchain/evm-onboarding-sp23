# Illini Blockchain EVM Onboarding

*Last updated for Spring 2023.*
### Motivation
We want to ramp up new developers to be able to meaningfully contribute to EVM projects.

**Goals**:
- Become familiar with EVM development workflow
- Get familiar with the most important EVM concepts
- Implement some smart contracts with Solidity
- Write some client code to interact with smart contracts

### Content Outline
<details>
<summary>Day 1</summary>

- [EVM Overview](https://ethereum.org/en/developers/docs/)
- Development Exercises
    - Ex 0: Make and merge a PR into an Illini Blockchain repo!
    - Ex 1: [Hardhat quick start](https://hardhat.org/hardhat-runner/docs/getting-started)
    - Ex 2: [Deploy to Goerli and verify contract](https://hardhat.org/hardhat-runner/docs/guides/verifying)
        - Use `.env` file instead of suggested method in tutorial
    - Ex 3: Deploy [Illini Blockchain NFT](https://github.com/IlliniBlockchain/nft-mint/tree/main/contracts), but with your own image
        - Mint it, and make sure it's viewable on [OpenSea](https://testnets.opensea.io)!

        Steps:
        1. Create a new hardhat project under the directory `my-nft`
        2. Copy our contracts for the NFT into your `contracts` folder
        3. Install the OpenZeppelin contracts that our NFT contract imports
            ```
            npm install @openzeppelin/contracts
            ```
        4. Modify the SVG image inside of the contract
        5. Compile, deploy, and verify on Goerli Testnet
        6. Use the Etherscan UI to mint your NFT
        7. Go to [OpenSea Testnets](https://testnets.opensea.io), search your address,
        filter to Goerli NFTs, and see your NFT!

</details>

<details>
<summary>Day 2</summary>

Solidity!
- Resources
    - [Solidity Docs](https://docs.soliditylang.org/en/v0.8.17/)
    - [Solidity by Example](https://solidity-by-example.org/)
- Exercise: Implement a simplified version of ERC20!
    1. Create a new branch for day 2 and get the skeleton code
        ```
        git checkout main
        git pull
        git checkout -b <yourname-day-2>
        git fetch origin day-2
        git merge origin/day-2
        ```
    2. Checkout the following files:
        - `simple-token/contracts/IERC20Simple.sol` is the interface contract for our simplified token.
        - `simple-token/contracts/ERC20Simple.sol` is our implementation of our token interface.
        - `simple-token/test/ERC20Simple.js` is our file for testing our implementation.
    3. Implement the `_mint`, `_burn`, `_transfer` functions in `simple-token/contracts/ERC20Simple.sol`
        - Note: you will need to implement `_mint` before tests for `_transfer` will work!
    4. Deploy and verify your contract on Goerli Testnet use your token contract through the Etherscan UI

</details>

<details>

<summary>Day 3</summary>

Client side!

- Resources
    - [Metamask Docs](https://docs.metamask.io/guide/)
    - [ethers.js](https://docs.ethers.io/v5/)
    - Illini Blockchain Examples
        - [Illini Blockchain NFT GitHub](https://github.com/IlliniBlockchain/nft-mint)
        - [Illini Blockchain DAO](https://github.com/IlliniBlockchain/dao-token)
- Exercise: Implement a UI to interact with ERC20Simple (deployed [here](https://goerli.etherscan.io/address/0xAf1594F37d2aE16F1a2421880B40b62f6574b5cc))!
    1. Create a new branch for day 3 and get the skeleton code
        ```
        git checkout main
        git pull
        git checkout -b <yourname-day-3>
        git fetch origin day-3
        git merge origin/day-3
        ```
    2. Checkout `simple-token-app`, most notably `simple-token-app/app/src/pages/App.js`
    3. You will need to..
        - Allow your frontend to import the contract ABI
        - Implement the `connectWallet`, `mint`, `transfer`, and `burn`

</details>
