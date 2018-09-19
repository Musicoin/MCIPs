    MCIP: 7
    Title: PPP Extra Reward
    Author: Eugene Gusev <eugene@musicoin.org>
    Type: Core and Backend
    Status: Draft
    Created: 2018-18-08


## Simple Summary
Pay the difference between $0.01 and 1mc, when 1mc cost less than $0.01

## Abstract
Pay extra compensation to musicians along with PPP, when PPP is less than $0.01 per play

## Motivation
Currently we can't provide the compensation lvl we like for musicoins when 1mc price (current default PPP license values) is lower than $0.01

## Specification
PPP extra reward tries to avoid situations when PPP and songs play licensed with 1 mc are cost less than $0.01 on the market.
So in the case 1mc is cost less than < $0.011 it would use PPP Extra Reward route to compensate the price difference +10% (to avoid market fluctuations).

MC price taken from the coinmarketcap and updated with 10 minutes intervals.

But in the period when 1 mc price is more than $0.01 PPP Extra Reward wouldn't be executed. So in case 1 mc price is higher than $0.01 musician will get only 1 mc from PPP, just as the song was licensed.

Formula: `PPP extra reward = (0.011 / priceInUsd ) - 1`


## Rationale
The price of PPP was designed as 1MC/play at the beginning, which is to regulate a rate to conceptualize the behaviors of smart contract. Along the time, the smart contract is getting more blurry since more logics are moving up to business layer(which is not immune), the regulation is getting loosen. 

At whitepaper 2.0, we have realize this direction and designed a new curve to regulate the price of PPP.  The curve is to fit the future price upward and adapt to lower denominator(e.g. If the price of MC goes to 1USD, the PPP price could be adjusted by system to 0.01MC… ). So literally, we have opened the door for flexible PPP.  The only thing we didn’t mention in Whitepaper 2.0 is to predict the case of price downward, which is happening now.  


## Backwards Compatibility
Full backward compatibility since PPP Extra Reward is not executed, when 1 mc price is higher than $0.01 on the market

## Test Cases
```
https://explorer.musicoin.org/account/0xf11b0a406faf905e48216afaf7db015fc3971392
https://explorer.musicoin.org/account/0xee6f52c18c6cf1b06ebdd31d8a2e987d26b62916
https://explorer.musicoin.org/account/0x5dd360d4d8dce2ff21549270e9e78ea91f06135d
https://explorer.musicoin.org/account/0x8e8bba22679ffb211c28f33834199812279962f2
```

## Implementation
https://github.com/Musicoin/core/pull/15

https://github.com/Musicoin/musicoin.org/pull/596
