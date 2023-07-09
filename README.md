# Here are some steps to deploy ERC-20 or creating a Token.

## MetaMask
1. Create your MetaMask wallet (get the wallet address).
2. In MetaMask go to setting then connect to Goreli Test-network.
3. At the moment you will not have any GoreliETH, so we need to mine it.
4. From https://goerli-faucet.pk910.de/ this website you can mine GoreliETH by using your wallet address. Then mine more then 0.01 .

## 20lab
1. Go to https://20lab.app/ this website.(20lab is an ERC-20 token generator tool)
2. Click Open App, then click on start.
3. Choose blockchain Goreli(Testnet), then enter your Token name, Token symbol, Initial supply (take very large number), 18 Decimals.
4. Now, you can choose the desired features you want then save it.
5. Then velidate and compile, it will connect to your MetaMask for GoreliETH (gas fee).
6. Then you can see your Tokan name and address in Dashboard.

### Go to https://goerli.etherscan.io/ this website then give your Token address in search-bar or click Etherscan icon below your token address in 20lab. 
Now, you can see your transactions history of that Token.

![Screenshot (56)](https://github.com/Amrendra2004/blockchain-basic/assets/118886890/392932f5-5931-4cab-a208-68027b866d81)

# Using a Development Environment such as Remix to compile and deploy your smart contract.
## Create or Modify the existing smart contract:
        // SPDX-License-Identifier: MIT
        pragma solidity ^0.8.18;

        import "https://github.com/OpenZeppelin/openzeppelin-contracts/blob/v4.0.0/contracts/token/ERC20/ERC20.sol";

        contract MyToken is ERC20 {
            constructor(string memory name, string memory symbol) ERC20(name, symbol) {
                // Mint 100 tokens to msg.sender
                // 1 token = 1 * (10 ** decimals)
                _mint(msg.sender, 100 * 10 ** uint(decimals()));
            }
        }
#### Note: You can look more into it from [Solidity docs](https://docs.soliditylang.org/en/latest/) and [Solidity by Example](https://solidity-by-example.org/)
## Compile using Solidity Compiler:
#### Check that your compiler version is same as the versions specified in the pragma solidity statement(0.8.18)
## Deploy the Contract:
#### 1. Click the Deploy and Run Transactions Icon on the left side menu.
#### 2. Choose Injected Web3 as your environment.
#### 3. Connect MetaMask to GoerliTest net.
#### 4. Click Deploy and select Confirm in the MetaMask notification window to pay for the transaction.
## View Contract Details:
#### Copy the contract address from the Deployed Contracts window on the left panel & head to [Goerli.Etherscan](https://goerli.etherscan.io) explore the details of your deployed smart contract.

![Screenshot (59)](https://github.com/Amrendra2004/blockchain-basic/assets/118886890/8db451b2-f749-4d3e-b650-c1eb08a1c77a)

