# 34\_decentralized\_mining\_structure

In CryptoStone, mining is not performed by a server on behalf of users. A user stakes STONX into the STONX pool of their choice, and once the PoM value reaches the required threshold of that pool over time, the user directly calls a contract function such as `claimGem()` to receive a Gem NFT.

1. The user holds STONX.
2. The user selects a STONX pool.
3. The user stakes STONX.
4. Mining Power is generated.
5. PoM accumulates over time.
6. When PoM reaches the required threshold, the user calls `claimGem()`.
7. The contract verifies whether mining conditions are met.
8. Attributes are generated using verifiable randomness.
9. A Gem NFT is issued.
10. The NFT is transferred to the user’s wallet.

In this process, no central server issues gemstones or assigns attributes. Mining conditions and results are determined by code.

Smart contracts do not execute automatically on their own. However, anyone can call the contract, and the contract verifies and executes results according to predetermined conditions. Therefore, CryptoStone’s mining structure can operate without a central server.

The developer believes the important point in this structure is not simply that “there is no server,” but that “even without a server, users can directly call the contract and receive mining results according to predetermined rules.”
