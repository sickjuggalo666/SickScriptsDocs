# Usage

Each Spot will have a check! You must complete a step before accessing some spots!&#x20;

Target is Disabled until you are done with animations to help prevent spamming&#x20;

Multiple checks for `if amount > money then` to make sure you aren't using an amount more than what you actually have! This also helps preventing players from starting a wash cycle and dropping the money. Server side checks right before payout make sure you actually have the amount in your Pockets. If not it will not continue if you do have the amount it will process the dirty money into clean money while applying a tax or "fee". Checks for money when washing to make sure you have that amount before starting the cycle.&#x20;

When first entering Money wash you will need to make sure to kick on the power to make the target points for the other steps!
