# The Beginner's Guide to FXDX

Learn how to trade and (or) become liquidity provider on FXDX platform.

This is a guide for beginners who want to get started on FXDX either via trading, providing liquidity or both. 

## Getting Started

### Connect your wallet

There are two wallets you can connect on FXDX platform:

- My Algo wallet
- Pera Wallet

You can choose your favourite wallet and connect using the Connect Wallet button on the top right corner. Once you are connected, you will see your account address and three dots which is for more settings. 

![Connected Wallet](/connectedwallet.JPG)

### Opting-in on FXDX

In order to perform any actions (trading or providing liquidity) on our non-custodial platform, you must opt-in for all the smart contracts and algorand smart assets (ASA) related to FXDX. 

These may include:

- 17 smart contracts 
- 3 ASAs - WALGO, USDC

### Minimum Balance Requirement

Whenever a user opt-in for smart contracts and ASAs, the minimum balance requirement increases. Users on FXDX must have minimum of 10 ALGOs in their wallet in order to trade or provide liquidity. For more information, check [here](https://developer.algorand.org/docs/get-details/parameter_tables/?from_query=minimum%20#minimum-balance). 

### Minimum Profit Rules

In order for any position to be close in profit, the position must meet two of the requirements:

- *Minimum Price Movement* - A minimum price change of 2% is required for a position to be in profit.
- *Minimum Profit Time* - The position must be opened for atleast 1.5 hours to be closed in profit.

These rules exist to prevent Oracle front-running and minimize depletion of pool from bad actors. 

# Trading 

## Opt-in

If a user wants to start trading on FXDX after connecting his/her wallet, he/she needs to opt-in to following:

### Vault App

The user needs to enter the amount of collateral they want to start trading with (minimum collateral size is $10), we are using 30 ALGOs in this example as shown:

![Vault Contract Opt-in](/vaultoptin.JPG)

Click the button and confirm the transaction from your wallet. 

Once you have confirmed, you will receive an alert saying "Vault App Approved" upon success. Now we have approved FXDX Vault contract, lets continue to next opt-in. 

### WALGO ASA

FXDX uses its native ASA called WALGO (Wrapped ALGO) in order to execute and settle trades efficiently. All users have to opt-in to WALGO for proper trade execution and settlement.

![WALGO Opt-in](/walgooptin.JPG)

Once you have confirmed, you will receive an alert saying "WALGO Approved" upon success. Now we have approved FXDX WALGO ASA, lets continue to next opt-in. 

### Position App

If the user is interested in opening a ***long*** position, which settles the ***profits in ALGO***, needs to opt-in to Position App as "Create Position App" button shown below:

![Positionoptin](/positionoptin.JPG)

Once you have confirmed, you will receive an alert saying "Position App Created for XYZ" upon success. In case of long position, XYZ would be "WALGO Long" and in case of short position, XYZ would be "WALGO Short". For short positions, please check the next section as user is required to opt-in to additional ASA.

### Position App For Short Position

If the user is interested in opening a ***short*** position, which settles the ***profits in USDC***, user must opt-in to USDC ASA if they have not already opted-in from previous Dapp interactions.

![USDCoptin](/usdcoptin.JPG)

Once you have confirmed, you will receive an alert saying "USDC Approved" upon success. Now the user needs to approve the Position App as shown [above](#position-app). 

## Opening Position

By default, if a user has opted-in for WALGO, he/she can open long position using ALGO as collateral. If a user wishes to provide USDC as collateral, he/she needs to opt-in to USDC ASA as mention in the section above. 

Now that the user has opted-in for necessary contracts and ASAs, he/she is ready to place his/her desired order. 

### Long Position

User is required to opt-in following as explained in earlier section:

- Vault App
- WALGO ASA
- Position App

Once all the above are approved, user needs to select the desired amount of collateral he/she wants to put and the leverage he/she wants to take. For this example, we are taking 30 ALGOs as collateral and opening a short position with 10x leverage. 

![long](https://github.com/fxdxdex/howto/blob/f11b17482a44ae9c78e39fce94935620c9e38abb/long.JPG)

One should carefully note the following before placing an order:

- Type of Order - Market or Limit
- Amount of Collateral 
- Type of Collateral - ALGO, USDC
- Leverage - 1.1 to 30.5x
- Total Notional Size (Collateral * Leverage) = (This amount - Collateral) would be reserved in the pool's avaliable for securing position.
- Entry Price 
- Liquidation Price - Price at which liquidation protocol would close the position if the (collateral - trading fee - borrow fees + profit - loss) < 0. For a long position, it would be lower than entry price.

In case a user is going for Limit Order, he/she need to put their desired Entry Price as well.

![limitlong](/limitlong.JPG)

After clicking "Long ALGO", user would be shown an confirmation box, where user can verify the order details before it is send to the smart contract for execution. 

- Market Order

![confirmlong](/confirmlong.JPG)

- Limit Order

![confirmlimitlong](/confirmlimitlong.JPG)

### Short Position

User is required to opt-in following as explained in earlier section:

- Vault App
- WALGO ASA
- USDC ASA
- Position App

Once all the above are approved, user needs to select the desired amount of collateral he/she wants to put and the leverage he/she wants to take. For this example, we are taking 10 USDC as collateral and opening a short position with 10x leverage. 

![short](/short.JPG) 

One should carefully note the following before placing an short order:

- Type of Order - Market or Limit
- Amount of Collateral 
- Type of Collateral - ALGO, USDC
- Profits In - USDC
- Leverage - 1.1 to 30.5x
- Total Notional Size (Collateral * Leverage) = (This amount - Collateral) would be reserved in the pool's avaliable for securing position.
- Entry Price 
- Liquidation Price - Price at which liquidation protocol would close the position if the (collateral - trading fee - borrow fees + profit - loss) < 0. For a short position, it would be higher than entry price.

In case a user is going for Limit Order, he/she need to put their desired Entry Price as well.

![limitshort](/limitshort.JPG)

After clicking "Short ALGO", user would be shown a confirmation box, where user can verify the order details before it is send to the smart contract for execution. 

- Market Order

![confirmshort](/confirmshort.JPG)

- Limit Order

![confirmlimitshort](/confirmlimitshort.JPG)

## Order Execution

### Market Order

If the user has placed an Market type Order, the order would be immediately executed at the current Oracle Price and would be shown as below under Positions Tab.

- Long Order

![marketlong](/marketlong.JPG)

- Short Order

![marketshort](/marketshort.JPG)


### Limit Order

If the user has placed an Limit type Order, the order would be executed when the oracle price is near the entered price and would be visible until its executed, under Orders Tab, as shown below. 

- Long Order

![limitlong](/limitlong1.JPG)

- Short Order

![limitshort](/limitshort1.JPG)

## Order Change

If the order is executed and available under Position, user can either:

- Deposit 
- Withdraw

### Deposit Collateral

If users want to reduce their chances of liquidation and leverage, they can deposit more collateral as per their needs. 

### Withdraw Collateral

If users want to exit position immediately or increase leverage for the same collateral, they can withdraw their collateral as per their needs. 

*Note: Users can't withdraw collateral if the value of collateral in USD in under $10.*

## Order Close

### Market Order 

If the order is executed and available under Positions and user wants to immediately exit the position, user can do so by choosing Market option after clicking on Close button. This will close the order at market price immediately.

Users can choose to close their order completely or partially as they need to. 

### Trigger Order

If the order is executed and available under Positions and user want to either put an Stop-Loss or Take Profit on their order, they can do so by choosing Trigger option under Close button, enter the desired price and confirm by clicking on "Create Order". 


# Liquidity Provider

FXDX relies on its liquidity providers to execute any trade. Anyone can provide liquidity on FXDX by buying FLP [here](https://mainnet.fxdx.exchange/buy_flp). 

## FLP - FXDX Liquidity Provider Token

FLP is the liquidity token of FXDX and is the lifeline of the platform which a liquidity provider receives in return for the deposited assets. 

One can get FLP by depositing following: 

- ALGO
- USDC

### Minting FLP

When a user deposits assets for liquidity, he/she mints FLP at FLP market price. 

The amount of FLP tokens received = (Deposited Assets in USD) / (Current FLP Price in USD). 

### Burning FLP

When a user withdraws assets for liquidity, he/she burns FLP at market price. 

## FLP Rewards

FLP holders are rewarded in combination of:

- ALGO 
- esFXDX
- Multiplier Points

### FLP - ALGO Rewards

FXDX currently distributes 100% of platform revenue (trading, liquidation, borrowing fees) to compensate their service. Rewards are distributed weekly and would be updated in real-time at [earn](https://mainnet.fxdx.exchange/earn). 

### FLP - esFXDX Rewards

FXDX currently distributes esFXDX in addition to ALGO rewards to reward early FLP adopters. Currently it is distributed at 0.18 esFXDX per 4.5 seconds. 

### Mutliplier 


## FLP Exposure and Risks

FLP holders have exposure to overall platform traders positions and their profit and loss apart from the exposure to FLP Index. 

### FLP Exposure

Platform users are always trading against the FLP pool, we are a peer-to-pool concentrated liquidity model. 

- If a trader exits in loss, the FLP pool takes the collateral (used to cover the loss), trading fees and borrowing fees from the trader. 
- If a trader exits in profit, the FLP pool gives the profit to the trader and takes trading and borrowing fees from the trader. 
- If a trader swaps any asset to any other asset avaliable in the FLP pool, pool takes the trading fees. 
- If a trader gets liquidated, the FLP pool takes the full collateral, trading fees and borrowing fees from the trader. 

The FLP holders are also exposed to FLP Index Composition. 

![flpool](/flppool.png)

Price of FLP = (Total Worth of Assets in Index  - Collaterals - Fees) / (FLP supply). 

If the price of ALGO decreases, the total worth of assets in FLP Index pool would decrease while the supply of FLP remains same, which would decrease the FLP price. 

If the price of ALGO increases, the total worth of assets in FLP Index pool would increase while the supply of FLP remains same, which would increase the FLP price.

### FLP Risk

All FLP holders are subjected to Market Risk via Pool Index Composition and Net PnL of platform traders, both are explained in previous sections.

## FLP Reward Claims


All FLP holders would receive ALGO rewards as well as esFXDX per second based on their allocation size in the FLP pool. 

They can claim it anytime as shown below. 

![rewardsclaim](/rewardsclaim.png) 

After clicking the Claim button you may see the following: 

![claimoptions](/claimoptions.png) 


