# WAX development quick links

## The WAX Blockchain

### Testnet

|                                      |                                                              |
| ------------------------------------ | ------------------------------------------------------------ |
| Chain id                             | 1064487b3cd1a897ce03ae5b6a865651747e2e152090f99c1d19d44e01aea5a4 |
| WAX & AtomicAssets endpoints         | https://validate.eosnation.io/waxtest/reports/endpoints.html |
| Bloks                                | https://wax-test.bloks.io/                                   |
| AtomicHub                            | https://wax-test.atomichub.io/                               |
| NeftyBlocks                          | https://test.neftyblocks.com/                                |
| Note                                 | [Anchor](https://greymass.com/anchor/) required for most dApps, Wax Cloud Wallet (WCW) not supported |
| Creating an account                  | https://faucet.waxsweden.org/create_account?your-wallet-name<br />**Has to be a valid EOS name, a-z 0-5 and 12 characters<br /> Save your keys** |
| Request more WAX                     | https://faucet.waxsweden.org/get_token?your-wallet-name <br />2 x 500 WAX per 24 hours |
| More info regarding testnet accounts | https://waxsweden.org/create-testnet-account/                |

### Mainnet

|                              |                                                              |
| ---------------------------- | ------------------------------------------------------------ |
| Chain id                     | 1064487b3cd1a897ce03ae5b6a865651747e2e152090f99c1d19d44e01aea5a4 |
| WAX & AtomicAssets endpoints | https://validate.eosnation.io/wax/reports/endpoints.html     |
| Bloks                        | https://wax.bloks.io/                                        |
| AtomicHub                    | https://wax.atomichub.io/                                    |
| NeftyBlocks                  | https://neftyblocks.com/                                     |

## Useful tools

### Development

| Tool       | Description                                                  | Links                     |
| ---------- | ------------------------------------------------------------ | ------------------------- |
| EOS Studio | IDE for EOS development.<br />Editor's node: use local eosio.cdt builders | https://www.eosstudio.io/ |



### Testing

*No, production is not the only place to test ;)*

| Tool       | Description                                                  | Links                                  |
| ---------- | ------------------------------------------------------------ | -------------------------------------- |
| eoslime    | EOS development and deployment framework based on eosjs.js. The framework's main purpose is to make the process of unit testing, deployment and compilation much simpler and much easier. | https://github.com/LimeChain/eoslime   |
| eosfactory | Python-based EOS smart-contract development & testing framework | https://github.com/tokenika/eosfactory |



### Blockchain interaction

| Tool            | Description                                                  | Links                                                    |
| --------------- | ------------------------------------------------------------ | -------------------------------------------------------- |
| Cleos           | CLI tool to interact with nodeos                             | https://developers.eos.io/manuals/eos/latest/cleos/index |
| eosjs           | Javascript API for integration with EOSIO-based blockchains using [EOSIO RPC API](https://developers.eos.io/eosio-nodeos/reference). | https://github.com/EOSIO/eosjs                           |
| eospy           | eos python library                                           | https://github.com/eosnewyork/eospy                      |
| aioeos          | Async Python library for interacting with EOS.io blockchain. | https://github.com/ulamlabs/aioeos                       |
| atomicassets-js | NPM module to interact with the AtomicAssets NFT standard    | https://github.com/pinknetworkx/atomicassets-js          |
| dFuse           | GraphQL API                                                  | https://wax.dfuse.eosnation.io/                          |
| demux-js-eos    | Demux Action Reader implementations to read block and action data from EOSIO-based blockchains. | https://github.com/EOSIO/demux-js-eos                    |



### Authentication

| Tool                 | Description                                                  | Links                                                    |
| -------------------- | ------------------------------------------------------------ | -------------------------------------------------------- |
| UAL                  | A library for allowing apps to easily use different auth providers. | https://github.com/EOSIO/universal-authenticator-library |
| UAL Wax Cloud Wallet | UAL authenticator for WAX Cloud Wallet                       | https://github.com/eosdac/ual-wax                        |
| UAL Anchor           | Identity and session through ESR using EOSIO/universal-authenticator-library | https://github.com/greymass/ual-anchor                   |
| wax-auth             | Fast, costless authentication flow for the Wax blockchain    | https://github.com/udbhav-s/wax-auth                     |



## Smart contract ecosystem

Editor's notes: 

- Personally I have found eosio.cdt 1.7 to produce less bulkier wasm than eosio.cdt 1.8
- Please use proven RNG methods for critical stuff (aka `orng.wax`), you do not need to deploy this contract yourself again

### Smart contract "standards"

| Contract                                                  | Description                                                  | Links                                                        |
| --------------------------------------------------------- | ------------------------------------------------------------ | ------------------------------------------------------------ |
| [eosio.token](https://wax.bloks.io/account/eosio.token)   | FT (fungible token) contract                                 | https://github.com/EOSIO/eosio.contracts/tree/master/contracts/eosio.token |
| [atomicassets](https://wax.bloks.io/account/atomicassets) | Smart Contract of the AtomicAssets standard.                 | https://github.com/pinknetworkx/atomicassets-contract        |
| atomicpacks                                               | The atomicpacks smart contract allows users to set up random pack openings, giving out [AtomicAssets](https://github.com/pinknetworkx/atomicassets-contract) NFTs. It uses the [WAX RNG Oracle](https://github.com/worldwide-asset-exchange/wax-orng) to get randomness. | https://github.com/pinknetworkx/atomicpacks-contract         |
| [atomicmarket](https://wax.bloks.io/account/atomicmarket) | AtomicMarket is a marketplace to sell and auction [AtomicAssets](https://github.com/pinknetworkx/atomicassets-contract) NFTs. | https://github.com/pinknetworkx/atomicmarket-contract        |
| [orng.wax](https://wax.bloks.io/account/orng.wax)         | The WAX Random Number Generator (WAX RNG) is a native blockchain service that provides provably fair random numbers for single-users. Based on the [Signidice algorithm](https://github.com/gluk256/misc/blob/master/rng4ethereum/signidice.md), WAX RNG offers excellent randomization, a cleaner workflow, and lightning-fast RSA verification. | https://developer.wax.io/dapps/wax-random-number-generator-wax-rng/ |
| Blenderizer                                               | Blenderizer is a Smart Contract for WAX Blockchain to play burning NFTs. You can set up a list of AtomicAssets NFTs IDs to burn and a ID of a new NFT to mint in exchange. This is a funy system to control NFT supply excesses and to make your collection more atractive. | https://github.com/3dkrender/Blenderizer                     |

### "Open" contracts

Editor's note: please <u>verify</u> and respect the contract licenses

| Contract        | Description                                                  | Links                                       |
| --------------- | ------------------------------------------------------------ | ------------------------------------------- |
| eos-stake-token | Stake token contract is based on the official 'eosio.token' contract, with some additional functions to realize basic token economy mechanism. | https://github.com/mykeylab/eos-stake-token |
|                 |                                                              |                                             |
|                 |                                                              |                                             |



### Learning sources

| Contract                          | Description                                                  | Links                                                 |
| --------------------------------- | ------------------------------------------------------------ | ----------------------------------------------------- |
| eosio.contracts                   | Smart contracts that provide some of the basic functions of the EOSIO blockchain | https://github.com/EOSIO/eosio.contracts              |
| Advanced EOS Development Examples | EOS Smart Contract Development Examples                      | https://github.com/MitchPierias/Advanced-EOS-Examples |
| Elemental Battles                 | The Elemental Battles Tutorial is divided into easy to follow lessons that take you through the process of creating your own fully-functional blockchain-based dApp. | https://github.com/EOSIO/eosio-card-game-repo         |
| EOS Knights                       | EOS Knights is the first blockchain game on the EOS platform. All player actions are performed on smart contracts. Data is also stored securely in the EOS blockchain. Let's play EOS Knights together!<br/>Hire a knight to protect the town from the goblins! | https://github.com/bada-studio/knights_contract       |
| Misc                              | EOSIO smart contracts collection                             | https://github.com/blockmatic/eosio-contracts-list    |
