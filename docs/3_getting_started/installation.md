# Installation

Lorena is a peer-to-peer security and private identity middleware. Following the installation guide you will be available to start coding [recipes](2_overview/recipes.md), connecting with other Lorena identities and taht's just the beginning!

Let's start with our first Lorena ID:
## 1. Get an invite!
Currently, we have a by-invitation only environment with a maximum of 100 identities. First thing you have to do is to ask us for an invitation to [this Riot room](https://riot.im/app/#/room/!euLDblFPfxcoBjSRBM:matrix.org?via=matrix.org), ask for @alex or @diego and tell us why you want to try Lorena. When you get invite, wew will setup an idspace for you and we will add you as admin for that IDSpace. You will receive two codes: **Connection String** and **PIN number**. You will use them later ;)

## 2. Install Lorena CLI
Download https://github.com/lorena-ssi/lorena-cli:
```bash
$ git clone https://github.com/lorena-ssi/lorena-cli
$ cd lorena-cli
$ npm install
```

## 3. Running Lorena CLI
To improve your experience using Lorena CLI we coded a terminal App that should be of use to learn on who to use the SDK.

The first time you run it will prompt you to create a new user and password. Also will ask you to fill the connection string and pin code you got in step 1:

Execute CLI
```bash
$ ./terminal
Username :_username_
Password :_password_
Connecting...Creating new connection
Connection String :_connstring_
PIN :_pincode_
```

The user and password are used to securely store all of your information locally. Your new wallet can be used in your FS (|~/.lorena/wallets/user) or in LocalStorage if you are working with the SDK from the Browser.

We recommend sending the connstring and the security code to new users using different channels.

What happened so far:
1. We installed an idspace in the cloud for you with a new DID, Zenroom Keypair and Matrix user (to interact With). We also registered your new public Key to the Blockchain.
2. We registered a new DID for the admin of the IDSpace, then zipped instructions on how to connect to the IDSpace (connstring). The ones you just used.
3. When launching the terminal for the first time, you are opening a channel with your IDSpace (a room in Matrix).
4. You are  sending your PublicKey to the IDSpace and receiveng a new DID (registered to the Blockchain with your new DID)
5. A New credential is iisued by the IDSpace, appointing you as amdin.

## 3. Using the SDK

```javascript
const Lorena = require('@lorena-ssi/lorena-cli').default
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
When the process finishes, you will promtp in Lorena CLI. Try help to see the functions available:

First try to interact with your Wallet:
```bash
lorena# help
lorena# info
lorena# credentials
lorena# credentials-member
```
You are now interacting with your Wallet!