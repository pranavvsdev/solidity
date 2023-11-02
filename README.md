# Solidity - creating a token

In my Solidity beginner module , I have created a token using solidity language on Remix IDE and I was able to mint and burn tokens.

## Description

In this module, I have successfully created a token called 'Decentralised' with token symbol - 'DCS' . I have used the concepts of functions and mapping to perform the mint and burn operations respectively. I have mapped the unsigned integer named balances to each address and I have also pre-minted 1000 tokens in the beginning to the total supply. But we should make sure that the balance in the respective address entered has more tokens than the value entered to the burn function. 

## Getting Started

### Executing program

To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.

Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension (e.g., token.sol). Copy and paste the following code into the file:

```javascript
pragma solidity ^0.8.9;

contract MyToken {

    // public variables here
    string public tokenname="Decentralised";
    string public tokenabbrv="DCS";
    uint public totalsupply=1000;
    // mapping variable here
    mapping(address => uint)public balance;
    // mint function
    function mint(address accntaddr, uint  valtomint)public {
      totalsupply += valtomint;
      balance[accntaddr] += valtomint;
   }
    // burn function
   function burn(address accntaddr, uint valtoburn)public {
      if(balance[accntaddr]>= valtoburn){
        totalsupply -= valtoburn;
        balance[accntaddr] -= valtoburn;
      }
     }
  }

```

To compile the code, click on the "Solidity Compiler" tab in the left-hand sidebar. Make sure the "Compiler" option is set to "0.8.9" (or above), and then click on the "Compile token.sol" button.

Once the code is compiled, you can deploy the contract by clicking on the "Deploy & Run Transactions" tab in the left-hand sidebar. Select the "token" contract from the dropdown menu, and then click on the "Deploy" button.

Once the contract is deployed, you can interact with it . 

The account address from which you deploy this contract will be the owner address. There will already be 1000 tokens present in the total supply as it is pre-minted . Also make sure that you enter the respective inputs before you call the functions .
## Authors

Pranav S Devang

@pranavssdevang@gmail.com

## License

This project is licensed under the [MIT] License - see the LICENSE.md file for details
