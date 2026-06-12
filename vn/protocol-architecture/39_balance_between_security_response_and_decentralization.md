# 39\_balance\_between\_security\_response\_and\_decentralization

CryptoStone takes No Admin Mint and No Central Server as core principles. However, during early development and deployment stages, a limited administrative structure may be necessary for security audits, testing, and vulnerability response.

| Stage                      | Management Structure                                               |
| -------------------------- | ------------------------------------------------------------------ |
| Testnet and audit stage    | Limited administrative authority may exist                         |
| Before official deployment | Parameter verification and security checks                         |
| After official launch      | Removal of core issuance, supply, and probability change authority |
| After finalization         | No Admin Mint, No Supply Change, No Probability Change             |

If an emergency pause function exists, it must only be used as a limited function to prevent security incidents, not as a function to manipulate issuance results or change supply. Emergency functions should also be restricted through publicly verifiable methods such as timelocks or multisignature structures, and must not become a means for the operator to arbitrarily change rarity or issuance quantity.

CryptoStone’s major contracts consist of the token contract, Gem NFT contract, Mining Pool Template, Pool Factory, and randomness generation structure. These contracts should preferably undergo security audits before and after deployment, and audit results and major vulnerability response records should be disclosed.

The key verification elements to be disclosed are as follows.

| Verification Item            | Description                                                                       |
| ---------------------------- | --------------------------------------------------------------------------------- |
| Contract Source Verification | Disclosure and verification of deployed contract source code                      |
| Audit Report                 | Audit report for major contracts and randomness structure                         |
| Admin Function List          | Existence of administrative functions and removal plan                            |
| Finalize Event               | Core parameter finalization time and event record                                 |
| LP Lock / Burn Proof         | Initial liquidity-related LP handling records                                     |
| Probability Table Hash       | Verification that probability tables match the values disclosed before deployment |
| Metadata Freeze              | Whether core attributes are immutable after issuance                              |

This structure is intended to balance practical security response and decentralized asset characteristics.
