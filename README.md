# Module-20-Homework

## Objective:
The objective is to build a smart contract to automate the joint savings account. this smart contract will accept two user addresses which could control the operations of this joint savings account eg, deposits and withdrawals from this account. As part of this exercise, I am required to deploy the smart contract and observe the results of various operations within the contract
the following steps were undertaken:

##  Step 1: Creating the Joint Savings account contract in solidity:
-  Using the starter code provided, I opened the solidity file called joint_savings.sol in Remix
-  After this I went on to define the variables in this contract for type account payable for the two  accounts - accountOne and accountTwo. I also created variable called LastToWithdraw as an address public type and two uint public type variables - lastWithdrawAmount and contractBalance
-   Then, the withdraw function is defined which takes in two arguments: amount(as type uint) and recipient(as type payable address). Within this withdraw function, the  require function was added for ensuring the following:
i) ensure that the recipient's addreses is either accountOne or accountTwo only. Otherwise a message pops out saying "You don't own this account!"; and
ii) ensure that the balance is sufficient to complete the withdraw function. if not, a message pops out saying "insufficient funds"
- An if statement is added to ensure that if lastToWithdraw variable is not equal to reipient, it is set to the current value of the recipient
- The transfer function of the recipient is then called to transfer the amount to the recipient
- The lastWithdrawnAmount is set to the amount
- The (new) contractBalance is set to address(this).balance less the amount
- The deposit function as a public payable type is added
- The contractBalance variable is called as being set equal to address(this).balance
- A public function called setAccounts is defined to take in two address payable arguments in the form of account1 and account2 and further the values of these two are set to the values of accountOne and accountTwo respectively
- Finally a fallback function is added to store ether that's sent from outside the deposit function

## Step 2: Compilation and Deployment:
All errors were cleared and this smart contract was successfully compiled and deployed. here are two images proving the successful deployment:
![Alt text](<Image 1 - Smart contract compilation-1.png>)
![Alt text](<Image 2 - Deploying JointSavings smart contract page 1.png>)

## Interaction with the deployed smart contract:
Each of the interactions done are listed and evidenced by the captured images:
1) setAccounts and deposit functionality with different amounts of crypto currencies: 
![Alt text](<Contract balance after depositing 1 ether in wei-1.png>)
![Alt text](<Contract balance after depositing 10 ether in wei.png>)
![Alt text](<Contract balance after withdrawing 5 ether in wei into account 1.png>)
![Alt text](<Contract balance after withdrawing 10 ether in wei into account 2.png>)

2) lastToWithdraw:
![Alt text](<LastToWithdraw account confirmation.png>)

3) lastWithdrawnAmount:
![Alt text](<LastWithdrawAmount confirmation.png>)
