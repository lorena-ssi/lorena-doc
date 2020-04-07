# Verifiable Credentials

[Credentials](https://www.w3.org/TR/vc-data-model/#dfn-credential) are a part of our daily lives; driver's licenses are used to assert that we are capable of operating a motor vehicle, university degrees can be used to assert our level of education, and government-issued passports enable us to travel between countries. This specification provides a mechanism to express these sorts of credentials on the Web in a way that is cryptographically secure, privacy respecting, and machine-verifiable.

### Roles

Each of the following roles denotes an entity (person or organization) which holds a unique Decentralized Identifier (DID) stored in a blockchain along with a public key, which together can be used to secure communication and verify continuity of identity between all parties.

- The **Subject** is the entity to which the information pertains. The Holder is the entity which is holding that information. For the purposes of Lorena, Subject and Holder are treated as the same.
- The **Issuer** is the entity which validates (either manually or automatically) a piece of information about the Subject, and provides a digital signature (signed with the public key associated with the Issuer's DID) that attests to this validation.
The **Verifier** is the entity which wants to know something about the Subject. The Verifier needs to authenticate information about the Subject, and it trusts the Issuer's judgement on that information.

The entities playing these roles all have equal standing: each one has a DID, a (secret) private key and its associated public key which is published with the DID on the blockchain, and each can hold Verifiable Credentials (VCs). The roles can shift, and can be a peer-to-peer relationship or hierarchical as appropriate to needs.