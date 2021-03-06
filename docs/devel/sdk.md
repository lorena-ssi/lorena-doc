# The SDK

The SDK is based on Javascript

Open an instance of Lorena and attach a Wallet to it.
```javascript
const wallet = new Wallet(username)
const lorena = new Lorena(wallet, { debug: true })
```

First time user (no Wallet). Open a connection with the organization that created the Identity.
It's the organization which connects to the Blockchain, registers the DID and links it to your public Key.

```javascript
// Open Wallet and connect to Lorena
const wallet = new Wallet(username)
<<<<<<< HEAD
const lorena = new Lorena(wallet, { debug: true, silent: true })
=======
const lorena = new Lorena(wallet, { debug: true })

// Add new Client (connection string and pin).
await lorena.newClient(connString, pin, username)

// Connect
await lorena.connect()
>>>>>>> c882833f35dddcaaa31f9868924c60687d6cda0c

// First wallet: Self credentials.
await lorena.initWallet('labtest')
const person = new Credential.Person(wallet.info.did)
person.fullName('John', 'Smith', 'Jr')
person.email('hjohn@smith.jr')
await lorena.signCredential(person)

// Save wallet.
await lorena.signCredential(person)
```

If it's not the first time connecting :
```javascript
const wallet = new Wallet(username)
const lorena = new Lorena(wallet, { debug: true })
if (await lorena.unlock(password)) {
  // Connect
  await lorena.connect()
}
```

# Interacting with Lorena P2P Identity Space.
You can listen to all of the messages being sent to your Identity
```javascript
  lorena.on('error', (e) => {
    console.log(e)
  })

  lorena.on('ready', async () => {
    console.log('connected')

    // You application starts here.
  })

```
