📜 Number Guessing Game – Smart Contract
A simple Solidity smart contract for a number guessing game with automated prize distribution. The first player to correctly guess the predefined number (7) wins the entire prize pool! 🚀

🔥 Features
✅ Decentralized Guessing Game – Players guess a number, and the first correct guess wins.
✅ Automated Prize Distribution – The winner receives the entire contract balance instantly.
✅ On-Chain Transactions – No intermediaries; all transactions are on the blockchain.
✅ Publicly Verifiable – Anyone can check the contract balance and see if a winner is chosen.

🛠️ How It Works
1️⃣ Deploy the contract (already deployed on Edu Chain).
2️⃣ Users deposit ETH as the prize using depositPrize().
3️⃣ Players guess using guessNumber(7).
4️⃣ The first correct guesser wins the balance in the contract.
5️⃣ Game ends when a winner is chosen.

🌍 Deployed Contract
📍 Edu Chain Deployment:
🔗 Contract Address: 0xc65695EBcBaCb7420e716f96F584938DD4d4335A

You can interact with this contract using block explorers or Web3 tools like Remix, Etherscan, or MetaMask.

📜 Smart Contract Code
The contract is written in Solidity 0.8.0 and has no constructors or imports, keeping it minimalistic.

solidity
Copy
Edit
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;

contract GuessTheNumber {
    uint256 private winningNumber = 7;
    address public winner;
    uint256 public prizeAmount;

    function guessNumber(uint256 _guess) public {
        require(winner == address(0), "Game over, winner already chosen.");
        require(_guess == winningNumber, "Wrong guess, try again!");

        winner = msg.sender;
        prizeAmount = address(this).balance;
        payable(msg.sender).transfer(address(this).balance);
    }

    function depositPrize() public payable {}

    function getBalance() public view returns (uint256) {
        return address(this).balance;
    }
}
🚀 How to Play
1️⃣ Send ETH to the contract using depositPrize() to add funds to the prize pool.
2️⃣ Call guessNumber(7) with the number 7 to try and win.
3️⃣ If correct and the first to guess, you win all the ETH in the contract!

📢 Contributing
Feel free to fork this repository, improve the game mechanics, or add new features! 🚀

📩 For any issues or improvements, submit a pull request or open an issue.

🛡️ License
This project is licensed under the MIT License – free to use and modify!

