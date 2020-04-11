# Tutorial
In this tutorial we are going show how to
 1. Create an identity (`Identity`) in a network.
 2. Add a Did Document to your identity.
 3. Update your identity's public key (`Key`).

How do the structures and storage look like in Substrate?

```rust
pub struct Key<Timestamp, Hash> {
    key: Vec<u8>,
    diddoc_hash: Option<Vec<u8>>,
    valid_from: Timestamp,
    valid_to: Option<Timestamp>
}

pub struct Identity<AccountId> {
    owner: AccountId,
    key_index: u64,
}

decl_storage! {
    trait Store for Module<T: Trait> as LorenaModule {
        Identities get(identity): map T::Hash => Identity<T::AccountId>;

        IdentityKeys get(identity_key): map (T::AccountId, u64) => Key<T::Timestamp, , Hash>
        IdentityKeysCount get(identity_keys_count): map T::AccountId => u64;

        Nonce: u64;
    }
  }

```

## Creating an Identity
What does identity mean and how is it created? Each entity of a network (substrate user) can hold one and only one `Identity`. These entities are described through a DID (**D**ecentrilized **ID**entifiers) of the form "did:lor:network:[subnetwork:...]:[person | organization]". In this example we are going to use `did:lor:eur:123456` representing a person in the European network.

Once you have your did, you will need a Zenroom public-key. The Zenroom public-key must be of type `Vec<u8>`, as well as the did.

The only thing left is to call the extrinsic `register_did` defined as:

```rust
pub fn register_did(origin, did: Vec<u8>, zkey: Vec<u8>)
```

This extrinsic will create you and `Identity`, using `did`, and a `Key` using `zkey`. It will also associate the created `Key` to the created `Identity`


## Add Did Document

Did Documents describe identities a little bit more. You can see services or authentications that are provided by the `Identity`.
In order to associate a Did Document to your identity you should have an IPFS representation of that Did Document. This representation of your Did Document will be stored in the registry (substrate in this case), so its mutability is traceable.

Once you have your IPFS representation of your Did Document you will added to your `Identity` using extrinsic `register_did_document`:

```rust
pub fn register_did_document(origin, did: Vec<u8>, new_diddoc_hash: Vec<u8>)
```

This extrinsic will add the Did Document IPFS hash to `key_index` of sender's `Identity`.

## Update public key

We may want at some point, maybe for security reasons, to update our keypair. This means that we will have to create a new public-key (with zenroom) and associated to your identity. To do so we will use the extrinsic `rotate_key` . This will make the last public-key the only valid one, even though the older public keys will be stored with their dates where this public-key was valid.

```rust
pub fn rotate_key(origin, did: Vec<u8>, new_key: Vec<u8>)
```

Rotate key will create a new `Key` for the sender and update sender's `Identity` `key_index`.
