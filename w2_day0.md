# 28.02.2022

Shufan

reading documentations of makerDAO

## Notes

1. Solidity IR-based Codegen Changes
    1. when storage struct is deleted, the slots are written to 0 totally (with padding).
    2. execution of modifier: only once.
2. makerDAO:
    1. Debt Ceiling for a vault type: if there is a big gap between it and the current minted amount of DAI of that type, then there is an 'OSM Timing Attack' risk. If the type drops quickly, user can mint DAI and shift the bad collateral to Maker, as there is a one-hour delay in the 'Oracle Security Module'.
    2. 
3. Curve: forex-market for stable coins
    1. less trading fees than uniswap, uniswap always trade with ETH, which means double trades between stable coins.
    2. 
4. AMM (Automated Market Maker) model
    1. allow digital assets to be traded without permission using liquidity pools.
    2. Liquidity refers to how easily one asset can be converted into another asset,
    1. impermanent loss
    flashbot service
    proxy immutable?

another risk: rug pull

5. classification of stable coins:
    1. off-chain collateralized: USDT, USDC, 
        1. backed by bank deposit, which is regularly audited
        2. minted by a centralized entity
    2. on-chain collateralized: DAI, SUSD, LUSD
    3. algorithmic stable coin: higher capital efficiency
        1. dynamically control the demand and supply
        2. rules for doing so are embedded into a smart contract
        3. how to build the trust?

6. Compound:
    1. a market to lend, make interest, collateral, borrow.
    2. compound loan is overcollateralized.

7. slippage:
    1. slippage refers to the difference between the expected price of a trade and the price at which the trade is executed.

