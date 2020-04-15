# Installation

Lorena is a secure and private peer-to-peer identity middleware. Following the installation guide you will be available to start coding [recipes](../2_overview/recipes.md), connecting with other Lorena identities and that's just the beginning!

Let's start with our first Lorena ID:
## 1. Get an invite!
Currently, we have a by-invitation only environment. First thing you have to do is to ask us for an invitation to [this Riot room](https://riot.im/app/#/room/!euLDblFPfxcoBjSRBM:matrix.org?via=matrix.org), ask for @alex or @diego and tell us why do you want to test Lorena for. We will setup an [IDSpace](../2_overview/idspaces.md) for you and we will add you as admin for that IDSpace and send you via PM :
- The new IDSpace DID
- The matrix User for that DID
- a secretCode to connect with your IDSpace

You will use it later ;)

## 2. Install Lorena SDK and Terminal
Download https://github.com/lorena-ssi/terminal:
```bash
$ git clone https://github.com/lorena-ssi/terminal
$ cd terminal
$ npm install
```

To improve your experience using Lorena we built a terminal App that should be of use to learn on who to use the SDK.

The terminal is an example on how to use Lorena SDK. It will help you understanding the basics of Lorena and how to interact with tour IDSpace.

## 3. Running Lorena Terminal
The first time you run it will prompt you to create a new Wallet.

Execute Terminal
```bash
$ ./terminal
Lorena Client

Username :<username>
Password :<pass>
A Wallet for username Does not exist
Create One (Y/n)
```

**What happened so far** : The user and password are used to securely store all of your information locally. Your new wallet can be STORED in your FS (|~/.lorena/wallets/user) or in LocalStorage if you are working with the SDK from the Browser.

Now you can fill in your data. Remember your profile details will be stored locally and never sent anywhere else without your explicit consent.

```bash
Key Pair + DID Added
First Name :John
Last Name (1) :Smith
Last Name (2) :Sikaris
DNI :1111111A
Phone number :55566744
Email :john@test.com
City/Town :Barcelona
Postal Code :08001
Neighborhood :El Born
Save Storage
```

**What happened so far** : Your wallet is ready with :
- A new DID (Not yet stored on the BLockchain)
- A new Keypair (zenroom keys) for you
- A new matrix user (for P2P communications)
- A first self-signed certificate with your own personal information.

So now you just set up your first Identity Wallet and you are ready playing with it.
Try to get information using these commands:
```bash
lorena# help
actions : [ list of actions ]
lorena# did
DID : did:lor:labtest:<DID>
lorena# pubkey
Public Key : <public Key>
lorena# info
{
  matrixUser: <matrixUser>,
  matrixPass: <matrixPass>,
  did: 'did:lor:labtest:<DID>',
  keyPair: {'did:lor:labtest:<DID>': { keypair: [Object] }},
  blockchainServer: 'wss://labtest.substrate.lorena.tech',
  matrixFederation: 'labtest.matrix.lorena.tech',
  matrixServer: 'https://labtest.matrix.lorena.tech'
}
```

Or even get your signed credential
```bash
lorena# credential
{
  <Your full self-signed Credential>
}
```

As you can see you are not connected to the IDSpace. Try to run rooms (your connections). It's empty. Let's connect to our own IDSpace

# Connecting to the IDSpace



## 3. Using the SDK

```javascript
const Lorena = require('@lorena-ssi/lorena-sdk').default
const Wallet = require('@lorena-ssi/wallet-lib').default

// Open your wallet and link it to Lorena.
const username = 'johnsmith'
const wallet = new Wallet(username)
const lorena = new Lorena(wallet, { debug: true, silent: true })

// Try to open the wallet (~/.lorena/wallets/johnsmith/)
const conf = await lorena.unlock(password)
if (conf === false) {
  // No Wallet - First time.
  // Here you need to specify the connstring and security code you already received
  await lorena.newClient(connString, pin, username)
  // Connect
    await lorena.connect()

    // Do the handshake with the server
    term.cyan('\nHandshake : get DID')
    await lorena.handshake(threadId++)

    // Save config.
    term.cyan('\nSave config & connect...')
    await lorena.lock(password)
  } else {
    await lorena.connect()
  }
}
```

Step by Step:
1. Create a new Wallet (where you keep your info)
2. Create a Lorena instance and link it to your wallet
3. First time
  - use the connstring and the pin to open a channel with your idspace
  - Connect and do the handshake
  - Lock (save) your new wallet
4. Not the first time : just connect

Your app is now ready to use Lorena!
```javascript
```
## 4. Play with it!
When the process finishes, you will prompt in Lorena Terminal. Try help to see the functions available:

First try to interact with your Wallet:
```bash
lorena# help
lorena# info
lorena# credentials
lorena# credentials-member
```
You are now interacting with your Wallet!
