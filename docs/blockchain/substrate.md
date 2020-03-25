# Introduction

## What are we using Blockchain for?
We need Blockchain as DKPI. Meaning we will store almost not information in the Blockchain, just DIDs, public keys and IPFS documents.

```rust
// Key Struct.
pub struct Key {
    key: String,
    ipfs: String,
    valid_from: DateTime<Utc>,
    valid_to: DateTime<Utc>
    
}

// Identity Struct.
pub struct Identity {
    owner: Vec<u8>,
    zkey: Hash,
    did_object_hash: Vec<u8>,
}

decl_storage! {
    trait Store for Module<T: Trait> as RadicesModule {
        Keys get(key): map T::Hash => Key;
        Identities get(identity_by_hash): T::Hash => Identity;
    }
}

```

But it needs to have an historic of keys so we can verify that a public key was valid when a Credential was signed with that key.

Every Identity Object has a unique identifier : The hash of the public_key and the date it was valid.

Function:

registerIdentity(Hash)
Gets the key being used now (if any) and sets valid_to to now().
Pushes a new key into Keys and sets this key as the actual key