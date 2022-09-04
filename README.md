# *Joint Savings Account*
---
## Smart Contract Joint Savings
This project constructs a smart contract for a blockchain based joint savings account. It utilizes Solidity, the Remix IDE, and Ganache testing environments to create a test contract. 

>""An investment in knowledge pays the best interest." — Benjamin Franklin"

## Technologies

This project uses Solidity, Remix IDE, and Ganache testing software to create the smart contract and deploy a testnet. 

[Solidity](https://github.com/ethereum/solidity)
[Remix](https://remix.ethereum.org/)
[Ganache](https://github.com/trufflesuite/ganache)

### Installation Guide

In order to use this program please import and utilie the following libraries and dependencies: 

```pragma solidity ^0.5.0;```

## Usage
The following blocks of code are fundamental in executing the program. 

 ```solidity 

contract JointSavings {
    address payable accountOne;
    address payable accountTwo;
    address public lastToWithdraw;
    uint public lastWithdrawAmount;
    uint public contractBalance;
    }

 ``` 

This code creates the initial contract name and sets the variable types. We have types `address `, `uint`, and identifiers `payable`, `public`. 

 ```solidity 

function withdraw(uint amount, address payable recipient) public {

        require(recipient == accountOne || recipient == accountTwo, 
        "You do not own this account!");

        require(contractBalance >= amount, "Insufficient Funds!");

        if (lastToWithdraw != recipient){
            lastToWithdraw = recipient;
            }

        recipient.transfer(amount);

        lastWithdrawAmount = amount;

        contractBalance = address(this).balance;
         
    }

 ``` 

This function sets the withdraw functionality. It has several `require` statments. If the conditionals of the `require` statements are not met the code will issue an error satement and cease to operate. This will save on gas expenditures for the contract. 

```solidity 
function setAccounts(address payable account1, address payable account2) public
    {
        accountOne = account1;
        accountTwo = account2;
    }
```
This function sets the account addresses. It takes the arguments `address` of type `payable` and labels them accordingly. 

## Results
The following media shows the results of our Joint Savings smart contract. 

![<alt text>](https://i.postimg.cc/xTqGd7Nm/Screen-Shot-2022-09-04-at-9-44-10-AM.png)

Function panel in Remix ready to be used. 

[![Screen-Recording-2022-09-04-at-9.59.58-AM.gif](https://s4.gifyu.com/images/Screen-Recording-2022-09-04-at-9.59.58-AM.gif)](https://gifyu.com/image/Swch4)

A withdraw function in action. 

![<alt text>](https://i.postimg.cc/mgz078Jz/Screen-Shot-2022-09-04-at-10-02-20-AM.png)

Account balances reflected on Ganache testnet. 

## Contributors

Jeffrey J. Wiley Jr

## License

MIT
