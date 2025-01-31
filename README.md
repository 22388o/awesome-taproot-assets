# Awesome Taproot Assets ⚡🍠🪙

 >A curated list of Taproot Assets projects and resources 
 
[![Awesome](https://awesome.re/badge-flat2.svg)](https://awesome.re)

![image](https://github.com/22388o/awesome-taproot-assets/assets/83122757/b75f91c3-1b38-448b-b635-f271230edafa)

**Contributions are welcome**

## What is Taproot Assets? 

Taproot Assets (formerly Taro) is a new Taproot-powered protocol for issuing assets on the bitcoin blockchain that can be transferred over the Lightning Network for instant, high volume, low fee transactions. At its core, Taproot Assets taps into the security and stability of the bitcoin network and the speed, scalability, and low fees of Lightning.

Taproot Assets relies on Taproot, bitcoin’s most recent upgrade, for a new tree structure that allows developers to embed arbitrary asset metadata within an existing output. It uses Schnorr signatures for improved simplicity and scalability, and, importantly, works with multi-hop transactions over Lightning.


### Potential Use Case

- RWAs
- Smart contracts with Bitcoin script
- Bitcoin as Collateral
- NFT/NFT Marketplace/NFT auction
- Crowdfunding
- Stablecoins (aka. Centralized like USDC and USDT)
- Stablecoins algorithm 
- Sythentic stablecoins
- Atomic Swap (between taproot assets only)
- Explorers
- Submarine Swap
- Wallets
- Rewards
- Mint Services (tokens)
- Social media (accepting payments via Stablecoins or tokens)
- Decentralized Exchange via Lightning Node
- Exchanges with centralized solutions
- Lightning Service Provider for Taproot Assets
- Virtual Machine (VM)
- Nodes (LND)
- OTC Exchange
- Cloud Service (Nodes, LSP)
- APIs
- GameFi
- System of points
- Compatible with DLCs & Taproot
- Centralized Exchanges
- Asset Management
- Custodial services 
- Derivatives
- Interoperability (UTXO chains)
- AI compatible tech
- MiniDEX with swaps
- Identities (aka. Nostr)
- Cross-assets(Taproot Assets<>RGB)
- BOLT12 compatible

## Tech Overview

Little overview around Taproot Assets

### How works

When minting a new asset, Taproot Assets will generate the relevant witness data, assign the asset to a key held by you and publish the corresponding bitcoin UTXO -- the minting transaction.

The outpoint this minting transaction consumes becomes the genesis_point of the newly minted asset, acting as its unique identifier. Assets can be spent to a new recipient, who provides the sender with the necessary information encoded in their Taproot Asset address.

To transact assets, the witnesses in the prior transaction are recommitted into one or multiple taproot outputs while the necessary witness data is passed to the recipient. Similar to bitcoin transactions, the remaining balance is spent back to the sender as a change output.

![image](https://github.com/22388o/awesome-taproot-assets/assets/83122757/d55c637d-e757-4348-8dec-4fdadacfcc95)


### Architecture

Taproot Assets are implemented as the Taproot Assets Daemon tapd and the Taproot Assets Command Line Interface tapcli. Additionally, tapd exposes a GRPC interface to allow for a direct integration into applications.

Taproot Assets leverage several LND features including the Taproot wallet and signing capabilities. These facilities are accessed through LND’s GRPC.

The Taproot Assets stack:

**Bitcoin blockchain backend (layer 1) <-> LND (layer 2) <-> Taproot Assets**

Custody of Taproot Assets is segmented across LND and Tapd to maximize security. LND holds the private key, which has had a taproot tweak applied to it, controlling the bitcoin UTXO holding the Taproot Asset. The taproot tweak on the other hand is held by Tapd. This increases the requirements for asset recovery as both the internal key as well as the taproot tweak are necessary to spend the output. This prevents LND from accidentally burning Taproot assets.

![image](https://github.com/22388o/awesome-taproot-assets/assets/83122757/50fbfe33-6b97-42e4-a256-dbee75b18ad3)

## Standards

- Non fungible tokens (NFTs)
- Fungible tokens
- Identities?

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

- [[bitcoin-dev] Taproot Assets on Mainnet: Announcing tapd v0.3.0-alpha](https://lists.linuxfoundation.org/pipermail/bitcoin-dev/2023-October/022019.html)

- [Entering the Bitcoin Renaissance: Making Bitcoin and Lightning Multi-Asset Networks 🌅💡](https://lightninglabs.substack.com/p/entering-the-bitcoin-renaissance)

- [The Next Frontiers of Lightning: Taproot Assets, Nostr, and AI, Oh My! ⚡️🥕🤖](https://lightninglabs.substack.com/p/the-next-frontiers-of-lightning-taproot)

- [To Bitcoin and Beyond: How Taro Expands the Lightning Universe 🌌⚡️](https://lightninglabs.substack.com/p/to-bitcoin-and-beyond-how-taro-expands)

- [Decentralizing Global FX With Taro: How Bitcoin Renders "Cross-Border" Payments Obsolete 🍠💱](https://lightninglabs.substack.com/p/decentralizing-global-fx-with-taro)

- [Bitcoinizing the Dollar, and the World, with Lightning 💸⚡🌍](https://lightninglabs.substack.com/p/bitcoinizing-the-dollar-and-the-world)

- [Rfq Service](https://lightning.engineering/api-docs/category/rfq-service/index.html)

- [Taproot Assets Channels Service](https://lightning.engineering/api-docs/category/taprootassetchannels-service)

- [Taproot Assets on Lightning: The Global Financial Interoperability Layer ⚡💱](https://lightning.engineering/posts/2024-07-23-taproot-assets-LN/)

- [A New Era for Stablecoins: Tether Is Coming to Bitcoin and Lightning ⚡💸](https://lightning.engineering/posts/2025-01-30-Tether-on-Lightning/)


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
- [All of a Sudden, It’s All About Bitcoin](https://www.coindesk.com/tech/2023/10/25/all-of-a-sudden-its-all-about-bitcoin/)
- [Taking stock of BTC ecological protocols, which protocols can win the last prize?](https://www.binance.com/en-IN/feed/post/1516603?ref=48152048)
- [Lightning Strikes Twice: How Taproot Assets Electrify Bitcoin's Future](https://lightningnetwork.plus/posts/481)
- [Taproot Assets on Mainnet: A Brief Overview](https://lightningnetwork.plus/posts/465)
 - [Off-Chain Transactions: The Evolution of Bitcoin Asset Protocols](https://mirror.xyz/0x5CCF44ACd0D19a97ad5aF0da492AC0388469DfE9/h7XChxETK-cBfGdc0sTq_cCuWeo13-sp1j-g0ZYoYdc)
- [Exploring the Multi-Asset Issuance Mechanism of Taproot Assets](https://wublock.substack.com/p/exploring-the-multi-asset-issuance)
- [Lightning Labs lança Taproot Assets para introduzir stablecoins e RWAs na blockchain do Bitcoin ](https://br.cointelegraph.com/news/lightning-labs-releases-taproot-assets-alpha-bringing-stablecoins-to-bitcoin)
- [Comparing BRC20 and Taproot Assets: Market Speculation vs Technical Advancement](https://wublock.substack.com/p/comparing-brc20-and-taproot-assets)
- [Evolution and challenge of BTC expansion from asset issuance](https://medium.com/@ACCapital1/evolution-and-challenge-of-btc-expansion-from-asset-issuance-d8caba8aeb07)
- [Taproot Assets Can Turn Bitcoin Into A Multi-Asset Chain](https://bitcoinmagazine.com/technical/taproot-assets-can-turn-bitcoin-into-a-multi-asset-chain)
- [Decoding the Complex Landscape of Bitcoin Layer 2: Navigating Challenges and Building Narratives](https://wublock.substack.com/p/decoding-the-complex-landscape-of)
- [What is the Taproot Assets Protocol?](https://trustmachines.co/learn/what-is-the-taproot-assets-protocol-by-li/)
- [CGV Research | From Colored Coins, Mastercoin/Omni to Ordinals/BRC20, a Comprehensive Analysis of Technological Evolution in the Bitcoin Ecosystem](https://wublock.substack.com/p/cgv-research-from-colored-coins-mastercoinomni)
- [Bitcoin Ecosystem — The Engine for the Next Bull Market](https://www.bitget.com/blog/articles/bitcoin-ecosystem-the-engine-for-the-next-bull-market)
- [Quais novas tecnologias devem surgir nos próximos anos no Bitcoin?](https://portaldobitcoin.uol.com.br/quais-novas-tecnologias-devem-surgir-nos-proximos-anos-no-bitcoin/)
- [Exploring the Landing Paths for Bitcoin Layer 2 Ecosystem ](https://wublock.substack.com/p/exploring-the-landing-paths-for-bitcoin)
- [A hundred flowers are blooming in Bitcoin Layer 2, a look at the progress of 6 major mainstream protocols](https://blockcast.it/2024/01/17/the-state-of-top-bitcoin-layer2-projects/)
- [Flash Protocol x LeverFi: Empowering Decentralized Asset Issuance and Trading in the BTC Ecosystem](https://medium.com/leverfi/flash-protocol-x-leverfi-empowering-decentralized-asset-issuance-and-trading-in-the-btc-ecosystem-74261dd71845)
- [Taproot Assets Structure](https://stacker.news/items/460297)
- [What Does Lightning’s Taproot Assets Mean for Stacks?](https://www.hiro.so/blog/what-does-lightnings-taproot-assets-mean-for-stacks)
- [Unlocking Possibilities: Exploring Taproot Assets Protocol on the Bitcoin Blockchain](https://medium.com/@anisotropic45/unlocking-possibilities-exploring-taproot-assets-protocol-on-the-bitcoin-blockchain-3f1bc454a20e)
- [Announcement: NostrAssets upgrades to Lnfi](https://medium.com/@lnfinetwork/announcement-nostrassets-upgrades-to-lnfi-f03b15a79372)
- [Joltz Launches Wallet and SDK, Making Taproot Assets Accessible to All](https://finance.yahoo.com/news/joltz-launches-wallet-sdk-making-111100641.html?guccounter=1)
- [Lightning Labs CTO Conducts First Mainnet Multi-Hop Asset Payment via Taproot Asset Channels](https://news.bitcoin.com/lightning-labs-cto-conducts-first-mainnet-multi-hop-asset-payment-via-taproot-asset-channels/)
- [Lightning Labs Paving the Way to Bring Stablecoins to Bitcoin](https://cryptonews.com/news/lightning-labs-bring-stablecoins-to-bitcoin.htm)
- [The Future of Bitcoin #3: Scaling Bitcoin](https://www.binance.com/en/research/analysis/the-future-of-bitcoin-3-scaling-bitcoin)
- [LightningFi #1 — Global Lightning Adoption with Channel Mining](https://lnfinetwork.medium.com/lightningfi-1-global-lightning-adoption-with-channel-mining-9dd7f2e2645e)
- [The Power of Taproot Assets: A new way of managing Digital Assets](https://www.cypherpunktimes.com/the-power-of-taproot-assets-a-new-way-of-managing-digital-assets/)
- [Launching the Future: LN Ecosystem and LN Alliance to Drive Bitcoin Lightning Network Adoption and Innovation](https://lnfinetwork.medium.com/launching-the-future-ln-ecosystem-and-ln-alliance-to-drive-bitcoin-lightning-network-adoption-and-3f186caaf951)
- [3 Protocols Bringing Asset Issuance to Bitcoi](https://www.techiexpert.com/3-protocols-bringing-asset-issuance-to-bitcoin/)
- [Client-Side Validation Protocol](https://rooch.network/learn/in-depth-tech/client-side-validation)
- [What Is Bitcoin’s Lightning Network, And How Does It Work?](https://medium.com/@lorenzoprotocol/what-is-bitcoins-lightning-network-and-how-does-it-work-4f68d747d300)
- [Taproot Assets - River Glossary](https://river.com/learn/terms/t/taro/)
- [Bitcoin Lightning Alliance To Accelerate Adoption Using New Asset Protocol](https://bitcoinmagazine.com/technical/bitcoin-lightning-alliance-to-accelerate-adoption-using-new-asset-protocol)
- [Lightning Network, Taproot Assets, and Nostr Merchandise Contest](https://medium.com/@nostrcommunity/lightning-network-taproot-assets-and-nostr-merchandise-contest-d4c3e7f03860)
- [Elizabeth Stark: Pioneering Bitcoin Scalability with Lightning Network](https://www.crypto-news-flash.com/elizabeth-stark-pioneering-bitcoin-scalability-with-lightning-network/)
- [Taproot Assets on Lightning: The Global Financial Interoperability Layer ⚡💱](https://lightning.engineering/posts/2024-07-23-taproot-assets-LN/)
- [Stablecoins Are Coming To Bitcoin's Lightning Network](https://bitcoinmagazine.com/technical/stablecoins-are-coming-to-bitcoins-lightning-network)
- [Second layers and other projects on top of bitcoin](https://braiins.com/blog/second-layers-and-other-projects-on-top-of-bitcoin)
- [Be the First to Bridge USDT to the Lightning Network and Earn Exciting Rewards with LN Bridge!](https://lnfinetwork.medium.com/be-the-first-to-bridge-usdt-to-the-lightning-network-and-earn-exciting-rewards-with-ln-bridge-a7ad2e66b887)
- [Challenging Stablecoin Platforms: Speed Wallet introduces USDT on Lightning to compete against Ethereum, TRON and SOLANA](https://www.tryspeed.com/blog/speed-wallet-introduces-usdt-on-lightning/)
- [Assessing the Lightning Network's Last-Mile Solutions](https://bitcoinmagazine.com/technical/assessing-the-lightning-networks-last-mile-solutions)
- [Taproot Assets: The next growth point for the stablecoin track to exceed a trillion-dollar market value](https://www.bitget.com/news/detail/12560604162334)
- [Bitcoin Lightning Network and Taproot Assets Explained](https://www.coinlive.com/news/bitcoin-lightning-network-and-taproot-assets-explained)
- [The Risks of Current Stablecoin Networks: Why Bitcoin and Lightning Offer a Safer Alternative](https://www.voltage.cloud/blog/the-risks-of-current-stablecoin-networks-why-bitcoin-and-lightning-offer-a-safer-alternative)
- [What Is Bitcoin DeFi: The Rise of BTCFi](https://learn.bybit.com/bitcoin/what-is-bitcoin-defi-btcfi/)
- [Evolution of Taro Protocol: Stablecoins and Multi-Asset Transfers With Taproot Assets](https://medium.com/coinmonks/evolution-of-taro-protocol-stablecoins-and-multi-asset-transfers-with-taproot-assets-5f9e6e8e1b32)
- [Lnfi and Bihelix Collaborate to Bridge Taproot and RGB Assets on the Lightning Network](https://medium.com/@lnfinetwork/lnfi-and-bihelix-collaborate-to-bridge-taproot-and-rgb-assets-on-the-lightning-network-798a664ea788)
- [Four Mainstream Bitcoin Scaling Solutions: Which Will Unlock BTCFi's Trillion-Dollar Potential?](https://www.gate.io/learn/articles/four-mainstream-bitcoin-scaling-solutions-which-will-unlock-btcfis-trillion-dollar-potential/4472)
- [What is the Taproot Assets Protocol (TAP)? A Beginner's Guide](https://www.samara-ag.com/market-insights/taproot-assets-protocol)
- [Bitcoin Layers: Lightning, RSK, Stacks & Co Explained](https://www.samara-ag.com/market-insights/bitcoin-layers-explained)
- [ Tether Brings USDt to Bitcoin’s Lightning Network, Ushering in a New Era of Unstoppable Technology](https://tether.io/news/tether-brings-usdt-to-bitcoins-lightning-network-ushering-in-a-new-era-of-unstoppable-technology/)
  
## Tutorial

- [Taproot Assets Demo: Mint, Send, and Receive Taproot Assets on Bitcoin with the Alpha Daemon](https://www.youtube.com/watch?v=xtklaJHfKIY)
- [Tapping into Taproot Assets #1: Install from Source ](https://www.youtube.com/watch?v=Z7KLo-pGBJA&t=9s)
- [Tapping into Taproot Assets #2: Prototype with Polar](https://www.youtube.com/watch?v=pYh-4EfdZaM)
- [Tapping into Taproot Assets #3: Launch with Litd ](https://www.youtube.com/watch?v=EaPZ3EbTWhE)
- [Tapping into Taproot Assets #4: Join a Universe Federation](https://www.youtube.com/watch?v=o6U812eSE_Q)
- [Tapping into Taproot Assets #5: Mint from the CLI ](https://www.youtube.com/watch?v=FccI6j0mxuE)
- [Tapping into Taproot Assets #6: Mint from the API ](https://www.youtube.com/watch?v=IL4ojWyFPSk)
- [Tapping into Taproot Assets #7: Send from the CLI ](https://www.youtube.com/watch?v=o30AiqbsYhw)
- [Tapping into Taproot Assets #8: Send from the API](https://www.youtube.com/watch?v=UEaNXu8me24)
- [Tapping into Taproot Assets #9: Burn from the CLI](https://youtu.be/qBTGxSHpyDo?si=TbbFD85yN270lt1B)
- [Tapping into Taproot Assets #10: Burn from the CLI](https://youtu.be/hYUBA-AxrtE?si=Ub8nVxrVn4Xwxb19)
- [Tapping into Taproot Assets #11: Update Tapd](https://www.youtube.com/watch?v=0nvkrWfxW3k)
- [Tapping into Taproot Assets- Playlist](https://youtube.com/playlist?list=PL-3jjRT_28Sh3u_9CPVJkm8BLomh23QGk&si=htdifsKVQ4rIpp_C)
- [Taproot Assets on Voltage](https://docs.voltage.cloud/guides/taproot-assets-on-voltage)
- [Taproot Assets on Lightning ⚡](https://www.youtube.com/watch?v=4ot23hdNwMQ)
- [Running a Taproot Assets Edge Node](https://www.youtube.com/watch?v=_cC0Qco48Ww)
- [Running a Taproot Assets Price Oracle](https://www.youtube.com/watch?v=4iVlDbILLWE)

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
- [Bitcoin's Taproot Assets Protocol w/ Ryan Gentry (BTC153)](https://www.youtube.com/watch?v=DhL0QLyq9jw)
- [Tapping into Taproot Assets #1: Install from Source ](https://www.youtube.com/watch?v=Z7KLo-pGBJA&t=9s)
- [Tapping into Taproot Assets #2: Prototype with Polar](https://www.youtube.com/watch?v=pYh-4EfdZaM)
- [ Tapping into Taproot Assets #3: Launch with Litd ](https://www.youtube.com/watch?v=EaPZ3EbTWhE)
- [Tapping into Taproot Assets #4: Join a Universe Federation](https://www.youtube.com/watch?v=o6U812eSE_Q)
- [Tapping into Taproot Assets #5: Mint from the CLI ](https://www.youtube.com/watch?v=FccI6j0mxuE)
- [Tapping into Taproot Assets #6: Mint from the API ](https://www.youtube.com/watch?v=IL4ojWyFPSk)
- [Tapping into Taproot Assets #7: Send from the CLI ](https://www.youtube.com/watch?v=o30AiqbsYhw)
- [Tapping into Taproot Assets #8: Send from the API](https://www.youtube.com/watch?v=UEaNXu8me24)
- [Tapping into Taproot Assets #9: Burn from the CLI](https://youtu.be/qBTGxSHpyDo?si=TbbFD85yN270lt1B)
- [Tapping into Taproot Assets #10: Burn from the CLI](https://youtu.be/hYUBA-AxrtE?si=Ub8nVxrVn4Xwxb19)
- [Tapping into Taproot Assets #11: Update Tapd](https://www.youtube.com/watch?v=0nvkrWfxW3k)
- [Tapping into Taproot Assets- Playlist](https://youtube.com/playlist?list=PL-3jjRT_28Sh3u_9CPVJkm8BLomh23QGk&si=htdifsKVQ4rIpp_C)
- [和Taproot Asset协议的提拉米苏钱包的创始人聊一聊，空投怎么发，Adam代币持有人有什么福利？｜未来和RGB融合的可能性](https://www.youtube.com/watch?v=xRPt-Yh6cd0)
- [How to withdraw Taproot Assets from Tiramisu wallet](https://www.youtube.com/watch?v=h1jl4SVEo3M)
- [How to Install taproot assets node on a Linux machine](https://www.youtube.com/watch?v=obqQXlxa1Ws)
- [Minting NFT a taproot assets NFT collection with Tiramisu Wallet](https://www.youtube.com/watch?v=6fDShbLxhno)
- [Navigating Your Node with Terminal #1: Install & Connect](https://www.youtube.com/watch?v=XibPhZtNQak&list=PL-3jjRT_28SgFlWoNdTjCT3yz1v5ecQU7)
- [Buy Taproot Assets with Tiramisu Wallet - how to deposit, withdraw and trade](https://www.youtube.com/watch?v=5ykR6VwP4os)
- [Taproot Assets Protocol - overview of existing coins and NFTs](https://www.youtube.com/watch?v=Iu8-vxB1BTY)
- [Joltz Wallet: First Non-Custodial Bitcoin & Taproot Assets Wallet](https://www.youtube.com/watch?v=-wVv4R5u9P4)
- [Tiramisu Wallet Review (Buy Sell Mint BTC layer 2 Taproot assets)](https://www.youtube.com/watch?v=TmKfX7SBNnI)
- [Bitcoin & Lightning Multiasset Networks with Taproot Assets (Oliver Gugger @ Adopting Bitcoin Conf.)](https://www.youtube.com/watch?v=wG8U-IhlDtQ)
- [Comparing Runes & Taproot Assets with Linden Stark - CTO at Joltz Rewards](https://www.youtube.com/watch?v=Tyu9doo8K5A)
- [Taproot Assets - Oliver Gugger - AB24CPT Day 2 - Machankura Stage](https://www.youtube.com/watch?v=qV4ysnT9hC8)
- [The Truth About Bitcoin Scaling with niftynei](https://www.youtube.com/watch?v=9MYp88Ii84A)
- [All Roads Lead to Lightning - Bitcoin Asia](https://www.youtube.com/watch?v=omamm4XoUfo)
- [Taproot Assets LN Channel Setup | Lnfi Network](https://www.youtube.com/watch?v=5xHy2NC5wdM)
- [Taproot Assets on Lightning ⚡](https://www.youtube.com/watch?v=4ot23hdNwMQ)
- [Running a Taproot Assets Edge Node](https://www.youtube.com/watch?v=_cC0Qco48Ww)
- [Running a Taproot Assets Price Oracle](https://www.youtube.com/watch?v=4iVlDbILLWE)
- [Taproot Assets on Lightning Workshop - TABConf 6](https://www.youtube.com/watch?v=I6qv9lLvdbg)
- [Joltz: Bitcoin Powered Payments Infrastructure](https://www.youtube.com/watch?v=4f7Py8FdG1c)
- [Taproot Assets: Stablecoins na velocidade da luz](https://www.youtube.com/watch?v=1gYfv25ubDU)

## Books

- [Mastering the Lightning Network (LN)](https://github.com/lnbook/lnbook)
- [Mastering Bitcoin, 2nd Edition](http://shop.oreilly.com/product/0636920049524.do)
- [Mastering Bitcoin, 3rd Edition](https://www.oreilly.com/library/view/mastering-bitcoin-3rd/9781098150082/) - with Taproot Assets
- [Bitcoin and Lightning Network on Raspberry Pi](https://www.apress.com/gp/book/9781484255216)

## Libraries and Daemon

- [Taproot Assets Daemon](https://pkg.go.dev/github.com/lightninglabs/taproot-assets)
- [Tapdash](https://github.com/Nsandomeno/tapdash)
- [Taproot Assets Bot](https://github.com/snow884/taproot-assets-trading-bots)
- [Tiramisu Wallet Client API](https://pypi.org/project/tiramisu-wallet-client/)
- [Joltz SDK](https://docs.joltz.app/sdk)
- [Taproot Assets Playground](https://github.com/LN-Zap/taproot-assets-playground)

  
## Wallets

- [Tiramisu Wallet: Mint, send, Exchange](https://mainnet.tiramisuwallet.com)
- [Tao Wallet: USD for everyone](https://github.com/dannydeezy/tao-wallet)
- [Joltz Wallet](https://wallet.joltz.app/)
- [UXUY](https://uxuy.com/)
- [Speed](https://www.speed.app/)
- [Bitmask](https://bitmask.app/)
- [Swiss Knife](https://github.com/bitcoin-numeraire/swissknife)


## Issues tokens platform

- Tiramisu Walet
- Joltz Wallet

## Explorer

- [Taproot Assets Explorer by Rollo](https://explorer.royllo.org/)
- [TapasIndex](https://www.tapasindex.com/)
- [Universe Taproot Assets by Lightning Labs](https://terminal.lightning.engineering/assets/mainnet/index.html)
- [Universe Taproot Assets by UXUY](https://uxuy.com/taproot)
- [Universe Taproot Assets by Tiramisu wallet](https://universe.tiramisuwallet.com)
- [Taproot Assets Explorer by Megalithic](https://megalithic.me/taproot_assets_explorer)

## Community

- [Lightning Labs Telegram](https://t.me/lightninglab)
- [Lightning Labs Slack](https://lightningcommunity.slack.com/join/shared_invite/zt-1pjbf93tz-cxIAWCIror78rOBBinAglg#/shared-invite/)
- [Lightning Labs Twitter(X)](https://twitter.com/lightning)
- [Taproot Assets Asia](https://t.me/taprootassets)

## Cloud

- [Voltage](https://voltage.cloud/)

## Nodes

- [LND](https://github.com/lightningnetwork/lnd)
- [MicroNode](https://docs.lnfi.network/micronode-early-access)
- [Amboss.Space](https://amboss.tech/)
- [LnFi](https://lnfi.network/)
  
## Exchanges

- [Tiramisu Wallet](https://mainnet.tiramisuwallet.com/walletapp/)
- [Lnfi](https://lnfi.network/lander/)
- [DFX Swiss](https://dfx.swiss/)
- [UXUY](https://uxuy.com/)
- [Lightning Assets](https://www.lightningassets.art/#/account)
- [Flash Protocol](https://flashprotocol.xyz/)
- [Taproot Exchange](https://taproot.exchange/home)
- [Yellow](https://yellow.money/)
- [Flashnet](http://flashnet.xyz)
- [Flash Protocol](https://flashprotocol.xyz)
- [LeverFi](https://www.leverfi.io/)
- [Taproot Assets Page](https://megalithic.me/taproot_assets)
- [Bittap](https://www.bittap.org/)
- [LN Markets](https://lnmarkets.com/en/)
  
## Tools

- [Lightning Terminal: Support Taproot Assets](https://github.com/lightninglabs/lightning-terminal)
- [Lightning Node Connect (LNC)](https://github.com/lightninglabs/lightning-node-connect)
- [Polar: Support Taproot Assets via Testnet](https://github.com/jamaljsr/polar)
- [Lightning-TaprootAssets](https://github.com/jacohend/ltd)
- [Royllo](https://www.royllo.org/)
- [Mega Mint](https://drive.google.com/file/d/1ojftCrY2mPx3C5EX-cyAPcsUrLbetRzE/view?resourcekey&pli=1)
- [LnTap](https://github.com/uxuycom/lntap)
- [Lightning Network+](https://lightningnetwork.plus/)
- [Taproot Assets Metadata Format](https://github.com/snow884/taproot-assets-metadata-format)
- [Taproot Assets Bot](https://stacker.news/items/560847)
- [BTC Ecosystem Tools](https://3p-labs.com/)


 ## Tokens and Stablecoins
 
- [HabibTaro](https://github.com/habibitcoin/habibtaro)
- [Root-USD](https://github.com/D33r-Gee/rootUSD-Prototype)
- [Tao](https://tao.deezy.io/)
- [Nostr Assets Protocol](https://test.nostrassets.com/#/account)
- Galaxy Digital
- UB
- [Eulen](https://eulen.app/)


 ## NFTs
 
- [THNDR Games](https://www.thndr.games/)
  
## Tokenized Securities and Asset Management 

- [Hayek Dynamics](https://hayekdynamics.com/)
- [TNA Protocol](https://tna-btc.com/)


## Rewards

- [Joltz Rewards](https://joltzrewards.com/)

## Development

- [Polar](https://lightningpolar.com)

## Companies support Taproot Assets

- [Lightning Labs](https://lightning.engineering/)
- [Tiramisu wallet](mainnet.tiramisuwallet.com)
- [LnFi](https://lnfi.network/)
- [DFX Swiss](https://dfx.swiss/)
- [Galaxy Digital](https://www.galaxy.com/)
- [Polar](https://lightningpolar.com)
- [Royllo](https://www.royllo.org/)
- [Deezy Inc](https://deezy.io/)
- [THNDR Games](https://www.thndr.games/)
- [Joltz Rewards](https://joltzrewards.com/)
- [Hayek Dynamics](https://hayekdynamics.com/)
- [UXUY](https://uxuy.com/)
- [Speed](https://www.speed.app/)
- [Voltage](https://voltage.cloud/)
- [Lightning Network+](https://lightningnetwork.plus/)
- [Bipa](https://bipa.app/)
- [Diamond Hands](https://www.diamondhands.community)
- [Node Runners Brasil](https://noderunnersbrasil.com.br/)
- [Lightning Assets](https://www.lightningassets.art/#/account)
- [Flash Protocol](https://flashprotocol.xyz/)
- [Uniport](http://uniport.network/)
- [Taproot Exchange](https://taproot.exchange/home)
- [TNA Protocol](https://tna-btc.com/)
- [Yellow](https://yellow.money/)
- [Eulen](https://eulen.app/)
- [Sonc](https://sonc.la/)
- [Diba](https://diba.io/)
- [Flashnet](http://flashnet.xyz)
- [Flash Protocol](https://flashprotocol.xyz)
- [LeverFi](https://www.leverfi.io/)
- [Gate.io](https://www.gate.io/en/inscription/bitcoin/taproot%20asset)
- [Taproot Assets Page](https://megalithic.me/taproot_assets)
- [Amboss.Space](https://amboss.tech/)
- [Megalith](https://megalithic.me/)
- [FewSats](https://www.fewsats.com/)
- [Bittap](https://www.bittap.org/)
- [Bitcoin Numaraire](https://github.com/bitcoin-numeraire/)
- [Bihelix](https://www.bihelix.net/)
- [Tether](https://tether.to/en/)

## Reference protocols or based

[Shielded CSV 🛡️: Private and Efficient Client-Side Validation](https://github.com/ShieldedCSV/ShieldedCSV)
  
## Extra list

- [awesome-taproot-asset by Discoco Protocol](https://github.com/Discoco-Protocol/awesome-taproot-asset)
- [awesome taproot assets by Ben2077](https://github.com/ben2077/awesome-taproot-assets)

## Disclaimer

Authors of this list is not responsible for eventual issues with third party projects be trading, speculation or any other thing. 

Please do your own research

## My other lists

[Awesome RGB Protocol](https://github.com/22388o/awesome-rgb-protocol)

## Contributors

<a align="center" href="https://github.com/22388o/awesome-taproot-assets/graphs/contributors">
  <img src="https://contrib.rocks/image?repo=22388o/awesome-taproot-assets" />
</a>
