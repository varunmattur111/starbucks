**StarbucksReward**

**Overview:**
This smart contract, named StarbucksReward, is designed to implement a reward system on the Ethereum blockchain. Users can earn and redeem points, with the contract owner having special privileges to manage the system.

**License:**
This smart contract is released under the MIT License, allowing users to freely use, modify, and distribute the code. See the SPDX-License-Identifier in the code for more details.

**Prerequisites:**
- Ethereum environment with a minimum version of 0.8.0.

**Contract Structure:**
1. **Owner:**
   - The contract has an owner, initially set to the address deploying the contract.
   - The owner is the only entity with the authority to perform certain actions, ensuring secure contract management.

2. **Contract Balance:**
   - `contractBalance` variable tracks the total balance within the contract. This could represent any form of value (e.g., tokens) that users can earn and redeem.

3. **Reward Points:**
   - Users' reward points are stored in a mapping (`rewardPoints`), associating addresses with their respective point balances.

4. **Events:**
   - The contract emits two events:
     - `PointsEarned`: Triggered when a user earns points, indicating the user's address and the number of points earned.
     - `PointsRedeemed`: Triggered when the owner redeems points, specifying the owner's address and the number of points redeemed.

5. **Constructor:**
   - Sets the deployer's address as the initial owner during contract deployment.

6. **Modifiers:**
   - `onlyOwner`: A modifier restricting certain functions to be callable only by the owner, enhancing security.

7. **Functions:**
   - `earnPoints(uint points) external`: Allows users to earn points. The provided points must be positive, and the user's balance is updated accordingly. Emits a `PointsEarned` event.

   - `withdrawPoints(uint pointsToWithdraw) external onlyOwner`: Permits the owner to withdraw points. It checks if the owner has a sufficient balance before deducting the specified points. Emits a `PointsRedeemed` event.

**Usage:**
1. **Deploying the Contract:**
   - Deploy the contract to the Ethereum blockchain.

2. **Earning Points:**
   - Users can call the `earnPoints` function, specifying the number of points they want to earn.

3. **Withdrawing Points:**
   - Only the owner can call the `withdrawPoints` function to redeem points from the contract.

**Security Considerations:**
- The `onlyOwner` modifier ensures that certain critical functions can only be executed by the contract owner.
- Positive points are enforced using the `assert` statement in the `earnPoints` function.
- A check is implemented to revert transactions if an attempt is made to withdraw more points than the owner possesses.

## Author

Varun Mattur

frdmeg4@gmail.com
