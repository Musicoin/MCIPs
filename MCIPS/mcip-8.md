    MCIP: 8
    Title: Quantitative Tightening(QT)
    Author: Isaac Mao <isaac@musicoin.org>
    Type: Core
    Status: finalized
    Created: 2018-09-18
    Updated: 2019-05-01


## Simple Summary
Based on the experiments of Playback-Tipping co-relationship, a more reasonable ration between UBI and money supply should be applied to make sure the whole economy model works more fluidly.

## Motivation
Money supply should be proportional to utility in the economy. As we have seen the increasing rate of utility in the network which is used for tipping musicians and accessing premium user experiences in application layer, the needs of adjusting the money supply to consumers is becoming acute.

## Rationale
- supply of money in one block reduced to 50/block (comparing to 250/block before)
- Keep UBI supply(50/block) to make sure PPP contract can be maintained consistently
- Keep dev supply (14/block) to make sure team can serve long goal and vision

Total yield(after QT) = 114/block (36.3% of original yield)

## Specification
- After block 5.2M:
```
  UBI Yield= 50;
  Mining Yield = 50;
  Dev yield = 14;  
```

## Backwards Compatibility
- Need hardfork but fully compatible with previous blocks in logic

## Implementation

- GMC
- Parity spec
