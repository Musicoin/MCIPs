        MCIP: 6
        Title: Applying EIP-155 Protocol for preventing the Replay Attack
        Status: Finalizing
        Type: Core
        Author: trustfarm (KT Ahn - 안씨아저씨) <trustfarm.info@gmail.com>,
                5chdn (Afri Schoedon) <schoedon@uni-potsdam.de>,
                im (Isaac Mao) <isaac@musicoin.org>
        Created: 2017-10-30

Abstract
--------
Hard fork of the Musicoin blockchain which enables the EIP-155 protocol to prevent replay attacks.

Motivation
----------
Currently, gmc-v2.x doesn't support Ethereum's EIP-155 Protocol, which defined the solution of reducing the risk of replay attack on Ethereum-based chains. If we don't consider this upgrade, Musicoin chain may face the similar threat as it gains popularity. Enabling EIP-155 will also allow users to securely store their assets on the Ledger Nano S and Trezor hard wallets, as well as MyEtherWallet.


Rationale
---------
By replacing CHAIN_ID with a unique value, the transaction hash will be different from chain to chain and possible to prevent from replay attack.

Specification
-------------
Apply to above gmc-v2.2x , rmc-v2.2x (parity-v1.8 based Musicoin node) at block 2,100,000 enable EIP-155 feature on Musicoin chain. Quote from EIP-155:

```If block.number >= FORK_BLKNUM and v = CHAIN_ID * 2 + 35 or v = CHAIN_ID * 2 + 36, then when computing the hash of a transaction for purposes of signing or recovering, instead of hashing only the first six elements (ie. nonce, gasprice, startgas, to, value, data), hash nine elements, with v replaced by CHAIN_ID, r = 0 and s = 0. The currently existing signature scheme using v = 27 and v = 28 remains valid and continues to operate under the same rules as it does now.
```

Backwards Compatibility
-----------------------
It needs to assign future blocknumber is better for user. If node set to N th blocknumber, node which enabled EIP-155 will re-sync from N th block height. It’s backward-compatible below the block height of 0~(N-1),EIP-155-enabled block. (N block)


Implementation
--------------
Parameters
----------

    FORK_BLKNUM: 2,222,222
    CHAIN_ID: 7762959 (MUSIC)
    
