# Wallet

A wallet is the place where we store all of the information for the CLI : DID, Credentials & contacts

A Wallet is provided to the CLI, this way you can create your own Wallet.

The Wallet works : on Linux (using your home directory) or in Browser (Local Storage)

ALl information is encrypted using a password, and assigned to a username.

```javascript
const wallet = new Wallet(username)
// ...
wallet.lock(password)
// ...
wallet.unlock(password)
```

lock : saves information into the wallet encrypted with a Password
unlock : decrypt and store information in the wallet