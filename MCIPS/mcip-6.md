      MCIP: 6
      Title: Appling EIP-155 Protocol for preventing the Replay Attack
      Status: Draft Proposal
      Type: Core
      Author: trustfarm (KT Ahn - 안씨아저씨) <trustfarm.info@gmail.com>, 
              5chdn (Afri Schoedon) <schoedon@uni-potsdam.de>, 
              im (Isaac Mao) <isaac@musicoin.org>
      Created: 2017-10-30

Abstract
--------

Prevent replay Attack, enabling the EIP-155 Protocol on Musicoin Chain.

Motivation
----------

Current gmc-v2.0 doesn't applied ethereum's EIP-155 Protocol.
So, there's risk of replay attack on ethereum based chain.
Thus we need to apply this feature on musicoin chain as soon as possible.

Specification
-------------

Apply to above gmc-v2.2x , rmc-v2.2x (parity-v1.8 based musicoin node)
at (what blocknumber [TBD] ) enable EIP-155 feature on musicoin chain.

Rationale
---------

From the testing the EIP-155 enabled feature on local environment,
It needs to assign future blocknumber is better for user.

Backwards Compatibility
-----------------------

If node set to **N** th blocknumber, node which enabled EIP-155 will **re-sync** from **N** th block height.
**0~(N-1)** block height : backward compatible.
above **N** block : EIP-155 enabled block.

Implementation
--------------

Above gmc-v2.1 , we can configure what time we apply EIP-155 by Musicoin community consensus.
It's enough on technically.

Consideration of Applying blocknumber
-------------------------------------

Suggestion of Discussed
1. Around 1.9M (Mid of Feb,2018) , Musicoin will scheduled to fork. and that time apply EIP-155.
2. Around 1.7M (Mid of Jan,2018) or More earlier (End of Year) , Soft fork EIP-155.
- Another Consideration with EIP-155 is enabling EIP-150 (Gas Fee change). 

