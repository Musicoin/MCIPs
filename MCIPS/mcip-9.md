    MCIP: 9
    Title: Proof of Value (PoV)
    Author: Isaac MUSIC <isaac@musicoin.org>
    Type: Core
    Status: Draft (terminated)
    Created: 2018-10-18
    Updated: 2019-10-18


## Simple Summary
Despite the increasing of useful transactions, we still see very malicious mining behaviors chasing empty blocks rather than utility. We hope a method called Utility Binding(UT) can help solve this problem.

## Motivation
Ethereum has the same problem for a long time, empty blocks. If there are no transactions, why bother to compute and generate coins? The problem would lead only to inflation but nothing valuable. Miners should not be blamed, but the design. So we have to rethink the architecture of the blockchain to make sure it serves the economy rather than just a blank idealism. The block that is able to propagate around the network more quickly will be the one to be accepted by the community and hence the one to get the block reward. In such design, empty blocks propagate around the network more quickly than blocks that aren't empty. It's definitely ok for general-purposed blockchain since there's no purpose(like Ethereum after "Global Computer" dream was proved unrealistic). But to Musicoin, the solid economy is laying on the sharing/consumption of music, which should not be ignored.


## Rationale
We can define a new rule to prove a block to be useful in real world, PPP in Musicoin is already a foundation of the economy(in micro way). If we attach PPP enforcement to block producing, it would be more reasonable to peg the real economy with the monetary supply, instead of speculating it's going to inflate or deflate(like BTC's stubborn design).

We may take two steps to implement though:
1. Forbid empty block to be accepted

we need to modify `consensus/ethash/sealer.go`
```
// Seal implements consensus.Engine, attempting to find a nonce that satisfies
// the block's difficulty requirements.
func (ethash *Ethash) Seal(chain consensus.ChainReader, block *types.Block, stop <-chan struct{}) (*types.Block, error) {
.....
if len(block.Transactions()) == 0 {
    log.Info("Sealing paused, waiting for transactions")
    return nil, nil
}
.....
```
2. Progress a block with at least one PPP contract. If there's no PPP, no blocks would be produced


## Specification
- After block 6.2M: We deploy step 1, then
- After block 7.2M: We deploy step 2  

## Backwards Compatibility
- Both two steps require hardfork but fully compatible with previous blocks in logic

## Implementation

- GMC
- Parity spec and customized version
