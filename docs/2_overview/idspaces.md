# IDSpaces

Decentralized Identities (DIDs) are simple unique identifiers in the format did:example:123456789abcdefghi. A DID resolves to a DID Document (a JSON file) which contains information associated with the DID, such as ways to cryptographically authenticate the entity in control of the DID, services that can be used to interact with the entity, Verifiable Credentials associated with the DID.

An **ID Space** is a secure way of storing DIDs, DID Documents, the private keys used to control them, Verifiable Credentials and Verifiable Presentations, and other assets used by an entity. It is similar to a digital wallet (such as Trezor, Ledger, or MyEtherWallet) in that it stores private keys, but it also stores more complex documents which express a Decentralized Identity.

An identity container provides methods of accessing those documents and providing information about the data stored in those documents without sharing the actual information. This is achieved by using Zero-Knowledge Proofs.

Privacy by design, portable and interoperable personal databases where users, objects and organizations can keep their data and control access to it. It’s the basis of the Identity and holds all of the credentials (created by others) belonging to the entity, verified contacts and interactions with other identities.

| Credential | Contact (DID) | Interaction | Permissions |
| -- | -- | -- | -- |
| I’m client at the bank | Bank | Payments/Transfers | Can send me emails |
| I’m insured | Insurance Company | Claims | Can read my e-watch and get a health ranking |

Identity Containers, to be usable they need a platform to hold the DIDs (Blockchain - Polkadot) and encrypted communication channels to send and receive credentials.
