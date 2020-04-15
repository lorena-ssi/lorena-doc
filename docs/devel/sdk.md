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
let threadId = 0
const wallet = new Wallet(username)
const lorena = new Lorena(wallet, { debug: true })

// Add new Client (connstring and pin).
await lorena.newClient(connString, pin, username)

// Connect
await lorena.connect()

// Do the handshake with the server
await lorena.handshake(threadId++)

// Save configuration.
await lorena.lock(password)
```

The threadId is the unique identifier for all of the threads you open to other peers (see recipes).

If it's not the first time connecting :
```javascript
let threadId = 0
const wallet = new Wallet(username)
const lorena = new Lorena(wallet, { debug: true })

// Connect
await lorena.connect()
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
