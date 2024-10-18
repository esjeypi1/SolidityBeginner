# SolidityBeginner

A beginner-friendly Solidity project that demonstrates basic concepts such as token creation, minting, and burning within a smart contract.

## Description

This project introduces the fundamentals of writing smart contracts in Solidity. It includes a simple implementation of a token contract where tokens can be minted and burned. The purpose of this project is to help beginners understand how to manage token supply and balances within a blockchain application using Solidity.

## Getting Started

To run this program, you can use Remix, an online Solidity IDE. Simply visit the Remix website at https://remix.ethereum.org.

Once there, click the "+" icon in the left sidebar to create a new file. Save the file with a .sol extension (e.g., project2.sol), then copy and paste the code below into the file.

```javascript
pragma solidity 0.8.18;
contract MyToken {

    // public variables here
    string public tokenName = "CHAMP";
    string public tokenAbbrv = "CHP";
    uint public totalSupply = 0;
    // mapping variable here
    mapping(address => uint) public balances;
    // mint function
    function mint(address _address, uint _value) public {
            totalSupply += _value;
            balances[_address] += _value;
    }

    // burn function
    function burn(address _address, uint _value) public {
            if(balances[_address] >= _value){
                totalSupply -= _value;
                balances[_address] -= _value;
            }
    }
}
```

### Executing program

To compile the code, 
* navigate to the "Solidity Compiler" tab in the left sidebar.
* Ensure that the "Compiler" version is set to "0.8.4" (or any other compatible version),
* then click the "Compile project2.sol" button.

After the code is compiled, go to the "Deploy & Run Transactions" tab in the left sidebar. From the dropdown menu, select the "project2" contract and click the "Deploy" button.

Once deployed, you can interact with the contract by calling the mint function. In the left sidebar, find the "project2" contract, then click on the mint function alongside the address and value to be minted. The same process will can also be done with the burn function but instead of adding a value, it subtracts. Finally, press the "transact" button to execute the function to add or subtract a value to a given address.

## Authors

Contributors names and contact info

Samuel Jacob Pacheco [esjeypi1]


## License

This project is licensed under the Samuel Jacob Pacheco License - see the LICENSE.md file for details
