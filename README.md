# Awesome Taproot Assets ⚡🍠

 A curated list of Taproot Assets projects and resources 
 
[![Awesome](https://awesome.re/badge-flat2.svg)](https://awesome.re)

![image](https://github.com/22388o/awesome-taproot-assets/assets/83122757/b75f91c3-1b38-448b-b635-f271230edafa)


## What is Taproot Assets? 

Taproot Assets (formerly Taro) is a new Taproot-powered protocol for issuing assets on the bitcoin blockchain that can be transferred over the Lightning Network for instant, high volume, low fee transactions. At its core, Taproot Assets taps into the security and stability of the bitcoin network and the speed, scalability, and low fees of Lightning.

Taproot Assets relies on Taproot, bitcoin’s most recent upgrade, for a new tree structure that allows developers to embed arbitrary asset metadata within an existing output. It uses Schnorr signatures for improved simplicity and scalability, and, importantly, works with multi-hop transactions over Lightning.


### Potential Use Case

- Tokenized Securities
- Tokenized Real State
- Bitcoin as Collateral
- NFTs
- Stablecoins
- Atomic Swap
- Explorers
- Submarine Swap
- Wallets
- Rewards
- Mint Services
- Social media (accepting payments via Stablecoins or tokens)

## Tech Overview

Little overview around Taproot Assets

### How works

When minting a new asset, Taproot Assets will generate the relevant witness data, assign the asset to a key held by you and publish the corresponding bitcoin UTXO -- the minting transaction.

The outpoint this minting transaction consumes becomes the genesis_point of the newly minted asset, acting as its unique identifier. Assets can be spent to a new recipient, who provides the sender with the necessary information encoded in their Taproot Asset address.

To transact assets, the witnesses in the prior transaction are recommitted into one or multiple taproot outputs while the necessary witness data is passed to the recipient. Similar to bitcoin transactions, the remaining balance is spent back to the sender as a change output.

### Architecture

Taproot Assets are implemented as the Taproot Assets Daemon tapd and the Taproot Assets Command Line Interface tapcli. Additionally, tapd exposes a GRPC interface to allow for a direct integration into applications.

Taproot Assets leverage several LND features including the Taproot wallet and signing capabilities. These facilities are accessed through LND’s GRPC.

The Taproot Assets stack:

**Bitcoin blockchain backend <-> LND <-> Taproot Assets**

Custody of Taproot Assets is segmented across LND and Tapd to maximize security. LND holds the private key, which has had a taproot tweak applied to it, controlling the bitcoin UTXO holding the Taproot Asset. The taproot tweak on the other hand is held by Tapd. This increases the requirements for asset recovery as both the internal key as well as the taproot tweak are necessary to spend the output. This prevents LND from accidentally burning Taproot assets.

### Status software

Taproot Assets is available in testnet and mainnet with [v0.3.0-alpha](https://github.com/lightninglabs/taproot-assets/releases/tag/v0.3.0)

## Lightning Labs Resources

- [Documentation](https://docs.lightning.engineering/the-lightning-network/taproot-assets)

- [Code](https://github.com/lightninglabs/taproot-assets)

- [Run client](https://docs.lightning.engineering/lightning-network-tools/taproot-assets/first-steps)

- [Tap into the Universe: Issue and Discover Assets on Bitcoin with the Taproot Assets Protocol](https://www.youtube.com/watch?v=8Qi7VOvKe5o)

- [API Taproot Assets Protocol](https://lightning.engineering/api-docs/api/taproot-assets/)

- [Taproot Assets: A New Protocol for Multi-Asset Bitcoin and Lightning](https://www.youtube.com/watch?v=-yiTtO_p3Cw)

- [A Technical Overview of Virtual PSBTs in the Taproot Assets Protocol](https://lightning.engineering/posts/2023-06-14-virtual-psbt/)

- [Announcing Taro: A New Protocol for Multi-Asset Bitcoin and Lightning 🍠💱🌍](https://lightning.engineering/posts/2022-4-5-taro-launch/)

- [[bitcoin-dev] BIP-????: The Taproot Assets Protocol](https://lists.linuxfoundation.org/pipermail/bitcoin-dev/2023-September/021938.html)

- [BIP: Taproot Asset On Chain Addresses](https://github.com/bitcoin/bips/blob/c156b7691d8b0f3880b5e506712c2527f840d1b1/bip-tap-addr.mediawiki)

- [Blip: Taproot Asset Protocol Channels](https://github.com/lightning/blips/blob/f60cfb7bdd6fa266f88b80f0f65a5d5541862ad6/blip-tap.md)

- [[Lightning-dev] blip-0029: Taproot Asset Protocol Channels](https://lists.linuxfoundation.org/pipermail/lightning-dev/2023-September/004089.html)

- [Announcing LND 0.17 beta: Tapping into Taproot 🥕⚡](https://lightning.engineering/posts/2023-10-03-lnd-0.17-launch/)

- [Taproot Assets on Mainnet: A New Era for Bitcoin and Beyond 🌅](https://lightning.engineering/posts/2023-10-18-taproot-assets-v0.3/)


## Articles

- [Understanding Taproot Assets Protocol](https://medium.com/@nayuta-gondo/understanding-taproot-assets-protocol-e2dfe3fc1e07)
- [RGB And Taro, Both Putting Tokens On Bitcoin, Take Two Different Approaches To Development](https://bitcoinmagazine.com/technical/rgb-taro-putting-tokens-on-bitcoin)
- [Addressing The Realities Of Taro’s Limitations](https://bitcoinmagazine.com/technical/addressing-realities-of-taros-limitations)
- [The Scaling Problem For Lightning Lab’s Taro On The Bitcoin Blockchain](https://bitcoinmagazine.com/technical/scaling-problem-for-lightning-labs-taro)
- [How Taro Brings Assets To Bitcoin Through Taproot And Lightning](https://bitcoinmagazine.com/technical/how-bitcoin-taro-protocol-works)
- [Developers Can Now Issue Assets Like Stablecoins On Bitcoin](https://bitcoinmagazine.com/technical/taro-launches-stablecoins-on-bitcoin)
- [Next Step To Widespread Bitcoin Adoption: Community Banks](https://bitcoinmagazine.com/technical/community-banks-improve-bitcoin-adoption)
- [Why It’s Important To Build Stablecoins On Bitcoin](https://bitcoinmagazine.com/culture/important-to-build-stablecoins-on-bitcoin)
- [Examining The Incentives Of Stablecoins On Bitcoin](https://bitcoinmagazine.com/technical/incentives-of-stablecoins-on-bitcoin)
- [BTC-Backed Stablecoins Will be An Integral Part Of The Bitcoin Economy](https://bitcoinmagazine.com/technical/world-needs-bitcoin-backed-stablecoins)
- [The Path To A Bitcoin Economy: Decentralized Bitcoin-Backed Credit](https://bitcoinmagazine.com/culture/decentralized-bitcoin-backed-credit)
- [Ordinals Have Proven Demand On Bitcoin, But Fees Will Push Users To Layer 2](https://bitcoinmagazine.com/culture/bitcoin-ordinal-problems-solved-by-layer-2)
- [Emergence of Token Layers on Bitcoin: Overview of Client-Side Validation, RGB and Taro](https://docsend.com/view/he8x9erkjmphphvn)
- [What is a Taproot Asset Universe](https://thebitcoinmanual.com/articles/taproot-asset-universe/)
- [Is Bitcoin Undervalued?](https://blog.bitfinex.com/education/is_bitcoin_undervalued/)
- [Taproot Assets: Issuing Assets on Bitcoin](https://voltage.cloud/blog/lightning-network-use-cases/taproot-assets-on-bitcoin-and-lightning-network/)
- [What is Taro in Bitcoin](https://river.com/learn/what-is-taro-in-bitcoin/)
- [Taproot Assets on Mainnet: A New Era for Bitcoin and Beyond 🌅](https://lightning.engineering/posts/2023-10-18-taproot-assets-v0.3/)
- [UXUY Implements Bitcoin Lightning Node to Serve Multi-Chain Trading for Taproot Assets](https://finance.yahoo.com/news/uxuy-implements-bitcoin-lightning-node-094000803.html)
- [Lightning Labs Rolls Out Taproot Assets Mainnet Alpha](https://bitcoinmagazine.com/technical/lightning-labs-rolls-out-taproot-assets-mainnet-alpha)

## Tutorial

- [ Taproot Assets Demo: Mint, Send, and Receive Taproot Assets on Bitcoin with the Alpha Daemon](https://www.youtube.com/watch?v=xtklaJHfKIY)



## Specifications

- [Lightning Network Specification](https://github.com/lightningnetwork/lightning-rfc)
- [Taproot Assets Specification](https://lists.linuxfoundation.org/pipermail/bitcoin-dev/2022-April/020196.html)
  
## Videos

- [Will Taproot Assets Be Good or Bad for Bitcoin?| E116](https://www.youtube.com/watch?v=Zrwv9TDNxSE)
- [Leo Weese from Lightning Labs explains Taproot Assets (formerly Taro)](https://www.youtube.com/watch?v=NcMVcMu9k3M)
- [Taro - Leo Weese - Adopting Bitcoin Day 1 - Galoy Stage](https://www.youtube.com/watch?v=TiyXT1JnyNc)
- [Taproot Assets and the Impact of Stablecoins on the Lightning Network | E119](https://www.youtube.com/watch?v=V3irumTQKao)
- [Taproot Assets on Lightning](https://www.youtube.com/watch?v=2h2MabzCN7M)
- [Bitcoin Builders Conference:Taproot Assets on Lightning](https://www.youtube.com/watch?v=2h2MabzCN7M&ab_channel=BitcoinBuildersConference)
- [Building on Taro, a Taproot-powered protocol for issuing bitcoin assets](https://www.youtube.com/watch?v=JNaryHu2mFc)


## Books

- [Mastering the Lightning Network (LN)](https://github.com/lnbook/lnbook)
- [Mastering Bitcoin, 2nd Edition](http://shop.oreilly.com/product/0636920049524.do)
- [Bitcoin and Lightning Network on Raspberry Pi](https://www.apress.com/gp/book/9781484255216)


## Wallets

- [Tiramisu Wallet: Mint, send, Exchange](https://testnet.tarowallet.net/walletapp/)
- [Tao Wallet: USD for everyone](https://github.com/dannydeezy/tao-wallet)
- [Joltz Wallet](https://www.loom.com/share/ea2edd0294054dae989db5f362f4a846?sid=31b9a7cf-cffe-4941-9aea-0c346b68b90c)
- [UXUY](https://uxuy.com/)
- [Speed](https://www.speed.app/)

## Explorer

- [Taproot Assets Explorer](https://explorer.royllo.org/)

## Community

- [Lightning Labs Telegram](https://t.me/lightninglab)
- [Lightning Labs Slack](https://lightningcommunity.slack.com/join/shared_invite/zt-1pjbf93tz-cxIAWCIror78rOBBinAglg#/shared-invite/)
- [Lightning Labs Twitter](https://twitter.com/lightning)

## Exchanges

- [L2.Auction](https://l2.auction/)
- [Tiramisu Wallet](https://testnet.tarowallet.net/walletapp/)
- [Nostr Assets Protocol](https://doc.nostrassets.com/)
- [DFX Swiss](https://dfx.swiss/)
- [UXUY](https://uxuy.com/)


## Tools

- [Lightning Terminal: Support Taproot Assets via Testnet](https://github.com/lightninglabs/lightning-terminal)
- [Lightning Node Connect (LNC)](https://github.com/lightninglabs/lightning-node-connect)
- [Polar: Support Taproot Assets via Testnet](https://github.com/jamaljsr/polar)
- [Lightning-TaprootAssets](https://github.com/jacohend/ltd)
- [Royllo](https://www.royllo.org/)
- [Mega Mint](https://drive.google.com/file/d/1ojftCrY2mPx3C5EX-cyAPcsUrLbetRzE/view?resourcekey&pli=1)


 ## Tokens and Stablecoins
 
- [HabibTaro](https://github.com/habibitcoin/habibtaro)
- [Root-USD](https://github.com/D33r-Gee/rootUSD-Prototype)
- [Tao](https://tao.deezy.io/)
- [Nostr Assets Protocol](https://test.nostrassets.com/#/account)
- Galaxy Digital
- UB

 ## NFTs
 
- [THNDR Games](https://www.thndr.games/)
  
## Tokenized Securities

- [Hayek Dynamics](https://hayekdynamics.com/)

## Rewards

- [Joltz Rewards](https://joltzrewards.com/)

## Companies support Taproot Assets

- Lightning Labs
- L2.Auction
- Tiramisu wallet
- Nostr Assets Protocol
- DFX Swiss
- Galaxy Digital
- Polar
- Royllo
- Deezy Inc
- UB
- THNDR Games
- Joltz Rewards
- Hayek Dynamics
- UXUY

## Extra list

- [awesome-taproot-asset by Discoco Protocol](https://github.com/Discoco-Protocol/awesome-taproot-asset)
- [awesome taproot assets by Ben2077](https://github.com/ben2077/awesome-taproot-assets)

