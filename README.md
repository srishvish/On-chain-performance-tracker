# On-chain-performance-tracker
On-Chain Performance Tracker is a decentralized application (DApp) that allows users to record, update, and view their performance data securely on the Ethereum blockchain. This project leverages smart contracts written in Solidity to store performance-related information such as scores and timestamps, which can be accessed by users or third parties at any time.
 smart contract address 0x3B5689Bae78dCd46628b9f94412Fd4BaF23c3b5b
Features
Submit Performance Data: Users can submit their performance scores along with the current timestamp.
Update Performance Data: Users can update their previously submitted performance data.
View Performance Data: Anyone can view the performance data of a specific user (if it exists).
Track Performance: The contract stores the performance data securely and transparently on the Ethereum blockchain.
Events: Every time performance data is updated, an event is emitted to notify external listeners.
Technologies
Solidity: Smart contract language for writing decentralized applications.
Ethereum: Decentralized blockchain platform that enables the execution of smart contracts.
Web3.js (optional, for front-end integration): JavaScript library for interacting with Ethereum nodes.
Contract Overview
The core contract consists of the following functionalities:

Submit Performance Data: Users submit their performance scores to the blockchain along with a timestamp.
Update Performance Data: Users can update their performance data.
View Performance Data: Allows users or anyone to check the performance data of a given address.
Event Emission: The contract emits an event when the performance data is updated to notify external systems.
Smart Contract Code
The smart contract is written in Solidity and contains the following key components:

Performance Struct
A structure to store the performance data:

solidity
Copy
struct Performance {
    uint256 score;
    uint256 timestamp;
    bool exists;
}
submitPerformance
This function allows a user to submit their performance score and save it on the blockchain:

solidity
Copy
function submitPerformance(uint256 _score) public { ... }
updatePerformance
Allows users to update their performance data if it exists:

solidity
Copy
function updatePerformance(uint256 _score) public { ... }
getPerformance
This function allows anyone to retrieve the performance data of a specific user:

solidity
Copy
function getPerformance(address _user) public view returns (uint256 score, uint256 timestamp) { ... }
hasPerformanceData
Checks if the user has any performance data stored on the blockchain:

solidity
Copy
function hasPerformanceData(address _user) public view returns (bool) { ... }
Events
The contract emits the PerformanceUpdated event whenever performance data is updated:

solidity
Copy
event PerformanceUpdated(address indexed user, uint256 score, uint256 timestamp);
How to Use
Deploy the Contract:

Deploy the PerformanceData smart contract on the Ethereum network using a tool like Remix IDE or a framework like Truffle.
Submit Data:

Call the submitPerformance(uint256 _score) function to submit a performance score for the sender's address. This action will store the score along with the current timestamp.
Update Data:

Use the updatePerformance(uint256 _score) function to update your performance data. You can only update data that has been previously submitted.
View Data:

Call the getPerformance(address _user) function to view the performance score and timestamp of a particular user.
Check if Data Exists:

Use the hasPerformanceData(address _user) function to check whether a user has performance data stored on the blockchain.
