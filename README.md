# Joint Savings Account Smart Contract

This project involves creating a Solidity smart contract for a joint savings account. The contract allows two user addresses to control a joint savings account and provides features for managing funds.

## Steps to Follow

### Step 1: Create a Joint Savings Account Contract in Solidity

1. Open the Solidity file named `joint_savings.sol` in the Remix IDE.
2. Define a new contract named `JointSavings`.
3. Define the following variables in the contract:
   - Two variables of type `address payable` named `accountOne` and `accountTwo`.
   - A variable of type `address public` named `lastToWithdraw`.
   - Two variables of type `uint public` named `lastWithdrawAmount` and `contractBalance`.
4. Define a function named `withdraw` that accepts two arguments: `amount` of type `uint` and `recipient` of type `payable address`. Implement the function as follows:
   - Use a `require` statement to check if `recipient` is equal to either `accountOne` or `accountTwo`. If not, it returns the error message "You don't own this account!".
   - Use a `require` statement to check if the contract has sufficient balance to accomplish the withdrawal. If not, it returns the error message "Insufficient funds!".
   - Use an `if` statement to check if `lastToWithdraw` is not equal to `recipient`. If so, update `lastToWithdraw` to the current `recipient`.
   - Transfer the `amount` to the `recipient` using the `transfer` function.
   - Update `lastWithdrawAmount` to the `amount`.
   - Update `contractBalance` to reflect the new balance of the contract.
5. Define a public payable function named `deposit` to allow depositing funds into the contract. Update `contractBalance` to reflect the new balance of the contract.
6. Define a public function named `setAccounts` that takes two `address payable` arguments, `account1` and `account2`. Set the values of `accountOne` and `accountTwo` accordingly.
7. Add a fallback function to allow the contract to store Ether sent from outside the deposit function.

### Step 2: Compile and Deploy Your Contract in the JavaScript VM

1. Compile the smart contract using the Remix IDE.
2. In the Remix IDE, navigate to the "Deploy & Run Transactions" pane and select "JavaScript VM" as the environment.
3. Click the "Deploy" button to deploy your smart contract and ensure it deploys successfully.

### Step 3: Interact with Your Deployed Smart Contract

Now that the contract is deployed, test its functionality. Capture screenshots of each step and save them in a folder named "Execution_Results".

1. Use the `setAccounts` function to define the authorized Ethereum addresses that can withdraw funds from the contract.
2. Test the deposit functionality by sending different amounts of Ether to the contract. After each transaction, use the `contractBalance` function to verify that the funds were added to the contract.
3. Test the withdrawal functionality by withdrawing funds from the contract. Use the `withdraw` function to withdraw specific amounts into `accountOne` and `accountTwo`. After each transaction, use the `contractBalance`, `lastToWithdraw`, and `lastWithdrawAmount` functions to verify the correctness of the withdrawals.


