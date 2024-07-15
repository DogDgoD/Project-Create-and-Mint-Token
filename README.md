# Project Title

Project: Create and Mint Token

## Description

LanceToken (LNE) is an ERC20-compliant token implemented in Solidity. This contract leverages the OpenZeppelin library for standard ERC20 token functionality and ownership management. The `LanceToken` contract allows the owner to mint new tokens, any token holder to burn their tokens, and users to transfer tokens between accounts. The contract is designed to be simple and efficient, providing essential ERC20 token features with secure owner-based control.

### Executing program

To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.

Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension (e.g., HelloWorld.sol). Copy and paste the following code into the file:

```solidity
// SPDX-License-Identifier: MIT
pragma solidity 0.8.18;

import "@openzeppelin/contracts@4.9.0/token/ERC20/ERC20.sol";
import "@openzeppelin/contracts@4.9.0/access/Ownable.sol";

contract LanceToken is ERC20, Ownable {
    constructor() ERC20("Lance", "LNE") {}

    function mint(address to, uint256 amount) public onlyOwner {
        _mint(to, amount);
    }

    function burn(uint256 amount) public {
        _burn(msg.sender, amount);
    }

    function transferToAccount(address from, address to, uint256 amount) public {
        _transfer(from, to, amount);
    }
}

```

## Authors

Contributors names and contact info

Lance Polo Paras
201911769@fit.edu.ph
