# ElasticSwap Tokenlists

Token Lists is a specification for lists of token metadata (e.g. address, decimals, etc.) that can
be used by any dApp interfaces that needs one or more lists of tokens. Anyone can create and
maintain a token list, as long as they follow the specification. The ElasticSwap community invites
you to add your token to our tokenlists!

## Adding Your Token to an Existing List

### General Requirements
1. Token should be verified on the [Snowtrace Explorer](https://snowtrace.io/verifyContract),
[Etherscan](https://etherscan.io/verifyContract) or the official explorer of the token's chain.
2. Token must be added to a list that it qualifies for:
    * **[Elastic Supply Tokenlist](./elastic.tokenlist.json)**: Token must be elastic in nature.
    * **[DeFi Tokenlist](./defi.tokenlist.json)**: Token must be a DeFi protocol token.
    * **[Stablecoin Tokenlist](./stablecoin.tokenlist.json)**: Token must be a stablecoin.

## Adding Your Token
1. Add an entry in the `tokens` field of the appropriate tokenlist. Please use the [checksum address](https://docs.ethers.io/v5/api/utils/address/#address). Here is an example using PNG:
    ```json
    {
      "chainId": 43114,
      "address": "0x75739a693459f33B1FBcC02099eea3eBCF150cBe",
      "decimals": 18,
      "name": "ElasticSwap TIC Token",
      "symbol": "TIC",
      "logoURI": "https://raw.githubusercontent.com/ElasticSwap/brand/master/ElasticSwap/square-400px.png"
    }
    ```
2. Update the `timestamp` field to the current timestamp.
3. Update the `version` field to adhere to semantic versioning:

    * Increment major version when tokens are removed
    * Increment minor version when tokens are added
    * Increment patch version when tokens already on the list have minor details changed (name,
    symbol, logo URL, decimals)

    ***Note:*** Changing a token address or chain ID is considered both a remove and an add, and
    should be a major version update.

## Adding Your Token Logo

Token logos are [hosted here](https://github.com/ElasticSwap/tokenlists/logos).
