      MCIP: 3
      Title: Universal Basic Income
      Status: Implemented
      Type: Standard
      Author: Isaac Mao <isaac@musicoin.org>
      Created: 2017-05-24

Abstract
--------

Based on the [Roadmap of $MUSIC](https://medium.com/@musicoin/roadmap-of-musicoin-blockchain-4a65620fefceroadmap), we are going to make $MUSIC blockchain more useful to boost real world demands. Universal Basic Income(UBI) is the core idea in "Heal the world"(v2.0). This approach will insert a reservoir to be used to pay music by blockchain as a basic benefit to global listeners. This policy is a proactive method to stimulate the whole music economy.  

Motivation
----------

In design, Musicians are at the center to the success of the whole system. Without the participation of musicians, the whole system would become valueless like most cryptocurrencies in market, given whatever money policy applied. In many cryptocurrencies realm, although miners accumulated a lot of coins, they are not going to use them apart from trading. Musicoin project may face the same challenge to really make the currency a useful one. At the early stage, there are still no enough musicians in the system, listeners(even music lovers) won’t regard it as a valuable service to them. And the less playback, the less incentives to get more musicians' interest to release their music to Musicoin project. It becomes another chicken-egg issue.

Early attempts of Muiscoin Project, especially in "Hello"(V1.0). Although with a some free plays from a donation pool which comes from community, to enable early listeners to have some free playbacks. However, they still need to pay after a while based on the requirements of Pay-per-play license embedded in blockchain. We observed that listeners may hesitate to continue the journey, even quit the system. The ultimate reason is the impulse to acquire more $MUSIC before hooking to the music enjoyment of the whole system. We need to find a solution to break the deadlock.

Rationale
---------

After a long time debate and deliberation, our community has adopted UBI(Universal Basic Income) scheme to solve the problem above and fuel the whole new $music economy. This MCIP is to UBI into the v2.0 of $music blockchain(codename: "Heal the world").

With UBI, every song is possible to be played for free to listeners although they didn't really get the money. Blockchain will help them pay to musicians which is equal to their getting basic income for musical life.

In this way, musicians won’t need to worry about losing their income, or sacrificing their income to tout listeners. Now PPP is not only a license but also an arbitrary policy. To global music listeners,UBI is designed for them like god gift. They will have FREE listening without guilt(it's why it's called Universal Basic Income), as long as the UBI pool has enough balance. With this scheme, they won’t hesitate to come back and listen to more songs.

We imagine UBI will not only please listeners in free playback, but also be possible to trigger more needs to tip musicians because listeners would be keen to have more intimate relationship with music and its creators, thus yield more demands for coins. We have observed 1:5 between music playbacks and tips in current blockchain. It means for every music was listened, there could be 5 times of tips being paid from listeners. This ratio can be higher in the future as more attachment could be built between musicians and music listers. After all, music is emotional art.

Furthermore, if listeners wants higher needs, they have to pay by themselves. Apart from tipping, playlist is a good case to study. Since every song played is for “free” now, users don’t need to pay if they only play one song, however, if they want to organize a playlist, either for himself or for sharing, he needs have a user name to make it and save it. For others wants to play the playlist, they need to pay to the creator of playlist to have a continuous playback one by one. Coins become more useful with such higher demands.

In this way, although UBI is part of monetary policy, it won't hurt the benefit of miners. Intead, the profitability of miners would be much higher than the proportion from the total issuance as the demand and circulation will be boosted. Actually the change will also mitigate the feeling of inflation by squeezing some coins into consumption instead of pouring to market directly.  

Specification
-------------

With UBI scheme, we need to change the block reward after by allocating 250 coins will go to miners, 50 will be kept as UBI, and 14 coins will be reserved as dev fund.

The implementation will be put into the block rewarding module in both go-musicoin and rust-musicoin. We will have a pseudo explanation over that:
```
statedb.AddBalance(header.Coinbase, rewardMinerBase)  'add coins to miner's coin base
statedb.AddBalance(common.Address{UBIContract}, rewardUBI) 'add to UBI base
statedb.AddBalance(common.Address{DevContract}, rewardDev) 'add to Dev base
```

The deployment of this change needs to [mcip-4.mediawiki | signal] in advance to study the current network.
