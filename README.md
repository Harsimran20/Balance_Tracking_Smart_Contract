# Simple Ethereum Wallet Contract

## 📄 Description
This is a basic Ethereum smart contract written in Solidity that functions as a simple wallet. Users can deposit and withdraw Ether securely while tracking their individual balances.

## 🚀 Features
- Deposit Ether into the contract.
- Withdraw Ether if the balance is sufficient.
- Check your own balance.

## 🛠️ Technologies Used
- Solidity ^0.8.0
- Ethereum Virtual Machine (EVM)
- Remix IDE (or compatible Ethereum development environment)

## 📦 Contract Overview
```solidity
mapping(address => uint) public balances;

function deposit() public payable {
    balances[msg.sender] += msg.value;
}

function withdraw(uint amount) public {
    require(balances[msg.sender] >= amount, "Insufficient Balance");
    balances[msg.sender] -= amount;
    payable(msg.sender).transfer(amount);
}

function checkBalance() public view returns (uint) {
    return balances[msg.sender];
}
🔒 Security Note
This contract is for educational purposes only. It does not include advanced security protections. Use in production at your own risk.

🧪 How to Use
Deploy using Remix or your preferred Solidity IDE.

Use the deposit function with Ether.

Use withdraw with the desired amount.

Use checkBalance to view your funds.

