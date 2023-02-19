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
    - Ex 3: Deploy a basic counter smart contract and access it from a basic front end!
    
**Steps for Ex 3:**
1. Create a new hardhat project under the directory 'my-counter'
2. Configure your .env file and hardat.config file like before - make sure the wallet you are using has some test eth
3. Delete the existing smart contracts in the smart contracts folder
4. Create a basic counter smart contract.  
   1. It should have 1 global state variable ```count``` and 2 public functions, one to increment, and one to get the count.
   2. Maybe write some test cases in the run.js folder?
5. Deploy to Goerli and verify your contract on etherscan.  Increment the count a few times using the etherscan ui.
6. Clone the following [repository](https://github.com/IlliniBlockchain/evm-onboarding-basic-counter-frontend) and create a branch
    ``` git checkout -b <your-name-counter> ```

7. cd into the repository, install dependencies and start on local host
    ```
    npm i
    npm start
    ```
8.  Get the Alchemy API key from step one, you will need to use it to connect to the Georli network!
9.  Head into the ``App.js`` folder, and make updates so that it connects to your smart contract, and so ```getCount()``` works
10. Push your changes and make a PR.  
11. All Done!

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
        git rebase origin/day-2
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
        git rebase origin/day-3
        ```
    2. Checkout `simple-token-app`, most notably `simple-token-app/app/src/pages/App.js`
    3. You will need to..
        - Allow your frontend to import the contract ABI
        - Implement the `connectWallet`, `mint`, `transfer`, and `burn`

</details>
