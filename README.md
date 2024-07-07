# Create and mint token

In this Solidity program  we create and manage a token by creating a smart contract. In the contract, we use ERC20 to add functionalities like total supply, balances, transferring tokens and many more.

## Description

This program is a written in Solidity, a programming language used for developing smart contracts on the Ethereum blockchain.In this contract, we have inherited two contracts ERC20.sol and Ownable.sol from the OpenZeppelin to add the functionalities of ERC-20 tokens. The contract have three functions-the mint function , burn function and the transfer function. The mint function takes two parameters: an address and a value. This function is only accessable to the owner i.e. only the owner can mint the tokens in this contract. The burn function destroy tokens. It takes an address and value just like the mint functions. The transfer function is used to send tokens from the sender to the receipent address. Any user can use the burn and the transfer function function.

## Getting Started
## Executing Program
To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.

Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension (e.g., avax.sol). Copy and paste the following code into the file:




bash


    // SPDX-License-Identifier: MIT
    pragma solidity ^0.8.0;

    import "https://github.com/OpenZeppelin/openzeppelin-contracts/blob/v4.0.0/contracts/token/ERC20/ERC20.sol";

    import "https://github.com/OpenZeppelin/openzeppelin-contracts/blob/v4.0.0/contracts/access/Ownable.sol";

    contract RhoToken is ERC20, Ownable {

     constructor() ERC20("rhotoken", "ROT") {
    _mint (owner(), 1000 * 10**uint(decimals()));
    }



    
    // Function for owner to mint new tokens
    function mint(address _to, uint256 _amount) public onlyOwner {
    _mint(_to, _amount);
    }

    // Function for any user to burn tokens
    function burn(uint256 _amount) public {
    _burn(msg.sender, _amount);
    }

    // transfer the amount of tokens from the sender to the receiver
    function _Transfer(address to, uint256 _amount)public {
     _transfer(msg.sender, to, _amount); 
    }
    }

To compile the code, click on the "Solidity Compiler" tab in the left-hand sidebar. Make sure the "Compiler" option is set to "0.8.0" (or another compatible version), and then click on the "Compile Assesment.sol" button.

Once the code is compiled, you can deploy the contract by clicking on the "Deploy & Run Transactions", also need to see the environment is connected to metamask, tab in the left-hand sidebar. Ensure that in deploy need to give someamountof token as an example.Then 
Click on the "Deploy" button.

In the "Deployed Contracts" section, expand the rhotoken contract. you will able to see the name u have given to your token in "name", symbol in "symbol", token decimal places in "decimal", amd total no of token in circulation in "totalsupply". we can check our balance within our first account by using address of first account in "balanceof" as well as we can transfer amd burn the many to the sender and owner.
.Confirm the transaction in MetaMask.







## Authors

- Shiwani
shivagarwal23@gmail.com



## License

This project is licensed under [MIT](https://choosealicense.com/licenses/mit/) License - see the LICENSE.md file for details
