# IDSpaces

Decentralized Identities (DIDs) are simple unique identifiers in the format did:example:123456789abcdefghi. A DID resolves to a DID Document (a JSON file) which contains information associated with the DID, such as ways to cryptographically authenticate the entity in control of the DID, services that can be used to interact with the entity, Verifiable Credentials associated with the DID.

An **ID Space** is a secure way of storing DIDs, DID Documents, the private keys used to control them, Verifiable Credentials and Verifiable Presentations, and other assets used by an entity. It is similar to a digital wallet (such as Trezor, Ledger, or MyEtherWallet) in that it stores private keys, but it also stores more complex documents which express a Decentralized Identity.

An identity container provides methods of accessing those documents and providing information about the data stored in those documents without sharing the actual information. This is achieved by using Zero-Knowledge Proofs.